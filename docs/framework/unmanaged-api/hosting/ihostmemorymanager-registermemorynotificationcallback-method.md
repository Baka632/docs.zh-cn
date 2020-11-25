---
title: IHostMemoryManager::RegisterMemoryNotificationCallback 方法
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.RegisterMemoryNotificationCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback
helpviewer_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback method [.NET Framework hosting]
- RegisterMemoryNotificationCallback method [.NET Framework hosting]
ms.assetid: 65d301f6-4dbb-4b5f-8eff-82540e2b6465
topic_type:
- apiref
ms.openlocfilehash: edb29378412583d7cdec804b08f8f622d642b02f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731301"
---
# <a name="ihostmemorymanagerregistermemorynotificationcallback-method"></a><span data-ttu-id="09b60-102">IHostMemoryManager::RegisterMemoryNotificationCallback 方法</span><span class="sxs-lookup"><span data-stu-id="09b60-102">IHostMemoryManager::RegisterMemoryNotificationCallback Method</span></span>

<span data-ttu-id="09b60-103">注册指向主机调用的回调函数的指针，以通知公共语言运行时 (计算机上当前内存负载的 CLR) 。</span><span class="sxs-lookup"><span data-stu-id="09b60-103">Registers a pointer to a callback function that the host invokes to notify the common language runtime (CLR) of the current memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09b60-104">语法</span><span class="sxs-lookup"><span data-stu-id="09b60-104">Syntax</span></span>  
  
```cpp  
HRESULT RegisterMemoryNotificationCallback (  
    [in] ICLRMemoryNotificationCallback* pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09b60-105">参数</span><span class="sxs-lookup"><span data-stu-id="09b60-105">Parameters</span></span>  

 `pCallback`  
 <span data-ttu-id="09b60-106">中一个接口指针，该指针指向由 CLR 实现的 [ICLRMemoryNotificationCallback](iclrmemorynotificationcallback-interface.md) 实例。</span><span class="sxs-lookup"><span data-stu-id="09b60-106">[in] An interface pointer to an [ICLRMemoryNotificationCallback](iclrmemorynotificationcallback-interface.md) instance that is implemented by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09b60-107">返回值</span><span class="sxs-lookup"><span data-stu-id="09b60-107">Return Value</span></span>  
  
|<span data-ttu-id="09b60-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="09b60-108">HRESULT</span></span>|<span data-ttu-id="09b60-109">说明</span><span class="sxs-lookup"><span data-stu-id="09b60-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="09b60-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="09b60-110">S_OK</span></span>|<span data-ttu-id="09b60-111">`RegisterMemoryNotificationCallback` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="09b60-111">`RegisterMemoryNotificationCallback` returned successfully.</span></span>|  
|<span data-ttu-id="09b60-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="09b60-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="09b60-113">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="09b60-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="09b60-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="09b60-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="09b60-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="09b60-115">The call timed out.</span></span>|  
|<span data-ttu-id="09b60-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="09b60-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="09b60-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="09b60-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="09b60-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="09b60-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="09b60-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="09b60-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="09b60-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="09b60-120">E_FAIL</span></span>|<span data-ttu-id="09b60-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="09b60-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="09b60-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="09b60-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="09b60-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="09b60-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09b60-124">注解</span><span class="sxs-lookup"><span data-stu-id="09b60-124">Remarks</span></span>  

 <span data-ttu-id="09b60-125">由于 `ICLRMemoryNotificationCallback` 接口仅定义了一个 ([ICLRMemoryNotificationCallback：： OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md)) 的方法，并且由于 `pCallback` 是一个指向 `ICLRMemoryNotificationCallback` CLR 提供的实例的指针，因此注册对于回调函数本身是有效的。</span><span class="sxs-lookup"><span data-stu-id="09b60-125">Because the `ICLRMemoryNotificationCallback` interface defines only one method ([ICLRMemoryNotificationCallback::OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md)), and because `pCallback` is a pointer to an `ICLRMemoryNotificationCallback` instance provided by the CLR, the registration is effectively for the callback function itself.</span></span> <span data-ttu-id="09b60-126">宿主调用 `OnMemoryNotification` 以报告内存压力条件，而不是使用标准的 Win32 `CreateMemoryResourceNotification` 函数。</span><span class="sxs-lookup"><span data-stu-id="09b60-126">The host invokes `OnMemoryNotification` to report memory pressure conditions, rather than using the standard Win32 `CreateMemoryResourceNotification` function.</span></span> <span data-ttu-id="09b60-127">有关详细信息，请参阅 Windows 平台文档。</span><span class="sxs-lookup"><span data-stu-id="09b60-127">For more information, see the Windows Platform documentation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="09b60-128">对 `OnMemoryNotification` 从不阻止的的调用。</span><span class="sxs-lookup"><span data-stu-id="09b60-128">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="09b60-129">它们始终立即返回。</span><span class="sxs-lookup"><span data-stu-id="09b60-129">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09b60-130">要求</span><span class="sxs-lookup"><span data-stu-id="09b60-130">Requirements</span></span>  

 <span data-ttu-id="09b60-131">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="09b60-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09b60-132">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="09b60-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="09b60-133">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="09b60-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="09b60-134">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09b60-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09b60-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09b60-135">See also</span></span>

- [<span data-ttu-id="09b60-136">ICLRMemoryNotificationCallback 接口</span><span class="sxs-lookup"><span data-stu-id="09b60-136">ICLRMemoryNotificationCallback Interface</span></span>](iclrmemorynotificationcallback-interface.md)
- [<span data-ttu-id="09b60-137">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="09b60-137">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
