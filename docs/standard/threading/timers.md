---
title: 计时器
description: 了解在多线程环境中使用哪些 .NET 计时器。
ms.date: 07/03/2018
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [.NET], timers
- timers, about timers
ms.assetid: 7091500d-be18-499b-a942-95366ce185e5
author: pkulikov
ms.openlocfilehash: 1ab612bc32a84c1248d311b0603a01a32a25199f
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "94826100"
---
# <a name="timers"></a><span data-ttu-id="9ecb7-103">计时器</span><span class="sxs-lookup"><span data-stu-id="9ecb7-103">Timers</span></span>

<span data-ttu-id="9ecb7-104">.NET 提供两种可在多线程环境中使用的计时器：</span><span class="sxs-lookup"><span data-stu-id="9ecb7-104">.NET provides two timers to use in a multithreaded environment:</span></span>

- <span data-ttu-id="9ecb7-105"><xref:System.Threading.Timer?displayProperty=nameWithType>，用于按固定时间间隔在 <xref:System.Threading.ThreadPool> 线程上执行单个回叫方法。</span><span class="sxs-lookup"><span data-stu-id="9ecb7-105"><xref:System.Threading.Timer?displayProperty=nameWithType>, which executes a single callback method on a <xref:System.Threading.ThreadPool> thread at regular intervals.</span></span>
- <span data-ttu-id="9ecb7-106"><xref:System.Timers.Timer?displayProperty=nameWithType>，默认情况下按固定时间间隔在 <xref:System.Threading.ThreadPool> 线程上引发事件。</span><span class="sxs-lookup"><span data-stu-id="9ecb7-106"><xref:System.Timers.Timer?displayProperty=nameWithType>, which by default raises an event on a <xref:System.Threading.ThreadPool> thread at regular intervals.</span></span>

> [!NOTE]
> <span data-ttu-id="9ecb7-107">某些 .NET 实现可能包含其他计时器：</span><span class="sxs-lookup"><span data-stu-id="9ecb7-107">Some .NET implementations may include additional timers:</span></span>
>
> - <span data-ttu-id="9ecb7-108"><xref:System.Windows.Forms.Timer?displayProperty=nameWithType>：一种 Windows 窗体组件，按固定时间间隔触发事件。</span><span class="sxs-lookup"><span data-stu-id="9ecb7-108"><xref:System.Windows.Forms.Timer?displayProperty=nameWithType>: a Windows Forms component that fires an event at regular intervals.</span></span> <span data-ttu-id="9ecb7-109">该组件没有用户界面，专门用于单线程环境。</span><span class="sxs-lookup"><span data-stu-id="9ecb7-109">The component has no user interface and is designed for use in a single-threaded environment.</span></span>  
> - <span data-ttu-id="9ecb7-110"><xref:System.Web.UI.Timer?displayProperty=nameWithType>：一种 ASP.NET 组件，按固定时间间隔执行异步或同步网页回发。</span><span class="sxs-lookup"><span data-stu-id="9ecb7-110"><xref:System.Web.UI.Timer?displayProperty=nameWithType>: an ASP.NET component that performs asynchronous or synchronous web page postbacks at a regular interval.</span></span>
> - <span data-ttu-id="9ecb7-111"><xref:System.Windows.Threading.DispatcherTimer?displayProperty=nameWithType>：集成到 <xref:System.Windows.Threading.Dispatcher> 队列中的计时器，该队列按指定时间间隔和指定优先级进行处理。</span><span class="sxs-lookup"><span data-stu-id="9ecb7-111"><xref:System.Windows.Threading.DispatcherTimer?displayProperty=nameWithType>: a timer that is integrated into the <xref:System.Windows.Threading.Dispatcher> queue which is processed at a specified interval of time and at a specified priority.</span></span>

## <a name="the-systemthreadingtimer-class"></a><span data-ttu-id="9ecb7-112">System.Threading.Timer 类</span><span class="sxs-lookup"><span data-stu-id="9ecb7-112">The System.Threading.Timer class</span></span>

<span data-ttu-id="9ecb7-113"><xref:System.Threading.Timer?displayProperty=nameWithType> 类可用于按指定时间间隔持续调用委托。</span><span class="sxs-lookup"><span data-stu-id="9ecb7-113">The <xref:System.Threading.Timer?displayProperty=nameWithType> class enables you to continuously call a delegate at specified time intervals.</span></span> <span data-ttu-id="9ecb7-114">此外，还可以使用此类计划按指定时间间隔对委托进行单次调用。</span><span class="sxs-lookup"><span data-stu-id="9ecb7-114">You can also use this class to schedule a single call to a delegate in a specified time interval.</span></span> <span data-ttu-id="9ecb7-115">该委托在 <xref:System.Threading.ThreadPool> 线程上执行。</span><span class="sxs-lookup"><span data-stu-id="9ecb7-115">The delegate is executed on a <xref:System.Threading.ThreadPool> thread.</span></span>

