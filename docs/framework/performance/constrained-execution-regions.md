---
title: 受约束的执行区域
description: 开始使用受约束的执行区域 (CER) ，这是用于创作可靠托管代码的机制的一部分。
ms.date: 03/30/2017
helpviewer_keywords:
- constrained execution regions
- CERs
ms.assetid: 99354547-39c1-4b0b-8553-938e8f8d1808
ms.openlocfilehash: 5014885e186b1fff16543c09d5652958f2463e3d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266852"
---
# <a name="constrained-execution-regions"></a><span data-ttu-id="632da-103">受约束的执行区域</span><span class="sxs-lookup"><span data-stu-id="632da-103">Constrained Execution Regions</span></span>

<span data-ttu-id="632da-104">受约束的执行区域 (CER) 是创建可靠托管代码机制的一部分。</span><span class="sxs-lookup"><span data-stu-id="632da-104">A constrained execution region (CER) is part of a mechanism for authoring reliable managed code.</span></span> <span data-ttu-id="632da-105">CER 定义一个区域，该区域内公共语言运行时 (CLR) 会受到约束，不能引发阻止该区域内代码完全执行的带外异常。</span><span class="sxs-lookup"><span data-stu-id="632da-105">A CER defines an area in which the common language runtime (CLR) is constrained from throwing out-of-band exceptions that would prevent the code in the area from executing in its entirety.</span></span> <span data-ttu-id="632da-106">在该区域中，用户代码受到约束，不能执行会导致引发带外异常的代码。</span><span class="sxs-lookup"><span data-stu-id="632da-106">Within that region, user code is constrained from executing code that would result in the throwing of out-of-band exceptions.</span></span> <span data-ttu-id="632da-107"><xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> 方法应该立即先于 `try` 块执行并将 `catch`、`finally`、`fault` 块标记为受约束的执行区域。</span><span class="sxs-lookup"><span data-stu-id="632da-107">The <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> method must immediately precede a `try` block and marks `catch`, `finally`, and `fault` blocks as constrained execution regions.</span></span> <span data-ttu-id="632da-108">标记为受约束的区域后，代码只能调用其他具有强可靠性协定的代码，并且代码不应对未准备好或不可靠的方法进行分配和虚拟调用，除非该代码已准备好处理失败。</span><span class="sxs-lookup"><span data-stu-id="632da-108">Once marked as a constrained region, code must only call other code with strong reliability contracts, and code should not allocate or make virtual calls to unprepared or unreliable methods unless the code is prepared to handle failures.</span></span> <span data-ttu-id="632da-109">CLR 会为 CER 中正在执行的代码延迟线程中止。</span><span class="sxs-lookup"><span data-stu-id="632da-109">The CLR delays thread aborts for code that is executing in a CER.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="632da-110">仅 .NET Framework 支持 CER。</span><span class="sxs-lookup"><span data-stu-id="632da-110">CER is only supported in .NET Framework.</span></span> <span data-ttu-id="632da-111">本文不适用于 .NET Core 或 .NET 5 及更高版本。</span><span class="sxs-lookup"><span data-stu-id="632da-111">This article doesn't apply to .NET Core or .NET 5 and above.</span></span>

 <span data-ttu-id="632da-112">除已批注的 `try` 块外，受约束的执行区域还以其他形式用于 CLR 中，特别是在 <xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject> 类派生的类中执行关键终结器和使用 <xref:System.Runtime.CompilerServices.RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup%2A> 方法执行的代码。</span><span class="sxs-lookup"><span data-stu-id="632da-112">Constrained execution regions are used in different forms in the CLR in addition to an annotated `try` block, notably critical finalizers executing in classes derived from the <xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject> class and code executed using the <xref:System.Runtime.CompilerServices.RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup%2A> method.</span></span>  
  
## <a name="cer-advance-preparation"></a><span data-ttu-id="632da-113">CER 事先准备</span><span class="sxs-lookup"><span data-stu-id="632da-113">CER Advance Preparation</span></span>  

 <span data-ttu-id="632da-114">CLR 事先准备 CER 以避免出现内存不足的情况。</span><span class="sxs-lookup"><span data-stu-id="632da-114">The CLR prepares CERs in advance to avoid out-of-memory conditions.</span></span> <span data-ttu-id="632da-115">需事先准备，防止 CLR 在实时编译或类型加载时发生内存不足的情况。</span><span class="sxs-lookup"><span data-stu-id="632da-115">Advance preparation is required so the CLR does not cause an out of memory condition during just-in-time compilation or type loading.</span></span>  
  
 <span data-ttu-id="632da-116">开发者需要指定一个代码区域作为 CER：</span><span class="sxs-lookup"><span data-stu-id="632da-116">The developer is required to indicate that a code region is a CER:</span></span>  
  
