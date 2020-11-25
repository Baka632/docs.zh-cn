---
title: ICLRPolicyManager::SetActionOnTimeout 方法
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetActionOnTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetActionOnTimeout
helpviewer_keywords:
- SetActionOnTimeout method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnTimeout method [.NET Framework hosting]
ms.assetid: 38439fa1-2b99-4fa8-a6ec-08afc0f83b9c
topic_type:
- apiref
ms.openlocfilehash: 3ddd78ea35d5709abb30af085b2212a09b28c2ef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725555"
---
# <a name="iclrpolicymanagersetactionontimeout-method"></a><span data-ttu-id="b5f52-102">ICLRPolicyManager::SetActionOnTimeout 方法</span><span class="sxs-lookup"><span data-stu-id="b5f52-102">ICLRPolicyManager::SetActionOnTimeout Method</span></span>

<span data-ttu-id="b5f52-103">指定在指定操作超时时公共语言运行时 (CLR) 应执行的策略操作。</span><span class="sxs-lookup"><span data-stu-id="b5f52-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation times out.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5f52-104">语法</span><span class="sxs-lookup"><span data-stu-id="b5f52-104">Syntax</span></span>  
  
```cpp  
HRESULT SetActionOnTimeout (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5f52-105">参数</span><span class="sxs-lookup"><span data-stu-id="b5f52-105">Parameters</span></span>  

 `operation`  
 <span data-ttu-id="b5f52-106">中 [EClrOperation](eclroperation-enumeration.md) 值之一，指示要为其指定超时操作的操作。</span><span class="sxs-lookup"><span data-stu-id="b5f52-106">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the operation for which to specify the timeout action.</span></span> <span data-ttu-id="b5f52-107">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="b5f52-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="b5f52-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="b5f52-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="b5f52-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="b5f52-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="b5f52-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="b5f52-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="b5f52-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="b5f52-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `action`  
 <span data-ttu-id="b5f52-112">中 [EPolicyAction](epolicyaction-enumeration.md) 值之一，指示操作超时时要执行的策略操作。</span><span class="sxs-lookup"><span data-stu-id="b5f52-112">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the policy action to be taken when the operation times out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b5f52-113">返回值</span><span class="sxs-lookup"><span data-stu-id="b5f52-113">Return Value</span></span>  
  
|<span data-ttu-id="b5f52-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b5f52-114">HRESULT</span></span>|<span data-ttu-id="b5f52-115">说明</span><span class="sxs-lookup"><span data-stu-id="b5f52-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b5f52-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="b5f52-116">S_OK</span></span>|<span data-ttu-id="b5f52-117">`SetActionOnTimeout` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="b5f52-117">`SetActionOnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="b5f52-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b5f52-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b5f52-119">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="b5f52-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b5f52-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b5f52-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b5f52-121">调用超时。</span><span class="sxs-lookup"><span data-stu-id="b5f52-121">The call timed out.</span></span>|  
|<span data-ttu-id="b5f52-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b5f52-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b5f52-123">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="b5f52-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b5f52-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b5f52-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b5f52-125">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="b5f52-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b5f52-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b5f52-126">E_FAIL</span></span>|<span data-ttu-id="b5f52-127">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="b5f52-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b5f52-128">方法返回 E_FAIL 后，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="b5f52-128">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b5f52-129">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="b5f52-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b5f52-130">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b5f52-130">E_INVALIDARG</span></span>|<span data-ttu-id="b5f52-131">无法为指定的设置超时 `operation` ，或者为提供的值无效 `operation` 。</span><span class="sxs-lookup"><span data-stu-id="b5f52-131">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b5f52-132">注解</span><span class="sxs-lookup"><span data-stu-id="b5f52-132">Remarks</span></span>  

 <span data-ttu-id="b5f52-133">超时值可以是 CLR 设置的默认超时值，也可以是主机在 [ICLRPolicyManager：： SetTimeout](iclrpolicymanager-settimeout-method.md) 方法的调用中指定的值。</span><span class="sxs-lookup"><span data-stu-id="b5f52-133">The timeout value can be either the default timeout set by the CLR, or a value specified by the host in a call to the [ICLRPolicyManager::SetTimeout](iclrpolicymanager-settimeout-method.md) method.</span></span>  
  
 <span data-ttu-id="b5f52-134">并非所有策略操作值都可以指定为 CLR 操作的超时行为。</span><span class="sxs-lookup"><span data-stu-id="b5f52-134">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="b5f52-135">`SetActionOnTimeout` 通常仅用于升级行为。</span><span class="sxs-lookup"><span data-stu-id="b5f52-135">`SetActionOnTimeout` is typically used only to escalate behavior.</span></span> <span data-ttu-id="b5f52-136">例如，主机可以指定线程中止进入强制线程中止，但不能指定相反的。</span><span class="sxs-lookup"><span data-stu-id="b5f52-136">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="b5f52-137">下表描述了有效值的有效值 `action` `operation` 。</span><span class="sxs-lookup"><span data-stu-id="b5f52-137">The table below describes the valid `action` values for valid `operation` values.</span></span>  
  
