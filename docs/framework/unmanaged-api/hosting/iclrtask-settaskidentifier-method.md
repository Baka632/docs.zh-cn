---
title: ICLRTask::SetTaskIdentifier 方法
ms.date: 03/30/2017
api_name:
- ICLRTask.SetTaskIdentifier
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SetTaskIdentifier
helpviewer_keywords:
- SetTaskIdentifier method [.NET Framework hosting]
- ICLRTask::SetTaskIdentifier method [.NET Framework hosting]
ms.assetid: bdb7f047-1e90-40fc-9e3b-d44a16509073
topic_type:
- apiref
ms.openlocfilehash: d1f731e00d4917b997dfba392cb9b6ce2afc082e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690741"
---
# <a name="iclrtasksettaskidentifier-method"></a><span data-ttu-id="1d602-102">ICLRTask::SetTaskIdentifier 方法</span><span class="sxs-lookup"><span data-stu-id="1d602-102">ICLRTask::SetTaskIdentifier Method</span></span>

<span data-ttu-id="1d602-103">指示公共语言运行时 (CLR) 将指定标识符值与当前 [ICLRTask](iclrtask-interface.md) 实例表示的任务相关联。</span><span class="sxs-lookup"><span data-stu-id="1d602-103">Instructs the common language runtime (CLR) to associate the specified identifier value with the task represented by the current [ICLRTask](iclrtask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d602-104">语法</span><span class="sxs-lookup"><span data-stu-id="1d602-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTaskIdentifier (  
    [in] DWORD Asked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d602-105">参数</span><span class="sxs-lookup"><span data-stu-id="1d602-105">Parameters</span></span>  

 `Asked`  
 <span data-ttu-id="1d602-106">中与当前实例表示的任务关联的公共语言运行时的唯一标识符 `ICLRTask` 。</span><span class="sxs-lookup"><span data-stu-id="1d602-106">[in] The unique identifier for the common language runtime to associate with the task represented by the current `ICLRTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1d602-107">返回值</span><span class="sxs-lookup"><span data-stu-id="1d602-107">Return Value</span></span>  
  
|<span data-ttu-id="1d602-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1d602-108">HRESULT</span></span>|<span data-ttu-id="1d602-109">说明</span><span class="sxs-lookup"><span data-stu-id="1d602-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1d602-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1d602-110">S_OK</span></span>|<span data-ttu-id="1d602-111">`SetTaskIdentifier` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="1d602-111">`SetTaskIdentifier` returned successfully.</span></span>|  
|<span data-ttu-id="1d602-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1d602-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1d602-113">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="1d602-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1d602-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1d602-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1d602-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="1d602-115">The call timed out.</span></span>|  
|<span data-ttu-id="1d602-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1d602-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1d602-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="1d602-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1d602-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1d602-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1d602-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="1d602-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1d602-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1d602-120">E_FAIL</span></span>|<span data-ttu-id="1d602-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="1d602-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1d602-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="1d602-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1d602-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="1d602-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d602-124">注解</span><span class="sxs-lookup"><span data-stu-id="1d602-124">Remarks</span></span>  

 <span data-ttu-id="1d602-125">宿主可以将标识符与任务相关联，以帮助在调试环境中集成 CLR 和宿主。</span><span class="sxs-lookup"><span data-stu-id="1d602-125">The host can associate an identifier with a task to help integrate the CLR and the host in a debugging environment.</span></span> <span data-ttu-id="1d602-126">标识符对于 CLR 没有意义。</span><span class="sxs-lookup"><span data-stu-id="1d602-126">The identifier has no meaning for the CLR.</span></span> <span data-ttu-id="1d602-127">CLR 将其传递到调试器应用程序。</span><span class="sxs-lookup"><span data-stu-id="1d602-127">The CLR passes it along to a debugger application.</span></span> <span data-ttu-id="1d602-128">调试器可以使用此标识符将 CLR 调用堆栈与宿主调用堆栈相关联，并使其各自的跟踪信息在调试器的用户界面中查看时能够统一。</span><span class="sxs-lookup"><span data-stu-id="1d602-128">The debugger can use this identifier to associate a CLR call stack with a host call stack, and enable their respective trace information to be unified when viewed in the debugger's user interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d602-129">要求</span><span class="sxs-lookup"><span data-stu-id="1d602-129">Requirements</span></span>  

 <span data-ttu-id="1d602-130">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1d602-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d602-131">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1d602-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1d602-132">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1d602-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1d602-133">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d602-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d602-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1d602-134">See also</span></span>

- [<span data-ttu-id="1d602-135">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="1d602-135">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="1d602-136">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="1d602-136">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="1d602-137">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="1d602-137">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="1d602-138">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="1d602-138">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