- <span data-ttu-id="632da-117">事先已准备好顶级 CER 区域和完整调用关系图中应用了 <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> 属性的方法。</span><span class="sxs-lookup"><span data-stu-id="632da-117">The top level CER region and methods in the full call graph that have the <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> attribute applied are prepared in advance.</span></span> <span data-ttu-id="632da-118"><xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> 只能保证 <xref:System.Runtime.ConstrainedExecution.Cer.Success> 或 <xref:System.Runtime.ConstrainedExecution.Cer.MayFail> 状态。</span><span class="sxs-lookup"><span data-stu-id="632da-118">The <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> can only state guarantees of <xref:System.Runtime.ConstrainedExecution.Cer.Success> or <xref:System.Runtime.ConstrainedExecution.Cer.MayFail>.</span></span>  
  
- <span data-ttu-id="632da-119">不能对无法静态确定的调用（如虚拟调度）执行事先准备。</span><span class="sxs-lookup"><span data-stu-id="632da-119">Advance preparation cannot be performed for calls that cannot be statically determined, such as virtual dispatch.</span></span> <span data-ttu-id="632da-120">请在这些情况中使用 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="632da-120">Use the <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A> method in these cases.</span></span> <span data-ttu-id="632da-121">使用 <xref:System.Runtime.CompilerServices.RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup%2A> 方法时，应对清理代码应用 <xref:System.Runtime.ConstrainedExecution.PrePrepareMethodAttribute> 属性。</span><span class="sxs-lookup"><span data-stu-id="632da-121">When using the <xref:System.Runtime.CompilerServices.RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup%2A> method, the <xref:System.Runtime.ConstrainedExecution.PrePrepareMethodAttribute> attribute should be applied to the clean up code.</span></span>  
  
## <a name="constraints"></a><span data-ttu-id="632da-122">约束</span><span class="sxs-lookup"><span data-stu-id="632da-122">Constraints</span></span>  

 <span data-ttu-id="632da-123">用户可写入 CER 的代码类型受限。</span><span class="sxs-lookup"><span data-stu-id="632da-123">Users are constrained in the type of code they can write in a CER.</span></span> <span data-ttu-id="632da-124">代码无法导致带外异常，可能是以下操作引起的：</span><span class="sxs-lookup"><span data-stu-id="632da-124">The code cannot cause an out-of-band exception, such as might result from the following operations:</span></span>  
  
- <span data-ttu-id="632da-125">显式分配。</span><span class="sxs-lookup"><span data-stu-id="632da-125">Explicit allocation.</span></span>  
  
- <span data-ttu-id="632da-126">装箱。</span><span class="sxs-lookup"><span data-stu-id="632da-126">Boxing.</span></span>  
  
- <span data-ttu-id="632da-127">获取锁。</span><span class="sxs-lookup"><span data-stu-id="632da-127">Acquiring a lock.</span></span>  
  
- <span data-ttu-id="632da-128">虚拟调用未准备好的方法。</span><span class="sxs-lookup"><span data-stu-id="632da-128">Calling unprepared methods virtually.</span></span>  
  
- <span data-ttu-id="632da-129">调用弱可靠性协定或不存在可靠性协定的方法。</span><span class="sxs-lookup"><span data-stu-id="632da-129">Calling methods with a weak or nonexistent reliability contract.</span></span>  
  
 <span data-ttu-id="632da-130">在.NET Framework version 2.0 版中，这些约束称为准则。</span><span class="sxs-lookup"><span data-stu-id="632da-130">In the .NET Framework version 2.0, these constraints are guidelines.</span></span> <span data-ttu-id="632da-131">通过代码分析工具提供诊断。</span><span class="sxs-lookup"><span data-stu-id="632da-131">Diagnostics are provided through code analysis tools.</span></span>  
  
