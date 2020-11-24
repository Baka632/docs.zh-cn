---
title: ICorProfilerCallback::ExceptionUnwindFinallyEnter 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFinallyEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyEnter method [.NET Framework profiling]
- ExceptionUnwindFinallyEnter method [.NET Framework profiling]
ms.assetid: c7fab986-b69f-4ec8-b7b7-91dcfc239cd0
topic_type:
- apiref
ms.openlocfilehash: 46e1fccc40606e10d8ff4083c7fe51da711c039a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686119"
---
# <a name="icorprofilercallbackexceptionunwindfinallyenter-method"></a><span data-ttu-id="2d107-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter 方法</span><span class="sxs-lookup"><span data-stu-id="2d107-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter Method</span></span>

<span data-ttu-id="2d107-103">通知探查器异常处理的展开阶段正在输入 `finally` 指定函数中包含的子句。</span><span class="sxs-lookup"><span data-stu-id="2d107-103">Notifies the profiler that the unwind phase of exception handling is entering a `finally` clause contained in the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d107-104">语法</span><span class="sxs-lookup"><span data-stu-id="2d107-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwindFinallyEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d107-105">参数</span><span class="sxs-lookup"><span data-stu-id="2d107-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="2d107-106">\[in] 包含子句的函数的 ID `finally` 。</span><span class="sxs-lookup"><span data-stu-id="2d107-106">\[in] The ID of the function that contains the `finally` clause.</span></span>

## <a name="remarks"></a><span data-ttu-id="2d107-107">注解</span><span class="sxs-lookup"><span data-stu-id="2d107-107">Remarks</span></span>  

 <span data-ttu-id="2d107-108">探查器不应在此方法的实现中被阻止，因为堆栈可能不处于允许垃圾回收的状态，因此无法启用抢先垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="2d107-108">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="2d107-109">如果探查器在此处阻止并且试图进行垃圾回收，则运行时将被阻止，直到此回调返回。</span><span class="sxs-lookup"><span data-stu-id="2d107-109">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="2d107-110">探查器的此方法的实现不应调入托管代码或以任何方式导致托管内存分配。</span><span class="sxs-lookup"><span data-stu-id="2d107-110">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d107-111">要求</span><span class="sxs-lookup"><span data-stu-id="2d107-111">Requirements</span></span>  

 <span data-ttu-id="2d107-112">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2d107-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d107-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2d107-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2d107-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d107-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d107-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d107-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d107-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2d107-116">See also</span></span>

- [<span data-ttu-id="2d107-117">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="2d107-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="2d107-118">GetNotifiedExceptionClauseInfo 方法</span><span class="sxs-lookup"><span data-stu-id="2d107-118">GetNotifiedExceptionClauseInfo Method</span></span>](icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)
- [<span data-ttu-id="2d107-119">ExceptionUnwindFinallyLeave 方法</span><span class="sxs-lookup"><span data-stu-id="2d107-119">ExceptionUnwindFinallyLeave Method</span></span>](icorprofilercallback-exceptionunwindfinallyleave-method.md)
