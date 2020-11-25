---
title: IHostSecurityContext 接口
ms.date: 03/30/2017
api_name:
- IHostSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityContext
helpviewer_keywords:
- IHostSecurityContext interface [.NET Framework hosting]
ms.assetid: 88e2eac0-8ccb-404f-abbc-287d55159842
topic_type:
- apiref
ms.openlocfilehash: aafaa1d648396ddaa76193fa15cf7f74394777a9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724801"
---
# <a name="ihostsecuritycontext-interface"></a><span data-ttu-id="31d9e-102">IHostSecurityContext 接口</span><span class="sxs-lookup"><span data-stu-id="31d9e-102">IHostSecurityContext Interface</span></span>

<span data-ttu-id="31d9e-103">允许公共语言运行时 (CLR) 维护宿主实现的安全上下文信息。</span><span class="sxs-lookup"><span data-stu-id="31d9e-103">Allows the common language runtime (CLR) to maintain security context information implemented by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="31d9e-104">方法</span><span class="sxs-lookup"><span data-stu-id="31d9e-104">Methods</span></span>  
  
|<span data-ttu-id="31d9e-105">方法</span><span class="sxs-lookup"><span data-stu-id="31d9e-105">Method</span></span>|<span data-ttu-id="31d9e-106">说明</span><span class="sxs-lookup"><span data-stu-id="31d9e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="31d9e-107">Capture 方法</span><span class="sxs-lookup"><span data-stu-id="31d9e-107">Capture Method</span></span>](ihostsecuritycontext-capture-method.md)|<span data-ttu-id="31d9e-108">获取 `IHostSecurityContext` 从对 [IHostSecurityManager：： GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md)的调用返回的实例的克隆。</span><span class="sxs-lookup"><span data-stu-id="31d9e-108">Gets a clone of the `IHostSecurityContext` instance returned from a call to [IHostSecurityManager::GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="31d9e-109">注解</span><span class="sxs-lookup"><span data-stu-id="31d9e-109">Remarks</span></span>  

 <span data-ttu-id="31d9e-110">宿主可以通过 CLR 和用户代码控制对线程标记的所有代码访问。</span><span class="sxs-lookup"><span data-stu-id="31d9e-110">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="31d9e-111">它还可以确保在异步操作或代码点之间跨受限制的代码访问传递完整的安全上下文信息。</span><span class="sxs-lookup"><span data-stu-id="31d9e-111">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="31d9e-112">`IHostSecurityContext` 封装此安全上下文信息，这对于运行时是不透明的。</span><span class="sxs-lookup"><span data-stu-id="31d9e-112">`IHostSecurityContext` encapsulates this security context information, which is opaque to the runtime.</span></span> <span data-ttu-id="31d9e-113">运行时使用捕获此信息 `Capture` ，并将其移动到线程池辅助角色项调度、终结器执行和模块和类构造函数中。</span><span class="sxs-lookup"><span data-stu-id="31d9e-113">The runtime captures this information using `Capture`, and moves it across thread pool worker item dispatch, finalizer execution, and module and class constructors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31d9e-114">要求</span><span class="sxs-lookup"><span data-stu-id="31d9e-114">Requirements</span></span>  

 <span data-ttu-id="31d9e-115">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="31d9e-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31d9e-116">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="31d9e-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="31d9e-117">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="31d9e-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="31d9e-118">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31d9e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31d9e-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31d9e-119">See also</span></span>

- [<span data-ttu-id="31d9e-120">ICLRHostProtectionManager 接口</span><span class="sxs-lookup"><span data-stu-id="31d9e-120">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="31d9e-121">IHostSecurityManager 接口</span><span class="sxs-lookup"><span data-stu-id="31d9e-121">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="31d9e-122">承载接口</span><span class="sxs-lookup"><span data-stu-id="31d9e-122">Hosting Interfaces</span></span>](hosting-interfaces.md)