## <a name="reliability-contracts"></a><span data-ttu-id="632da-132">可靠性协定</span><span class="sxs-lookup"><span data-stu-id="632da-132">Reliability Contracts</span></span>  

 <span data-ttu-id="632da-133"><xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> 是记录给定方法的可靠性保证和损坏状态的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="632da-133">The <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> is a custom attribute that documents the reliability guarantees and the corruption state of a given method.</span></span>  
  
### <a name="reliability-guarantees"></a><span data-ttu-id="632da-134">可靠性保证</span><span class="sxs-lookup"><span data-stu-id="632da-134">Reliability Guarantees</span></span>  

 <span data-ttu-id="632da-135">可靠性保证由 <xref:System.Runtime.ConstrainedExecution.Cer> 枚举值表示，指示给定方法的可靠程度：</span><span class="sxs-lookup"><span data-stu-id="632da-135">Reliability guarantees, represented by <xref:System.Runtime.ConstrainedExecution.Cer> enumeration values, indicate the degree of reliability of a given method:</span></span>  
  
- <span data-ttu-id="632da-136"><xref:System.Runtime.ConstrainedExecution.Cer.MayFail>.</span><span class="sxs-lookup"><span data-stu-id="632da-136"><xref:System.Runtime.ConstrainedExecution.Cer.MayFail>.</span></span> <span data-ttu-id="632da-137">异常情况下，方法可能会失败。</span><span class="sxs-lookup"><span data-stu-id="632da-137">Under exceptional conditions, the method might fail.</span></span> <span data-ttu-id="632da-138">在这种情况下，方法会向调用方法报告是成功还是失败。</span><span class="sxs-lookup"><span data-stu-id="632da-138">In this case, the method reports back to the calling method whether it succeeded or failed.</span></span> <span data-ttu-id="632da-139">方法必须包含在 CER 中，以确保它可以报告返回值。</span><span class="sxs-lookup"><span data-stu-id="632da-139">The method must be contained in a CER to ensure that it can report the return value.</span></span>  
  
- <span data-ttu-id="632da-140"><xref:System.Runtime.ConstrainedExecution.Cer.None>.</span><span class="sxs-lookup"><span data-stu-id="632da-140"><xref:System.Runtime.ConstrainedExecution.Cer.None>.</span></span> <span data-ttu-id="632da-141">方法、类型和程序集没有 CER 的概念，如果状态损坏没有得到实质性的缓解，在 CER 内进行调用很可能是不安全的。</span><span class="sxs-lookup"><span data-stu-id="632da-141">The method, type, or assembly has no concept of a CER and is most likely not safe to call within a CER without substantial mitigation from state corruption.</span></span> <span data-ttu-id="632da-142">它不利用 CER 保证。</span><span class="sxs-lookup"><span data-stu-id="632da-142">It does not take advantage of CER guarantees.</span></span> <span data-ttu-id="632da-143">这意味着：</span><span class="sxs-lookup"><span data-stu-id="632da-143">This implies the following:</span></span>  
  
    1. <span data-ttu-id="632da-144">异常情况下，方法可能会失败。</span><span class="sxs-lookup"><span data-stu-id="632da-144">Under exceptional conditions the method might fail.</span></span>  
  
    2. <span data-ttu-id="632da-145">方法可能报告失败，也可能不报告失败。</span><span class="sxs-lookup"><span data-stu-id="632da-145">The method might or might not report that it failed.</span></span>  
  
    3. <span data-ttu-id="632da-146">最可能的方案是，未将方法编写为使用 CER。</span><span class="sxs-lookup"><span data-stu-id="632da-146">The method is not written to use a CER, the most likely scenario.</span></span>  
  
    4. <span data-ttu-id="632da-147">如果方法、类型和程序集没有显示标识为成功，则会隐式标识为 <xref:System.Runtime.ConstrainedExecution.Cer.None>。</span><span class="sxs-lookup"><span data-stu-id="632da-147">If a method, type, or assembly is not explicitly identified to succeed, it is implicitly identified as <xref:System.Runtime.ConstrainedExecution.Cer.None>.</span></span>  
  
