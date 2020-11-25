---
title: ICorDebugStepper 接口
ms.date: 03/30/2017
api_name:
- ICorDebugStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper
helpviewer_keywords:
- ICorDebugStepper interface [.NET Framework debugging]
ms.assetid: ed8364eb-f01b-46f6-b5e3-5dda9cae2dfe
topic_type:
- apiref
ms.openlocfilehash: 8b5bbb65034e5b715532397c9ecc650da9aee912
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718288"
---
# <a name="icordebugstepper-interface"></a><span data-ttu-id="e1527-102">ICorDebugStepper 接口</span><span class="sxs-lookup"><span data-stu-id="e1527-102">ICorDebugStepper Interface</span></span>

<span data-ttu-id="e1527-103">表示在代码执行过程中由调试器执行的一个步骤。此步骤作为命令颁发和完成之间的标识符使用，可以实现取消对某个步骤的执行。</span><span class="sxs-lookup"><span data-stu-id="e1527-103">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e1527-104">方法</span><span class="sxs-lookup"><span data-stu-id="e1527-104">Methods</span></span>  
  
|<span data-ttu-id="e1527-105">方法</span><span class="sxs-lookup"><span data-stu-id="e1527-105">Method</span></span>|<span data-ttu-id="e1527-106">说明</span><span class="sxs-lookup"><span data-stu-id="e1527-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e1527-107">Deactivate 方法</span><span class="sxs-lookup"><span data-stu-id="e1527-107">Deactivate Method</span></span>](icordebugstepper-deactivate-method.md)|<span data-ttu-id="e1527-108">使此 `ICorDebugStepper` 方法取消它收到的最后一个步骤命令。</span><span class="sxs-lookup"><span data-stu-id="e1527-108">Causes this `ICorDebugStepper` to cancel the last step command it received.</span></span>|  
|[<span data-ttu-id="e1527-109">IsActive 方法</span><span class="sxs-lookup"><span data-stu-id="e1527-109">IsActive Method</span></span>](icordebugstepper-isactive-method.md)|<span data-ttu-id="e1527-110">获取一个值，该值指示此是否 `ICorDebugStepper` 当前正在执行步骤。</span><span class="sxs-lookup"><span data-stu-id="e1527-110">Gets a value that indicates whether this `ICorDebugStepper` is currently executing a step.</span></span>|  
|[<span data-ttu-id="e1527-111">SetInterceptMask 方法</span><span class="sxs-lookup"><span data-stu-id="e1527-111">SetInterceptMask Method</span></span>](icordebugstepper-setinterceptmask-method.md)|<span data-ttu-id="e1527-112">设置一个 CorDebugIntercept 值，该值指定要单步执行的代码的类型。</span><span class="sxs-lookup"><span data-stu-id="e1527-112">Sets a CorDebugIntercept value that specifies the types of code that are stepped into.</span></span>|  
|[<span data-ttu-id="e1527-113">SetRangeIL 方法</span><span class="sxs-lookup"><span data-stu-id="e1527-113">SetRangeIL Method</span></span>](icordebugstepper-setrangeil-method.md)|<span data-ttu-id="e1527-114">设置一个值，该值指示对 [ICorDebugStepper：： StepRange](icordebugstepper-steprange-method.md) 的调用是传递与本机代码相关的参数值，还是传递给 Microsoft 中间语言 (MSIL) 正在逐步执行的方法的代码。</span><span class="sxs-lookup"><span data-stu-id="e1527-114">Sets a value that indicates whether calls to [ICorDebugStepper::StepRange](icordebugstepper-steprange-method.md) pass argument values relative to the native code or to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>|  
|[<span data-ttu-id="e1527-115">SetUnmappedStopMask 方法</span><span class="sxs-lookup"><span data-stu-id="e1527-115">SetUnmappedStopMask Method</span></span>](icordebugstepper-setunmappedstopmask-method.md)|<span data-ttu-id="e1527-116">设置一个 CorDebugUnmappedStop 值，该值指定将在其中停止执行的未映射代码的类型。</span><span class="sxs-lookup"><span data-stu-id="e1527-116">Sets a CorDebugUnmappedStop value that specifies the type of unmapped code in which execution will halt.</span></span>|  
|[<span data-ttu-id="e1527-117">Step 方法</span><span class="sxs-lookup"><span data-stu-id="e1527-117">Step Method</span></span>](icordebugstepper-step-method.md)|<span data-ttu-id="e1527-118">使此 `ICorDebugStepper` 单步执行其包含线程，并根据需要继续单步执行线程中调用的函数。</span><span class="sxs-lookup"><span data-stu-id="e1527-118">Causes this `ICorDebugStepper` to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>|  
|[<span data-ttu-id="e1527-119">StepOut 方法</span><span class="sxs-lookup"><span data-stu-id="e1527-119">StepOut Method</span></span>](icordebugstepper-stepout-method.md)|<span data-ttu-id="e1527-120">使此在 `ICorDebugStepper` 其包含线程中单步执行，并在当前帧将控件返回到调用帧时完成。</span><span class="sxs-lookup"><span data-stu-id="e1527-120">Causes this `ICorDebugStepper` to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>|  
|[<span data-ttu-id="e1527-121">StepRange 方法</span><span class="sxs-lookup"><span data-stu-id="e1527-121">StepRange Method</span></span>](icordebugstepper-steprange-method.md)|<span data-ttu-id="e1527-122">使此操作在 `ICorDebugStepper` 其包含线程中单步执行，并在到达指定范围最后一个以上的代码时返回。</span><span class="sxs-lookup"><span data-stu-id="e1527-122">Causes this `ICorDebugStepper` to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1527-123">注解</span><span class="sxs-lookup"><span data-stu-id="e1527-123">Remarks</span></span>  

 <span data-ttu-id="e1527-124">`ICorDebugStepper`接口具有以下用途：</span><span class="sxs-lookup"><span data-stu-id="e1527-124">The `ICorDebugStepper` interface serves the following purposes:</span></span>  
  
