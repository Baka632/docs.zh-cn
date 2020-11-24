---
title: ICLRGCManager::SetGCStartupLimits 方法
ms.date: 03/30/2017
api_name:
- ICLRGCManager.SetGCStartupLimits
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, ICLRGCManager interface [.NET Framework hosting]
- ICLRGCManager::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: 1c8d9959-95b5-4131-be4a-556d97774014
topic_type:
- apiref
ms.openlocfilehash: 169d344975762b97f89e8dc32d72f2b9c95fea11
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678163"
---
# <a name="iclrgcmanagersetgcstartuplimits-method"></a><span data-ttu-id="55c7b-102">ICLRGCManager::SetGCStartupLimits 方法</span><span class="sxs-lookup"><span data-stu-id="55c7b-102">ICLRGCManager::SetGCStartupLimits Method</span></span>

<span data-ttu-id="55c7b-103">设置垃圾回收段的大小以及垃圾回收系统的第0代的最大大小。</span><span class="sxs-lookup"><span data-stu-id="55c7b-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="55c7b-104">从 .NET Framework 4.5 开始，可以 `DWORD` 使用 [ICLRGCManager2：： SetGCStartupLimitsEx](iclrgcmanager2-setgcstartuplimitsex-method.md) 方法将段大小和最大第0代大小设置为大于的值。</span><span class="sxs-lookup"><span data-stu-id="55c7b-104">Starting with the .NET Framework 4.5, you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [ICLRGCManager2::SetGCStartupLimitsEx](iclrgcmanager2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55c7b-105">语法</span><span class="sxs-lookup"><span data-stu-id="55c7b-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55c7b-106">参数</span><span class="sxs-lookup"><span data-stu-id="55c7b-106">Parameters</span></span>  

 `SegmentSize`  
 <span data-ttu-id="55c7b-107">中垃圾收集段的指定大小。</span><span class="sxs-lookup"><span data-stu-id="55c7b-107">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="55c7b-108">最小段大小为 4 MB。</span><span class="sxs-lookup"><span data-stu-id="55c7b-108">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="55c7b-109">段可以增加 1 MB 或更大的增量。</span><span class="sxs-lookup"><span data-stu-id="55c7b-109">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="55c7b-110">中第0代的指定最大大小。</span><span class="sxs-lookup"><span data-stu-id="55c7b-110">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="55c7b-111">最小第0代大小为 64 KB。</span><span class="sxs-lookup"><span data-stu-id="55c7b-111">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="55c7b-112">返回值</span><span class="sxs-lookup"><span data-stu-id="55c7b-112">Return Value</span></span>  
  
|<span data-ttu-id="55c7b-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="55c7b-113">HRESULT</span></span>|<span data-ttu-id="55c7b-114">说明</span><span class="sxs-lookup"><span data-stu-id="55c7b-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="55c7b-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="55c7b-115">S_OK</span></span>|<span data-ttu-id="55c7b-116">`SetGCStartupLimits` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="55c7b-116">`SetGCStartupLimits` returned successfully.</span></span>|  
|<span data-ttu-id="55c7b-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="55c7b-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="55c7b-118"> (CLR) 的公共语言运行时未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="55c7b-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="55c7b-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="55c7b-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="55c7b-120">调用超时。</span><span class="sxs-lookup"><span data-stu-id="55c7b-120">The call timed out.</span></span>|  
|<span data-ttu-id="55c7b-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="55c7b-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="55c7b-122">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="55c7b-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="55c7b-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="55c7b-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="55c7b-124">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="55c7b-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="55c7b-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="55c7b-125">E_FAIL</span></span>|<span data-ttu-id="55c7b-126">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="55c7b-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="55c7b-127">方法返回 E_FAIL 后，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="55c7b-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="55c7b-128">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="55c7b-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55c7b-129">注解</span><span class="sxs-lookup"><span data-stu-id="55c7b-129">Remarks</span></span>  

 <span data-ttu-id="55c7b-130">设置的值 `SetGCStartupLimits` 只能指定一次。</span><span class="sxs-lookup"><span data-stu-id="55c7b-130">The values that `SetGCStartupLimits` sets can be specified only once.</span></span> <span data-ttu-id="55c7b-131">`SetGCStartupLimits`将忽略以后对的调用。</span><span class="sxs-lookup"><span data-stu-id="55c7b-131">Later calls to `SetGCStartupLimits` are ignored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55c7b-132">要求</span><span class="sxs-lookup"><span data-stu-id="55c7b-132">Requirements</span></span>  

 <span data-ttu-id="55c7b-133">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="55c7b-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55c7b-134">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="55c7b-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="55c7b-135">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="55c7b-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="55c7b-136">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55c7b-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55c7b-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="55c7b-137">See also</span></span>

- [<span data-ttu-id="55c7b-138">自动内存管理</span><span class="sxs-lookup"><span data-stu-id="55c7b-138">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="55c7b-139">垃圾回收</span><span class="sxs-lookup"><span data-stu-id="55c7b-139">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="55c7b-140">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="55c7b-140">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="55c7b-141">ICLRGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="55c7b-141">ICLRGCManager Interface</span></span>](iclrgcmanager-interface.md)