- <span data-ttu-id="632da-148"><xref:System.Runtime.ConstrainedExecution.Cer.Success>.</span><span class="sxs-lookup"><span data-stu-id="632da-148"><xref:System.Runtime.ConstrainedExecution.Cer.Success>.</span></span> <span data-ttu-id="632da-149">异常情况下，保证方法一定成功。</span><span class="sxs-lookup"><span data-stu-id="632da-149">Under exceptional conditions, the method is guaranteed to succeed.</span></span> <span data-ttu-id="632da-150">若要达到这种级别的可靠性，应始终在调用的方法周围构造 CER，即使方法是从非 CER 区域调用的。</span><span class="sxs-lookup"><span data-stu-id="632da-150">To achieve this level of reliability you should always construct a CER around the method that is called, even when it is called from within a non-CER region.</span></span> <span data-ttu-id="632da-151">如果方法完成了预期任务，它就是成功的，虽然这种成功可能只是主观意义上的成功。</span><span class="sxs-lookup"><span data-stu-id="632da-151">A method is successful if it accomplishes what is intended, although success can be viewed subjectively.</span></span> <span data-ttu-id="632da-152">例如，用 `ReliabilityContractAttribute(Cer.Success)` 标记计数意味着当它在 CER 下运行时，它始终返回 <xref:System.Collections.ArrayList> 中的元素的数目计数，并且它永远不能将内部的字段保留为不确定状态。</span><span class="sxs-lookup"><span data-stu-id="632da-152">For example, marking Count with `ReliabilityContractAttribute(Cer.Success)` implies that when it is run under a CER, it always returns a count of the number of elements in the <xref:System.Collections.ArrayList> and it can never leave the internal fields in an undetermined state.</span></span>  <span data-ttu-id="632da-153">但是，<xref:System.Threading.Interlocked.CompareExchange%2A> 方法也标记为成功，此处的成功意味着该值不会因争用条件而替换为新值。</span><span class="sxs-lookup"><span data-stu-id="632da-153">However, the <xref:System.Threading.Interlocked.CompareExchange%2A> method is marked as success as well, with the understanding that success may mean the value could not be replaced with a new value due to a race condition.</span></span>  <span data-ttu-id="632da-154">关键在于方法的行为方式与记录的行为方式相同，不需要编写 CER 代码来预期正确但不可靠的代码行为之外的任何异常行为。</span><span class="sxs-lookup"><span data-stu-id="632da-154">The key point is that the method behaves in the way it is documented to behave, and CER code does not need to be written to expect any unusual behavior beyond what correct but unreliable code would look like.</span></span>  
  
### <a name="corruption-levels"></a><span data-ttu-id="632da-155">损坏级别</span><span class="sxs-lookup"><span data-stu-id="632da-155">Corruption levels</span></span>  

 <span data-ttu-id="632da-156">损坏级别由 <xref:System.Runtime.ConstrainedExecution.Consistency> 枚举值表示，指示给定坏境中状态的损坏程度：</span><span class="sxs-lookup"><span data-stu-id="632da-156">Corruption levels, represented by <xref:System.Runtime.ConstrainedExecution.Consistency> enumeration values, indicate how much state may be corrupted in a given environment:</span></span>  
  
- <span data-ttu-id="632da-157"><xref:System.Runtime.ConstrainedExecution.Consistency.MayCorruptAppDomain>.</span><span class="sxs-lookup"><span data-stu-id="632da-157"><xref:System.Runtime.ConstrainedExecution.Consistency.MayCorruptAppDomain>.</span></span> <span data-ttu-id="632da-158">异常情况下，公共语言运行时 (CLR) 对当前应用改程序域中的状态一致性不做任何保证。</span><span class="sxs-lookup"><span data-stu-id="632da-158">Under exceptional conditions, the common language runtime (CLR) makes no guarantees regarding state consistency in the current application domain.</span></span>  
  
- <span data-ttu-id="632da-159"><xref:System.Runtime.ConstrainedExecution.Consistency.MayCorruptInstance>.</span><span class="sxs-lookup"><span data-stu-id="632da-159"><xref:System.Runtime.ConstrainedExecution.Consistency.MayCorruptInstance>.</span></span> <span data-ttu-id="632da-160">异常情况下，方法保证将状态损坏限制为当前实例。</span><span class="sxs-lookup"><span data-stu-id="632da-160">Under exceptional conditions, the method is guaranteed to limit state corruption to the current instance.</span></span>  
  
- <span data-ttu-id="632da-161"><xref:System.Runtime.ConstrainedExecution.Consistency.MayCorruptProcess>，异常情况下，CLR 对状态一致性不做任何保证；即这种情况可能会损坏进程。</span><span class="sxs-lookup"><span data-stu-id="632da-161"><xref:System.Runtime.ConstrainedExecution.Consistency.MayCorruptProcess>, Under exceptional conditions, the CLR makes no guarantees regarding state consistency; that is, the condition might corrupt the process.</span></span>  
  
