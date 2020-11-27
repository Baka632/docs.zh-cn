---
title: releaseHandleFailed MDA
description: 查看 releaseHandleFailed 托管调试助手 (MDA) ，这可能是由于 .NET 中的资源或内存泄漏导致的。
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), handles
- release handle failed
- CriticalHandle class, run-time errors
- releaseHandleFailed MDA
- ReleaseHandle method
- SafeHandle class, run-time errors
- MDAs (managed debugging assistants), handles
ms.assetid: 44cd98ba-95e5-40a1-874d-e8e163612c51
ms.openlocfilehash: b337a7283e961d0fae2b51d92a21fa77f7249250
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267125"
---
# <a name="releasehandlefailed-mda"></a><span data-ttu-id="708be-103">releaseHandleFailed MDA</span><span class="sxs-lookup"><span data-stu-id="708be-103">releaseHandleFailed MDA</span></span>

<span data-ttu-id="708be-104">当 <xref:System.Runtime.InteropServices.SafeHandle> 或 <xref:System.Runtime.InteropServices.CriticalHandle> 派生的类的 <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> 方法返回 `false` 时，激活 `releaseHandleFailed` 托管调试助手 (MDA) 通知开发人员。</span><span class="sxs-lookup"><span data-stu-id="708be-104">The `releaseHandleFailed` managed debugging assistant (MDA) is activated is to notify developers when the <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> method of a class derived from <xref:System.Runtime.InteropServices.SafeHandle> or <xref:System.Runtime.InteropServices.CriticalHandle> returns `false`.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="708be-105">症状</span><span class="sxs-lookup"><span data-stu-id="708be-105">Symptoms</span></span>  

 <span data-ttu-id="708be-106">资源或内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="708be-106">Resource or memory leaks.</span></span>  <span data-ttu-id="708be-107">如果 <xref:System.Runtime.InteropServices.SafeHandle> 或 <xref:System.Runtime.InteropServices.CriticalHandle> 派生的类的 <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> 方法失败，则由类所封装的资源可能尚未释放或清理。</span><span class="sxs-lookup"><span data-stu-id="708be-107">If the <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> method of the class deriving from <xref:System.Runtime.InteropServices.SafeHandle> or <xref:System.Runtime.InteropServices.CriticalHandle> fails, then the resource encapsulated by the class might not have been released or cleaned up.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="708be-108">原因</span><span class="sxs-lookup"><span data-stu-id="708be-108">Cause</span></span>  

 <span data-ttu-id="708be-109">如果用户创建派生自 <xref:System.Runtime.InteropServices.SafeHandle> 或 <xref:System.Runtime.InteropServices.CriticalHandle> 的类，则他们必须提供 <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> 方法的实现；因此，这些情况是特定于单个资源的。</span><span class="sxs-lookup"><span data-stu-id="708be-109">Users must provide the implementation of the <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> method if they create classes that derive from <xref:System.Runtime.InteropServices.SafeHandle> or <xref:System.Runtime.InteropServices.CriticalHandle>; thus, the circumstances are specific to the individual resource.</span></span> <span data-ttu-id="708be-110">但是，需求如下所示：</span><span class="sxs-lookup"><span data-stu-id="708be-110">However, the requirements are as follows:</span></span>  
  
- <span data-ttu-id="708be-111"><xref:System.Runtime.InteropServices.SafeHandle> 和 <xref:System.Runtime.InteropServices.CriticalHandle> 类型表示重要进程资源的包装。</span><span class="sxs-lookup"><span data-stu-id="708be-111"><xref:System.Runtime.InteropServices.SafeHandle> and <xref:System.Runtime.InteropServices.CriticalHandle> types represent wrappers around vital process resources.</span></span> <span data-ttu-id="708be-112">随着时间的推移，内存泄漏会使该过程不可用。</span><span class="sxs-lookup"><span data-stu-id="708be-112">A memory leak would make the process unusable over time.</span></span>  
  
