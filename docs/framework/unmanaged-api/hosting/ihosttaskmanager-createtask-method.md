---
title: IHostTaskManager::CreateTask 方法
ms.date: 03/30/2017
api_name:
- IHostTaskManager.CreateTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::CreateTask
helpviewer_keywords:
- CreateTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::CreateTask method [.NET Framework hosting]
ms.assetid: a6f8ad36-61e1-42b0-9db2-add575646d18
topic_type:
- apiref
ms.openlocfilehash: 7fdf25d44bdf630e306cf0f5dcb3387a3b0f7c76
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731678"
---
# <a name="ihosttaskmanagercreatetask-method"></a><span data-ttu-id="0c9be-102">IHostTaskManager::CreateTask 方法</span><span class="sxs-lookup"><span data-stu-id="0c9be-102">IHostTaskManager::CreateTask Method</span></span>

<span data-ttu-id="0c9be-103">请求宿主创建新任务。</span><span class="sxs-lookup"><span data-stu-id="0c9be-103">Requests that the host create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c9be-104">语法</span><span class="sxs-lookup"><span data-stu-id="0c9be-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateTask (  
    [in]  DWORD stacksize,
    [in]  LPTHREAD_START_ROUTINE pStartAddress,  
    [in]  PVOID pParameter,  
    [out] IHostTask **ppTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c9be-105">参数</span><span class="sxs-lookup"><span data-stu-id="0c9be-105">Parameters</span></span>  

 `stacksize`  
 <span data-ttu-id="0c9be-106">中请求的堆栈的请求大小（以字节为单位），或默认大小为 0 (零) 。</span><span class="sxs-lookup"><span data-stu-id="0c9be-106">[in] The requested size, in bytes, of the requested stack, or 0 (zero) for the default size.</span></span>  
  
 `pStartAddress`  
 <span data-ttu-id="0c9be-107">中指向任务要执行的函数的指针。</span><span class="sxs-lookup"><span data-stu-id="0c9be-107">[in] A pointer to the function the task is to execute.</span></span>  
  
 `pParameter`  
 <span data-ttu-id="0c9be-108">中指向要传递到函数的用户数据的指针; 如果函数不采用任何参数，则为 null。</span><span class="sxs-lookup"><span data-stu-id="0c9be-108">[in] A pointer to the user data to be passed to the function, or null if the function takes no parameters.</span></span>  
  
 `ppTask`  
 <span data-ttu-id="0c9be-109">弄指向主机创建的 [IHostTask](ihosttask-interface.md) 实例的地址的指针; 如果无法创建任务，则为 null。</span><span class="sxs-lookup"><span data-stu-id="0c9be-109">[out] A pointer to the address of an [IHostTask](ihosttask-interface.md) instance created by the host, or null if the task cannot be created.</span></span> <span data-ttu-id="0c9be-110">在通过调用 [IHostTask：： Start](ihosttask-start-method.md)显式启动任务之前，任务将保持挂起状态。</span><span class="sxs-lookup"><span data-stu-id="0c9be-110">The task remains in a suspended state until it is explicitly started by a call to [IHostTask::Start](ihosttask-start-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0c9be-111">返回值</span><span class="sxs-lookup"><span data-stu-id="0c9be-111">Return Value</span></span>  
  
|<span data-ttu-id="0c9be-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0c9be-112">HRESULT</span></span>|<span data-ttu-id="0c9be-113">说明</span><span class="sxs-lookup"><span data-stu-id="0c9be-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0c9be-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="0c9be-114">S_OK</span></span>|<span data-ttu-id="0c9be-115">`CreateTask` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="0c9be-115">`CreateTask` returned successfully.</span></span>|  
|<span data-ttu-id="0c9be-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0c9be-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0c9be-117"> (CLR) 的公共语言运行时未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="0c9be-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0c9be-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0c9be-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0c9be-119">调用超时。</span><span class="sxs-lookup"><span data-stu-id="0c9be-119">The call timed out.</span></span>|  
|<span data-ttu-id="0c9be-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0c9be-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0c9be-121">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="0c9be-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0c9be-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0c9be-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0c9be-123">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="0c9be-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0c9be-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0c9be-124">E_FAIL</span></span>|<span data-ttu-id="0c9be-125">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="0c9be-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0c9be-126">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="0c9be-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0c9be-127">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="0c9be-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0c9be-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="0c9be-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="0c9be-129">没有足够的内存可用于创建请求的任务。</span><span class="sxs-lookup"><span data-stu-id="0c9be-129">Not enough memory was available to create the requested task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c9be-130">注解</span><span class="sxs-lookup"><span data-stu-id="0c9be-130">Remarks</span></span>  

 <span data-ttu-id="0c9be-131">CLR 调用 `CreateTask` 来请求宿主创建新任务。</span><span class="sxs-lookup"><span data-stu-id="0c9be-131">The CLR calls `CreateTask` to request that the host create a new task.</span></span> <span data-ttu-id="0c9be-132">主机返回指向实例的接口指针 `IHostTask` 。</span><span class="sxs-lookup"><span data-stu-id="0c9be-132">The host returns an interface pointer to an `IHostTask` instance.</span></span> <span data-ttu-id="0c9be-133">返回的任务必须保持挂起状态，直到通过调用显式启动它 `IHostTask::Start` 。</span><span class="sxs-lookup"><span data-stu-id="0c9be-133">The returned task must remain suspended until it is explicitly started by a call to `IHostTask::Start`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c9be-134">要求</span><span class="sxs-lookup"><span data-stu-id="0c9be-134">Requirements</span></span>  

 <span data-ttu-id="0c9be-135">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0c9be-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c9be-136">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="0c9be-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0c9be-137">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0c9be-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0c9be-138">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c9be-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c9be-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c9be-139">See also</span></span>

- [<span data-ttu-id="0c9be-140">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="0c9be-140">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="0c9be-141">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="0c9be-141">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="0c9be-142">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="0c9be-142">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="0c9be-143">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="0c9be-143">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
