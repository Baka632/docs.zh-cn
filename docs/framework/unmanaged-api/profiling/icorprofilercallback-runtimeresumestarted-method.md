---
title: ICorProfilerCallback::RuntimeResumeStarted 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeResumeStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeResumeStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeResumeStarted method [.NET Framework profiling]
- RuntimeResumeStarted method [.NET Framework profiling]
ms.assetid: 5854bfb2-c568-4f19-904a-7c9d41e7b995
topic_type:
- apiref
ms.openlocfilehash: 9a283d305c1a19112574cbf3486b1c67e64ed24c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717214"
---
# <a name="icorprofilercallbackruntimeresumestarted-method"></a><span data-ttu-id="1c32d-102">ICorProfilerCallback::RuntimeResumeStarted 方法</span><span class="sxs-lookup"><span data-stu-id="1c32d-102">ICorProfilerCallback::RuntimeResumeStarted Method</span></span>

<span data-ttu-id="1c32d-103">通知探查器运行时正在恢复所有运行时线程。</span><span class="sxs-lookup"><span data-stu-id="1c32d-103">Notifies the profiler that the runtime is resuming all run-time threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c32d-104">语法</span><span class="sxs-lookup"><span data-stu-id="1c32d-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeResumeStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="1c32d-105">要求</span><span class="sxs-lookup"><span data-stu-id="1c32d-105">Requirements</span></span>  

 <span data-ttu-id="1c32d-106">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1c32d-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c32d-107">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1c32d-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1c32d-108">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c32d-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c32d-109">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c32d-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c32d-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1c32d-110">See also</span></span>

- [<span data-ttu-id="1c32d-111">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="1c32d-111">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="1c32d-112">RuntimeResumeFinished 方法</span><span class="sxs-lookup"><span data-stu-id="1c32d-112">RuntimeResumeFinished Method</span></span>](icorprofilercallback-runtimeresumefinished-method.md)
