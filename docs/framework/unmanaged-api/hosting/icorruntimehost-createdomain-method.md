---
title: ICorRuntimeHost::CreateDomain 方法
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomain
helpviewer_keywords:
- CreateDomain method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomain method [.NET Framework hosting]
ms.assetid: b96c5ef3-a9df-4c7c-9952-432d3272cb5c
topic_type:
- apiref
ms.openlocfilehash: c495ce47b699d2e32d1f02e4afcf0444a9930c34
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723904"
---
# <a name="icorruntimehostcreatedomain-method"></a><span data-ttu-id="5457f-102">ICorRuntimeHost::CreateDomain 方法</span><span class="sxs-lookup"><span data-stu-id="5457f-102">ICorRuntimeHost::CreateDomain Method</span></span>

<span data-ttu-id="5457f-103">创建应用程序域。</span><span class="sxs-lookup"><span data-stu-id="5457f-103">Creates an application domain.</span></span> <span data-ttu-id="5457f-104">调用方接收类型为的实例的接口指针 <xref:System._AppDomain> <xref:System.AppDomain?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="5457f-104">The caller receives an interface pointer of type <xref:System._AppDomain> to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5457f-105">语法</span><span class="sxs-lookup"><span data-stu-id="5457f-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateDomain (  
    [in] LPWSTR    pwzFriendlyName,  
    [in] IUnknown* pIdentityArray,  
    [out] void   **pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5457f-106">参数</span><span class="sxs-lookup"><span data-stu-id="5457f-106">Parameters</span></span>  

 `pwzFriendlyName`  
 <span data-ttu-id="5457f-107">中用于给域指定友好名称的可选参数。</span><span class="sxs-lookup"><span data-stu-id="5457f-107">[in] An optional parameter used to give a friendly name to the domain.</span></span> <span data-ttu-id="5457f-108">此友好名称可在用户界面（例如调试器）中显示，以标识域。</span><span class="sxs-lookup"><span data-stu-id="5457f-108">This friendly name can be displayed in user interfaces such as debuggers to identify the domain.</span></span>  
  
 `pIdentityArray`  
 <span data-ttu-id="5457f-109">中指向实例的可选指针数组， `IIdentity` 这些实例表示通过安全策略映射以建立权限集的证据。</span><span class="sxs-lookup"><span data-stu-id="5457f-109">[in] An optional array of pointers to `IIdentity` instances that represent evidence mapped through security policy to establish a  permission set.</span></span> <span data-ttu-id="5457f-110">`IIdentity`可以通过调用[CreateEvidence](icorruntimehost-createevidence-method.md)方法来获取对象。</span><span class="sxs-lookup"><span data-stu-id="5457f-110">An `IIdentity` object can be obtained by calling the [CreateEvidence](icorruntimehost-createevidence-method.md) method.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="5457f-111">弄类型为的接口指针 <xref:System._AppDomain> <xref:System.AppDomain?displayProperty=nameWithType> ，可用于进一步控制域。</span><span class="sxs-lookup"><span data-stu-id="5457f-111">[out] An interface pointer of type <xref:System._AppDomain> to an instance of <xref:System.AppDomain?displayProperty=nameWithType> that can be used to further control the domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5457f-112">返回值</span><span class="sxs-lookup"><span data-stu-id="5457f-112">Return Value</span></span>  
  
|<span data-ttu-id="5457f-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5457f-113">HRESULT</span></span>|<span data-ttu-id="5457f-114">说明</span><span class="sxs-lookup"><span data-stu-id="5457f-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5457f-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="5457f-115">S_OK</span></span>|<span data-ttu-id="5457f-116">操作成功。</span><span class="sxs-lookup"><span data-stu-id="5457f-116">The operation was successful.</span></span>|  
|<span data-ttu-id="5457f-117">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="5457f-117">S_FALSE</span></span>|<span data-ttu-id="5457f-118">操作未能完成。</span><span class="sxs-lookup"><span data-stu-id="5457f-118">The operation failed to complete.</span></span>|  
|<span data-ttu-id="5457f-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5457f-119">E_FAIL</span></span>|<span data-ttu-id="5457f-120">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="5457f-120">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="5457f-121">如果某个方法返回 E_FAIL，则公共语言运行时 (CLR) 在该进程中不再可用。</span><span class="sxs-lookup"><span data-stu-id="5457f-121">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="5457f-122">对任何宿主 Api 的后续调用都会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="5457f-122">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5457f-123">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5457f-123">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5457f-124">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="5457f-124">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5457f-125">要求</span><span class="sxs-lookup"><span data-stu-id="5457f-125">Requirements</span></span>  

 <span data-ttu-id="5457f-126">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5457f-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5457f-127">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5457f-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5457f-128">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5457f-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5457f-129">**.NET Framework 版本：** 1.0、1。1</span><span class="sxs-lookup"><span data-stu-id="5457f-129">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5457f-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5457f-130">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="5457f-131">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="5457f-131">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
