---
title: IHostTaskManager::Sleep 方法
ms.date: 03/30/2017
api_name:
- IHostTaskManager.Sleep
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::Sleep
helpviewer_keywords:
- IHostTaskManager::Sleep method [.NET Framework hosting]
- Sleep method, IHostTaskManager interface [.NET Framework hosting]
ms.assetid: f67d25f3-9199-4c5f-b1e8-1c819243cfd5
topic_type:
- apiref
ms.openlocfilehash: 372b15a565f8a7484c1c42c387098a38f7bbf428
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702051"
---
# <a name="ihosttaskmanagersleep-method"></a><span data-ttu-id="7d318-102">IHostTaskManager::Sleep 方法</span><span class="sxs-lookup"><span data-stu-id="7d318-102">IHostTaskManager::Sleep Method</span></span>

<span data-ttu-id="7d318-103">通知宿主当前任务将要进入睡眠状态。</span><span class="sxs-lookup"><span data-stu-id="7d318-103">Notifies the host that the current task is going to sleep.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d318-104">语法</span><span class="sxs-lookup"><span data-stu-id="7d318-104">Syntax</span></span>  
  
```cpp  
HRESULT Sleep (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d318-105">参数</span><span class="sxs-lookup"><span data-stu-id="7d318-105">Parameters</span></span>  

 `dwMilliseconds`  
 <span data-ttu-id="7d318-106">中线程将进入睡眠状态的时间间隔（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="7d318-106">[in] The time interval, in milliseconds, that the thread will sleep.</span></span>  
  
 `option`  
 <span data-ttu-id="7d318-107">中 [WAIT_OPTION](wait-option-enumeration.md) 枚举值之一，指示当此操作阻止时宿主应执行的操作。</span><span class="sxs-lookup"><span data-stu-id="7d318-107">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) enumeration values, indicating what action the host should take if this action blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7d318-108">返回值</span><span class="sxs-lookup"><span data-stu-id="7d318-108">Return Value</span></span>  
  
|<span data-ttu-id="7d318-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7d318-109">HRESULT</span></span>|<span data-ttu-id="7d318-110">说明</span><span class="sxs-lookup"><span data-stu-id="7d318-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7d318-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7d318-111">S_OK</span></span>|<span data-ttu-id="7d318-112">`Sleep` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="7d318-112">`Sleep` returned successfully.</span></span>|  
|<span data-ttu-id="7d318-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7d318-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7d318-114"> (CLR) 的公共语言运行时未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="7d318-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7d318-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7d318-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7d318-116">调用超时。</span><span class="sxs-lookup"><span data-stu-id="7d318-116">The call timed out.</span></span>|  
|<span data-ttu-id="7d318-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7d318-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7d318-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="7d318-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7d318-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7d318-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7d318-120">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="7d318-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7d318-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7d318-121">E_FAIL</span></span>|<span data-ttu-id="7d318-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="7d318-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7d318-123">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="7d318-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7d318-124">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="7d318-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d318-125">注解</span><span class="sxs-lookup"><span data-stu-id="7d318-125">Remarks</span></span>  

 <span data-ttu-id="7d318-126">在 `IHostTaskManager::Sleep` <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> 从用户代码调用时，CLR 通常会调用。</span><span class="sxs-lookup"><span data-stu-id="7d318-126">The CLR typically calls `IHostTaskManager::Sleep` when <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> is called from user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d318-127">要求</span><span class="sxs-lookup"><span data-stu-id="7d318-127">Requirements</span></span>  

 <span data-ttu-id="7d318-128">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7d318-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d318-129">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="7d318-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7d318-130">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7d318-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7d318-131">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d318-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d318-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d318-132">See also</span></span>

- [<span data-ttu-id="7d318-133">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="7d318-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="7d318-134">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="7d318-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="7d318-135">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="7d318-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="7d318-136">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="7d318-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
