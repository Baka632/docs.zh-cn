---
title: ICorProfilerInfo::GetHandleFromThread 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetHandleFromThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetHandleFromThread
helpviewer_keywords:
- GetHandleFromThread method [.NET Framework profiling]
- ICorProfilerInfo::GetHandleFromThread method [.NET Framework profiling]
ms.assetid: 36cdc9f5-7579-4cd2-aa36-fc05c741584c
topic_type:
- apiref
ms.openlocfilehash: 632a9070eab227bc48ce76c51ea08f98060d680d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722528"
---
# <a name="icorprofilerinfogethandlefromthread-method"></a><span data-ttu-id="1be2e-102">ICorProfilerInfo::GetHandleFromThread 方法</span><span class="sxs-lookup"><span data-stu-id="1be2e-102">ICorProfilerInfo::GetHandleFromThread Method</span></span>

<span data-ttu-id="1be2e-103">将线程的 ID 映射到 Win32 线程句柄。</span><span class="sxs-lookup"><span data-stu-id="1be2e-103">Maps the ID of a thread to a Win32 thread handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1be2e-104">语法</span><span class="sxs-lookup"><span data-stu-id="1be2e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandleFromThread(  
    [in]  ThreadID threadId,  
    [out] HANDLE  *phThread);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1be2e-105">参数</span><span class="sxs-lookup"><span data-stu-id="1be2e-105">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="1be2e-106">中要映射的线程 ID。</span><span class="sxs-lookup"><span data-stu-id="1be2e-106">[in] The thread ID to be mapped.</span></span>  
  
 `phThread`  
 <span data-ttu-id="1be2e-107">弄指向 Win32 线程句柄的指针。</span><span class="sxs-lookup"><span data-stu-id="1be2e-107">[out] A pointer to a Win32 thread handle.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1be2e-108">注解</span><span class="sxs-lookup"><span data-stu-id="1be2e-108">Remarks</span></span>  

 <span data-ttu-id="1be2e-109">探查器必须 `DuplicateHandle` 先对句柄调用 Win32 函数，然后才能使用该句柄。</span><span class="sxs-lookup"><span data-stu-id="1be2e-109">The profiler must call the Win32 `DuplicateHandle` function on the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1be2e-110">要求</span><span class="sxs-lookup"><span data-stu-id="1be2e-110">Requirements</span></span>  

 <span data-ttu-id="1be2e-111">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1be2e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1be2e-112">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1be2e-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1be2e-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1be2e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1be2e-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1be2e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1be2e-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1be2e-115">See also</span></span>

- [<span data-ttu-id="1be2e-116">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="1be2e-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