- <span data-ttu-id="708be-113"><xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> 方法必须成功执行其功能。</span><span class="sxs-lookup"><span data-stu-id="708be-113">The <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> method must not fail to perform its function.</span></span> <span data-ttu-id="708be-114">一旦进程获取此类资源，<xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> 就是唯一将其释放的方法。</span><span class="sxs-lookup"><span data-stu-id="708be-114">Once the process acquires such a resource, <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> is the only way to release it.</span></span> <span data-ttu-id="708be-115">因此，失败意味着资源泄漏。</span><span class="sxs-lookup"><span data-stu-id="708be-115">Therefore, failure implies resource leaks.</span></span>  
  
- <span data-ttu-id="708be-116">在执行 <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> 期间发生的任何故障阻碍了资源释放，这是实现 <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> 方法本身的 Bug。</span><span class="sxs-lookup"><span data-stu-id="708be-116">Any failure that does occur during the execution of <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A>, impeding the release of the resource, is a bug in the implementation of the <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> method itself.</span></span> <span data-ttu-id="708be-117">即使该代码调用由其他人授权的代码来执行其功能，程序员也要负责确保履行该合同。</span><span class="sxs-lookup"><span data-stu-id="708be-117">It is the responsibility of the programmer to ensure that the contract is fulfilled, even if that code calls code authored by someone else to perform its function.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="708be-118">解决方法</span><span class="sxs-lookup"><span data-stu-id="708be-118">Resolution</span></span>  

 <span data-ttu-id="708be-119">应检查使用引发 MDA 通知的特定 <xref:System.Runtime.InteropServices.SafeHandle>（或 <xref:System.Runtime.InteropServices.CriticalHandle>）类型的代码，查找原始句柄值从 <xref:System.Runtime.InteropServices.SafeHandle> 提取的位置或复制的其他位置。</span><span class="sxs-lookup"><span data-stu-id="708be-119">The code that uses the specific <xref:System.Runtime.InteropServices.SafeHandle> (or <xref:System.Runtime.InteropServices.CriticalHandle>) type that raised the MDA notification should be reviewed, looking for places where the raw handle value is extracted from the <xref:System.Runtime.InteropServices.SafeHandle> and copied elsewhere.</span></span> <span data-ttu-id="708be-120">这是 <xref:System.Runtime.InteropServices.SafeHandle> 或 <xref:System.Runtime.InteropServices.CriticalHandle> 实现失败的一般原因，由于原始句柄值的使用在那时将不再由运行时跟踪。</span><span class="sxs-lookup"><span data-stu-id="708be-120">This is the usual cause of failures within <xref:System.Runtime.InteropServices.SafeHandle> or <xref:System.Runtime.InteropServices.CriticalHandle> implementations, because the usage of the raw handle value is then no longer tracked by the runtime.</span></span> <span data-ttu-id="708be-121">如果原始句柄复制随后关闭，则可能导致之后的 <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> 调用失败，因为关闭是在相同句柄上尝试的，而该句柄现已无效。</span><span class="sxs-lookup"><span data-stu-id="708be-121">If the raw handle copy is subsequently closed, it can cause a later <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> call to fail because the close is attempted on the same handle, which is now invalid.</span></span>  
  
 <span data-ttu-id="708be-122">可能不正确的句柄复制，有多种方式：</span><span class="sxs-lookup"><span data-stu-id="708be-122">There are a number of ways in which incorrect handle duplication can occur:</span></span>  
  
