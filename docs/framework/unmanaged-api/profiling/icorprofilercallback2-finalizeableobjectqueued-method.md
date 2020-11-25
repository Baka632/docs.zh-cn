---
title: ICorProfilerCallback2::FinalizeableObjectQueued 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.FinalizeableObjectQueued
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::FinalizeableObjectQueued
helpviewer_keywords:
- FinalizeableObjectQueued method [.NET Framework profiling]
- ICorProfilerCallback2::FinalizeableObjectQueued method [.NET Framework profiling]
ms.assetid: 92d76893-683c-475d-9996-5bff03cdb10f
topic_type:
- apiref
ms.openlocfilehash: 4429524b5f3baff3251acbd7ef7954d30a3e0093
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731942"
---
# <a name="icorprofilercallback2finalizeableobjectqueued-method"></a><span data-ttu-id="056eb-102">ICorProfilerCallback2::FinalizeableObjectQueued 方法</span><span class="sxs-lookup"><span data-stu-id="056eb-102">ICorProfilerCallback2::FinalizeableObjectQueued Method</span></span>

<span data-ttu-id="056eb-103">通知代码探查器，具有终结器的对象已排入终结器线程，以执行其 `Finalize` 方法。</span><span class="sxs-lookup"><span data-stu-id="056eb-103">Notifies the code profiler that an object with a finalizer has been queued to the finalizer thread for execution of its `Finalize` method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="056eb-104">语法</span><span class="sxs-lookup"><span data-stu-id="056eb-104">Syntax</span></span>  
  
```cpp  
HRESULT FinalizeableObjectQueued(  
    [in] DWORD finalizerFlags,  
    [in] ObjectID objectID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="056eb-105">参数</span><span class="sxs-lookup"><span data-stu-id="056eb-105">Parameters</span></span>  

 `finalizerFlags`  
 <span data-ttu-id="056eb-106">中一个 [COR_PRF_FINALIZER_FLAGS](cor-prf-finalizer-flags-enumeration.md) 枚举的值，该值描述终结器的各个方面。</span><span class="sxs-lookup"><span data-stu-id="056eb-106">[in] A value of the [COR_PRF_FINALIZER_FLAGS](cor-prf-finalizer-flags-enumeration.md) enumeration that describes aspects of the finalizer.</span></span>  
  
 `objectID`  
 <span data-ttu-id="056eb-107">中已排队的对象的 ID。</span><span class="sxs-lookup"><span data-stu-id="056eb-107">[in] The ID of the object that has been queued.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="056eb-108">要求</span><span class="sxs-lookup"><span data-stu-id="056eb-108">Requirements</span></span>  

 <span data-ttu-id="056eb-109">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="056eb-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="056eb-110">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="056eb-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="056eb-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="056eb-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="056eb-112">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="056eb-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="056eb-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="056eb-113">See also</span></span>

- [<span data-ttu-id="056eb-114">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="056eb-114">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="056eb-115">ICorProfilerCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="056eb-115">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
