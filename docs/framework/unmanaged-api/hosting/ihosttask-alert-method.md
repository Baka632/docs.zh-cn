---
title: IHostTask::Alert 方法
ms.date: 03/30/2017
api_name:
- IHostTask.Alert
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Alert
helpviewer_keywords:
- IHostTask::Alert method [.NET Framework hosting]
- Alert method, IHostTask interface [.NET Framework hosting]
ms.assetid: 5245d4b5-b6c3-48df-9cb9-8caf059f43fb
topic_type:
- apiref
ms.openlocfilehash: 5a4870a4472081a78cd1fade51f441c22aa5eb48
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720472"
---
# <a name="ihosttaskalert-method"></a><span data-ttu-id="ea28a-102">IHostTask::Alert 方法</span><span class="sxs-lookup"><span data-stu-id="ea28a-102">IHostTask::Alert Method</span></span>

<span data-ttu-id="ea28a-103">请求宿主唤醒当前 [IHostTask](ihosttask-interface.md) 实例表示的任务，以便可以中止该任务。</span><span class="sxs-lookup"><span data-stu-id="ea28a-103">Requests that the host wake the task represented by the current [IHostTask](ihosttask-interface.md) instance, so the task can be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea28a-104">语法</span><span class="sxs-lookup"><span data-stu-id="ea28a-104">Syntax</span></span>  
  
```cpp  
HRESULT Alert ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ea28a-105">返回值</span><span class="sxs-lookup"><span data-stu-id="ea28a-105">Return Value</span></span>  
  
|<span data-ttu-id="ea28a-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ea28a-106">HRESULT</span></span>|<span data-ttu-id="ea28a-107">说明</span><span class="sxs-lookup"><span data-stu-id="ea28a-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ea28a-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="ea28a-108">S_OK</span></span>|<span data-ttu-id="ea28a-109">该方法已成功返回。</span><span class="sxs-lookup"><span data-stu-id="ea28a-109">The method returned successfully.</span></span>|  
|<span data-ttu-id="ea28a-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ea28a-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ea28a-111"> (CLR) 的公共语言运行时未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="ea28a-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ea28a-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ea28a-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ea28a-113">调用超时。</span><span class="sxs-lookup"><span data-stu-id="ea28a-113">The call timed out.</span></span>|  
|<span data-ttu-id="ea28a-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ea28a-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ea28a-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="ea28a-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ea28a-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ea28a-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ea28a-117">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="ea28a-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ea28a-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ea28a-118">E_FAIL</span></span>|<span data-ttu-id="ea28a-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="ea28a-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ea28a-120">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="ea28a-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ea28a-121">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="ea28a-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea28a-122">注解</span><span class="sxs-lookup"><span data-stu-id="ea28a-122">Remarks</span></span>  

 <span data-ttu-id="ea28a-123">`Alert`当 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> 从用户代码调用时，或当 <xref:System.AppDomain> 与当前的关联关闭时，CLR 将调用方法 <xref:System.Threading.Thread> 。</span><span class="sxs-lookup"><span data-stu-id="ea28a-123">The CLR calls the `Alert` method when <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> is called from user code, or when the <xref:System.AppDomain> associated with the current <xref:System.Threading.Thread> shuts down.</span></span> <span data-ttu-id="ea28a-124">由于调用是异步进行的，因此主机必须立即返回。</span><span class="sxs-lookup"><span data-stu-id="ea28a-124">The host must return immediately, because the call is made asynchronously.</span></span> <span data-ttu-id="ea28a-125">如果主机无法立即对任务发出警报，则必须在下一次进入状态时唤醒该任务。</span><span class="sxs-lookup"><span data-stu-id="ea28a-125">If the host cannot alert the task immediately, it must wake up the next time it enters a state in which it can be alerted.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ea28a-126">`Alert` 仅影响运行时将 WAIT_ALERTABLE [WAIT_OPTION](wait-option-enumeration.md) 值传递到 [联接](ihosttask-join-method.md)等方法的任务。</span><span class="sxs-lookup"><span data-stu-id="ea28a-126">`Alert` affects only those tasks to which the runtime has passed a [WAIT_OPTION](wait-option-enumeration.md) value of WAIT_ALERTABLE to methods such as [Join](ihosttask-join-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea28a-127">要求</span><span class="sxs-lookup"><span data-stu-id="ea28a-127">Requirements</span></span>  

 <span data-ttu-id="ea28a-128">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ea28a-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea28a-129">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ea28a-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ea28a-130">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ea28a-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ea28a-131">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea28a-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea28a-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ea28a-132">See also</span></span>

- [<span data-ttu-id="ea28a-133">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="ea28a-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="ea28a-134">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="ea28a-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="ea28a-135">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="ea28a-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="ea28a-136">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="ea28a-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
