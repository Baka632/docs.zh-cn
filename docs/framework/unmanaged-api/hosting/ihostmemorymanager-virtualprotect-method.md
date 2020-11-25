---
title: IHostMemoryManager::VirtualProtect 方法
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualProtect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualProtect
helpviewer_keywords:
- IHostMemoryManager::VirtualProtect method [.NET Framework hosting]
- VirtualProtect method [.NET Framework hosting]
ms.assetid: 13be0299-df0d-4951-aabf-0676a30b385f
topic_type:
- apiref
ms.openlocfilehash: 9822e5a1fb09e9d3bce541ff63cf766ae8611789
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731243"
---
# <a name="ihostmemorymanagervirtualprotect-method"></a><span data-ttu-id="9dbae-102">IHostMemoryManager::VirtualProtect 方法</span><span class="sxs-lookup"><span data-stu-id="9dbae-102">IHostMemoryManager::VirtualProtect Method</span></span>

<span data-ttu-id="9dbae-103">用作相应 Win32 函数的逻辑包装。</span><span class="sxs-lookup"><span data-stu-id="9dbae-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="9dbae-104">的 Win32 实现在 `VirtualProtect` 调用进程的虚拟地址空间中更改已提交页面区域的保护。</span><span class="sxs-lookup"><span data-stu-id="9dbae-104">The Win32 implementation of `VirtualProtect` changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dbae-105">语法</span><span class="sxs-lookup"><span data-stu-id="9dbae-105">Syntax</span></span>  
  
```cpp  
HRESULT VirtualProtect (  
    [in]  void*   lpAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flNewProtect,  
    [out] DWORD*  pflOldProtect  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9dbae-106">参数</span><span class="sxs-lookup"><span data-stu-id="9dbae-106">Parameters</span></span>  

 `lpAddress`  
 <span data-ttu-id="9dbae-107">中指向要更改其保护属性的虚拟内存基址的指针。</span><span class="sxs-lookup"><span data-stu-id="9dbae-107">[in] A pointer to the base address of the virtual memory whose protection attributes are to be changed.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="9dbae-108">中要更改的内存页区域的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="9dbae-108">[in] The size, in bytes, of the region of memory pages to be changed.</span></span>  
  
 `flNewProtect`  
 <span data-ttu-id="9dbae-109">中要应用的内存保护的类型。</span><span class="sxs-lookup"><span data-stu-id="9dbae-109">[in] The type of memory protection to apply.</span></span>  
  
 `pflOldProtect`  
 <span data-ttu-id="9dbae-110">弄指向上一个内存保护值的指针。</span><span class="sxs-lookup"><span data-stu-id="9dbae-110">[out] A pointer to the previous memory protection value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9dbae-111">返回值</span><span class="sxs-lookup"><span data-stu-id="9dbae-111">Return Value</span></span>  
  
|<span data-ttu-id="9dbae-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9dbae-112">HRESULT</span></span>|<span data-ttu-id="9dbae-113">说明</span><span class="sxs-lookup"><span data-stu-id="9dbae-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9dbae-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="9dbae-114">S_OK</span></span>|<span data-ttu-id="9dbae-115">`VirtualProtect` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="9dbae-115">`VirtualProtect` returned successfully.</span></span>|  
|<span data-ttu-id="9dbae-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9dbae-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9dbae-117"> (CLR) 的公共语言运行时未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="9dbae-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9dbae-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9dbae-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9dbae-119">调用超时。</span><span class="sxs-lookup"><span data-stu-id="9dbae-119">The call timed out.</span></span>|  
|<span data-ttu-id="9dbae-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9dbae-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9dbae-121">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="9dbae-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9dbae-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9dbae-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9dbae-123">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="9dbae-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9dbae-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9dbae-124">E_FAIL</span></span>|<span data-ttu-id="9dbae-125">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="9dbae-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9dbae-126">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="9dbae-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9dbae-127">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="9dbae-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9dbae-128">注解</span><span class="sxs-lookup"><span data-stu-id="9dbae-128">Remarks</span></span>  

 <span data-ttu-id="9dbae-129">的此实现 `VirtualProtect` 返回一个 HRESULT 值，而 Win32 实现返回非零值以指示成功，并返回一个零值以指示失败。</span><span class="sxs-lookup"><span data-stu-id="9dbae-129">This implementation of `VirtualProtect` returns an HRESULT value, while the Win32 implementation returns a non-zero value to indicate success, and a zero value to indicate failure.</span></span> <span data-ttu-id="9dbae-130">有关详细信息，请参阅 Windows 平台文档。</span><span class="sxs-lookup"><span data-stu-id="9dbae-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9dbae-131">要求</span><span class="sxs-lookup"><span data-stu-id="9dbae-131">Requirements</span></span>  

 <span data-ttu-id="9dbae-132">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9dbae-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9dbae-133">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9dbae-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9dbae-134">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9dbae-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9dbae-135">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9dbae-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dbae-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9dbae-136">See also</span></span>

- [<span data-ttu-id="9dbae-137">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="9dbae-137">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
