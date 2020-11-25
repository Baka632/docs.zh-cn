---
title: ICorRuntimeHost::CurrentDomain 方法
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CurrentDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CurrentDomain
helpviewer_keywords:
- ICorRuntimeHost::CreateDomain method [.NET Framework hosting]
- CurrentDomain method [.NET Framework hosting]
ms.assetid: dd2afb38-675b-4c3c-a9f3-8ab3b133eb02
topic_type:
- apiref
ms.openlocfilehash: 33d56354a560949b2f451df9ef82d4f433951195
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715558"
---
# <a name="icorruntimehostcurrentdomain-method"></a><span data-ttu-id="b678f-102">ICorRuntimeHost::CurrentDomain 方法</span><span class="sxs-lookup"><span data-stu-id="b678f-102">ICorRuntimeHost::CurrentDomain Method</span></span>

<span data-ttu-id="b678f-103">获取类型的接口指针 <xref:System.AppDomain?displayProperty=nameWithType> ，该指针表示当前线程上加载的域。</span><span class="sxs-lookup"><span data-stu-id="b678f-103">Gets an interface pointer of type <xref:System.AppDomain?displayProperty=nameWithType> that represents the domain loaded on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b678f-104">语法</span><span class="sxs-lookup"><span data-stu-id="b678f-104">Syntax</span></span>  
  
```cpp  
HRESULT CurrentDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b678f-105">参数</span><span class="sxs-lookup"><span data-stu-id="b678f-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="b678f-106">弄 <xref:System.AppDomain?displayProperty=nameWithType> 表示线程的当前应用程序域的类型的指针。</span><span class="sxs-lookup"><span data-stu-id="b678f-106">[out] A pointer of type <xref:System.AppDomain?displayProperty=nameWithType> that represents the thread's current application domain.</span></span> <span data-ttu-id="b678f-107">此指针的类型为 `IUnknown` ，因此调用方通常应调用 `QueryInterface` 以获取类型的指针 <xref:System._AppDomain> 。</span><span class="sxs-lookup"><span data-stu-id="b678f-107">This pointer is typed `IUnknown`, so callers should generally call `QueryInterface` to obtain a pointer of type <xref:System._AppDomain>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b678f-108">返回值</span><span class="sxs-lookup"><span data-stu-id="b678f-108">Return Value</span></span>  
  
|<span data-ttu-id="b678f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b678f-109">HRESULT</span></span>|<span data-ttu-id="b678f-110">说明</span><span class="sxs-lookup"><span data-stu-id="b678f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b678f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b678f-111">S_OK</span></span>|<span data-ttu-id="b678f-112">操作成功。</span><span class="sxs-lookup"><span data-stu-id="b678f-112">The operation was successful.</span></span>|  
|<span data-ttu-id="b678f-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="b678f-113">S_FALSE</span></span>|<span data-ttu-id="b678f-114">操作未能完成。</span><span class="sxs-lookup"><span data-stu-id="b678f-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="b678f-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b678f-115">E_FAIL</span></span>|<span data-ttu-id="b678f-116">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="b678f-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="b678f-117">如果某个方法返回 E_FAIL，则公共语言运行时 (CLR) 在该进程中不再可用。</span><span class="sxs-lookup"><span data-stu-id="b678f-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="b678f-118">对任何宿主 Api 的后续调用都会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="b678f-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b678f-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b678f-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b678f-120">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="b678f-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b678f-121">要求</span><span class="sxs-lookup"><span data-stu-id="b678f-121">Requirements</span></span>  

 <span data-ttu-id="b678f-122">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b678f-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b678f-123">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b678f-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b678f-124">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b678f-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b678f-125">**.NET Framework 版本：** 1.0、1。1</span><span class="sxs-lookup"><span data-stu-id="b678f-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b678f-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b678f-126">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="b678f-127">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="b678f-127">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