- <span data-ttu-id="632da-162"><xref:System.Runtime.ConstrainedExecution.Consistency.WillNotCorruptState>.</span><span class="sxs-lookup"><span data-stu-id="632da-162"><xref:System.Runtime.ConstrainedExecution.Consistency.WillNotCorruptState>.</span></span> <span data-ttu-id="632da-163">异常情况下，方法保证不损坏状态。</span><span class="sxs-lookup"><span data-stu-id="632da-163">Under exceptional conditions, the method is guaranteed not to corrupt state.</span></span>  
  
## <a name="reliability-trycatchfinally"></a><span data-ttu-id="632da-164">可靠性 try/catch/finally</span><span class="sxs-lookup"><span data-stu-id="632da-164">Reliability try/catch/finally</span></span>  

 <span data-ttu-id="632da-165">可靠性 `try/catch/finally` 是一种异常处理机制，其预知性保证的级别与非托管版本相同。</span><span class="sxs-lookup"><span data-stu-id="632da-165">The reliability `try/catch/finally` is an exception handling mechanism with the same level of predictability guarantees as the unmanaged version.</span></span> <span data-ttu-id="632da-166">`catch/finally` 块为 CER。</span><span class="sxs-lookup"><span data-stu-id="632da-166">The `catch/finally` block is the CER.</span></span> <span data-ttu-id="632da-167">块中的方法需要事先准备，并且必需是不可中断的。</span><span class="sxs-lookup"><span data-stu-id="632da-167">Methods in the block require advance preparation and must be noninterruptible.</span></span>  
  
 <span data-ttu-id="632da-168">在 .NET Framework 2.0 版中，代码通过在 try 块之前直接调用 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> 来通知运行时 try 是可靠的。</span><span class="sxs-lookup"><span data-stu-id="632da-168">In the .NET Framework version 2.0, code informs the runtime that a try is reliable by calling <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> immediately preceding a try block.</span></span> <span data-ttu-id="632da-169"><xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> 是编译器支持类 <xref:System.Runtime.CompilerServices.RuntimeHelpers> 的成员。</span><span class="sxs-lookup"><span data-stu-id="632da-169"><xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> is a member of <xref:System.Runtime.CompilerServices.RuntimeHelpers>, a compiler support class.</span></span> <span data-ttu-id="632da-170">通过使用编译器暂停可用性，直接调用 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>。</span><span class="sxs-lookup"><span data-stu-id="632da-170">Call <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> directly pending its availability through compilers.</span></span>  
  
## <a name="noninterruptible-regions"></a><span data-ttu-id="632da-171">不可中断区域</span><span class="sxs-lookup"><span data-stu-id="632da-171">Noninterruptible Regions</span></span>  

 <span data-ttu-id="632da-172">不可中断区域将一组指令分组到 CER。</span><span class="sxs-lookup"><span data-stu-id="632da-172">A noninterruptible region groups a set of instructions into a CER.</span></span>  
  
 <span data-ttu-id="632da-173">在 .NET Framework 2.0 版中，通过使用编译器支持暂停可用性，用户代码创建不可中断的区域，其中具有包含前面是 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> 方法调用的空 try/catch 块的可靠 try/catch/finally。</span><span class="sxs-lookup"><span data-stu-id="632da-173">In .NET Framework version 2.0, pending availability through compiler support, user code creates non-interruptible regions with a reliable try/catch/finally that contains an empty try/catch block preceded by a <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> method call.</span></span>  
  