- <span data-ttu-id="e1527-125">它充当发出的步骤命令与完成该命令之间的标识符。</span><span class="sxs-lookup"><span data-stu-id="e1527-125">It acts as an identifier between a step command that is issued and the completion of that command.</span></span>  
  
- <span data-ttu-id="e1527-126">它提供一个中心接口，用于封装可执行的所有单步执行。</span><span class="sxs-lookup"><span data-stu-id="e1527-126">It provides a central interface to encapsulate all the stepping that can be performed.</span></span>  
  
- <span data-ttu-id="e1527-127">它提供了一种提前取消单步执行操作的方法。</span><span class="sxs-lookup"><span data-stu-id="e1527-127">It provides a way to prematurely cancel a stepping operation.</span></span>  
  
 <span data-ttu-id="e1527-128">每个线程可以有多个分档器。</span><span class="sxs-lookup"><span data-stu-id="e1527-128">There can be more than one stepper per thread.</span></span> <span data-ttu-id="e1527-129">例如，在单步执行某个函数时可能会命中断点，用户可能希望在该函数中启动新的单步执行操作。</span><span class="sxs-lookup"><span data-stu-id="e1527-129">For example, a breakpoint may be hit while stepping over a function, and the user may wish to start a new stepping operation inside that function.</span></span> <span data-ttu-id="e1527-130">调试器负责确定如何处理这种情况。</span><span class="sxs-lookup"><span data-stu-id="e1527-130">It is up to the debugger to determine how to handle this situation.</span></span> <span data-ttu-id="e1527-131">调试器可能需要取消原始单步执行操作或嵌套两个操作。</span><span class="sxs-lookup"><span data-stu-id="e1527-131">The debugger may want to cancel the original stepping operation or nest the two operations.</span></span> <span data-ttu-id="e1527-132">`ICorDebugStepper`接口支持这两种选择。</span><span class="sxs-lookup"><span data-stu-id="e1527-132">The `ICorDebugStepper` interface supports both choices.</span></span>  
  
 <span data-ttu-id="e1527-133">如果公共语言运行时 (CLR) 进行跨线程的已封送调用，则分档器可以在线程之间迁移。</span><span class="sxs-lookup"><span data-stu-id="e1527-133">A stepper may migrate between threads if the common language runtime (CLR) makes a cross-threaded, marshaled call.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e1527-134">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="e1527-134">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1527-135">要求</span><span class="sxs-lookup"><span data-stu-id="e1527-135">Requirements</span></span>  

 <span data-ttu-id="e1527-136">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e1527-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1527-137">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1527-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1527-138">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1527-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1527-139">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1527-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1527-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e1527-140">See also</span></span>

- [<span data-ttu-id="e1527-141">调试接口</span><span class="sxs-lookup"><span data-stu-id="e1527-141">Debugging Interfaces</span></span>](debugging-interfaces.md)
