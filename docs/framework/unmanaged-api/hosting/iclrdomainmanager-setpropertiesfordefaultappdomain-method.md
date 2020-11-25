---
title: ICLRDomainManager::SetPropertiesForDefaultAppDomain 方法
ms.date: 03/30/2017
api_name:
- ICLRDomainManager.SetPropertiesForDefaultAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain
helpviewer_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
- SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 43e61c4b-c435-45ec-9ef6-c68403aa4200
ms.openlocfilehash: b5577d0444caf14fb47d9d7e2de60a8399378db7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702129"
---
# <a name="iclrdomainmanagersetpropertiesfordefaultappdomain-method"></a><span data-ttu-id="45a59-102">ICLRDomainManager::SetPropertiesForDefaultAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="45a59-102">ICLRDomainManager::SetPropertiesForDefaultAppDomain Method</span></span>

<span data-ttu-id="45a59-103">设置将用于初始化默认应用程序域的属性。</span><span class="sxs-lookup"><span data-stu-id="45a59-103">Sets properties that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45a59-104">语法</span><span class="sxs-lookup"><span data-stu-id="45a59-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPropertiesForDefaultAppDomain(  
    [in] DWORD nProperties,  
    [in] LPCWSTR *pwszPropertyNames,  
    [in] LPCWSTR *pwszPropertyValues  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45a59-105">参数</span><span class="sxs-lookup"><span data-stu-id="45a59-105">Parameters</span></span>  

 `nProperties`  
 <span data-ttu-id="45a59-106">中和中的项数 `pwszPropertyNames` `pwszPropertyValues` 。</span><span class="sxs-lookup"><span data-stu-id="45a59-106">[in] The number of entries in `pwszPropertyNames` and `pwszPropertyValues`.</span></span>  
  
 `pwszPropertyNames`  
 <span data-ttu-id="45a59-107">中属性名称的数组; 如果没有属性，则为 null。</span><span class="sxs-lookup"><span data-stu-id="45a59-107">[in] An array of property names, or null if there are no properties.</span></span> <span data-ttu-id="45a59-108">目前，此方法识别的唯一属性名称为 "PARTIAL_TRUST_VISIBLE_ASSEMBLIES"。</span><span class="sxs-lookup"><span data-stu-id="45a59-108">Currently, the only property name that is recognized by this method is "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".</span></span>  
  
 `pwszPropertyValues`  
 <span data-ttu-id="45a59-109">中属性值的数组; 如果没有属性，则为 null。</span><span class="sxs-lookup"><span data-stu-id="45a59-109">[in] An array of property values, or null if there are no properties.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="45a59-110">返回值</span><span class="sxs-lookup"><span data-stu-id="45a59-110">Return Value</span></span>  

 <span data-ttu-id="45a59-111">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="45a59-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="45a59-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="45a59-112">HRESULT</span></span>|<span data-ttu-id="45a59-113">说明</span><span class="sxs-lookup"><span data-stu-id="45a59-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="45a59-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="45a59-114">S_OK</span></span>|<span data-ttu-id="45a59-115">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="45a59-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="45a59-116">HRESULT_FROM_WIN32 (ERROR_UNKNOWN_PROPERTY) </span><span class="sxs-lookup"><span data-stu-id="45a59-116">HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)</span></span>|<span data-ttu-id="45a59-117">`pwszPropertyNames` 包含此方法无法识别的属性名称。</span><span class="sxs-lookup"><span data-stu-id="45a59-117">`pwszPropertyNames` includes a property name that is not recognized by this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45a59-118">注解</span><span class="sxs-lookup"><span data-stu-id="45a59-118">Remarks</span></span>  

 <span data-ttu-id="45a59-119">"PARTIAL_TRUST_VISIBLE_ASSEMBLIES" 的属性值是一个程序集的列表，这些程序集具有 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 带有标志的条件性 (APTCA) 特性 <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> ，在默认应用程序域中对部分受信任的调用方可见。</span><span class="sxs-lookup"><span data-stu-id="45a59-119">The property value for "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" is a list of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute with the <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> flag, which are to be made visible to partially trusted callers in the default application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45a59-120">要求</span><span class="sxs-lookup"><span data-stu-id="45a59-120">Requirements</span></span>  

 <span data-ttu-id="45a59-121">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="45a59-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45a59-122">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="45a59-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="45a59-123">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="45a59-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="45a59-124">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45a59-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45a59-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="45a59-125">See also</span></span>

- [<span data-ttu-id="45a59-126">承载</span><span class="sxs-lookup"><span data-stu-id="45a59-126">Hosting</span></span>](index.md)
- [<span data-ttu-id="45a59-127">ICLRDomainManager 接口</span><span class="sxs-lookup"><span data-stu-id="45a59-127">ICLRDomainManager Interface</span></span>](iclrdomainmanager-interface.md)
