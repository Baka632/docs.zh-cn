---
title: fatalExecutionEngineError MDA
description: 查看 .NET 中的 fatalExecutionEngineError 托管调试助手 (MDA) ，这可能是由于意外的进程终止而激活。
ms.date: 03/30/2017
helpviewer_keywords:
- corrupted CLR
- fatal execution error
- terminated processes
- unexpected terminations
- fatal errors
- MDAs (managed debugging assistants), fatal errors
- process termination
- FatalExecutionEngineError MDA
- managed debugging assistants (MDAs), fatal errors
ms.assetid: 8b559e44-2393-4e4e-8160-7558d37a4a89
ms.openlocfilehash: a9347338d53755b74b3ff291f75cb6b221134130
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244270"
---
# <a name="fatalexecutionengineerror-mda"></a><span data-ttu-id="055e8-103">fatalExecutionEngineError MDA</span><span class="sxs-lookup"><span data-stu-id="055e8-103">fatalExecutionEngineError MDA</span></span>

<span data-ttu-id="055e8-104">在公共语言运行时 (CLR) 中检测到灾难性错误时，会激活 `fatalExecutionEngineError` 托管调试助手 (MDA)。</span><span class="sxs-lookup"><span data-stu-id="055e8-104">The `fatalExecutionEngineError` managed debugging assistant (MDA) is activated when a fatal error in the common language runtime (CLR) has been detected.</span></span> <span data-ttu-id="055e8-105">进程会终止。</span><span class="sxs-lookup"><span data-stu-id="055e8-105">The process will be terminated.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="055e8-106">症状</span><span class="sxs-lookup"><span data-stu-id="055e8-106">Symptoms</span></span>  

 <span data-ttu-id="055e8-107">进程意外终止。</span><span class="sxs-lookup"><span data-stu-id="055e8-107">Unexpected process termination.</span></span> <span data-ttu-id="055e8-108">无法确定其他症状，因为有多种原因会导致 CLR 故障。</span><span class="sxs-lookup"><span data-stu-id="055e8-108">Other symptoms cannot be determined because a CLR failure can occur for a variety of reasons.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="055e8-109">原因</span><span class="sxs-lookup"><span data-stu-id="055e8-109">Cause</span></span>  

 <span data-ttu-id="055e8-110">CLR 已严重损坏。</span><span class="sxs-lookup"><span data-stu-id="055e8-110">The CLR has been fatally corrupted.</span></span> <span data-ttu-id="055e8-111">这通常是由数据损坏导致的，而数据损坏可能涉及许多问题，如调用格式不正确的平台调用函数以及将无效的数据传递到 CLR。</span><span class="sxs-lookup"><span data-stu-id="055e8-111">This is most often caused by data corruption, which can be caused by a number of problems, such as calls to malformed platform invoke functions and passing invalid data to the CLR.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="055e8-112">解决方法</span><span class="sxs-lookup"><span data-stu-id="055e8-112">Resolution</span></span>  

 <span data-ttu-id="055e8-113">启用其他 MAD 可能有助于确定此问题。</span><span class="sxs-lookup"><span data-stu-id="055e8-113">Enabling additional MDAs might help identify the problem.</span></span> <span data-ttu-id="055e8-114">以下 MDA 对诊断该问题尤为有用：</span><span class="sxs-lookup"><span data-stu-id="055e8-114">The following MDAs can be particularly helpful in diagnosing the issue:</span></span>  
  
- [<span data-ttu-id="055e8-115">invalidOverlappedToPinvoke</span><span class="sxs-lookup"><span data-stu-id="055e8-115">invalidOverlappedToPinvoke</span></span>](invalidoverlappedtopinvoke-mda.md)  
  
- [<span data-ttu-id="055e8-116">overlappedFreeError</span><span class="sxs-lookup"><span data-stu-id="055e8-116">overlappedFreeError</span></span>](overlappedfreeerror-mda.md)  
  
- [<span data-ttu-id="055e8-117">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="055e8-117">pInvokeStackImbalance</span></span>](pinvokestackimbalance-mda.md)  
  
- [<span data-ttu-id="055e8-118">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="055e8-118">gcUnmanagedToManaged</span></span>](gcunmanagedtomanaged-mda.md)  
  
- [<span data-ttu-id="055e8-119">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="055e8-119">gcManagedToUnmanaged</span></span>](gcmanagedtounmanaged-mda.md)  
  
- [<span data-ttu-id="055e8-120">callbackOnCollectedDelegate</span><span class="sxs-lookup"><span data-stu-id="055e8-120">callbackOnCollectedDelegate</span></span>](callbackoncollecteddelegate-mda.md)  
  
- [<span data-ttu-id="055e8-121">reportAvOnComRelease</span><span class="sxs-lookup"><span data-stu-id="055e8-121">reportAvOnComRelease</span></span>](reportavoncomrelease-mda.md)  
  
- [<span data-ttu-id="055e8-122">invalidVariant</span><span class="sxs-lookup"><span data-stu-id="055e8-122">invalidVariant</span></span>](invalidvariant-mda.md)  
  
- [<span data-ttu-id="055e8-123">invalidIUnknown</span><span class="sxs-lookup"><span data-stu-id="055e8-123">invalidIUnknown</span></span>](invalidiunknown-mda.md)  
  
- [<span data-ttu-id="055e8-124">raceOnRCWCleanup</span><span class="sxs-lookup"><span data-stu-id="055e8-124">raceOnRCWCleanup</span></span>](raceonrcwcleanup-mda.md)  
  
- [<span data-ttu-id="055e8-125">invalidFunctionPointerInDelegate</span><span class="sxs-lookup"><span data-stu-id="055e8-125">invalidFunctionPointerInDelegate</span></span>](invalidfunctionpointerindelegate-mda.md)  
  
- [<span data-ttu-id="055e8-126">invalidGCHandleCookie</span><span class="sxs-lookup"><span data-stu-id="055e8-126">invalidGCHandleCookie</span></span>](invalidgchandlecookie-mda.md)  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="055e8-127">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="055e8-127">Effect on the Runtime</span></span>  

 <span data-ttu-id="055e8-128">此 MDA 对运行时无任何影响。</span><span class="sxs-lookup"><span data-stu-id="055e8-128">This MDA has no effect on the runtime's behavior.</span></span>  
  
## <a name="output"></a><span data-ttu-id="055e8-129">输出</span><span class="sxs-lookup"><span data-stu-id="055e8-129">Output</span></span>  

 <span data-ttu-id="055e8-130">造成灾难性错误的 CLR 函数的地址，发生错误的线程的 ID，以及错误代码。</span><span class="sxs-lookup"><span data-stu-id="055e8-130">The address of the CLR function that caused the fatal error, the ID of the thread where the error occurred, and the error code.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="055e8-131">Configuration</span><span class="sxs-lookup"><span data-stu-id="055e8-131">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <fatalExecutionEngineError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="055e8-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="055e8-132">See also</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>
- <xref:System.Runtime.ConstrainedExecution.Cer>
- [<span data-ttu-id="055e8-133">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="055e8-133">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
