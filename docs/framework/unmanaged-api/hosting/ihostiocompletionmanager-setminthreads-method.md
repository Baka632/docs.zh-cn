---
title: IHostIoCompletionManager::SetMinThreads 方法
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetMinThreads
helpviewer_keywords:
- SetMinThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::SetMinThreads method [.NET Framework hosting]
ms.assetid: dea34b81-8d2b-4cc3-8696-0ad4291d8a92
topic_type:
- apiref
ms.openlocfilehash: 64ea9fdd477ec005b089f451101b742278ab4266
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672404"
---
# <a name="ihostiocompletionmanagersetminthreads-method"></a><span data-ttu-id="ed6a3-102">IHostIoCompletionManager::SetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="ed6a3-102">IHostIoCompletionManager::SetMinThreads Method</span></span>

<span data-ttu-id="ed6a3-103">设置主机应为 i/o 完成分配的最小线程数。</span><span class="sxs-lookup"><span data-stu-id="ed6a3-103">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed6a3-104">语法</span><span class="sxs-lookup"><span data-stu-id="ed6a3-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMinThreads (  
    [in] DWORD dwMinIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed6a3-105">参数</span><span class="sxs-lookup"><span data-stu-id="ed6a3-105">Parameters</span></span>  

 `dwMinIoCompletionThreads`  
 <span data-ttu-id="ed6a3-106">中宿主应创建的 i/o 完成线程的最小数目。</span><span class="sxs-lookup"><span data-stu-id="ed6a3-106">[in] The minimum number of I/O completion threads that the host should create.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ed6a3-107">返回值</span><span class="sxs-lookup"><span data-stu-id="ed6a3-107">Return Value</span></span>  
  
|<span data-ttu-id="ed6a3-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ed6a3-108">HRESULT</span></span>|<span data-ttu-id="ed6a3-109">说明</span><span class="sxs-lookup"><span data-stu-id="ed6a3-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ed6a3-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ed6a3-110">S_OK</span></span>|<span data-ttu-id="ed6a3-111">`SetMinThreads` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="ed6a3-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="ed6a3-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ed6a3-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ed6a3-113"> (CLR) 的公共语言运行时未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="ed6a3-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ed6a3-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ed6a3-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ed6a3-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="ed6a3-115">The call timed out.</span></span>|  
|<span data-ttu-id="ed6a3-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ed6a3-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ed6a3-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="ed6a3-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ed6a3-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ed6a3-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ed6a3-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="ed6a3-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ed6a3-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ed6a3-120">E_FAIL</span></span>|<span data-ttu-id="ed6a3-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="ed6a3-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ed6a3-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="ed6a3-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ed6a3-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="ed6a3-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ed6a3-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="ed6a3-124">E_NOTIMPL</span></span>|<span data-ttu-id="ed6a3-125">宿主不提供的实现 `SetMinThreads` 。</span><span class="sxs-lookup"><span data-stu-id="ed6a3-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed6a3-126">注解</span><span class="sxs-lookup"><span data-stu-id="ed6a3-126">Remarks</span></span>  

 <span data-ttu-id="ed6a3-127">出于实现、性能或可伸缩性等原因，主机可能需要对可分配给处理 i/o 请求的线程数进行独占控制。</span><span class="sxs-lookup"><span data-stu-id="ed6a3-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="ed6a3-128">出于此原因，主机不需要实现 `SetMinThreads` 。</span><span class="sxs-lookup"><span data-stu-id="ed6a3-128">For this reason, the host is not required to implement `SetMinThreads`.</span></span> <span data-ttu-id="ed6a3-129">在这种情况下，宿主应从此方法返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="ed6a3-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed6a3-130">要求</span><span class="sxs-lookup"><span data-stu-id="ed6a3-130">Requirements</span></span>  

 <span data-ttu-id="ed6a3-131">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ed6a3-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed6a3-132">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ed6a3-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ed6a3-133">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ed6a3-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ed6a3-134">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed6a3-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed6a3-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed6a3-135">See also</span></span>

- [<span data-ttu-id="ed6a3-136">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="ed6a3-136">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="ed6a3-137">SetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="ed6a3-137">SetMaxThreads Method</span></span>](ihostiocompletionmanager-setmaxthreads-method.md)
- [<span data-ttu-id="ed6a3-138">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="ed6a3-138">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
