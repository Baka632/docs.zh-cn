---
title: ICorDebugThread 接口
ms.date: 03/30/2017
api_name:
- ICorDebugThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread
helpviewer_keywords:
- ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3930fd9b-2bc3-4b72-80a0-b6eeb94d60c6
topic_type:
- apiref
ms.openlocfilehash: 5165ef081aad849c11747807d8cc76b2df0a6c74
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729312"
---
# <a name="icordebugthread-interface"></a><span data-ttu-id="87d61-102">ICorDebugThread 接口</span><span class="sxs-lookup"><span data-stu-id="87d61-102">ICorDebugThread Interface</span></span>

<span data-ttu-id="87d61-103">表示进程中的线程。</span><span class="sxs-lookup"><span data-stu-id="87d61-103">Represents a thread in a process.</span></span> <span data-ttu-id="87d61-104">`ICorDebugThread` 实例的生存期与它表示的线程的生存期相同。</span><span class="sxs-lookup"><span data-stu-id="87d61-104">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="87d61-105">方法</span><span class="sxs-lookup"><span data-stu-id="87d61-105">Methods</span></span>  
  
|<span data-ttu-id="87d61-106">方法</span><span class="sxs-lookup"><span data-stu-id="87d61-106">Method</span></span>|<span data-ttu-id="87d61-107">说明</span><span class="sxs-lookup"><span data-stu-id="87d61-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="87d61-108">ClearCurrentException 方法</span><span class="sxs-lookup"><span data-stu-id="87d61-108">ClearCurrentException Method</span></span>](icordebugthread-clearcurrentexception-method.md)|<span data-ttu-id="87d61-109">未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="87d61-109">This method is not implemented.</span></span> <span data-ttu-id="87d61-110">请勿使用。</span><span class="sxs-lookup"><span data-stu-id="87d61-110">Do not use it.</span></span>|  
|[<span data-ttu-id="87d61-111">CreateEval 方法</span><span class="sxs-lookup"><span data-stu-id="87d61-111">CreateEval Method</span></span>](icordebugthread-createeval-method.md)|<span data-ttu-id="87d61-112">创建一个对此运行的 ICorDebugEval 对象 `ICorDebugThread` 。</span><span class="sxs-lookup"><span data-stu-id="87d61-112">Creates an ICorDebugEval object that operates on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="87d61-113">CreateStepper 方法</span><span class="sxs-lookup"><span data-stu-id="87d61-113">CreateStepper Method</span></span>](icordebugthread-createstepper-method.md)|<span data-ttu-id="87d61-114">创建一个 ICorDebugStepper 对象，该对象允许单步执行此中的活动框架 `ICorDebugThread` 。</span><span class="sxs-lookup"><span data-stu-id="87d61-114">Creates an ICorDebugStepper object that allows stepping through the active frame in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="87d61-115">EnumerateChains 方法</span><span class="sxs-lookup"><span data-stu-id="87d61-115">EnumerateChains Method</span></span>](icordebugthread-enumeratechains-method.md)|<span data-ttu-id="87d61-116">获取一个接口指针，该指针指向包含此中所有堆栈链的 ICorDebugChainEnum 枚举器 `ICorDebugThread` 。</span><span class="sxs-lookup"><span data-stu-id="87d61-116">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="87d61-117">GetActiveChain 方法</span><span class="sxs-lookup"><span data-stu-id="87d61-117">GetActiveChain Method</span></span>](icordebugthread-getactivechain-method.md)|<span data-ttu-id="87d61-118">获取此上的活动 ICorDebugChain 的接口指针 `ICorDebugThread` 。</span><span class="sxs-lookup"><span data-stu-id="87d61-118">Gets an interface pointer to the active ICorDebugChain on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="87d61-119">GetActiveFrame 方法</span><span class="sxs-lookup"><span data-stu-id="87d61-119">GetActiveFrame Method</span></span>](icordebugthread-getactiveframe-method.md)|<span data-ttu-id="87d61-120">获取此上的活动 ICorDebugFrame 的接口指针 `ICorDebugThread` 。</span><span class="sxs-lookup"><span data-stu-id="87d61-120">Gets an interface pointer to the active ICorDebugFrame on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="87d61-121">GetAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="87d61-121">GetAppDomain Method</span></span>](icordebugthread-getappdomain-method.md)|<span data-ttu-id="87d61-122">获取一个接口指针，该指针指向此当前正在执行的应用程序域 `ICorDebugThread` 。</span><span class="sxs-lookup"><span data-stu-id="87d61-122">Gets an interface pointer to the application domain in which this `ICorDebugThread` is currently executing.</span></span>|  
|[<span data-ttu-id="87d61-123">GetCurrentException 方法</span><span class="sxs-lookup"><span data-stu-id="87d61-123">GetCurrentException Method</span></span>](icordebugthread-getcurrentexception-method.md)|<span data-ttu-id="87d61-124">获取一个指向 ICorDebugValue 对象的接口指针，该对象表示当前由托管代码引发的异常。</span><span class="sxs-lookup"><span data-stu-id="87d61-124">Gets an interface pointer to an ICorDebugValue object that represents an exception currently being thrown by managed code.</span></span>|  
|[<span data-ttu-id="87d61-125">GetDebugState 方法</span><span class="sxs-lookup"><span data-stu-id="87d61-125">GetDebugState Method</span></span>](icordebugthread-getdebugstate-method.md)|<span data-ttu-id="87d61-126">获取描述此的当前调试状态的 CorDebugThreadState 值 `ICorDebugThread` 。</span><span class="sxs-lookup"><span data-stu-id="87d61-126">Gets a CorDebugThreadState value that describes the current debug state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="87d61-127">GetHandle 方法</span><span class="sxs-lookup"><span data-stu-id="87d61-127">GetHandle Method</span></span>](icordebugthread-gethandle-method.md)|<span data-ttu-id="87d61-128">获取此的活动部分的当前句柄 `ICorDebugThread` 。</span><span class="sxs-lookup"><span data-stu-id="87d61-128">Gets the current handle for the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="87d61-129">GetID 方法</span><span class="sxs-lookup"><span data-stu-id="87d61-129">GetID Method</span></span>](icordebugthread-getid-method.md)|<span data-ttu-id="87d61-130">获取此的活动部分的当前操作系统标识符 `ICorDebugThread` 。</span><span class="sxs-lookup"><span data-stu-id="87d61-130">Gets the current operating system identifier of the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="87d61-131">GetObject 方法</span><span class="sxs-lookup"><span data-stu-id="87d61-131">GetObject Method</span></span>](icordebugthread-getobject-method.md)|<span data-ttu-id="87d61-132"> (CLR) 线程获取公共语言运行时的接口指针。</span><span class="sxs-lookup"><span data-stu-id="87d61-132">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>|  
|[<span data-ttu-id="87d61-133">GetProcess 方法</span><span class="sxs-lookup"><span data-stu-id="87d61-133">GetProcess Method</span></span>](icordebugthread-getprocess-method.md)|<span data-ttu-id="87d61-134">获取一个接口指针，该指针指向此 `ICorDebugThread` 构成部分的进程。</span><span class="sxs-lookup"><span data-stu-id="87d61-134">Gets an interface pointer to the process of which this `ICorDebugThread` forms a part.</span></span>|  
|[<span data-ttu-id="87d61-135">GetRegisterSet 方法</span><span class="sxs-lookup"><span data-stu-id="87d61-135">GetRegisterSet Method</span></span>](icordebugthread-getregisterset-method.md)|<span data-ttu-id="87d61-136">获取一个接口指针，该指针指向与此关联的寄存器集 `ICorDebugThread` 。</span><span class="sxs-lookup"><span data-stu-id="87d61-136">Gets an interface pointer to the register set associated with this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="87d61-137">GetUserState 方法</span><span class="sxs-lookup"><span data-stu-id="87d61-137">GetUserState Method</span></span>](icordebugthread-getuserstate-method.md)|<span data-ttu-id="87d61-138">获取描述此的当前状态的 CorDebugUserState 值的按位组合 `ICorDebugThread` 。</span><span class="sxs-lookup"><span data-stu-id="87d61-138">Gets a bitwise combination of CorDebugUserState values that describe the current state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="87d61-139">SetDebugState 方法</span><span class="sxs-lookup"><span data-stu-id="87d61-139">SetDebugState Method</span></span>](icordebugthread-setdebugstate-method.md)|<span data-ttu-id="87d61-140">设置 `CorDebugThreadState` 描述此的调试状态的值的按位组合 `ICorDebugThread` 。</span><span class="sxs-lookup"><span data-stu-id="87d61-140">Sets a bitwise combination of `CorDebugThreadState` values that describe the debugging state of this `ICorDebugThread`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87d61-141">注解</span><span class="sxs-lookup"><span data-stu-id="87d61-141">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="87d61-142">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="87d61-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87d61-143">要求</span><span class="sxs-lookup"><span data-stu-id="87d61-143">Requirements</span></span>  

 <span data-ttu-id="87d61-144">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="87d61-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87d61-145">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="87d61-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="87d61-146">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87d61-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87d61-147">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87d61-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87d61-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="87d61-148">See also</span></span>

- [<span data-ttu-id="87d61-149">调试接口</span><span class="sxs-lookup"><span data-stu-id="87d61-149">Debugging Interfaces</span></span>](debugging-interfaces.md)