- <span data-ttu-id="708be-123">查找对 <xref:System.Runtime.InteropServices.SafeHandle.DangerousGetHandle%2A> 方法的调用。</span><span class="sxs-lookup"><span data-stu-id="708be-123">Look for calls to the <xref:System.Runtime.InteropServices.SafeHandle.DangerousGetHandle%2A> method.</span></span> <span data-ttu-id="708be-124">对此方法的调用应极其罕见，以及对 <xref:System.Runtime.InteropServices.SafeHandle.DangerousAddRef%2A> 和 <xref:System.Runtime.InteropServices.SafeHandle.DangerousRelease%2A> 方法的调用应围绕你的任何发现。</span><span class="sxs-lookup"><span data-stu-id="708be-124">Calls to this method should be exceedingly rare, and any that you find should be surrounded by calls to the <xref:System.Runtime.InteropServices.SafeHandle.DangerousAddRef%2A> and <xref:System.Runtime.InteropServices.SafeHandle.DangerousRelease%2A> methods.</span></span> <span data-ttu-id="708be-125">后面的方法指定原始句柄值能安全使用的代码区域。</span><span class="sxs-lookup"><span data-stu-id="708be-125">These latter methods specify the region of code in which the raw handle value may be safely used.</span></span> <span data-ttu-id="708be-126">在此区域外，或如果引用计数永远不会增加至第一，则可以在任何时候通过调用另一线程上的 <xref:System.Runtime.InteropServices.SafeHandle.Dispose%2A> 或 <xref:System.Runtime.InteropServices.SafeHandle.Close%2A> 使句柄值失效。</span><span class="sxs-lookup"><span data-stu-id="708be-126">Outside this region, or if the reference count is never incremented in the first place, the handle value can be invalidated at any time by a call to <xref:System.Runtime.InteropServices.SafeHandle.Dispose%2A> or <xref:System.Runtime.InteropServices.SafeHandle.Close%2A> on another thread.</span></span> <span data-ttu-id="708be-127">一旦所有对 <xref:System.Runtime.InteropServices.SafeHandle.DangerousGetHandle%2A> 的使用都被跟踪，则应该跟随原始句柄采用的路径，确保它不会被移交给将最终调用 `CloseHandle` 的某些组件或将释放句柄的另一低级别的本机方法。</span><span class="sxs-lookup"><span data-stu-id="708be-127">Once all uses of <xref:System.Runtime.InteropServices.SafeHandle.DangerousGetHandle%2A> have been tracked down, you should follow the path the raw handle takes to ensure it is not handed off to some component that will eventually call `CloseHandle` or another low-level native method that will release the handle.</span></span>  
  
- <span data-ttu-id="708be-128">确保用以初始化带有有效原始句柄值的 <xref:System.Runtime.InteropServices.SafeHandle> 的代码拥有句柄。</span><span class="sxs-lookup"><span data-stu-id="708be-128">Ensure that the code that is used to initialize the <xref:System.Runtime.InteropServices.SafeHandle> with a valid raw handle value owns the handle.</span></span> <span data-ttu-id="708be-129">如果在没有将 `ownsHandle` 参数设置到基构造函数中的 `false` 时，围绕代码没有的句柄构造 <xref:System.Runtime.InteropServices.SafeHandle>，则 <xref:System.Runtime.InteropServices.SafeHandle> 和实际句柄拥有者都可以关闭该句柄，如果 <xref:System.Runtime.InteropServices.SafeHandle> 失去争用，这将会导致 <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> 中出错。</span><span class="sxs-lookup"><span data-stu-id="708be-129">If you form a <xref:System.Runtime.InteropServices.SafeHandle> around a handle your code does not own without setting the `ownsHandle` parameter to `false` in the base constructor, then both the <xref:System.Runtime.InteropServices.SafeHandle> and the real handle owner can try to close the handle, leading to an error in <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> if the <xref:System.Runtime.InteropServices.SafeHandle> loses the race.</span></span>  
  