<span data-ttu-id="9ecb7-116">在创建 <xref:System.Threading.Timer?displayProperty=nameWithType> 对象时，需指定定义回叫方法的 <xref:System.Threading.TimerCallback> 委托、传递到该回叫的可选状态对象、首次调用该回叫前的延迟时间以及两次回叫调用之间的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="9ecb7-116">When you create a <xref:System.Threading.Timer?displayProperty=nameWithType> object, you specify a <xref:System.Threading.TimerCallback> delegate that defines the callback method, an optional state object that is passed to the callback, the amount of time to delay before the first invocation of the callback, and the time interval between callback invocations.</span></span> <span data-ttu-id="9ecb7-117">若要取消挂起的计时器，请调用 <xref:System.Threading.Timer.Dispose%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="9ecb7-117">To cancel a pending timer, call the <xref:System.Threading.Timer.Dispose%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="9ecb7-118">以下示例创建一个计时器，该计时器在一秒（1000 毫秒）后首次调用提供的委托，之后每两秒调用一次该委托。</span><span class="sxs-lookup"><span data-stu-id="9ecb7-118">The following example creates a timer that calls the provided delegate for the first time after one second (1000 milliseconds) and then calls it every two seconds.</span></span> <span data-ttu-id="9ecb7-119">示例中的状态对象用于计算调用该委托的次数。</span><span class="sxs-lookup"><span data-stu-id="9ecb7-119">The state object in the example is used to count how many times the delegate is called.</span></span> <span data-ttu-id="9ecb7-120">当调用委托至少达 10 次时，计时器将停止。</span><span class="sxs-lookup"><span data-stu-id="9ecb7-120">The timer is stopped when the delegate has been called at least 10 times.</span></span>

[!code-cpp[System.Threading.Timer#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.Timer/CPP/source2.cpp#2)]
[!code-csharp[System.Threading.Timer#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.Timer/CS/source2.cs#2)]
[!code-vb[System.Threading.Timer#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.Timer/VB/source2.vb#2)]

<span data-ttu-id="9ecb7-121">有关更多信息和示例，请参见<xref:System.Threading.Timer?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="9ecb7-121">For more information and examples, see <xref:System.Threading.Timer?displayProperty=nameWithType>.</span></span>

## <a name="the-systemtimerstimer-class"></a><span data-ttu-id="9ecb7-122">System.Timers.Timer 类</span><span class="sxs-lookup"><span data-stu-id="9ecb7-122">The System.Timers.Timer class</span></span>

<span data-ttu-id="9ecb7-123"><xref:System.Timers.Timer?displayProperty=nameWithType> 是另一个可在多线程环境中使用的计时器，该计时器默认情况下在 <xref:System.Threading.ThreadPool> 线程上引发事件。</span><span class="sxs-lookup"><span data-stu-id="9ecb7-123">Another timer that can be used in a multithreaded environment is <xref:System.Timers.Timer?displayProperty=nameWithType> that by default raises an event on a <xref:System.Threading.ThreadPool> thread.</span></span>

<span data-ttu-id="9ecb7-124">在创建 <xref:System.Timers.Timer?displayProperty=nameWithType> 对象时，可以指定引发 <xref:System.Timers.Timer.Elapsed> 事件的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="9ecb7-124">When you create a <xref:System.Timers.Timer?displayProperty=nameWithType> object, you may specify the time interval in which to raise an <xref:System.Timers.Timer.Elapsed> event.</span></span> <span data-ttu-id="9ecb7-125">使用 <xref:System.Timers.Timer.Enabled%2A> 属性指示计时器是否应引发 <xref:System.Timers.Timer.Elapsed> 事件。</span><span class="sxs-lookup"><span data-stu-id="9ecb7-125">Use the <xref:System.Timers.Timer.Enabled%2A> property to indicate if a timer should raise an <xref:System.Timers.Timer.Elapsed> event.</span></span> <span data-ttu-id="9ecb7-126">如果仅需在经过指定时间间隔后引发一次 <xref:System.Timers.Timer.Elapsed> 事件，请将 <xref:System.Timers.Timer.AutoReset%2A> 设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="9ecb7-126">If you need an <xref:System.Timers.Timer.Elapsed> event to be raised only once after the specified interval has elapsed, set the <xref:System.Timers.Timer.AutoReset%2A> to `false`.</span></span> <span data-ttu-id="9ecb7-127"><xref:System.Timers.Timer.AutoReset%2A> 属性的默认值为 `true`，表示将按 <xref:System.Timers.Timer.Interval%2A> 属性定义的时间间隔定期引发 <xref:System.Timers.Timer.Elapsed> 事件。</span><span class="sxs-lookup"><span data-stu-id="9ecb7-127">The default value of the <xref:System.Timers.Timer.AutoReset%2A> property is `true`, which means that an <xref:System.Timers.Timer.Elapsed> event is raised regularly at the interval defined by the <xref:System.Timers.Timer.Interval%2A> property.</span></span>

<span data-ttu-id="9ecb7-128">有关更多信息和示例，请参见<xref:System.Timers.Timer?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="9ecb7-128">For more information and examples, see <xref:System.Timers.Timer?displayProperty=nameWithType>.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9ecb7-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="9ecb7-129">See also</span></span>

- <xref:System.Threading.Timer?displayProperty=nameWithType>
- <xref:System.Timers.Timer?displayProperty=nameWithType>
- [<span data-ttu-id="9ecb7-130">线程处理对象和功能</span><span class="sxs-lookup"><span data-stu-id="9ecb7-130">Threading Objects and Features</span></span>](threading-objects-and-features.md)
