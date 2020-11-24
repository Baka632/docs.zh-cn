---
title: IHostMAlloc::Free 方法
ms.date: 03/30/2017
api_name:
- IHostMAlloc.Free
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::Free
helpviewer_keywords:
- IHostMAlloc::Free method [.NET Framework hosting]
- Free method, IHostMAlloc interface [.NET Framework hosting]
ms.assetid: c89abf5b-1120-4437-8b57-4a99fb3ae7f9
topic_type:
- apiref
ms.openlocfilehash: d4c9048c89d55ed048a55a771572823905a056df
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687120"
---
# <a name="ihostmallocfree-method"></a><span data-ttu-id="088c8-102">IHostMAlloc::Free 方法</span><span class="sxs-lookup"><span data-stu-id="088c8-102">IHostMAlloc::Free Method</span></span>

<span data-ttu-id="088c8-103">释放使用 [分配](ihostmalloc-alloc-method.md) 函数分配的内存。</span><span class="sxs-lookup"><span data-stu-id="088c8-103">Frees memory that was allocated by using the [Alloc](ihostmalloc-alloc-method.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="088c8-104">语法</span><span class="sxs-lookup"><span data-stu-id="088c8-104">Syntax</span></span>  
  
```cpp  
HRESULT Free (  
    [in] void* pMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="088c8-105">参数</span><span class="sxs-lookup"><span data-stu-id="088c8-105">Parameters</span></span>  

 `pMem`  
 <span data-ttu-id="088c8-106">中指向要释放的内存的指针。</span><span class="sxs-lookup"><span data-stu-id="088c8-106">[in] A pointer to the memory to be freed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="088c8-107">返回值</span><span class="sxs-lookup"><span data-stu-id="088c8-107">Return Value</span></span>  
  
|<span data-ttu-id="088c8-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="088c8-108">HRESULT</span></span>|<span data-ttu-id="088c8-109">说明</span><span class="sxs-lookup"><span data-stu-id="088c8-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="088c8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="088c8-110">S_OK</span></span>|<span data-ttu-id="088c8-111">`Free` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="088c8-111">`Free` returned successfully.</span></span>|  
|<span data-ttu-id="088c8-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="088c8-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="088c8-113"> (CLR) 的公共语言运行时未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="088c8-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="088c8-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="088c8-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="088c8-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="088c8-115">The call timed out.</span></span>|  
|<span data-ttu-id="088c8-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="088c8-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="088c8-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="088c8-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="088c8-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="088c8-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="088c8-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="088c8-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="088c8-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="088c8-120">E_FAIL</span></span>|<span data-ttu-id="088c8-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="088c8-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="088c8-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="088c8-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="088c8-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="088c8-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="088c8-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="088c8-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="088c8-125">尝试释放未通过主机分配的内存。</span><span class="sxs-lookup"><span data-stu-id="088c8-125">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="088c8-126">注解</span><span class="sxs-lookup"><span data-stu-id="088c8-126">Remarks</span></span>  

 <span data-ttu-id="088c8-127">如果 `pMem` 参数引用未使用调用分配的内存区域 `Alloc` ，则宿主应返回 HOST_E_INVALIDOPERATION。</span><span class="sxs-lookup"><span data-stu-id="088c8-127">If the `pMem` parameter refers to a region of memory that was not allocated by using a call to `Alloc`, the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="088c8-128">要求</span><span class="sxs-lookup"><span data-stu-id="088c8-128">Requirements</span></span>  

 <span data-ttu-id="088c8-129">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="088c8-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="088c8-130">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="088c8-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="088c8-131">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="088c8-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="088c8-132">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="088c8-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="088c8-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="088c8-133">See also</span></span>

- [<span data-ttu-id="088c8-134">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="088c8-134">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="088c8-135">IHostMalloc 接口</span><span class="sxs-lookup"><span data-stu-id="088c8-135">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