- <span data-ttu-id="708be-130">当 <xref:System.Runtime.InteropServices.SafeHandle> 在应用程序域之间封送，请确认正在使用 <xref:System.Runtime.InteropServices.SafeHandle> 派生已被标记为可序列化。</span><span class="sxs-lookup"><span data-stu-id="708be-130">When a <xref:System.Runtime.InteropServices.SafeHandle> is marshaled between application domains, confirm the <xref:System.Runtime.InteropServices.SafeHandle> derivation being used has been marked as serializable.</span></span> <span data-ttu-id="708be-131">在极少数情况下，当派生自 <xref:System.Runtime.InteropServices.SafeHandle> 的类已进行序列化，它应实现 <xref:System.Runtime.Serialization.ISerializable> 接口或使用其他方法之一来手动控制序列化和反序列化进程。</span><span class="sxs-lookup"><span data-stu-id="708be-131">In the rare cases where a class derived from <xref:System.Runtime.InteropServices.SafeHandle> has been made serializable, it should implement the <xref:System.Runtime.Serialization.ISerializable> interface or use one of the other techniques for controlling the serialization and deserialization process manually.</span></span> <span data-ttu-id="708be-132">这是必需的，因为默认序列化操作是为了创建封闭原始句柄值的按位克隆，从而生成两个 <xref:System.Runtime.InteropServices.SafeHandle> 拥有相同句柄的实例。</span><span class="sxs-lookup"><span data-stu-id="708be-132">This is required because the default serialization action is to create a bitwise clone of the enclosed raw handle value, resulting in two <xref:System.Runtime.InteropServices.SafeHandle> instances thinking they own the same handle.</span></span> <span data-ttu-id="708be-133">两者都将尝试在某个时刻调用相同句柄上的 <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A>。</span><span class="sxs-lookup"><span data-stu-id="708be-133">Both will try to call <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> on the same handle at some point.</span></span> <span data-ttu-id="708be-134">执行此操作的第二个 <xref:System.Runtime.InteropServices.SafeHandle> 将失败。</span><span class="sxs-lookup"><span data-stu-id="708be-134">The second <xref:System.Runtime.InteropServices.SafeHandle> to do this will fail.</span></span> <span data-ttu-id="708be-135">序列化 <xref:System.Runtime.InteropServices.SafeHandle> 时的正确操作过程是为本机句柄类型调用 `DuplicateHandle` 功能或类似功能，以进行不同的合法句柄复制。</span><span class="sxs-lookup"><span data-stu-id="708be-135">The correct course of action when serializing a <xref:System.Runtime.InteropServices.SafeHandle> is to call the `DuplicateHandle` function or a similar function for your native handle type to make a distinct legal handle copy.</span></span> <span data-ttu-id="708be-136">如果句柄类型不支持，则包装它的 <xref:System.Runtime.InteropServices.SafeHandle> 类型不能设置为可序列化。</span><span class="sxs-lookup"><span data-stu-id="708be-136">If your handle type does not support this then the <xref:System.Runtime.InteropServices.SafeHandle> type wrapping it cannot be made serializable.</span></span>  
  
- <span data-ttu-id="708be-137">可以跟踪句柄之前关闭的位置，通过将调试器断点放在用来释放该句柄的本机例程上（例如 `CloseHandle` 函数），当最终调用 <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> 方法时，会导致失败。</span><span class="sxs-lookup"><span data-stu-id="708be-137">It may be possible to track where a handle is being closed early, leading to a failure when the <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> method is finally called, by placing a debugger breakpoint on the native routine used to release the handle, for example the `CloseHandle` function.</span></span> <span data-ttu-id="708be-138">这在压力方案中或甚至是中型功能测试中都不可能实现，由于此类例程处理的通信通常非常繁忙。</span><span class="sxs-lookup"><span data-stu-id="708be-138">This may not be possible for stress scenarios or even medium-sized functional tests due to the heavy traffic such routines often deal with.</span></span> <span data-ttu-id="708be-139">它可能有助于检测调用本机释放方法的代码，以便捕获调用方的标识，或者可能捕获完整堆栈跟踪，以及被释放句柄的值。</span><span class="sxs-lookup"><span data-stu-id="708be-139">It may help to instrument the code that calls the native release method, in order to capture the identity of the caller, or possibly a full stack trace, and the value of the handle being released.</span></span>  <span data-ttu-id="708be-140">句柄值可以与此 MDA 报告的值进行比较。</span><span class="sxs-lookup"><span data-stu-id="708be-140">The handle value can be compared with the value reported by this MDA.</span></span>  
  
