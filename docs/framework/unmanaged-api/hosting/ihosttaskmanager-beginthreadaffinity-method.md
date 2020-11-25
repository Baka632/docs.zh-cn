---
title: IHostTaskManager::BeginThreadAffinity 方法
ms.date: 03/30/2017
api_name:
- IHostTaskManager.BeginThreadAffinity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::BeginThreadAffinity
helpviewer_keywords:
- IHostTaskManager::BeginThreadAffinity method [.NET Framework hosting]
- BeginThreadAffinity method [.NET Framework hosting]
ms.assetid: fea3ab88-ce41-4c5a-847b-bb78cd748da6
topic_type:
- apiref
ms.openlocfilehash: 6f6d57a52d960c975d468f370477b5d7e29c3aa2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727336"
---
# <a name="ihosttaskmanagerbeginthreadaffinity-method"></a><span data-ttu-id="2c723-102">IHostTaskManager::BeginThreadAffinity 方法</span><span class="sxs-lookup"><span data-stu-id="2c723-102">IHostTaskManager::BeginThreadAffinity Method</span></span>

<span data-ttu-id="2c723-103">通知宿主托管代码正在输入一个时间段，在此期间，不能将当前任务移动到另一个操作系统线程。</span><span class="sxs-lookup"><span data-stu-id="2c723-103">Notifies the host that managed code is entering a period in which the current task must not be moved to another operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c723-104">语法</span><span class="sxs-lookup"><span data-stu-id="2c723-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="2c723-105">返回值</span><span class="sxs-lookup"><span data-stu-id="2c723-105">Return Value</span></span>  
  
|<span data-ttu-id="2c723-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2c723-106">HRESULT</span></span>|<span data-ttu-id="2c723-107">说明</span><span class="sxs-lookup"><span data-stu-id="2c723-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2c723-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="2c723-108">S_OK</span></span>|<span data-ttu-id="2c723-109">`BeginThreadAffinity` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="2c723-109">`BeginThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="2c723-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2c723-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2c723-111"> (CLR) 的公共语言运行时未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="2c723-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2c723-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2c723-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2c723-113">调用超时。</span><span class="sxs-lookup"><span data-stu-id="2c723-113">The call timed out.</span></span>|  
|<span data-ttu-id="2c723-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2c723-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2c723-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="2c723-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2c723-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2c723-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2c723-117">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="2c723-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2c723-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2c723-118">E_FAIL</span></span>|<span data-ttu-id="2c723-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="2c723-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2c723-120">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="2c723-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2c723-121">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="2c723-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c723-122">注解</span><span class="sxs-lookup"><span data-stu-id="2c723-122">Remarks</span></span>  

 <span data-ttu-id="2c723-123">CLR 通常在对的 `IHostTaskManager::BeginThreadAffinity` 调用的上下文中调用 <xref:System.Threading.Thread.BeginThreadAffinity%2A?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="2c723-123">The CLR typically calls `IHostTaskManager::BeginThreadAffinity` in the context of a call to <xref:System.Threading.Thread.BeginThreadAffinity%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2c723-124">在对 [IHostTaskManager：： EndThreadAffinity](ihosttaskmanager-endthreadaffinity-method.md)进行相应的调用之前，不能重新计划当前任务。</span><span class="sxs-lookup"><span data-stu-id="2c723-124">The current task must not be rescheduled until a corresponding call is made to [IHostTaskManager::EndThreadAffinity](ihosttaskmanager-endthreadaffinity-method.md).</span></span> <span data-ttu-id="2c723-125">可以切换出任务，但当它们切换回时，必须将它们分配到从中进行切换的相同操作系统线程。对的嵌套调用 `BeginThreadAffinity` 不起作用，因为调用指的是当前任务。</span><span class="sxs-lookup"><span data-stu-id="2c723-125">Tasks can be switched out, but when they are switched back in, they must be assigned to the same operating system thread from which they were switched out. Nested calls to `BeginThreadAffinity` have no effect, because the call refers to the current task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c723-126">要求</span><span class="sxs-lookup"><span data-stu-id="2c723-126">Requirements</span></span>  

 <span data-ttu-id="2c723-127">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2c723-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c723-128">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2c723-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2c723-129">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2c723-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2c723-130">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c723-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c723-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2c723-131">See also</span></span>

- [<span data-ttu-id="2c723-132">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="2c723-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="2c723-133">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="2c723-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="2c723-134">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="2c723-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="2c723-135">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="2c723-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
