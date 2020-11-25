---
title: ICorProfilerInfo::GetThreadContext 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetThreadContext
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetThreadContext
helpviewer_keywords:
- ICorProfilerInfo::GetThreadContext method [.NET Framework profiling]
- GetThreadContext method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 79446216-4b8b-484c-8fe3-e87dbf9df2fd
topic_type:
- apiref
ms.openlocfilehash: 2e24d72c8be1ace10b2feb15101ed8f83db386c2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724086"
---
# <a name="icorprofilerinfogetthreadcontext-method"></a><span data-ttu-id="4a822-102">ICorProfilerInfo::GetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="4a822-102">ICorProfilerInfo::GetThreadContext Method</span></span>

<span data-ttu-id="4a822-103">获取当前与指定线程关联的上下文标识。</span><span class="sxs-lookup"><span data-stu-id="4a822-103">Gets the context identity currently associated with the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a822-104">语法</span><span class="sxs-lookup"><span data-stu-id="4a822-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in]  ThreadID  threadId,  
    [out] ContextID *pContextId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a822-105">参数</span><span class="sxs-lookup"><span data-stu-id="4a822-105">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="4a822-106">中线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="4a822-106">[in] The ID of the thread.</span></span>  
  
 `pContextId`  
 <span data-ttu-id="4a822-107">弄指向当前与指定线程关联的上下文 ID 的指针。</span><span class="sxs-lookup"><span data-stu-id="4a822-107">[out] A pointer to the context ID currently associated with the specified thread.</span></span> <span data-ttu-id="4a822-108">如果该线程当前没有关联的上下文，则此函数将返回 CORPROF_E_DATAINCOMPLETE。</span><span class="sxs-lookup"><span data-stu-id="4a822-108">If the thread has no context currently associated with it, this function will return CORPROF_E_DATAINCOMPLETE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a822-109">要求</span><span class="sxs-lookup"><span data-stu-id="4a822-109">Requirements</span></span>  

 <span data-ttu-id="4a822-110">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4a822-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a822-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4a822-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4a822-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a822-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a822-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a822-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a822-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a822-114">See also</span></span>

- [<span data-ttu-id="4a822-115">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="4a822-115">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
