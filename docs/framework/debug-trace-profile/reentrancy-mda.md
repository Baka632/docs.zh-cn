---
title: 重入 MDA
description: 查看可在对象堆损坏或从本机到托管代码进行转换时发生的其他严重错误时激活的重入 MDA。
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged code, debugging
- transitioning threads unmanaged to managed code
- reentrancy MDA
- reentrancy without an orderly transition
- managed debugging assistants (MDAs), reentrancy
- illegal reentrancy
- MDAs (managed debugging assistants), reentrancy
- threading [.NET Framework], managed debugging assistants
- managed code, debugging
- native debugging, MDAs
ms.assetid: 7240c3f3-7df8-4b03-bbf1-17cdce142d45
ms.openlocfilehash: 0480b1a5aafbc8c4f9645ba83383d3a222d1f1c5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96264577"
---
# <a name="reentrancy-mda"></a><span data-ttu-id="bc624-103">重入 MDA</span><span class="sxs-lookup"><span data-stu-id="bc624-103">reentrancy MDA</span></span>

<span data-ttu-id="bc624-104">先前未通过有序转换执行从托管代码到本机代码的转换的情况下，如果尝试执行从本机代码到托管代码的转换，会激活 `reentrancy` 托管调试助手 (MDA)。</span><span class="sxs-lookup"><span data-stu-id="bc624-104">The `reentrancy` managed debugging assistant (MDA) is activated when an attempt is made to transition from native to managed code in cases where a prior switch from managed to native code was not performed through an orderly transition.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="bc624-105">症状</span><span class="sxs-lookup"><span data-stu-id="bc624-105">Symptoms</span></span>  

 <span data-ttu-id="bc624-106">从本机转换到托管代码时，对象堆已损坏或发生其他严重错误。</span><span class="sxs-lookup"><span data-stu-id="bc624-106">The object heap is corrupted or other serious errors are occurring when transitioning from native to managed code.</span></span>  
  
 <span data-ttu-id="bc624-107">沿任一方向在本机代码和托管代码之间进行切换的线程必须执行有序转换。</span><span class="sxs-lookup"><span data-stu-id="bc624-107">Threads that switch between native and managed code in either direction must perform an orderly transition.</span></span> <span data-ttu-id="bc624-108">但是，操作系统中的某些底层扩展性点（例如向量异常处理程序）可从托管代码切换到本机代码而无需执行有序转换。</span><span class="sxs-lookup"><span data-stu-id="bc624-108">However, certain low-level extensibility points in the operating system, such as the vectored exception handler, allow switches from managed to native code without performing an orderly transition.</span></span>  <span data-ttu-id="bc624-109">这些转换由操作系统控制，而不是公共语言运行时 (CLR) 控制。</span><span class="sxs-lookup"><span data-stu-id="bc624-109">These switches are under operating system control, rather than under common language runtime (CLR) control.</span></span>  <span data-ttu-id="bc624-110">在这些扩展性点内执行的任何本机代码都必须避免回调入托管代码。</span><span class="sxs-lookup"><span data-stu-id="bc624-110">Any native code that executes inside these extensibility points must avoid calling back into managed code.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="bc624-111">原因</span><span class="sxs-lookup"><span data-stu-id="bc624-111">Cause</span></span>  

 <span data-ttu-id="bc624-112">执行托管代码时激活了某个底层操作系统扩展性点，例如向量异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="bc624-112">A low-level operating system extensibility point, such as the vectored exception handler, has activated while executing managed code.</span></span>  <span data-ttu-id="bc624-113">通过该扩展性点调用的应用程序代码正在尝试回调入托管代码。</span><span class="sxs-lookup"><span data-stu-id="bc624-113">The application code that is invoked through that extensibility point is attempting to call back into managed code.</span></span>  
  
 <span data-ttu-id="bc624-114">此问题通常是由应用程序代码引起的。</span><span class="sxs-lookup"><span data-stu-id="bc624-114">This problem is always caused by application code.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="bc624-115">解决方法</span><span class="sxs-lookup"><span data-stu-id="bc624-115">Resolution</span></span>  

 <span data-ttu-id="bc624-116">检查堆栈跟踪，确定激活此 MDA 的线程。</span><span class="sxs-lookup"><span data-stu-id="bc624-116">Examine the stack trace for the thread that has activated this MDA.</span></span>  <span data-ttu-id="bc624-117">线程正在尝试非法调入托管代码。</span><span class="sxs-lookup"><span data-stu-id="bc624-117">The thread is attempting to illegally call into managed code.</span></span>  <span data-ttu-id="bc624-118">堆栈跟踪应该展示使用此扩展性点的应用程序代码、提供此扩展性点的操作系统代码和此扩展性点中断的托管代码。</span><span class="sxs-lookup"><span data-stu-id="bc624-118">The stack trace should reveal the application code using this extensibility point, the operating system code that provides this extensibility point, and the managed code that was interrupted by the extensibility point.</span></span>  
  
 <span data-ttu-id="bc624-119">例如，尝试从矢量异常处理程序中调用托管代码时会看到 MDA 激活。</span><span class="sxs-lookup"><span data-stu-id="bc624-119">For example, you will see the MDA activated in an attempt to call managed code from inside a vectored exception handler.</span></span>  <span data-ttu-id="bc624-120">堆栈上会看到操作系统异常处理代码和某些触发 <xref:System.DivideByZeroException> 或 <xref:System.AccessViolationException> 等异常的托管代码。</span><span class="sxs-lookup"><span data-stu-id="bc624-120">On the stack you will see the operating system exception handling code and some managed code triggering an exception such as a <xref:System.DivideByZeroException> or an <xref:System.AccessViolationException>.</span></span>  
  
 <span data-ttu-id="bc624-121">在此示例中，正确的解决方法是完全以非托管代码实现向量异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="bc624-121">In this example, the correct resolution is to implement the vectored exception handler completely in unmanaged code.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="bc624-122">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="bc624-122">Effect on the Runtime</span></span>  

 <span data-ttu-id="bc624-123">此 MDA 对 CLR 无任何影响。</span><span class="sxs-lookup"><span data-stu-id="bc624-123">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="bc624-124">输出</span><span class="sxs-lookup"><span data-stu-id="bc624-124">Output</span></span>  

 <span data-ttu-id="bc624-125">MDA 报告正在尝试非法重入。</span><span class="sxs-lookup"><span data-stu-id="bc624-125">The MDA reports that illegal reentrancy is being attempted.</span></span>  <span data-ttu-id="bc624-126">检查线程的堆栈以确定发生原因和如何更正此问题。</span><span class="sxs-lookup"><span data-stu-id="bc624-126">Examine the thread's stack to determine why this is happening and how to correct the problem.</span></span> <span data-ttu-id="bc624-127">下面是示例输出。</span><span class="sxs-lookup"><span data-stu-id="bc624-127">The following is sample output.</span></span>  
  
