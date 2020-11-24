---
title: IHostSecurityManager 接口
ms.date: 03/30/2017
api_name:
- IHostSecurityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager
helpviewer_keywords:
- IHostSecurityManager interface [.NET Framework hosting]
ms.assetid: c3be2cbd-2d93-438b-9888-9a0251b63c03
topic_type:
- apiref
ms.openlocfilehash: 37f606a67bef79936c81b2a36f12a00d24bd82f1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680529"
---
# <a name="ihostsecuritymanager-interface"></a><span data-ttu-id="0b1b2-102">IHostSecurityManager 接口</span><span class="sxs-lookup"><span data-stu-id="0b1b2-102">IHostSecurityManager Interface</span></span>

<span data-ttu-id="0b1b2-103">提供允许访问和控制当前正在执行的线程的安全上下文的方法。</span><span class="sxs-lookup"><span data-stu-id="0b1b2-103">Provides methods that allow access to and control over the security context of the currently executing thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0b1b2-104">方法</span><span class="sxs-lookup"><span data-stu-id="0b1b2-104">Methods</span></span>  
  
|<span data-ttu-id="0b1b2-105">方法</span><span class="sxs-lookup"><span data-stu-id="0b1b2-105">Method</span></span>|<span data-ttu-id="0b1b2-106">说明</span><span class="sxs-lookup"><span data-stu-id="0b1b2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0b1b2-107">GetSecurityContext 方法</span><span class="sxs-lookup"><span data-stu-id="0b1b2-107">GetSecurityContext Method</span></span>](ihostsecuritymanager-getsecuritycontext-method.md)|<span data-ttu-id="0b1b2-108">从主机获取请求的 [IHostSecurityContext](ihostsecuritycontext-interface.md) 。</span><span class="sxs-lookup"><span data-stu-id="0b1b2-108">Gets the requested [IHostSecurityContext](ihostsecuritycontext-interface.md) from the host.</span></span>|  
|[<span data-ttu-id="0b1b2-109">ImpersonateLoggedOnUser 方法</span><span class="sxs-lookup"><span data-stu-id="0b1b2-109">ImpersonateLoggedOnUser Method</span></span>](ihostsecuritymanager-impersonateloggedonuser-method.md)|<span data-ttu-id="0b1b2-110">请求使用当前用户标识的凭据执行代码。</span><span class="sxs-lookup"><span data-stu-id="0b1b2-110">Requests that code be executed using the credentials of the current user identity.</span></span>|  
|[<span data-ttu-id="0b1b2-111">OpenThreadToken 方法</span><span class="sxs-lookup"><span data-stu-id="0b1b2-111">OpenThreadToken Method</span></span>](ihostsecuritymanager-openthreadtoken-method.md)|<span data-ttu-id="0b1b2-112">打开与当前线程关联的自由访问标记。</span><span class="sxs-lookup"><span data-stu-id="0b1b2-112">Opens the discretionary access token associated with the current thread.</span></span>|  
|[<span data-ttu-id="0b1b2-113">RevertToSelf 方法</span><span class="sxs-lookup"><span data-stu-id="0b1b2-113">RevertToSelf Method</span></span>](ihostsecuritymanager-reverttoself-method.md)|<span data-ttu-id="0b1b2-114">终止当前用户标识的模拟并返回原始线程标记。</span><span class="sxs-lookup"><span data-stu-id="0b1b2-114">Terminates impersonation of the current user identity and returns the original thread token.</span></span>|  
|[<span data-ttu-id="0b1b2-115">SetSecurityContext 方法</span><span class="sxs-lookup"><span data-stu-id="0b1b2-115">SetSecurityContext Method</span></span>](ihostsecuritymanager-setsecuritycontext-method.md)|<span data-ttu-id="0b1b2-116">设置当前正在执行的线程的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="0b1b2-116">Sets the security context for the currently executing thread.</span></span>|  
|[<span data-ttu-id="0b1b2-117">SetThreadToken 方法</span><span class="sxs-lookup"><span data-stu-id="0b1b2-117">SetThreadToken Method</span></span>](ihostsecuritymanager-setthreadtoken-method.md)|<span data-ttu-id="0b1b2-118">设置当前正在执行的线程的句柄。</span><span class="sxs-lookup"><span data-stu-id="0b1b2-118">Sets a handle for the currently executing thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b1b2-119">注解</span><span class="sxs-lookup"><span data-stu-id="0b1b2-119">Remarks</span></span>  

 <span data-ttu-id="0b1b2-120">宿主可以通过公共语言运行时 (CLR) 和用户代码来控制对线程标记的所有代码访问。</span><span class="sxs-lookup"><span data-stu-id="0b1b2-120">A host can control all code access to thread tokens by both the common language runtime (CLR) and user code.</span></span> <span data-ttu-id="0b1b2-121">它还可以确保在异步操作或代码点之间跨受限制的代码访问传递完整的安全上下文信息。</span><span class="sxs-lookup"><span data-stu-id="0b1b2-121">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="0b1b2-122">`IHostSecurityContext` 封装此安全上下文信息，这对于 CLR 是不透明的。</span><span class="sxs-lookup"><span data-stu-id="0b1b2-122">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span>  
  
 <span data-ttu-id="0b1b2-123">CLR 在内部处理托管线程上下文。</span><span class="sxs-lookup"><span data-stu-id="0b1b2-123">The CLR handles managed thread context internally.</span></span> <span data-ttu-id="0b1b2-124">它在以下情况下查询特定于进程的 `IHostSecurityManager` ：</span><span class="sxs-lookup"><span data-stu-id="0b1b2-124">It queries the process-specific `IHostSecurityManager` in the following situations:</span></span>  
  
- <span data-ttu-id="0b1b2-125">终结器线程上的终结器执行期间。</span><span class="sxs-lookup"><span data-stu-id="0b1b2-125">On the finalizer thread, during finalizer execution.</span></span>  
  
- <span data-ttu-id="0b1b2-126">在类和模块构造函数执行期间。</span><span class="sxs-lookup"><span data-stu-id="0b1b2-126">During class and module constructor execution.</span></span>  
  
- <span data-ttu-id="0b1b2-127">在工作线程上的异步点，调用 [IHostThreadPoolManager：： QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="0b1b2-127">At asynchronous points on the worker thread, in calls to the [IHostThreadPoolManager::QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md) method.</span></span>  
  
- <span data-ttu-id="0b1b2-128">用于 i/o 完成端口的服务。</span><span class="sxs-lookup"><span data-stu-id="0b1b2-128">In servicing of I/O completion ports.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b1b2-129">要求</span><span class="sxs-lookup"><span data-stu-id="0b1b2-129">Requirements</span></span>  

 <span data-ttu-id="0b1b2-130">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0b1b2-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b1b2-131">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="0b1b2-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0b1b2-132">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0b1b2-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0b1b2-133">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b1b2-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b1b2-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0b1b2-134">See also</span></span>

- [<span data-ttu-id="0b1b2-135">IHostSecurityContext 接口</span><span class="sxs-lookup"><span data-stu-id="0b1b2-135">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="0b1b2-136">承载接口</span><span class="sxs-lookup"><span data-stu-id="0b1b2-136">Hosting Interfaces</span></span>](hosting-interfaces.md)
