---
title: ICorProfilerCallback::ExceptionSearchFunctionEnter 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFunctionEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFunctionEnter
helpviewer_keywords:
- ExceptionSearchFunctionEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchFunctionEnter method [.NET Framework profiling]
ms.assetid: bfd54573-b7e6-4bd1-a184-7f08a8b39fae
topic_type:
- apiref
ms.openlocfilehash: 9c39d984db62326b31a4760a817ee82def6dd78f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699815"
---
# <a name="icorprofilercallbackexceptionsearchfunctionenter-method"></a><span data-ttu-id="4a5d2-102">ICorProfilerCallback::ExceptionSearchFunctionEnter 方法</span><span class="sxs-lookup"><span data-stu-id="4a5d2-102">ICorProfilerCallback::ExceptionSearchFunctionEnter Method</span></span>

<span data-ttu-id="4a5d2-103">通知探查器，异常处理的搜索阶段已开始搜索函数以查找当前异常的处理程序。</span><span class="sxs-lookup"><span data-stu-id="4a5d2-103">Notifies the profiler that the search phase of exception handling has begun searching a function to find a handler for the current exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a5d2-104">语法</span><span class="sxs-lookup"><span data-stu-id="4a5d2-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFunctionEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a5d2-105">参数</span><span class="sxs-lookup"><span data-stu-id="4a5d2-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="4a5d2-106">\[in] 已输入的函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="4a5d2-106">\[in] The ID of the function that has been entered.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="4a5d2-107">要求</span><span class="sxs-lookup"><span data-stu-id="4a5d2-107">Requirements</span></span>  

 <span data-ttu-id="4a5d2-108">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4a5d2-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a5d2-109">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4a5d2-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4a5d2-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a5d2-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a5d2-111">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a5d2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a5d2-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a5d2-112">See also</span></span>

- [<span data-ttu-id="4a5d2-113">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="4a5d2-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="4a5d2-114">ExceptionSearchFunctionLeave 方法</span><span class="sxs-lookup"><span data-stu-id="4a5d2-114">ExceptionSearchFunctionLeave Method</span></span>](icorprofilercallback-exceptionsearchfunctionleave-method.md)
