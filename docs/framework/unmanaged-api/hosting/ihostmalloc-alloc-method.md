---
title: IHostMAlloc::Alloc 方法
ms.date: 03/30/2017
api_name:
- IHostMAlloc.Alloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::Alloc
helpviewer_keywords:
- Alloc method, IHostMAlloc interface [.NET Framework hosting]
- IHostMAlloc::Alloc method [.NET Framework hosting]
ms.assetid: a3007f5e-d75d-4b37-842b-704e9edced5e
topic_type:
- apiref
ms.openlocfilehash: 5858b03676db0839621b121131ded4da9950ce88
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675121"
---
# <a name="ihostmallocalloc-method"></a><span data-ttu-id="51a07-102">IHostMAlloc::Alloc 方法</span><span class="sxs-lookup"><span data-stu-id="51a07-102">IHostMAlloc::Alloc Method</span></span>

<span data-ttu-id="51a07-103">请求宿主从堆分配指定内存量。</span><span class="sxs-lookup"><span data-stu-id="51a07-103">Requests that the host allocate the specified amount of memory from the heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51a07-104">语法</span><span class="sxs-lookup"><span data-stu-id="51a07-104">Syntax</span></span>  
  
```cpp  
HRESULT Alloc (  
    [in] SIZE_T  cbSize,
    [in] EMemoryCriticalLevel dwCriticalLevel,
    [out] void** ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51a07-105">参数</span><span class="sxs-lookup"><span data-stu-id="51a07-105">Parameters</span></span>  

 `cbSize`  
 <span data-ttu-id="51a07-106">中当前内存分配请求的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="51a07-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="51a07-107">中 [EMemoryCriticalLevel](ememorycriticallevel-enumeration.md) 值之一，指示分配失败的影响。</span><span class="sxs-lookup"><span data-stu-id="51a07-107">[in] One of the [EMemoryCriticalLevel](ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="51a07-108">弄指向分配的内存的指针; 如果请求无法完成，则为 null。</span><span class="sxs-lookup"><span data-stu-id="51a07-108">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="51a07-109">返回值</span><span class="sxs-lookup"><span data-stu-id="51a07-109">Return Value</span></span>  
  
|<span data-ttu-id="51a07-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="51a07-110">HRESULT</span></span>|<span data-ttu-id="51a07-111">说明</span><span class="sxs-lookup"><span data-stu-id="51a07-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="51a07-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="51a07-112">S_OK</span></span>|<span data-ttu-id="51a07-113">`Alloc` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="51a07-113">`Alloc` returned successfully.</span></span>|  
|<span data-ttu-id="51a07-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="51a07-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="51a07-115"> (CLR) 的公共语言运行时未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="51a07-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="51a07-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="51a07-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="51a07-117">调用超时。</span><span class="sxs-lookup"><span data-stu-id="51a07-117">The call timed out.</span></span>|  
|<span data-ttu-id="51a07-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="51a07-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="51a07-119">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="51a07-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="51a07-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="51a07-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="51a07-121">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="51a07-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="51a07-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="51a07-122">E_FAIL</span></span>|<span data-ttu-id="51a07-123">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="51a07-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="51a07-124">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="51a07-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="51a07-125">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="51a07-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="51a07-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="51a07-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="51a07-127">没有足够的内存可用来完成分配请求。</span><span class="sxs-lookup"><span data-stu-id="51a07-127">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51a07-128">注解</span><span class="sxs-lookup"><span data-stu-id="51a07-128">Remarks</span></span>  

 <span data-ttu-id="51a07-129">CLR `IHostMalloc` 通过调用 [IHostMemoryManager：： CreateMalloc](ihostmemorymanager-createmalloc-method.md) 方法获取指向实例的接口指针。</span><span class="sxs-lookup"><span data-stu-id="51a07-129">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51a07-130">要求</span><span class="sxs-lookup"><span data-stu-id="51a07-130">Requirements</span></span>  

 <span data-ttu-id="51a07-131">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="51a07-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51a07-132">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="51a07-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="51a07-133">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="51a07-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="51a07-134">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51a07-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51a07-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="51a07-135">See also</span></span>

- [<span data-ttu-id="51a07-136">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="51a07-136">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="51a07-137">IHostMalloc 接口</span><span class="sxs-lookup"><span data-stu-id="51a07-137">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
