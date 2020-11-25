---
title: ICLRRuntimeHost::SetHostControl 方法
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.SetHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::SetHostControl
helpviewer_keywords:
- SetHostControl method [.NET Framework hosting]
- ICLRRuntimeHost::SetHostControl method [.NET Framework hosting]
ms.assetid: 6136be87-e631-4756-81ed-74b66581bad4
topic_type:
- apiref
ms.openlocfilehash: 32483be43d4d4fe9d185c091e15a13c6feb95600
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728818"
---
# <a name="iclrruntimehostsethostcontrol-method"></a><span data-ttu-id="2d8a4-102">ICLRRuntimeHost::SetHostControl 方法</span><span class="sxs-lookup"><span data-stu-id="2d8a4-102">ICLRRuntimeHost::SetHostControl Method</span></span>

<span data-ttu-id="2d8a4-103">设置公共语言运行时 (CLR) 可用于获取宿主的 [IHostControl 接口](ihostcontrol-interface.md)实现的接口指针。</span><span class="sxs-lookup"><span data-stu-id="2d8a4-103">Sets the interface pointer that the common language runtime (CLR) can use to get the host's implementation of [IHostControl Interface](ihostcontrol-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d8a4-104">语法</span><span class="sxs-lookup"><span data-stu-id="2d8a4-104">Syntax</span></span>  
  
```cpp  
HRESULT SetHostControl(  
    [in] IHostControl* pHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d8a4-105">参数</span><span class="sxs-lookup"><span data-stu-id="2d8a4-105">Parameters</span></span>  

 `pHostControl`  
 <span data-ttu-id="2d8a4-106">中指向主机的 [IHostControl 接口](ihostcontrol-interface.md)实现的接口指针。</span><span class="sxs-lookup"><span data-stu-id="2d8a4-106">[in] An interface pointer to the host's implementation of [IHostControl Interface](ihostcontrol-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2d8a4-107">返回值</span><span class="sxs-lookup"><span data-stu-id="2d8a4-107">Return Value</span></span>  
  
|<span data-ttu-id="2d8a4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2d8a4-108">HRESULT</span></span>|<span data-ttu-id="2d8a4-109">说明</span><span class="sxs-lookup"><span data-stu-id="2d8a4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2d8a4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2d8a4-110">S_OK</span></span>|<span data-ttu-id="2d8a4-111">`SetHostControl` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="2d8a4-111">`SetHostControl` returned successfully.</span></span>|  
|<span data-ttu-id="2d8a4-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2d8a4-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2d8a4-113">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="2d8a4-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2d8a4-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2d8a4-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2d8a4-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="2d8a4-115">The call timed out.</span></span>|  
|<span data-ttu-id="2d8a4-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2d8a4-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2d8a4-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="2d8a4-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2d8a4-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2d8a4-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2d8a4-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="2d8a4-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2d8a4-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2d8a4-120">E_FAIL</span></span>|<span data-ttu-id="2d8a4-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="2d8a4-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2d8a4-122">如果方法返回 E_FAIL，则 CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="2d8a4-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2d8a4-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="2d8a4-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2d8a4-124">E_CLR_ALREADY_STARTED</span><span class="sxs-lookup"><span data-stu-id="2d8a4-124">E_CLR_ALREADY_STARTED</span></span>|<span data-ttu-id="2d8a4-125">CLR 已初始化。</span><span class="sxs-lookup"><span data-stu-id="2d8a4-125">The CLR has already been initialized.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d8a4-126">注解</span><span class="sxs-lookup"><span data-stu-id="2d8a4-126">Remarks</span></span>  

 <span data-ttu-id="2d8a4-127">必须在 `SetHostControl` 初始化 CLR 之前调用，也就是说，在调用 [Start 方法](iclrruntimehost-start-method.md) 或使用任何 [元数据接口](../metadata/metadata-interfaces.md)之前。</span><span class="sxs-lookup"><span data-stu-id="2d8a4-127">You must call `SetHostControl` before the CLR is initialized, that is, before you call [Start Method](iclrruntimehost-start-method.md) or use any of the [Metadata Interfaces](../metadata/metadata-interfaces.md).</span></span> <span data-ttu-id="2d8a4-128">建议在 `SetHostControl` 调用 [CorBindToCurrentRuntime 函数](corbindtocurrentruntime-function.md) 或 [CorBindToRuntimeEx 函数](corbindtoruntimeex-function.md)之后立即调用。</span><span class="sxs-lookup"><span data-stu-id="2d8a4-128">It is recommended that you call `SetHostControl` immediately after calling [CorBindToCurrentRuntime Function](corbindtocurrentruntime-function.md) or [CorBindToRuntimeEx Function](corbindtoruntimeex-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d8a4-129">要求</span><span class="sxs-lookup"><span data-stu-id="2d8a4-129">Requirements</span></span>  

 <span data-ttu-id="2d8a4-130">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2d8a4-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d8a4-131">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2d8a4-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2d8a4-132">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2d8a4-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2d8a4-133">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d8a4-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d8a4-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2d8a4-134">See also</span></span>

- [<span data-ttu-id="2d8a4-135">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="2d8a4-135">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
- [<span data-ttu-id="2d8a4-136">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="2d8a4-136">IHostControl Interface</span></span>](ihostcontrol-interface.md)
