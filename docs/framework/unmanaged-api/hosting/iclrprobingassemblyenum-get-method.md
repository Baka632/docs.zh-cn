---
title: ICLRProbingAssemblyEnum::Get 方法
ms.date: 03/30/2017
api_name:
- ICLRProbingAssemblyEnum.Get
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRProbingAssemblyEnum::Get
helpviewer_keywords:
- Get method, ICLRProbingAssemblyEnum interface [.NET Framework hosting]
- ICLRProbingAssemblyEnum::Get method [.NET Framework hosting]
ms.assetid: fdb67a77-782f-44cf-a8a1-b75999b0f3c8
topic_type:
- apiref
ms.openlocfilehash: 9a6145ff2874890f052f18a7e537e20ff259933c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728935"
---
# <a name="iclrprobingassemblyenumget-method"></a><span data-ttu-id="68216-102">ICLRProbingAssemblyEnum::Get 方法</span><span class="sxs-lookup"><span data-stu-id="68216-102">ICLRProbingAssemblyEnum::Get Method</span></span>

<span data-ttu-id="68216-103">获取指定索引处的程序集标识。</span><span class="sxs-lookup"><span data-stu-id="68216-103">Gets the assembly identity at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68216-104">语法</span><span class="sxs-lookup"><span data-stu-id="68216-104">Syntax</span></span>  
  
```cpp  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="68216-105">参数</span><span class="sxs-lookup"><span data-stu-id="68216-105">Parameters</span></span>  

 `dwIndex`  
 <span data-ttu-id="68216-106">中要返回的程序集标识的从零开始的索引。</span><span class="sxs-lookup"><span data-stu-id="68216-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="68216-107">弄包含程序集标识数据的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="68216-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="68216-108">[in，out]缓冲区的大小 `pwzBuffer` 。</span><span class="sxs-lookup"><span data-stu-id="68216-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="68216-109">返回值</span><span class="sxs-lookup"><span data-stu-id="68216-109">Return Value</span></span>  
  
|<span data-ttu-id="68216-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="68216-110">HRESULT</span></span>|<span data-ttu-id="68216-111">说明</span><span class="sxs-lookup"><span data-stu-id="68216-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="68216-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="68216-112">S_OK</span></span>|<span data-ttu-id="68216-113">`Get` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="68216-113">`Get` returned successfully.</span></span>|  
|<span data-ttu-id="68216-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="68216-114">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="68216-115">`pwzBuffer` 太小。</span><span class="sxs-lookup"><span data-stu-id="68216-115">`pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="68216-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="68216-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="68216-117">枚举中没有更多的项。</span><span class="sxs-lookup"><span data-stu-id="68216-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="68216-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="68216-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="68216-119"> (CLR) 的公共语言运行时未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="68216-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="68216-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="68216-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="68216-121">调用超时。</span><span class="sxs-lookup"><span data-stu-id="68216-121">The call timed out.</span></span>|  
|<span data-ttu-id="68216-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="68216-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="68216-123">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="68216-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="68216-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="68216-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="68216-125">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="68216-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="68216-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="68216-126">E_FAIL</span></span>|<span data-ttu-id="68216-127">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="68216-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="68216-128">如果方法返回 E_FAIL，则 CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="68216-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="68216-129">对任何宿主方法的后续调用都会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="68216-129">Subsequent calls to any hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68216-130">注解</span><span class="sxs-lookup"><span data-stu-id="68216-130">Remarks</span></span>  

 <span data-ttu-id="68216-131">索引0处的标识是特定于处理器体系结构的标识。</span><span class="sxs-lookup"><span data-stu-id="68216-131">The identity at index 0 is the identity specific to the processor architecture.</span></span> <span data-ttu-id="68216-132">位于索引1处的标识是适用于 Microsoft 中间语言 (MSIL) 的特定于体系结构的程序集。</span><span class="sxs-lookup"><span data-stu-id="68216-132">The identity at index 1 is the architecture-neutral assembly for Microsoft intermediate language (MSIL).</span></span> <span data-ttu-id="68216-133">索引2处的标识不包含体系结构信息。</span><span class="sxs-lookup"><span data-stu-id="68216-133">The identity at index 2 contains no architecture information.</span></span>  
  
 <span data-ttu-id="68216-134">`Get` 通常称为两次。</span><span class="sxs-lookup"><span data-stu-id="68216-134">`Get` is typically called twice.</span></span> <span data-ttu-id="68216-135">第一次调用为提供 null 值 `pwzBuffer` ，并将设置 `pcchBufferSize` 为适合的大小 `pwzBuffer` 。</span><span class="sxs-lookup"><span data-stu-id="68216-135">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="68216-136">第二个调用提供适当大小的 `pwzBuffer` ，并在完成时包含规范程序集标识数据。</span><span class="sxs-lookup"><span data-stu-id="68216-136">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68216-137">要求</span><span class="sxs-lookup"><span data-stu-id="68216-137">Requirements</span></span>  

 <span data-ttu-id="68216-138">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="68216-138">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68216-139">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="68216-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="68216-140">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="68216-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="68216-141">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68216-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68216-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="68216-142">See also</span></span>

- [<span data-ttu-id="68216-143">ICLRProbingAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="68216-143">ICLRProbingAssemblyEnum Interface</span></span>](iclrprobingassemblyenum-interface.md)
- [<span data-ttu-id="68216-144">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="68216-144">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
