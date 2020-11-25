---
title: IHostIoCompletionManager::GetAvailableThreads 方法
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetAvailableThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetAvailableThreads
helpviewer_keywords:
- GetAvailableThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::GetAvailableThreads method [.NET Framework hosting]
ms.assetid: bab363d1-b859-47a4-9884-5661c611cce7
topic_type:
- apiref
ms.openlocfilehash: 3e9f4e98962532efe4b2e2a779add841b7b3a835
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724255"
---
# <a name="ihostiocompletionmanagergetavailablethreads-method"></a><span data-ttu-id="5f1ed-102">IHostIoCompletionManager::GetAvailableThreads 方法</span><span class="sxs-lookup"><span data-stu-id="5f1ed-102">IHostIoCompletionManager::GetAvailableThreads Method</span></span>

<span data-ttu-id="5f1ed-103">获取主机管理的、当前未处理请求的线程总数的 i/o 完成线程数。</span><span class="sxs-lookup"><span data-stu-id="5f1ed-103">Gets the number of I/O completion threads, of the total number of threads managed by the host, that are not currently servicing requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f1ed-104">语法</span><span class="sxs-lookup"><span data-stu-id="5f1ed-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f1ed-105">参数</span><span class="sxs-lookup"><span data-stu-id="5f1ed-105">Parameters</span></span>  

 `pdwAvailableIoCompletionThreads`  
 <span data-ttu-id="5f1ed-106">弄一个指针，指向由主机管理的、当前可用于服务请求的 i/o 完成线程数。</span><span class="sxs-lookup"><span data-stu-id="5f1ed-106">[out] A pointer to the number of I/O completion threads managed by the host that are currently available to service requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5f1ed-107">返回值</span><span class="sxs-lookup"><span data-stu-id="5f1ed-107">Return Value</span></span>  
  
|<span data-ttu-id="5f1ed-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5f1ed-108">HRESULT</span></span>|<span data-ttu-id="5f1ed-109">说明</span><span class="sxs-lookup"><span data-stu-id="5f1ed-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5f1ed-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5f1ed-110">S_OK</span></span>|<span data-ttu-id="5f1ed-111">`GetAvailableThreads` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="5f1ed-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="5f1ed-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5f1ed-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5f1ed-113"> (CLR) 的公共语言运行时未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="5f1ed-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5f1ed-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5f1ed-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5f1ed-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="5f1ed-115">The call timed out.</span></span>|  
|<span data-ttu-id="5f1ed-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5f1ed-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5f1ed-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="5f1ed-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5f1ed-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5f1ed-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5f1ed-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="5f1ed-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5f1ed-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5f1ed-120">E_FAIL</span></span>|<span data-ttu-id="5f1ed-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="5f1ed-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5f1ed-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="5f1ed-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5f1ed-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="5f1ed-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5f1ed-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="5f1ed-124">E_NOTIMPL</span></span>|<span data-ttu-id="5f1ed-125">宿主不提供的实现 `GetAvailableThreads` 。</span><span class="sxs-lookup"><span data-stu-id="5f1ed-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5f1ed-126">注解</span><span class="sxs-lookup"><span data-stu-id="5f1ed-126">Remarks</span></span>  

 <span data-ttu-id="5f1ed-127">出于实现、性能或可伸缩性等原因，主机可能需要对 i/o 完成线程池的大小进行独占控制。</span><span class="sxs-lookup"><span data-stu-id="5f1ed-127">A host might want exclusive control over the size of the I/O completion thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="5f1ed-128">因此，主机不需要实现 `GetAvailableThreads` 。</span><span class="sxs-lookup"><span data-stu-id="5f1ed-128">Therefore, the host is not required to implement `GetAvailableThreads`.</span></span> <span data-ttu-id="5f1ed-129">在这种情况下，宿主应从此方法返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="5f1ed-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f1ed-130">要求</span><span class="sxs-lookup"><span data-stu-id="5f1ed-130">Requirements</span></span>  

 <span data-ttu-id="5f1ed-131">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5f1ed-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f1ed-132">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5f1ed-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5f1ed-133">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5f1ed-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5f1ed-134">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f1ed-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f1ed-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f1ed-135">See also</span></span>

- [<span data-ttu-id="5f1ed-136">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="5f1ed-136">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="5f1ed-137">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="5f1ed-137">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
