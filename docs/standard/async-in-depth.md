---
title: 深入了解异步
description: 了解如何使用基于 .NET 任务的异步模型直接编写绑定 I/O 和 CPU 的异步代码。
author: cartermp
ms.author: wiwagn
ms.date: 06/20/2016
ms.assetid: 1e38f9d9-8f84-46ee-a15f-199aec4f2e34
ms.openlocfilehash: 7fcc41c4ea5037d643402fc722e8f16f28d560ee
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "94823324"
---
# <a name="async-in-depth"></a><span data-ttu-id="c5809-103">深入了解异步</span><span class="sxs-lookup"><span data-stu-id="c5809-103">Async in depth</span></span>

<span data-ttu-id="c5809-104">使用基于 .NET 任务的异步模型可直接编写绑定 I/O 和 CPU 的异步代码。</span><span class="sxs-lookup"><span data-stu-id="c5809-104">Writing I/O- and CPU-bound asynchronous code is straightforward using the .NET Task-based async model.</span></span> <span data-ttu-id="c5809-105">该模型由 `Task` 和 `Task<T>` 类型以及 C# 和 Visual Basic 中的 `async` 和 `await` 关键字公开。</span><span class="sxs-lookup"><span data-stu-id="c5809-105">The model is exposed by the `Task` and `Task<T>` types and the `async` and `await` keywords in C# and Visual Basic.</span></span> <span data-ttu-id="c5809-106">（有关特定语言的资源，请参见[另请参阅](#see-also)部分。）本文解释如何使用 .NET 异步，并深入介绍其中使用的异步框架。</span><span class="sxs-lookup"><span data-stu-id="c5809-106">(Language-specific resources are found in the [See also](#see-also) section.) This article explains how to use .NET async and provides insight into the async framework used under the covers.</span></span>

## <a name="task-and-taskt"></a><span data-ttu-id="c5809-107">任务和 Task\<T></span><span class="sxs-lookup"><span data-stu-id="c5809-107">Task and Task\<T></span></span>

