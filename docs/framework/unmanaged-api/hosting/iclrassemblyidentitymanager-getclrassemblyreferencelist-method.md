---
title: ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList 方法
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetCLRAssemblyReferenceList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList
helpviewer_keywords:
- GetClrAssemblyReferenceList method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList method [.NET Framework hosting]
ms.assetid: cb5ffae5-287b-4a87-9ca8-7ce3ae0601b7
topic_type:
- apiref
ms.openlocfilehash: cfc384a71ac7e91181bdec09f0d385bacbe31753
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716663"
---
# <a name="iclrassemblyidentitymanagergetclrassemblyreferencelist-method"></a><span data-ttu-id="4f4d1-102">ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList 方法</span><span class="sxs-lookup"><span data-stu-id="4f4d1-102">ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList Method</span></span>

<span data-ttu-id="4f4d1-103">从提供的部分程序集标识列表中获取指向 [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) 实例的接口指针。</span><span class="sxs-lookup"><span data-stu-id="4f4d1-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f4d1-104">语法</span><span class="sxs-lookup"><span data-stu-id="4f4d1-104">Syntax</span></span>  
  
```cpp  
HRESULT  GetCLRAssemblyReferenceList (  
    [in] LPCWSTR *ppwzAssemblyReferences,  
    [in] DWORD    dwNumOfReferences,  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f4d1-105">参数</span><span class="sxs-lookup"><span data-stu-id="4f4d1-105">Parameters</span></span>  

 `ppwzAssemblyReferences`  
 <span data-ttu-id="4f4d1-106">中以 null 结尾的字符串数组，格式为 "name，property = value ..."，它指定部分程序集标识的列表。</span><span class="sxs-lookup"><span data-stu-id="4f4d1-106">[in] An array of null-terminated strings in the form "name, property=value..." that specify a list of partial assembly identities.</span></span>  
  
 `dwNumOfReferences`  
 <span data-ttu-id="4f4d1-107">中中的项数 `ppwzAssemblyReferences` 。</span><span class="sxs-lookup"><span data-stu-id="4f4d1-107">[in] The number of items in `ppwzAssemblyReferences`.</span></span>  
  
 `ppReferenceList`  
 <span data-ttu-id="4f4d1-108">弄一个指向对象的接口指针， `ICLRAssemblyReferenceList` 该对象包含在中指定的程序集列表的程序集标识数据 `ppwzAssemblyReferences` 。</span><span class="sxs-lookup"><span data-stu-id="4f4d1-108">[out] An interface pointer to an `ICLRAssemblyReferenceList` object that contains the assembly identity data for the list of assemblies specified in `ppwzAssemblyReferences`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4f4d1-109">返回值</span><span class="sxs-lookup"><span data-stu-id="4f4d1-109">Return Value</span></span>  
  
|<span data-ttu-id="4f4d1-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4f4d1-110">HRESULT</span></span>|<span data-ttu-id="4f4d1-111">说明</span><span class="sxs-lookup"><span data-stu-id="4f4d1-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4f4d1-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="4f4d1-112">S_OK</span></span>|<span data-ttu-id="4f4d1-113">该方法已成功返回。</span><span class="sxs-lookup"><span data-stu-id="4f4d1-113">The method returned successfully.</span></span>|  
|<span data-ttu-id="4f4d1-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4f4d1-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4f4d1-115"> (CLR) 的公共语言运行时未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="4f4d1-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4f4d1-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4f4d1-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4f4d1-117">调用超时。</span><span class="sxs-lookup"><span data-stu-id="4f4d1-117">The call timed out.</span></span>|  
|<span data-ttu-id="4f4d1-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4f4d1-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4f4d1-119">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="4f4d1-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4f4d1-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4f4d1-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4f4d1-121">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="4f4d1-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4f4d1-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4f4d1-122">E_FAIL</span></span>|<span data-ttu-id="4f4d1-123">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="4f4d1-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4f4d1-124">如果方法返回 E_FAIL，则 CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="4f4d1-124">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4f4d1-125">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="4f4d1-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4f4d1-126">要求</span><span class="sxs-lookup"><span data-stu-id="4f4d1-126">Requirements</span></span>  

 <span data-ttu-id="4f4d1-127">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4f4d1-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f4d1-128">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="4f4d1-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4f4d1-129">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4f4d1-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4f4d1-130">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f4d1-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f4d1-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4f4d1-131">See also</span></span>

- [<span data-ttu-id="4f4d1-132">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="4f4d1-132">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="4f4d1-133">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="4f4d1-133">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
