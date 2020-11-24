---
title: ICorDebugController::Stop 方法
ms.date: 03/30/2017
api_name:
- ICorDebugController.Stop
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Stop
helpviewer_keywords:
- Stop method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Stop method [.NET Framework debugging]
ms.assetid: c34e79be-a7fb-479e-8dec-d126a4c330e5
topic_type:
- apiref
ms.openlocfilehash: 11cc6e4108a2064a8a9fcefa760bf3c3411d63fb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679853"
---
# <a name="icordebugcontrollerstop-method"></a><span data-ttu-id="56dc6-102">ICorDebugController::Stop 方法</span><span class="sxs-lookup"><span data-stu-id="56dc6-102">ICorDebugController::Stop Method</span></span>

<span data-ttu-id="56dc6-103">在进程中运行托管代码的所有线程上执行协作停止。</span><span class="sxs-lookup"><span data-stu-id="56dc6-103">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56dc6-104">语法</span><span class="sxs-lookup"><span data-stu-id="56dc6-104">Syntax</span></span>  
  
```cpp  
HRESULT Stop (  
    [in] DWORD dwTimeoutIgnored  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56dc6-105">参数</span><span class="sxs-lookup"><span data-stu-id="56dc6-105">Parameters</span></span>  

 `dwTimeoutIgnored`  
 <span data-ttu-id="56dc6-106">未使用。</span><span class="sxs-lookup"><span data-stu-id="56dc6-106">Not used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="56dc6-107">注解</span><span class="sxs-lookup"><span data-stu-id="56dc6-107">Remarks</span></span>  

 <span data-ttu-id="56dc6-108">`Stop` 在进程中运行托管代码的所有线程上执行协作停止。</span><span class="sxs-lookup"><span data-stu-id="56dc6-108">`Stop` performs a cooperative stop on all threads running managed code in the process.</span></span> <span data-ttu-id="56dc6-109">在仅限托管的调试会话期间，非托管线程可能会继续运行 (但在尝试调用托管代码) 时将被阻止。</span><span class="sxs-lookup"><span data-stu-id="56dc6-109">During a managed-only debugging session, unmanaged threads may continue to run (but will be blocked when trying to call managed code).</span></span> <span data-ttu-id="56dc6-110">在互操作调试会话期间，也将停止非托管线程。</span><span class="sxs-lookup"><span data-stu-id="56dc6-110">During an interop debugging session, unmanaged threads will also be stopped.</span></span> <span data-ttu-id="56dc6-111">`dwTimeoutIgnored`该值当前被忽略，并被视为无限 (-1) 。</span><span class="sxs-lookup"><span data-stu-id="56dc6-111">The `dwTimeoutIgnored` value is currently ignored and treated as INFINITE (-1).</span></span> <span data-ttu-id="56dc6-112">如果协作式停止由于死锁而失败，则所有线程都将被挂起并返回 E_TIMEOUT。</span><span class="sxs-lookup"><span data-stu-id="56dc6-112">If the cooperative stop fails due to a deadlock, all threads are suspended and E_TIMEOUT is returned.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="56dc6-113">`Stop` 是调试 API 中唯一的同步方法。</span><span class="sxs-lookup"><span data-stu-id="56dc6-113">`Stop` is the only synchronous method in the debugging API.</span></span> <span data-ttu-id="56dc6-114">如果 `Stop` 返回 S_OK，则停止该进程。</span><span class="sxs-lookup"><span data-stu-id="56dc6-114">When `Stop` returns S_OK, the process is stopped.</span></span> <span data-ttu-id="56dc6-115">不会提供回调以通知侦听器停止。</span><span class="sxs-lookup"><span data-stu-id="56dc6-115">No callback is given to notify listeners of the stop.</span></span> <span data-ttu-id="56dc6-116">调试器必须调用 [ICorDebugController：： Continue](icordebugcontroller-continue-method.md) 以允许进程恢复。</span><span class="sxs-lookup"><span data-stu-id="56dc6-116">The debugger must call [ICorDebugController::Continue](icordebugcontroller-continue-method.md) to allow the process to resume.</span></span>  
  
 <span data-ttu-id="56dc6-117">调试器维护一个停止计数器。</span><span class="sxs-lookup"><span data-stu-id="56dc6-117">The debugger maintains a stop counter.</span></span> <span data-ttu-id="56dc6-118">当计数器变为零时，控制器会恢复。</span><span class="sxs-lookup"><span data-stu-id="56dc6-118">When the counter goes to zero, the controller is resumed.</span></span> <span data-ttu-id="56dc6-119">每次调用 `Stop` 或每个调度回调都会递增计数器。</span><span class="sxs-lookup"><span data-stu-id="56dc6-119">Each call to `Stop` or each dispatched callback increments the counter.</span></span> <span data-ttu-id="56dc6-120">每次调用都会 `ICorDebugController::Continue` 递减计数器。</span><span class="sxs-lookup"><span data-stu-id="56dc6-120">Each call to `ICorDebugController::Continue` decrements the counter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56dc6-121">要求</span><span class="sxs-lookup"><span data-stu-id="56dc6-121">Requirements</span></span>  

 <span data-ttu-id="56dc6-122">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="56dc6-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56dc6-123">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="56dc6-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="56dc6-124">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="56dc6-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="56dc6-125">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56dc6-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56dc6-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="56dc6-126">See also</span></span>
