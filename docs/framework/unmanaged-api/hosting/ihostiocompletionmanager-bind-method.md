---
title: IHostIoCompletionManager::Bind 方法
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.Bind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::Bind
helpviewer_keywords:
- IHostIoCompletionManager::Bind method [.NET Framework hosting]
- Bind method [.NET Framework hosting]
ms.assetid: acd74cb5-7e22-4a07-83c3-82288e1abd9f
topic_type:
- apiref
ms.openlocfilehash: 5231db8de6129ed593e4e0d508b312b7034c01f0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733901"
---
# <a name="ihostiocompletionmanagerbind-method"></a><span data-ttu-id="f1131-102">IHostIoCompletionManager::Bind 方法</span><span class="sxs-lookup"><span data-stu-id="f1131-102">IHostIoCompletionManager::Bind Method</span></span>

<span data-ttu-id="f1131-103">将指定的句柄绑定到由之前对 [CreateIoCompletionPort](ihostiocompletionmanager-createiocompletionport-method.md)的调用创建的 i/o 完成端口。</span><span class="sxs-lookup"><span data-stu-id="f1131-103">Binds the specified handle to an I/O completion port that has been created by an earlier call to [CreateIoCompletionPort](ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1131-104">语法</span><span class="sxs-lookup"><span data-stu-id="f1131-104">Syntax</span></span>  
  
```cpp  
HRESULT Bind (  
    [in] HANDLE hPort,  
    [in] HANDLE hHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1131-105">参数</span><span class="sxs-lookup"><span data-stu-id="f1131-105">Parameters</span></span>  

 `hPort`  
 <span data-ttu-id="f1131-106">中要绑定到的 i/o 完成端口 `hHandle` 。</span><span class="sxs-lookup"><span data-stu-id="f1131-106">[in] The I/O completion port to which to bind `hHandle`.</span></span> <span data-ttu-id="f1131-107">如果的值 `hPort` 为 null， `hHandle` 则绑定到默认 i/o 完成端口。</span><span class="sxs-lookup"><span data-stu-id="f1131-107">If the value of `hPort` is null, `hHandle` is bound to the default I/O completion port.</span></span>  
  
 `hHandle`  
 <span data-ttu-id="f1131-108">中要绑定到的操作系统句柄 `hPort` 。</span><span class="sxs-lookup"><span data-stu-id="f1131-108">[in] The operating system handle to bind to `hPort`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f1131-109">返回值</span><span class="sxs-lookup"><span data-stu-id="f1131-109">Return Value</span></span>  
  
|<span data-ttu-id="f1131-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f1131-110">HRESULT</span></span>|<span data-ttu-id="f1131-111">说明</span><span class="sxs-lookup"><span data-stu-id="f1131-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f1131-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="f1131-112">S_OK</span></span>|<span data-ttu-id="f1131-113">`Bind` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="f1131-113">`Bind` returned successfully.</span></span>|  
|<span data-ttu-id="f1131-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f1131-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f1131-115"> (CLR) 的公共语言运行时未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="f1131-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f1131-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f1131-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f1131-117">调用超时。</span><span class="sxs-lookup"><span data-stu-id="f1131-117">The call timed out.</span></span>|  
|<span data-ttu-id="f1131-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f1131-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f1131-119">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="f1131-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f1131-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f1131-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f1131-121">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="f1131-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f1131-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f1131-122">E_FAIL</span></span>|<span data-ttu-id="f1131-123">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="f1131-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f1131-124">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="f1131-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f1131-125">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="f1131-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1131-126">注解</span><span class="sxs-lookup"><span data-stu-id="f1131-126">Remarks</span></span>  

 <span data-ttu-id="f1131-127">I/o 完成端口是使用对的调用创建的 `CreateIoCompletionPort` 。</span><span class="sxs-lookup"><span data-stu-id="f1131-127">An I/O completion port is created by using a call to `CreateIoCompletionPort`.</span></span> <span data-ttu-id="f1131-128">CLR 调用 `Bind` 将句柄绑定到该端口。</span><span class="sxs-lookup"><span data-stu-id="f1131-128">The CLR calls `Bind` to bind a handle to that port.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f1131-129">当 i/o 请求完成时，主机必须调用 [ICLRIoCompletionManager：： OnComplete](iclriocompletionmanager-oncomplete-method.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="f1131-129">When an I/O request completes, the host must call the [ICLRIoCompletionManager::OnComplete](iclriocompletionmanager-oncomplete-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1131-130">要求</span><span class="sxs-lookup"><span data-stu-id="f1131-130">Requirements</span></span>  

 <span data-ttu-id="f1131-131">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f1131-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1131-132">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f1131-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f1131-133">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f1131-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f1131-134">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1131-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1131-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f1131-135">See also</span></span>

- [<span data-ttu-id="f1131-136">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="f1131-136">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
