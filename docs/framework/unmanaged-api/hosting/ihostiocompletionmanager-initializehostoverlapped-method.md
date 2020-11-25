---
title: IHostIoCompletionManager::InitializeHostOverlapped 方法
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.InitializeHostOverlapped
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped
helpviewer_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped method [.NET Framework hosting]
- InitializeHostOverlapped method [.NET Framework hosting]
ms.assetid: c35199bf-bc47-4901-b467-4e8a37644bbb
topic_type:
- apiref
ms.openlocfilehash: 397dbbeb0b85cb549a8b5917f977ecb13b3d6539
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720212"
---
# <a name="ihostiocompletionmanagerinitializehostoverlapped-method"></a><span data-ttu-id="ccdd9-102">IHostIoCompletionManager::InitializeHostOverlapped 方法</span><span class="sxs-lookup"><span data-stu-id="ccdd9-102">IHostIoCompletionManager::InitializeHostOverlapped Method</span></span>

<span data-ttu-id="ccdd9-103">向宿主提供初始化任何自定义数据以追加到 `OVERLAPPED` 用于异步 i/o 请求的 Win32 结构的机会。</span><span class="sxs-lookup"><span data-stu-id="ccdd9-103">Provides the host with an opportunity to initialize any custom data to append to a Win32 `OVERLAPPED` structure that is used for asynchronous I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccdd9-104">语法</span><span class="sxs-lookup"><span data-stu-id="ccdd9-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeHostOverlapped (  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ccdd9-105">参数</span><span class="sxs-lookup"><span data-stu-id="ccdd9-105">Parameters</span></span>  

 `pvOverlapped`  
 <span data-ttu-id="ccdd9-106">中指向要 `OVERLAPPED` 包含在 i/o 请求中的 Win32 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="ccdd9-106">[in] A pointer to the Win32 `OVERLAPPED` structure to be included with the I/O request.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ccdd9-107">返回值</span><span class="sxs-lookup"><span data-stu-id="ccdd9-107">Return Value</span></span>  
  
|<span data-ttu-id="ccdd9-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ccdd9-108">HRESULT</span></span>|<span data-ttu-id="ccdd9-109">说明</span><span class="sxs-lookup"><span data-stu-id="ccdd9-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ccdd9-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ccdd9-110">S_OK</span></span>|<span data-ttu-id="ccdd9-111">`InitializeHostOverlapped` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="ccdd9-111">`InitializeHostOverlapped` returned successfully.</span></span>|  
|<span data-ttu-id="ccdd9-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ccdd9-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ccdd9-113"> (CLR) 的公共语言运行时未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="ccdd9-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ccdd9-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ccdd9-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ccdd9-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="ccdd9-115">The call timed out.</span></span>|  
|<span data-ttu-id="ccdd9-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ccdd9-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ccdd9-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="ccdd9-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ccdd9-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ccdd9-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ccdd9-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="ccdd9-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ccdd9-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ccdd9-120">E_FAIL</span></span>|<span data-ttu-id="ccdd9-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="ccdd9-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ccdd9-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="ccdd9-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ccdd9-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="ccdd9-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ccdd9-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="ccdd9-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="ccdd9-125">没有足够的内存可用于分配请求的资源。</span><span class="sxs-lookup"><span data-stu-id="ccdd9-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ccdd9-126">注解</span><span class="sxs-lookup"><span data-stu-id="ccdd9-126">Remarks</span></span>  

 <span data-ttu-id="ccdd9-127">Windows 平台函数使用 `OVERLAPPED` 结构来存储异步 i/o 请求的状态。</span><span class="sxs-lookup"><span data-stu-id="ccdd9-127">The Windows Platform functions use the `OVERLAPPED` structure to store state for asynchronous I/O requests.</span></span> <span data-ttu-id="ccdd9-128">CLR 将调用 `InitializeHostOverlapped` 方法，以为宿主向宿主追加自定义数据的机会 `OVERLAPPED` 。</span><span class="sxs-lookup"><span data-stu-id="ccdd9-128">The CLR calls the `InitializeHostOverlapped` method to give the host the opportunity to append custom data to an `OVERLAPPED` instance.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ccdd9-129">若要从自定义数据块开始，主机必须将偏移量设置为 `OVERLAPPED` () 结构的大小 `sizeof(OVERLAPPED)` 。</span><span class="sxs-lookup"><span data-stu-id="ccdd9-129">To get to the beginning of their custom data block, hosts must set the offset to the size of the `OVERLAPPED` structure (`sizeof(OVERLAPPED)`).</span></span>  
  
 <span data-ttu-id="ccdd9-130">E_OUTOFMEMORY 的返回值指示宿主未能初始化其自定义数据。</span><span class="sxs-lookup"><span data-stu-id="ccdd9-130">A return value of E_OUTOFMEMORY indicates that the host has failed to initialize its custom data.</span></span> <span data-ttu-id="ccdd9-131">在这种情况下，CLR 将报告错误并导致调用失败。</span><span class="sxs-lookup"><span data-stu-id="ccdd9-131">In this case, the CLR reports an error and fails the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccdd9-132">要求</span><span class="sxs-lookup"><span data-stu-id="ccdd9-132">Requirements</span></span>  

 <span data-ttu-id="ccdd9-133">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ccdd9-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccdd9-134">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ccdd9-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ccdd9-135">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ccdd9-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ccdd9-136">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccdd9-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccdd9-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ccdd9-137">See also</span></span>

- [<span data-ttu-id="ccdd9-138">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="ccdd9-138">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="ccdd9-139">GetHostOverlappedSize 方法</span><span class="sxs-lookup"><span data-stu-id="ccdd9-139">GetHostOverlappedSize Method</span></span>](ihostiocompletionmanager-gethostoverlappedsize-method.md)
- [<span data-ttu-id="ccdd9-140">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="ccdd9-140">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
