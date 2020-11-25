---
title: ICorDebugChain 接口
ms.date: 03/30/2017
api_name:
- ICorDebugChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain
helpviewer_keywords:
- ICorDebugChain interface [.NET Framework debugging]
ms.assetid: f671f519-1cb3-4ae5-b9f1-abc5e783459f
topic_type:
- apiref
ms.openlocfilehash: a0285970a8a42c078aa663579e1d5998d0d1c037
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724450"
---
# <a name="icordebugchain-interface"></a><span data-ttu-id="c340f-102">ICorDebugChain 接口</span><span class="sxs-lookup"><span data-stu-id="c340f-102">ICorDebugChain Interface</span></span>

<span data-ttu-id="c340f-103">表示一个物理或逻辑调用堆栈段。</span><span class="sxs-lookup"><span data-stu-id="c340f-103">Represents a segment of a physical or logical call stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c340f-104">方法</span><span class="sxs-lookup"><span data-stu-id="c340f-104">Methods</span></span>  
  
|<span data-ttu-id="c340f-105">方法</span><span class="sxs-lookup"><span data-stu-id="c340f-105">Method</span></span>|<span data-ttu-id="c340f-106">说明</span><span class="sxs-lookup"><span data-stu-id="c340f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c340f-107">EnumerateFrames 方法</span><span class="sxs-lookup"><span data-stu-id="c340f-107">EnumerateFrames Method</span></span>](icordebugchain-enumerateframes-method.md)|<span data-ttu-id="c340f-108">获取一个枚举数，该枚举数包含链中所有托管堆栈帧（从最新帧开始）。</span><span class="sxs-lookup"><span data-stu-id="c340f-108">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>|  
|[<span data-ttu-id="c340f-109">GetActiveFrame 方法</span><span class="sxs-lookup"><span data-stu-id="c340f-109">GetActiveFrame Method</span></span>](icordebugchain-getactiveframe-method.md)|<span data-ttu-id="c340f-110">获取当前链上的活动 (，即最近) 的帧。</span><span class="sxs-lookup"><span data-stu-id="c340f-110">Gets the active (that is, most recent) frame on the chain.</span></span>|  
|[<span data-ttu-id="c340f-111">GetCallee 方法</span><span class="sxs-lookup"><span data-stu-id="c340f-111">GetCallee Method</span></span>](icordebugchain-getcallee-method.md)|<span data-ttu-id="c340f-112">获取此链调用的链。</span><span class="sxs-lookup"><span data-stu-id="c340f-112">Gets the chain that was called by this chain.</span></span>|  
|[<span data-ttu-id="c340f-113">GetCaller 方法</span><span class="sxs-lookup"><span data-stu-id="c340f-113">GetCaller Method</span></span>](icordebugchain-getcaller-method.md)|<span data-ttu-id="c340f-114">获取调用此链的链。</span><span class="sxs-lookup"><span data-stu-id="c340f-114">Gets the chain that called this chain.</span></span>|  
|[<span data-ttu-id="c340f-115">GetContext 方法</span><span class="sxs-lookup"><span data-stu-id="c340f-115">GetContext Method</span></span>](icordebugchain-getcontext-method.md)|<span data-ttu-id="c340f-116">未实现。</span><span class="sxs-lookup"><span data-stu-id="c340f-116">Not implemented.</span></span>|  
|[<span data-ttu-id="c340f-117">GetNext 方法</span><span class="sxs-lookup"><span data-stu-id="c340f-117">GetNext Method</span></span>](icordebugchain-getnext-method.md)|<span data-ttu-id="c340f-118">获取线程的下一个帧链。</span><span class="sxs-lookup"><span data-stu-id="c340f-118">Gets the next chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="c340f-119">GetPrevious 方法</span><span class="sxs-lookup"><span data-stu-id="c340f-119">GetPrevious Method</span></span>](icordebugchain-getprevious-method.md)|<span data-ttu-id="c340f-120">获取线程的上一个帧链。</span><span class="sxs-lookup"><span data-stu-id="c340f-120">Gets the previous chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="c340f-121">GetReason 方法</span><span class="sxs-lookup"><span data-stu-id="c340f-121">GetReason Method</span></span>](icordebugchain-getreason-method.md)|<span data-ttu-id="c340f-122">获取此调用链的 genesis 的原因。</span><span class="sxs-lookup"><span data-stu-id="c340f-122">Gets the reason for the genesis of this calling chain.</span></span>|  
|[<span data-ttu-id="c340f-123">GetRegisterSet 方法</span><span class="sxs-lookup"><span data-stu-id="c340f-123">GetRegisterSet Method</span></span>](icordebugchain-getregisterset-method.md)|<span data-ttu-id="c340f-124">获取此链的活动部分的寄存器集。</span><span class="sxs-lookup"><span data-stu-id="c340f-124">Gets the register set for the active part of this chain.</span></span>|  
|[<span data-ttu-id="c340f-125">GetStackRange 方法</span><span class="sxs-lookup"><span data-stu-id="c340f-125">GetStackRange Method</span></span>](icordebugchain-getstackrange-method.md)|<span data-ttu-id="c340f-126">获取此链的堆栈段的地址范围。</span><span class="sxs-lookup"><span data-stu-id="c340f-126">Gets the address range of the stack segment for this chain.</span></span>|  
|[<span data-ttu-id="c340f-127">GetThread 方法</span><span class="sxs-lookup"><span data-stu-id="c340f-127">GetThread Method</span></span>](icordebugchain-getthread-method.md)|<span data-ttu-id="c340f-128">获取此调用链所属的物理线程。</span><span class="sxs-lookup"><span data-stu-id="c340f-128">Gets the physical thread this call chain is part of.</span></span>|  
|[<span data-ttu-id="c340f-129">IsManaged 方法</span><span class="sxs-lookup"><span data-stu-id="c340f-129">IsManaged Method</span></span>](icordebugchain-ismanaged-method.md)|<span data-ttu-id="c340f-130">获取一个值，该值指示此链是否正在运行托管代码。</span><span class="sxs-lookup"><span data-stu-id="c340f-130">Gets a value that indicates whether this chain is running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c340f-131">注解</span><span class="sxs-lookup"><span data-stu-id="c340f-131">Remarks</span></span>  

 <span data-ttu-id="c340f-132">链中的堆栈帧占用连续堆栈空间并共享相同的线程和上下文。</span><span class="sxs-lookup"><span data-stu-id="c340f-132">The stack frames in a chain occupy contiguous stack space and share the same thread and context.</span></span> <span data-ttu-id="c340f-133">链可以表示托管或非托管代码链。</span><span class="sxs-lookup"><span data-stu-id="c340f-133">A chain may represent either managed or unmanaged code chains.</span></span> <span data-ttu-id="c340f-134">空 `ICorDebugChain` 实例表示非托管代码链。</span><span class="sxs-lookup"><span data-stu-id="c340f-134">An empty `ICorDebugChain` instance represents an unmanaged code chain.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c340f-135">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="c340f-135">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c340f-136">要求</span><span class="sxs-lookup"><span data-stu-id="c340f-136">Requirements</span></span>  

 <span data-ttu-id="c340f-137">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c340f-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c340f-138">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c340f-138">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c340f-139">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c340f-139">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c340f-140">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c340f-140">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c340f-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c340f-141">See also</span></span>

- [<span data-ttu-id="c340f-142">调试接口</span><span class="sxs-lookup"><span data-stu-id="c340f-142">Debugging Interfaces</span></span>](debugging-interfaces.md)
