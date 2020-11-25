---
title: ICorProfilerCallback::RuntimeSuspendStarted 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted method [.NET Framework profiling]
- RuntimeSuspendStarted method [.NET Framework profiling]
ms.assetid: c8461cac-e31b-4efa-ad2c-26598173eb96
topic_type:
- apiref
ms.openlocfilehash: b778088f53a3c49def95d715f5fefcb26af81489
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731977"
---
# <a name="icorprofilercallbackruntimesuspendstarted-method"></a><span data-ttu-id="91132-102">ICorProfilerCallback::RuntimeSuspendStarted 方法</span><span class="sxs-lookup"><span data-stu-id="91132-102">ICorProfilerCallback::RuntimeSuspendStarted Method</span></span>

<span data-ttu-id="91132-103">通知探查器运行时将要挂起所有运行时线程。</span><span class="sxs-lookup"><span data-stu-id="91132-103">Notifies the profiler that the runtime is about to suspend all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91132-104">语法</span><span class="sxs-lookup"><span data-stu-id="91132-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeSuspendStarted(  
    [in] COR_PRF_SUSPEND_REASON suspendReason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91132-105">参数</span><span class="sxs-lookup"><span data-stu-id="91132-105">Parameters</span></span>  

 `suspendReason`  
 <span data-ttu-id="91132-106">中一个 [COR_PRF_SUSPEND_REASON](cor-prf-suspend-reason-enumeration.md) 枚举的值，该值指示挂起的原因。</span><span class="sxs-lookup"><span data-stu-id="91132-106">[in] A value of the [COR_PRF_SUSPEND_REASON](cor-prf-suspend-reason-enumeration.md) enumeration that indicates the reason for the suspension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91132-107">注解</span><span class="sxs-lookup"><span data-stu-id="91132-107">Remarks</span></span>  

 <span data-ttu-id="91132-108">允许非托管代码中的所有运行时线程继续运行，直到它们尝试重新进入运行时。</span><span class="sxs-lookup"><span data-stu-id="91132-108">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="91132-109">此时，它们也将被挂起，直到运行时恢复。</span><span class="sxs-lookup"><span data-stu-id="91132-109">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="91132-110">这也适用于输入运行时的新线程。</span><span class="sxs-lookup"><span data-stu-id="91132-110">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="91132-111">如果运行时中的所有线程已处于中断的代码中，则会立即将其挂起，或者当它们到达中断的代码时要求它们挂起。</span><span class="sxs-lookup"><span data-stu-id="91132-111">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91132-112">要求</span><span class="sxs-lookup"><span data-stu-id="91132-112">Requirements</span></span>  

 <span data-ttu-id="91132-113">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="91132-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91132-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="91132-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="91132-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91132-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91132-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91132-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91132-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="91132-117">See also</span></span>

- [<span data-ttu-id="91132-118">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="91132-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="91132-119">RuntimeSuspendAborted 方法</span><span class="sxs-lookup"><span data-stu-id="91132-119">RuntimeSuspendAborted Method</span></span>](icorprofilercallback-runtimesuspendaborted-method.md)
- [<span data-ttu-id="91132-120">RuntimeSuspendFinished 方法</span><span class="sxs-lookup"><span data-stu-id="91132-120">RuntimeSuspendFinished Method</span></span>](icorprofilercallback-runtimesuspendfinished-method.md)