## <a name="critical-finalizer-object"></a><span data-ttu-id="632da-174">关键终结器对象</span><span class="sxs-lookup"><span data-stu-id="632da-174">Critical Finalizer Object</span></span>  

 <span data-ttu-id="632da-175"><xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject> 保证垃圾回收会执行终结器。</span><span class="sxs-lookup"><span data-stu-id="632da-175">A <xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject> guarantees that garbage collection will execute the finalizer.</span></span> <span data-ttu-id="632da-176">进行分配时，应事先准备好终结器及其调用关系图。</span><span class="sxs-lookup"><span data-stu-id="632da-176">Upon allocation, the finalizer and its call graph are prepared in advance.</span></span> <span data-ttu-id="632da-177">终结器方法在 CER 中执行，并且必须遵从所有关于 CER 和终结器的约束。</span><span class="sxs-lookup"><span data-stu-id="632da-177">The finalizer method executes in a CER, and must obey all the constraints on CERs and finalizers.</span></span>  
  
 <span data-ttu-id="632da-178">从 <xref:System.Runtime.InteropServices.SafeHandle> 和 <xref:System.Runtime.InteropServices.CriticalHandle> 继承的任何类型都保证在 CER 内执行其终结器。</span><span class="sxs-lookup"><span data-stu-id="632da-178">Any types inheriting from <xref:System.Runtime.InteropServices.SafeHandle> and <xref:System.Runtime.InteropServices.CriticalHandle> are guaranteed to have their finalizer execute within a CER.</span></span> <span data-ttu-id="632da-179">在 <xref:System.Runtime.InteropServices.SafeHandle> 派生的类中实现 <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> 以执行释放图柄所需的任何代码。</span><span class="sxs-lookup"><span data-stu-id="632da-179">Implement <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> in <xref:System.Runtime.InteropServices.SafeHandle> derived classes to execute any code that is required to free the handle.</span></span>  
  
## <a name="code-not-permitted-in-cers"></a><span data-ttu-id="632da-180">CER 中不允许的代码</span><span class="sxs-lookup"><span data-stu-id="632da-180">Code Not Permitted in CERs</span></span>  

 <span data-ttu-id="632da-181">CER 中不允许以下操作：</span><span class="sxs-lookup"><span data-stu-id="632da-181">The following operations are not permitted in CERs:</span></span>  
  
- <span data-ttu-id="632da-182">显示分配。</span><span class="sxs-lookup"><span data-stu-id="632da-182">Explicit allocations.</span></span>  
  
- <span data-ttu-id="632da-183">获取锁。</span><span class="sxs-lookup"><span data-stu-id="632da-183">Acquiring a lock.</span></span>  
  
- <span data-ttu-id="632da-184">装箱。</span><span class="sxs-lookup"><span data-stu-id="632da-184">Boxing.</span></span>  
  
- <span data-ttu-id="632da-185">多维数组访问。</span><span class="sxs-lookup"><span data-stu-id="632da-185">Multidimensional array access.</span></span>  
  
- <span data-ttu-id="632da-186">通过反射进行的方法调用。</span><span class="sxs-lookup"><span data-stu-id="632da-186">Method calls through reflection.</span></span>  
  
- <span data-ttu-id="632da-187"><xref:System.Threading.Monitor.Enter%2A> 或 <xref:System.IO.FileStream.Lock%2A>。</span><span class="sxs-lookup"><span data-stu-id="632da-187"><xref:System.Threading.Monitor.Enter%2A> or <xref:System.IO.FileStream.Lock%2A>.</span></span>  
  
- <span data-ttu-id="632da-188">安全检查。</span><span class="sxs-lookup"><span data-stu-id="632da-188">Security checks.</span></span> <span data-ttu-id="632da-189">不执行请求，仅链接请求。</span><span class="sxs-lookup"><span data-stu-id="632da-189">Do not perform demands, only link demands.</span></span>  
  
- <span data-ttu-id="632da-190">COM 对象和代理的 <xref:System.Reflection.Emit.OpCodes.Isinst> 和 <xref:System.Reflection.Emit.OpCodes.Castclass></span><span class="sxs-lookup"><span data-stu-id="632da-190"><xref:System.Reflection.Emit.OpCodes.Isinst> and <xref:System.Reflection.Emit.OpCodes.Castclass> for COM objects and proxies</span></span>  
  
- <span data-ttu-id="632da-191">获取或设置透明代理上的字段。</span><span class="sxs-lookup"><span data-stu-id="632da-191">Getting or setting fields on a transparent proxy.</span></span>  
  
- <span data-ttu-id="632da-192">序列化。</span><span class="sxs-lookup"><span data-stu-id="632da-192">Serialization.</span></span>  
  
- <span data-ttu-id="632da-193">函数函数指针和委托。</span><span class="sxs-lookup"><span data-stu-id="632da-193">Function pointers and delegates.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="632da-194">另请参阅</span><span class="sxs-lookup"><span data-stu-id="632da-194">See also</span></span>

- [<span data-ttu-id="632da-195">可靠性最佳做法</span><span class="sxs-lookup"><span data-stu-id="632da-195">Reliability Best Practices</span></span>](reliability-best-practices.md)