- <span data-ttu-id="708be-141">注意：某些本机句柄类型（例如所有可以通过 `CloseHandle` 函数释放的 Win32 处理程序）会共享相同的句柄命名空间。</span><span class="sxs-lookup"><span data-stu-id="708be-141">Note that some native handle types, such as all the Win32 handles that can be released via the `CloseHandle` function, share the same handle namespace.</span></span> <span data-ttu-id="708be-142">一个句柄类型的错误释放会导致另一个句柄类型出现问题。</span><span class="sxs-lookup"><span data-stu-id="708be-142">An erroneous release of one handle type can cause problems with another.</span></span> <span data-ttu-id="708be-143">例如，意外地两次关闭 Win32 事件句柄可能会导致过早关闭一个明显不相关的文件句柄。</span><span class="sxs-lookup"><span data-stu-id="708be-143">For instance, accidentally closing a Win32 event handle twice might lead to an apparently unrelated file handle being closed prematurely.</span></span> <span data-ttu-id="708be-144">当释放该句柄和句柄值可使用于跟踪另一个资源（可能为另一种类型）时，将发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="708be-144">This happens when the handle is released and the handle value becomes available for use to track another resource, potentially of another type.</span></span> <span data-ttu-id="708be-145">如果发生这种情况，并且后跟错误的第二次释放，则不相关线程句柄可能会失效。</span><span class="sxs-lookup"><span data-stu-id="708be-145">If this happens and is followed by an erroneous second release, the handle of an unrelated thread might be invalidated.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="708be-146">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="708be-146">Effect on the Runtime</span></span>  

 <span data-ttu-id="708be-147">此 MDA 对 CLR 无任何影响。</span><span class="sxs-lookup"><span data-stu-id="708be-147">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="708be-148">输出</span><span class="sxs-lookup"><span data-stu-id="708be-148">Output</span></span>  

 <span data-ttu-id="708be-149">一条消息，该消息表明 <xref:System.Runtime.InteropServices.SafeHandle> 或 <xref:System.Runtime.InteropServices.CriticalHandle> 未能正确释放该句柄。</span><span class="sxs-lookup"><span data-stu-id="708be-149">A message indicating that a <xref:System.Runtime.InteropServices.SafeHandle> or a <xref:System.Runtime.InteropServices.CriticalHandle> failed to properly release the handle.</span></span> <span data-ttu-id="708be-150">例如：</span><span class="sxs-lookup"><span data-stu-id="708be-150">For example:</span></span>  
  
```output
"A SafeHandle or CriticalHandle of type 'MyBrokenSafeHandle'
failed to properly release the handle with value 0x0000BEEF. This
usually indicates that the handle was released incorrectly via
another means (such as extracting the handle using DangerousGetHandle
and closing it directly or building another SafeHandle around it."  
```  
  
## <a name="configuration"></a><span data-ttu-id="708be-151">Configuration</span><span class="sxs-lookup"><span data-stu-id="708be-151">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <releaseHandleFailed/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="708be-152">示例</span><span class="sxs-lookup"><span data-stu-id="708be-152">Example</span></span>  

 <span data-ttu-id="708be-153">以下是可激活 `releaseHandleFailed` MDA 的代码示例。</span><span class="sxs-lookup"><span data-stu-id="708be-153">The following is a code example that can activate the `releaseHandleFailed` MDA.</span></span>  
  
```csharp
bool ReleaseHandle()  
{  
    // Calling the Win32 CloseHandle function to release the
    // native handle wrapped by this SafeHandle. This method returns
    // false on failure, but should only fail if the input is invalid
    // (which should not happen here). The method specifically must not
    // fail simply because of lack of resources or other transient
    // failures beyond the user’s control. That would make it unacceptable
    // to call CloseHandle as part of the implementation of this method.  
    return CloseHandle(handle);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="708be-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="708be-154">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="708be-155">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="708be-155">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="708be-156">互操作封送处理</span><span class="sxs-lookup"><span data-stu-id="708be-156">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