|<span data-ttu-id="b5f52-138">值 `operation`</span><span class="sxs-lookup"><span data-stu-id="b5f52-138">Value for `operation`</span></span>|<span data-ttu-id="b5f52-139">`action` 的有效值</span><span class="sxs-lookup"><span data-stu-id="b5f52-139">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="b5f52-140">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="b5f52-140">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="b5f52-141">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="b5f52-141">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="b5f52-142">- eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="b5f52-142">-   eRudeAbortThread</span></span><br /><span data-ttu-id="b5f52-143">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="b5f52-143">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="b5f52-144">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="b5f52-144">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="b5f52-145">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="b5f52-145">-   eExitProcess</span></span><br /><span data-ttu-id="b5f52-146">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="b5f52-146">-   eFastExitProcess</span></span><br /><span data-ttu-id="b5f52-147">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="b5f52-147">-   eRudeExitProcess</span></span><br /><span data-ttu-id="b5f52-148">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="b5f52-148">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="b5f52-149">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="b5f52-149">OPR_AppDomainUnload</span></span>|<span data-ttu-id="b5f52-150">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="b5f52-150">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="b5f52-151">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="b5f52-151">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="b5f52-152">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="b5f52-152">-   eExitProcess</span></span><br /><span data-ttu-id="b5f52-153">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="b5f52-153">-   eFastExitProcess</span></span><br /><span data-ttu-id="b5f52-154">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="b5f52-154">-   eRudeExitProcess</span></span><br /><span data-ttu-id="b5f52-155">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="b5f52-155">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="b5f52-156">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="b5f52-156">OPR_ProcessExit</span></span>|<span data-ttu-id="b5f52-157">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="b5f52-157">-   eExitProcess</span></span><br /><span data-ttu-id="b5f52-158">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="b5f52-158">-   eFastExitProcess</span></span><br /><span data-ttu-id="b5f52-159">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="b5f52-159">-   eRudeExitProcess</span></span><br /><span data-ttu-id="b5f52-160">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="b5f52-160">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b5f52-161">要求</span><span class="sxs-lookup"><span data-stu-id="b5f52-161">Requirements</span></span>  

 <span data-ttu-id="b5f52-162">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b5f52-162">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5f52-163">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b5f52-163">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b5f52-164">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b5f52-164">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b5f52-165">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5f52-165">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5f52-166">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b5f52-166">See also</span></span>

- [<span data-ttu-id="b5f52-167">EClrOperation 枚举</span><span class="sxs-lookup"><span data-stu-id="b5f52-167">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="b5f52-168">EPolicyAction 枚举</span><span class="sxs-lookup"><span data-stu-id="b5f52-168">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="b5f52-169">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="b5f52-169">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="b5f52-170">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="b5f52-170">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