```output
Additional Information: Attempting to call into managed code without
transitioning out first.  Do not attempt to run managed code inside
low-level native extensibility points. Managed Debugging Assistant
'Reentrancy' has detected a problem in 'D:\ConsoleApplication1\  
ConsoleApplication1\bin\Debug\ConsoleApplication1.vshost.exe'.  
```  
  
## <a name="configuration"></a><span data-ttu-id="bc624-128">Configuration</span><span class="sxs-lookup"><span data-stu-id="bc624-128">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <reentrancy />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="bc624-129">示例</span><span class="sxs-lookup"><span data-stu-id="bc624-129">Example</span></span>  

 <span data-ttu-id="bc624-130">以下代码示例引发 <xref:System.AccessViolationException>。</span><span class="sxs-lookup"><span data-stu-id="bc624-130">The following code example causes an <xref:System.AccessViolationException> to be thrown.</span></span>  <span data-ttu-id="bc624-131">支持矢量异常处理的 Windows 版本中，这会调用托管向量异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="bc624-131">On versions of Windows that support vectored exception handling, this will cause the managed vectored exception handler to be called.</span></span>  <span data-ttu-id="bc624-132">如果启用 `reentrancy` MDA，MDA 将在尝试从操作系统矢量异常处理支持代码调用到 `MyHandler` 时激活。</span><span class="sxs-lookup"><span data-stu-id="bc624-132">If the `reentrancy` MDA is enabled, the MDA will activate during the attempted call to `MyHandler` from the operating system's vectored exception handling support code.</span></span>  
  
```csharp
using System;  
public delegate int ExceptionHandler(IntPtr ptrExceptionInfo);  
  
public class Reenter
{  
    public static ExceptionHandler keepAlive;  
  
    [System.Runtime.InteropServices.DllImport("kernel32", ExactSpelling=true,
        CharSet=System.Runtime.InteropServices.CharSet.Auto)]  
    public static extern IntPtr AddVectoredExceptionHandler(int bFirst,
        ExceptionHandler handler);  
  
    static int MyHandler(IntPtr ptrExceptionInfo)
    {  
        // EXCEPTION_CONTINUE_SEARCH  
        return 0;  
    }  
    void Run() {}  
  
    static void Main()
    {  
        keepAlive = new ExceptionHandler(Reenter.MyHandler);  
        IntPtr ret = AddVectoredExceptionHandler(1, keepAlive);  
        try
        {  
            // Dispatch on null should AV.  
            Reenter r = null;
            r.Run();  
        }
        catch { }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="bc624-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bc624-133">See also</span></span>

- [<span data-ttu-id="bc624-134">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="bc624-134">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
