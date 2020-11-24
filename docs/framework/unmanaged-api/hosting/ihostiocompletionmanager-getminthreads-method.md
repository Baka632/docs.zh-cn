---
title: IHostIoCompletionManager::GetMinThreads 方法
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetMinThreads
helpviewer_keywords:
- GetMinThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::GetMinThreads method [.NET Framework hosting]
ms.assetid: d7a7f733-677d-481c-b3d5-444fcc502b8e
topic_type:
- apiref
ms.openlocfilehash: d321ce08edf4780fc5f26ac627849b9129c2f283
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673207"
---
# <a name="ihostiocompletionmanagergetminthreads-method"></a><span data-ttu-id="01c15-102">IHostIoCompletionManager::GetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="01c15-102">IHostIoCompletionManager::GetMinThreads Method</span></span>

<span data-ttu-id="01c15-103">获取主机提供的、用于处理 i/o 请求的最小线程数。</span><span class="sxs-lookup"><span data-stu-id="01c15-103">Gets the minimum number of threads that the host provides for processing I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01c15-104">语法</span><span class="sxs-lookup"><span data-stu-id="01c15-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMinThreads (  
    [out] DWORD *pdwMinIOCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01c15-105">参数</span><span class="sxs-lookup"><span data-stu-id="01c15-105">Parameters</span></span>  

 `pdwMinIOCompletionThreads`  
 <span data-ttu-id="01c15-106">弄一个指针，它指向主机提供的用于处理 i/o 请求的最小线程数。</span><span class="sxs-lookup"><span data-stu-id="01c15-106">[out] A pointer to the minimum number of threads that the host provides to process I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01c15-107">返回值</span><span class="sxs-lookup"><span data-stu-id="01c15-107">Return Value</span></span>  
  
|<span data-ttu-id="01c15-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="01c15-108">HRESULT</span></span>|<span data-ttu-id="01c15-109">说明</span><span class="sxs-lookup"><span data-stu-id="01c15-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="01c15-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="01c15-110">S_OK</span></span>|<span data-ttu-id="01c15-111">`GetMinThreads` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="01c15-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="01c15-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="01c15-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="01c15-113"> (CLR) 的公共语言运行时未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="01c15-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="01c15-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="01c15-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="01c15-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="01c15-115">The call timed out.</span></span>|  
|<span data-ttu-id="01c15-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="01c15-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="01c15-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="01c15-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="01c15-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="01c15-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="01c15-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="01c15-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="01c15-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="01c15-120">E_FAIL</span></span>|<span data-ttu-id="01c15-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="01c15-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="01c15-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="01c15-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="01c15-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="01c15-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="01c15-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="01c15-124">E_NOTIMPL</span></span>|<span data-ttu-id="01c15-125">宿主不提供的实现 `GetMinThreads` 。</span><span class="sxs-lookup"><span data-stu-id="01c15-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01c15-126">注解</span><span class="sxs-lookup"><span data-stu-id="01c15-126">Remarks</span></span>  

 <span data-ttu-id="01c15-127">出于实现、性能或可伸缩性等原因，主机可能需要对分配给服务 i/o 请求的线程数进行独占控制。</span><span class="sxs-lookup"><span data-stu-id="01c15-127">A host might want exclusive control over the number of threads allotted to service I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="01c15-128">出于此原因，主机不需要实现 `GetMinThreads` 。</span><span class="sxs-lookup"><span data-stu-id="01c15-128">For this reason, the host is not required to implement `GetMinThreads`.</span></span> <span data-ttu-id="01c15-129">在这种情况下，宿主应从此方法返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="01c15-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01c15-130">要求</span><span class="sxs-lookup"><span data-stu-id="01c15-130">Requirements</span></span>  

 <span data-ttu-id="01c15-131">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="01c15-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01c15-132">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="01c15-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="01c15-133">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="01c15-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="01c15-134">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01c15-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01c15-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01c15-135">See also</span></span>

- [<span data-ttu-id="01c15-136">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="01c15-136">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="01c15-137">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="01c15-137">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
