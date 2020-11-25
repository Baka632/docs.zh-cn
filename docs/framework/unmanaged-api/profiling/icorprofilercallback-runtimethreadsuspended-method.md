---
title: ICorProfilerCallback::RuntimeThreadSuspended 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeThreadSuspended
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeThreadSuspended
helpviewer_keywords:
- RuntimeThreadSuspended method [.NET Framework profiling]
- ICorProfilerCallback::RuntimeThreadSuspended method [.NET Framework profiling]
ms.assetid: de830a8b-6ee1-4900-ace3-4237108f6b12
topic_type:
- apiref
ms.openlocfilehash: 33a39cf2781f49ff0e31989831c4c9829889ec3d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731990"
---
# <a name="icorprofilercallbackruntimethreadsuspended-method"></a><span data-ttu-id="3c877-102">ICorProfilerCallback::RuntimeThreadSuspended 方法</span><span class="sxs-lookup"><span data-stu-id="3c877-102">ICorProfilerCallback::RuntimeThreadSuspended Method</span></span>

<span data-ttu-id="3c877-103">通知探查器指定的线程已挂起或将要挂起。</span><span class="sxs-lookup"><span data-stu-id="3c877-103">Notifies the profiler that the specified thread has been suspended or is about to be suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c877-104">语法</span><span class="sxs-lookup"><span data-stu-id="3c877-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeThreadSuspended(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c877-105">参数</span><span class="sxs-lookup"><span data-stu-id="3c877-105">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="3c877-106">中已挂起的线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="3c877-106">[in] The ID of the thread that has been suspended.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c877-107">注解</span><span class="sxs-lookup"><span data-stu-id="3c877-107">Remarks</span></span>  

 <span data-ttu-id="3c877-108">在 `RuntimeThreadSuspended` [ICorProfilerCallback：： RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) 与关联的 [ICorProfilerCallback：： RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) 回调之间随时会发生通知。</span><span class="sxs-lookup"><span data-stu-id="3c877-108">The `RuntimeThreadSuspended` notification can occur any time between the [ICorProfilerCallback::RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) and the associated [ICorProfilerCallback::RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span> <span data-ttu-id="3c877-109">在 [ICorProfilerCallback：： RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) 之间发生的通知， `RuntimeResumeStarted` 适用于已在非托管代码中运行并在进入运行时时挂起的线程。</span><span class="sxs-lookup"><span data-stu-id="3c877-109">Notifications that occur between [ICorProfilerCallback::RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) and `RuntimeResumeStarted` are for threads that had been running in unmanaged code and were suspended upon entry to the runtime.</span></span>  
  
 <span data-ttu-id="3c877-110">通常，此回调恰好在挂起线程之后发生。</span><span class="sxs-lookup"><span data-stu-id="3c877-110">Generally, this callback occurs just after a thread is suspended.</span></span> <span data-ttu-id="3c877-111">但是，如果当前正在执行的线程 (调用此回调的线程) 为挂起的线程，则该回调将在线程挂起之前发生。</span><span class="sxs-lookup"><span data-stu-id="3c877-111">However, if the currently executing thread (the thread that called this callback) is the one that is being suspended, this callback will occur just before the thread is suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c877-112">要求</span><span class="sxs-lookup"><span data-stu-id="3c877-112">Requirements</span></span>  

 <span data-ttu-id="3c877-113">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3c877-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c877-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3c877-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3c877-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c877-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c877-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c877-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c877-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3c877-117">See also</span></span>

- [<span data-ttu-id="3c877-118">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="3c877-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="3c877-119">RuntimeThreadResumed 方法</span><span class="sxs-lookup"><span data-stu-id="3c877-119">RuntimeThreadResumed Method</span></span>](icorprofilercallback-runtimethreadresumed-method.md)