<span data-ttu-id="c5809-108">任务是用于实现称之为[并发 Promise 模型](https://en.wikipedia.org/wiki/Futures_and_promises)的构造。</span><span class="sxs-lookup"><span data-stu-id="c5809-108">Tasks are constructs used to implement what is known as the [Promise Model of Concurrency](https://en.wikipedia.org/wiki/Futures_and_promises).</span></span>  <span data-ttu-id="c5809-109">简单地说，它们“承诺”，会在稍后完成工作，让你使用干净的 API 与 promise 协作。</span><span class="sxs-lookup"><span data-stu-id="c5809-109">In short, they offer you a "promise" that work will be completed at a later point, letting you coordinate with the promise with a clean API.</span></span>

- <span data-ttu-id="c5809-110">`Task` 表示不返回值的单个操作。</span><span class="sxs-lookup"><span data-stu-id="c5809-110">`Task` represents a single operation which does not return a value.</span></span>
- <span data-ttu-id="c5809-111">`Task<T>` 表示返回 `T` 类型的值的单个操作。</span><span class="sxs-lookup"><span data-stu-id="c5809-111">`Task<T>` represents a single operation which returns a value of type `T`.</span></span>

<span data-ttu-id="c5809-112">请务必将任务理解为工作的异步抽象，而非  在线程之上的抽象。</span><span class="sxs-lookup"><span data-stu-id="c5809-112">It’s important to reason about tasks as abstractions of work happening asynchronously, and *not* an abstraction over threading.</span></span> <span data-ttu-id="c5809-113">默认情况下，任务在当前线程上执行，且在适当时会将工作委托给操作系统。</span><span class="sxs-lookup"><span data-stu-id="c5809-113">By default, tasks execute on the current thread and delegate work to the Operating System, as appropriate.</span></span> <span data-ttu-id="c5809-114">可选择性地通过 `Task.Run` API 显式请求任务在独立线程上运行。</span><span class="sxs-lookup"><span data-stu-id="c5809-114">Optionally, tasks can be explicitly requested to run on a separate thread via the `Task.Run` API.</span></span>

<span data-ttu-id="c5809-115">任务会公开一个 API 协议来监视、等候和访问任务的结果值（如 `Task<T>`）。</span><span class="sxs-lookup"><span data-stu-id="c5809-115">Tasks expose an API protocol for monitoring, waiting upon and accessing the result value (in the case of `Task<T>`) of a task.</span></span> <span data-ttu-id="c5809-116">含有 `await` 关键字的语言集成可提供高级别抽象来使用任务。</span><span class="sxs-lookup"><span data-stu-id="c5809-116">Language integration, with the `await` keyword, provides a higher-level abstraction for using tasks.</span></span>

<span data-ttu-id="c5809-117">任务运行时，使用 `await` 在任务完成前将控制让步于其调用方，可让应用程序和服务执行有用工作。</span><span class="sxs-lookup"><span data-stu-id="c5809-117">Using `await` allows your application or service to perform useful work while a task is running by yielding control to its caller until the task is done.</span></span> <span data-ttu-id="c5809-118">任务完成后代码无需依靠回调或事件便可继续执行。</span><span class="sxs-lookup"><span data-stu-id="c5809-118">Your code does not need to rely on callbacks or events to continue execution after the task has been completed.</span></span> <span data-ttu-id="c5809-119">语言和任务 API 集成会为你完成此操作。</span><span class="sxs-lookup"><span data-stu-id="c5809-119">The language and task API integration does that for you.</span></span> <span data-ttu-id="c5809-120">如果正在使用 `Task<T>`，任务完成时，`await` 关键字还将“打开”返回的值。</span><span class="sxs-lookup"><span data-stu-id="c5809-120">If you’re using `Task<T>`, the `await` keyword will additionally "unwrap" the value returned when the Task is complete.</span></span>  <span data-ttu-id="c5809-121">下面进一步详细介绍了此工作原理。</span><span class="sxs-lookup"><span data-stu-id="c5809-121">The details of how this works are explained further below.</span></span>

<span data-ttu-id="c5809-122">可在[基于任务的异步模式 (TAP)](./asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) 主题中了解有关任务以及与任务交互的不同方法的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c5809-122">You can learn more about tasks and the different ways to interact with them in the [Task-based Asynchronous Pattern (TAP)](./asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) topic.</span></span>

## <a name="deeper-dive-into-tasks-for-an-io-bound-operation"></a><span data-ttu-id="c5809-123">深入了解针对绑定 I/O 的操作的任务</span><span class="sxs-lookup"><span data-stu-id="c5809-123">Deeper Dive into Tasks for an I/O-Bound Operation</span></span>

<span data-ttu-id="c5809-124">以下部分介绍了使用典型异步 I/O 调用时会出现的各种情况。</span><span class="sxs-lookup"><span data-stu-id="c5809-124">The following section describes a 10,000 foot view of what happens with a typical async I/O call.</span></span> <span data-ttu-id="c5809-125">我们先看两个例子。</span><span class="sxs-lookup"><span data-stu-id="c5809-125">Let's start with a couple examples.</span></span>

<span data-ttu-id="c5809-126">第一个示例调用异步方法，并返回活动任务，很可能尚未完成。</span><span class="sxs-lookup"><span data-stu-id="c5809-126">The first example calls an async method and returns an active task, likely yet to complete.</span></span>

```csharp
public Task<string> GetHtmlAsync()
{
    // Execution is synchronous here
    var client = new HttpClient();

    return client.GetStringAsync("https://www.dotnetfoundation.org");
}
```

<span data-ttu-id="c5809-127">第二个示例还使用了 `async` 和 `await` 关键字对任务进行操作。</span><span class="sxs-lookup"><span data-stu-id="c5809-127">The second example adds the use of the `async` and `await` keywords to operate on the task.</span></span>

```csharp
public async Task<string> GetFirstCharactersCountAsync(string url, int count)
{
    // Execution is synchronous here
    var client = new HttpClient();

    // Execution of GetFirstCharactersCountAsync() is yielded to the caller here
    // GetStringAsync returns a Task<string>, which is *awaited*
    var page = await client.GetStringAsync("https://www.dotnetfoundation.org");

    // Execution resumes when the client.GetStringAsync task completes,
    // becoming synchronous again.

    if (count > page.Length)
    {
        return page;
    }
    else
    {
        return page.Substring(0, count);
    }
}
```

<span data-ttu-id="c5809-128">对 `GetStringAsync()` 的调用通过低级别 .NET 库进行（可能是调用其他异步方法），直到其到达 P/Invoke 互操作调用，进入本机网络库。</span><span class="sxs-lookup"><span data-stu-id="c5809-128">The call to `GetStringAsync()` calls through lower-level .NET libraries (perhaps calling other async methods) until it reaches a P/Invoke interop call into a native networking library.</span></span> <span data-ttu-id="c5809-129">本机库随后可能会调入系统 API 调用（例如 Linux 上套接字的 `write()`）。</span><span class="sxs-lookup"><span data-stu-id="c5809-129">The native library may subsequently call into a System API call (such as `write()` to a socket on Linux).</span></span> <span data-ttu-id="c5809-130">可能会使用 [TaskCompletionSource](xref:System.Threading.Tasks.TaskCompletionSource%601.SetResult(%600)) 在本机/托管边界创建一个任务对象。</span><span class="sxs-lookup"><span data-stu-id="c5809-130">A task object will be created at the native/managed boundary, possibly using [TaskCompletionSource](xref:System.Threading.Tasks.TaskCompletionSource%601.SetResult(%600)).</span></span> <span data-ttu-id="c5809-131">将通过层向上传递任务对象，对其进行操作或直接返回，最后返回到初始调用方。</span><span class="sxs-lookup"><span data-stu-id="c5809-131">The task object will be passed up through the layers, possibly operated on or directly returned, eventually returned to the initial caller.</span></span>

<span data-ttu-id="c5809-132">在上述第二个示例中，`Task<T>` 对象直接从 `GetStringAsync` 返回。</span><span class="sxs-lookup"><span data-stu-id="c5809-132">In the second example above, a `Task<T>` object will be returned from `GetStringAsync`.</span></span> <span data-ttu-id="c5809-133">由于使用了 `await` 关键字，因此该方法会返回一个新建的任务对象。</span><span class="sxs-lookup"><span data-stu-id="c5809-133">The use of the `await` keyword causes the method to return a newly created task object.</span></span> <span data-ttu-id="c5809-134">在 `GetFirstCharactersCountAsync` 方法中，控制权从此位置返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="c5809-134">Control returns to the caller from this location in the `GetFirstCharactersCountAsync` method.</span></span> <span data-ttu-id="c5809-135">[Task&lt;T&gt;](xref:System.Threading.Tasks.Task%601) 对象的方法和属性使调用者能够监视任务的进度。GetFirstCharactersCountAsync 中剩余的代码执行完毕时，该任务便完成。</span><span class="sxs-lookup"><span data-stu-id="c5809-135">The methods and properties of the [Task&lt;T&gt;](xref:System.Threading.Tasks.Task%601) object enable callers to monitor the progress of the task, which will complete when the remaining code in GetFirstCharactersCountAsync has executed.</span></span>

<span data-ttu-id="c5809-136">调用系统 API 后，请求位于内核空间，一路来到操作系统的网络子系统（例如 Linux 内核中的 `/net`）。</span><span class="sxs-lookup"><span data-stu-id="c5809-136">After the System API call, the request is now in kernel space, making its way to the networking subsystem of the OS (such as `/net` in the Linux Kernel).</span></span>  <span data-ttu-id="c5809-137">此处操作系统将对网络请求进行异步  处理。</span><span class="sxs-lookup"><span data-stu-id="c5809-137">Here the OS will handle the networking request *asynchronously*.</span></span>  <span data-ttu-id="c5809-138">所用操作系统不同，细节可能有所不同（可能会将设备驱动程序调用安排为发送回运行时的信号，或者会执行设备驱动程序调用然后  有一个信号发送回来），但最终都会通知运行时网络请求正在进行中。</span><span class="sxs-lookup"><span data-stu-id="c5809-138">Details may be different depending on the OS used (the device driver call may be scheduled as a signal sent back to the runtime, or a device driver call may be made and *then* a signal sent back), but eventually the runtime will be informed that the networking request is in progress.</span></span>  <span data-ttu-id="c5809-139">此时，设备驱动程序工作处于已计划、正在进行或是已完成（请求已“通过网络”发出），但由于这些均为异步进行，设备驱动程序可立即着手处理其他事项！</span><span class="sxs-lookup"><span data-stu-id="c5809-139">At this time, the work for the device driver will either be scheduled, in-progress, or already finished (the request is already out "over the wire") - but because this is all happening asynchronously, the device driver is able to immediately handle something else!</span></span>

<span data-ttu-id="c5809-140">例如，在 Windows 中操作系统线程调用网络设备驱动程序并要求它通过表示操作的中断请求数据包 (IRP) 执行网络操作。</span><span class="sxs-lookup"><span data-stu-id="c5809-140">For example, in Windows an OS thread makes a call to the network device driver and asks it to perform the networking operation via an Interrupt Request Packet (IRP) which represents the operation.</span></span>  <span data-ttu-id="c5809-141">设备驱动程序接收 IRP，调用网络，将 IRP 标记为“待定”，并返回到操作系统。</span><span class="sxs-lookup"><span data-stu-id="c5809-141">The device driver receives the IRP, makes the call to the network, marks the IRP as "pending", and returns back to the OS.</span></span>  <span data-ttu-id="c5809-142">由于现在操作系统线程了解到 IRP 为“待定”，因此无需再为此作业进行进一步操作，将其“返回”，这样它就可用于完成其他工作。</span><span class="sxs-lookup"><span data-stu-id="c5809-142">Because the OS thread now knows that the IRP is "pending", it doesn't have any more work to do for this job and "returns" back so that it can be used to perform other work.</span></span>

<span data-ttu-id="c5809-143">请求完成且数据通过设备驱动程序返回后，会经由中断通知 CPU 新接收到的数据。</span><span class="sxs-lookup"><span data-stu-id="c5809-143">When the request is fulfilled and data comes back through the device driver, it notifies the CPU of new data received via an interrupt.</span></span>  <span data-ttu-id="c5809-144">处理中断的方式因操作系统不同而有所不同，但最终都会通过操作系统将数据传递到系统互操作调用（例如，Linux 中的中断处理程序将安排 IRQ 的下半部分通过操作系统异步向上传递数据）。</span><span class="sxs-lookup"><span data-stu-id="c5809-144">How this interrupt gets handled will vary depending on the OS, but eventually the data will be passed through the OS until it reaches a system interop call (for example, in Linux an interrupt handler will schedule the bottom half of the IRQ to pass the data up through the OS asynchronously).</span></span>  <span data-ttu-id="c5809-145">请注意这仍  是异步进行的！</span><span class="sxs-lookup"><span data-stu-id="c5809-145">Note that this *also* happens asynchronously!</span></span>  <span data-ttu-id="c5809-146">在下一个可用线程能执行异步方法且“解包”已完成任务的结果前，结果会排入队列。</span><span class="sxs-lookup"><span data-stu-id="c5809-146">The result is queued up until the next available thread is able to execute the async method and "unwrap" the result of the completed task.</span></span>

<span data-ttu-id="c5809-147">在整个过程中，关键点在于 **没有线程专用于运行任务**。</span><span class="sxs-lookup"><span data-stu-id="c5809-147">Throughout this entire process, a key takeaway is that **no thread is dedicated to running the task**.</span></span>  <span data-ttu-id="c5809-148">尽管需要在一些上下文中执行工作（即，操作系统确实必须将数据传递到设备驱动程序并响应中断），但没有专用于 *等待* 数据从请求返回的线程。</span><span class="sxs-lookup"><span data-stu-id="c5809-148">Although work is executed in some context (that is, the OS does have to pass data to a device driver and respond to an interrupt), there is no thread dedicated to *waiting* for data from the request to come back.</span></span>  <span data-ttu-id="c5809-149">这让系统能处理更多的工作而不是等待某些 I/O 调用结束。</span><span class="sxs-lookup"><span data-stu-id="c5809-149">This allows the system to handle a much larger volume of work rather than waiting for some I/O call to finish.</span></span>

<span data-ttu-id="c5809-150">虽从上述内容来看需要完成许多工作，但以实际时间来计量，这远少于执行实际 I/O 工作所花费的时间。</span><span class="sxs-lookup"><span data-stu-id="c5809-150">Although the above may seem like a lot of work to be done, when measured in terms of wall clock time, it’s miniscule compared to the time it takes to do the actual I/O work.</span></span> <span data-ttu-id="c5809-151">虽然不是完全精确，但此类调用可能的时间线如下所示：</span><span class="sxs-lookup"><span data-stu-id="c5809-151">Although not at all precise, a potential timeline for such a call would look like this:</span></span>

<span data-ttu-id="c5809-152">0-1————————————————————————————————————————————————–2-3</span><span class="sxs-lookup"><span data-stu-id="c5809-152">0-1————————————————————————————————————————————————–2-3</span></span>

- <span data-ttu-id="c5809-153">从点 `0` 到 `1` 所花费时间很长，直到异步方法将控制让步于其调用方才结束。</span><span class="sxs-lookup"><span data-stu-id="c5809-153">Time spent from points `0` to `1` is everything up until an async method yields control to its caller.</span></span>
- <span data-ttu-id="c5809-154">从点 `1` 到点 `2` 所用时间是花费在 I/O 上的时间，且 CPU 没有耗时。</span><span class="sxs-lookup"><span data-stu-id="c5809-154">Time spent from points `1` to `2` is the time spent on I/O, with no CPU cost.</span></span>
- <span data-ttu-id="c5809-155">最后，点 `2` 到点 `3` 所花费时间用于将控制（和可能的值）传递回异步方法，此时将再次执行。</span><span class="sxs-lookup"><span data-stu-id="c5809-155">Finally, time spent from points `2` to `3` is passing control back (and potentially a value) to the async method, at which point it is executing again.</span></span>

### <a name="what-does-this-mean-for-a-server-scenario"></a><span data-ttu-id="c5809-156">这对服务器方案而言意味着什么？</span><span class="sxs-lookup"><span data-stu-id="c5809-156">What does this mean for a server scenario?</span></span>

<span data-ttu-id="c5809-157">此模型可很好地处理典型的服务器方案工作负荷。</span><span class="sxs-lookup"><span data-stu-id="c5809-157">This model works well with a typical server scenario workload.</span></span>  <span data-ttu-id="c5809-158">由于没有专用于阻止未完成任务的线程，服务器线程池可服务更多的 Web 请求。</span><span class="sxs-lookup"><span data-stu-id="c5809-158">Because there are no threads dedicated to blocking on unfinished tasks, the server threadpool can service a much higher volume of web requests.</span></span>

<span data-ttu-id="c5809-159">考虑使用两个服务器：一个运行异步代码，一个不运行异步代码。</span><span class="sxs-lookup"><span data-stu-id="c5809-159">Consider two servers: one that runs async code, and one that does not.</span></span>  <span data-ttu-id="c5809-160">鉴于本示例的目的，每个服务器只有 5 个可用于服务请求的线程。</span><span class="sxs-lookup"><span data-stu-id="c5809-160">For the purpose of this example, each server only has 5 threads available to service requests.</span></span>  <span data-ttu-id="c5809-161">请注意，这样小的数目仅可用于演示。</span><span class="sxs-lookup"><span data-stu-id="c5809-161">Note that these numbers are imaginarily small and serve only in a demonstrative context.</span></span>

<span data-ttu-id="c5809-162">假设两个服务器都接收到 6 个并发请求。</span><span class="sxs-lookup"><span data-stu-id="c5809-162">Assume both servers receive 6 concurrent requests.</span></span> <span data-ttu-id="c5809-163">每个请求执行一个 I/O 操作。</span><span class="sxs-lookup"><span data-stu-id="c5809-163">Each request performs an I/O operation.</span></span>  <span data-ttu-id="c5809-164">未  运行异步代码的服务器必须对第 6 个请求排队，直到 5 个线程中的一个完成了绑定 I/O 的工作并编写了响应。</span><span class="sxs-lookup"><span data-stu-id="c5809-164">The server *without* async code has to queue up the 6th request until one of the 5 threads have finished the I/O-bound work and written a response.</span></span> <span data-ttu-id="c5809-165">此时收到了第 20 个请求，由于队列过长，服务器可能会开始变慢。</span><span class="sxs-lookup"><span data-stu-id="c5809-165">At the point that the 20th request comes in, the server might start to slow down, because the queue is getting too long.</span></span>

<span data-ttu-id="c5809-166">运行有  异步代码的服务器也需对第 6 个请求排队，但由于使用了 `async` 和 `await`，绑定了 I/O 的工作开始时，每个线程都会得到释放，无需等到工作结束。</span><span class="sxs-lookup"><span data-stu-id="c5809-166">The server *with* async code running on it still queues up the 6th request, but because it uses `async` and `await`, each of its threads are freed up when the I/O-bound work starts, rather than when it finishes.</span></span>  <span data-ttu-id="c5809-167">收到第 20 个请求时，传入请求队列将变得很小（如果其中还有请求的话），且服务器不会变慢。</span><span class="sxs-lookup"><span data-stu-id="c5809-167">By the time the 20th request comes in, the queue for incoming requests will be far smaller (if it has anything in it at all), and the server won't slow down.</span></span>

<span data-ttu-id="c5809-168">尽管这是一个人为想象的示例，但在现实世界中其工作方式与此类似。</span><span class="sxs-lookup"><span data-stu-id="c5809-168">Although this is a contrived example, it works in a very similar fashion in the real world.</span></span>  <span data-ttu-id="c5809-169">事实上，相比服务器将线程专用于接收到的每个请求，使用 `async` 和 `await` 能够使服务器多处理一个数量级的请求。</span><span class="sxs-lookup"><span data-stu-id="c5809-169">In fact, you can expect a server to be able to handle an order of magnitude more requests using `async` and `await` than if it were dedicating a thread for each request it receives.</span></span>

### <a name="what-does-this-mean-for-client-scenario"></a><span data-ttu-id="c5809-170">这对客户端方案而言意味着什么？</span><span class="sxs-lookup"><span data-stu-id="c5809-170">What does this mean for client scenario?</span></span>

<span data-ttu-id="c5809-171">使用 `async` 和 `await` 对客户端应用带来的最大好处在于提高了响应能力。</span><span class="sxs-lookup"><span data-stu-id="c5809-171">The biggest gain for using `async` and `await` for a client app is an increase in responsiveness.</span></span>  <span data-ttu-id="c5809-172">尽管可以手动生成线程让应用响应，但相比仅使用 `async` 和 `await`，生成线程的操作更加昂贵。</span><span class="sxs-lookup"><span data-stu-id="c5809-172">Although you can make an app responsive by spawning threads manually, the act of spawning a thread is an expensive operation relative to just using `async` and `await`.</span></span>  <span data-ttu-id="c5809-173">特别是对于手机游戏等应用而言，在涉及 I/O 时尽可能少地影响 UI 线程，这点至关重要。</span><span class="sxs-lookup"><span data-stu-id="c5809-173">Especially for something like a mobile game, impacting the UI thread as little as possible where I/O is concerned is crucial.</span></span>

<span data-ttu-id="c5809-174">更重要的是，由于绑定 I/O 的工作在 CPU 上几乎没有耗时，所以将整个 CPU 线程专用于执行几乎没有任何作用的工作将是一种资源浪费。</span><span class="sxs-lookup"><span data-stu-id="c5809-174">More importantly, because I/O-bound work spends virtually no time on the CPU, dedicating an entire CPU thread to perform barely any useful work would be a poor use of resources.</span></span>

<span data-ttu-id="c5809-175">此外，使用 `async` 方法将工作调度到 UI 线程（例如，更新 UI）十分简单，且无需额外的工作（例如调用线程安全的委托）。</span><span class="sxs-lookup"><span data-stu-id="c5809-175">Additionally, dispatching work to the UI thread (such as updating a UI) is very simple with `async` methods, and does not require extra work (such as calling a thread-safe delegate).</span></span>

## <a name="deeper-dive-into-task-and-taskt-for-a-cpu-bound-operation"></a><span data-ttu-id="c5809-176">深入了解绑定 CPU 的操作的任务和 Task\<T></span><span class="sxs-lookup"><span data-stu-id="c5809-176">Deeper Dive into Task and Task\<T> for a CPU-Bound Operation</span></span>

<span data-ttu-id="c5809-177">绑定 CPU 的 `async` 代码与绑定 I/O 的 `async` 代码有些许不同。</span><span class="sxs-lookup"><span data-stu-id="c5809-177">CPU-bound `async` code is a bit different than I/O-bound `async` code.</span></span>  <span data-ttu-id="c5809-178">由于工作在 CPU 上执行，无法解决线程专用于计算的问题。</span><span class="sxs-lookup"><span data-stu-id="c5809-178">Because the work is done on the CPU, there's no way to get around dedicating a thread to the computation.</span></span>  <span data-ttu-id="c5809-179">`async` 和 `await` 的运用使得可以与后台线程交互并让异步方法调用方可响应。</span><span class="sxs-lookup"><span data-stu-id="c5809-179">The use of `async` and `await` provides you with a clean way to interact with a background thread and keep the caller of the async method responsive.</span></span>  <span data-ttu-id="c5809-180">请注意这不会为共享数据提供任何保护。</span><span class="sxs-lookup"><span data-stu-id="c5809-180">Note that this does not provide any protection for shared data.</span></span>  <span data-ttu-id="c5809-181">如果正在使用共享数据，仍需要采用合适的同步策略。</span><span class="sxs-lookup"><span data-stu-id="c5809-181">If you are using shared data, you will still need to apply an appropriate synchronization strategy.</span></span>

<span data-ttu-id="c5809-182">这里详细介绍了绑定 CPU 的异步调用的方方面面：</span><span class="sxs-lookup"><span data-stu-id="c5809-182">Here's a 10,000 foot view of a CPU-bound async call:</span></span>

```csharp
public async Task<int> CalculateResult(InputData data)
{
    // This queues up the work on the threadpool.
    var expensiveResultTask = Task.Run(() => DoExpensiveCalculation(data));

    // Note that at this point, you can do some other work concurrently,
    // as CalculateResult() is still executing!

    // Execution of CalculateResult is yielded here!
    var result = await expensiveResultTask;

    return result;
}
```

<span data-ttu-id="c5809-183">`CalculateResult()` 在调用它的线程上执行。</span><span class="sxs-lookup"><span data-stu-id="c5809-183">`CalculateResult()` executes on the thread it was called on.</span></span>  <span data-ttu-id="c5809-184">调用 `Task.Run` 时，它会在线程池上对昂贵的绑定 CPU 的操作 `DoExpensiveCalculation()` 进行排队，并收到一个 `Task<int>` 句柄。</span><span class="sxs-lookup"><span data-stu-id="c5809-184">When it calls `Task.Run`, it queues the expensive CPU-bound operation, `DoExpensiveCalculation()`, on the thread pool and receives a `Task<int>` handle.</span></span>  <span data-ttu-id="c5809-185">`DoExpensiveCalculation()` 最终在下一个可用线程上并行运行（很可能在另一个 CPU 内核上）。</span><span class="sxs-lookup"><span data-stu-id="c5809-185">`DoExpensiveCalculation()` is eventually run concurrently on the next available thread, likely on another CPU core.</span></span>  <span data-ttu-id="c5809-186">当 `DoExpensiveCalculation()` 忙于处理另一线程时它可能进行并行工作，因为调用 `CalculateResult()` 的线程仍在执行。</span><span class="sxs-lookup"><span data-stu-id="c5809-186">It's possible to do concurrent work while `DoExpensiveCalculation()` is busy on another thread, because the thread which called `CalculateResult()` is still executing.</span></span>

<span data-ttu-id="c5809-187">一旦遇到 `await`，`CalculateResult()` 执行会让步于调用方，在 `DoExpensiveCalculation()` 执行运算的同时，允许其他任务在当前线程执行。</span><span class="sxs-lookup"><span data-stu-id="c5809-187">Once `await` is encountered, the execution of `CalculateResult()` is yielded to its caller, allowing other work to be done with the current thread while `DoExpensiveCalculation()` is churning out a result.</span></span>  <span data-ttu-id="c5809-188">`DoExpensiveCalculation()` 完成后，结果会在主线程上排队等待运行。</span><span class="sxs-lookup"><span data-stu-id="c5809-188">Once it has finished, the result is queued up to run on the main thread.</span></span>  <span data-ttu-id="c5809-189">最后，主线程将返回执行得到 `DoExpensiveCalculation()` 结果的 `CalculateResult()`，。</span><span class="sxs-lookup"><span data-stu-id="c5809-189">Eventually, the main thread will return to executing `CalculateResult()`, at which point it will have the result of `DoExpensiveCalculation()`.</span></span>

### <a name="why-does-async-help-here"></a><span data-ttu-id="c5809-190">异步为什么在此处会起作用？</span><span class="sxs-lookup"><span data-stu-id="c5809-190">Why does async help here?</span></span>

<span data-ttu-id="c5809-191">`async` 和 `await` 是在需要可响应性时管理绑定 CPU 的工作的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="c5809-191">`async` and `await` are the best practice for managing CPU-bound work when you need responsiveness.</span></span> <span data-ttu-id="c5809-192">存在多个可将异步用于绑定 CPU 的工作的模式。</span><span class="sxs-lookup"><span data-stu-id="c5809-192">There are multiple patterns for using async with CPU-bound work.</span></span> <span data-ttu-id="c5809-193">请务必注意，使用异步成本有少许费用，不推荐紧凑循环使用它。</span><span class="sxs-lookup"><span data-stu-id="c5809-193">It's important to note that there is a small cost to using async and it's not recommended for tight loops.</span></span>  <span data-ttu-id="c5809-194">如何编写此新功能的代码完全取决于你。</span><span class="sxs-lookup"><span data-stu-id="c5809-194">It's up to you to determine how you write your code around this new capability.</span></span>

## <a name="see-also"></a><span data-ttu-id="c5809-195">请参阅</span><span class="sxs-lookup"><span data-stu-id="c5809-195">See also</span></span>

- [<span data-ttu-id="c5809-196">C# 中的异步编程</span><span class="sxs-lookup"><span data-stu-id="c5809-196">Asynchronous programming in C#</span></span>](../csharp/async.md)
- [<span data-ttu-id="c5809-197">使用 Async 和 Await 的异步编程 (C#)</span><span class="sxs-lookup"><span data-stu-id="c5809-197">Asynchronous programming with async and await (C#)</span></span>](../csharp/programming-guide/concepts/async/index.md)
- [<span data-ttu-id="c5809-198">F# 中的异步编程</span><span class="sxs-lookup"><span data-stu-id="c5809-198">Async Programming in F#</span></span>](../fsharp/tutorials/asynchronous-and-concurrent-programming/async.md)
- [<span data-ttu-id="c5809-199">使用 Async 和 Await 的异步编程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c5809-199">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../visual-basic/programming-guide/concepts/async/index.md)
