---
title: IHostTaskManager::LeaveRuntime 方法
ms.date: 03/30/2017
api_name:
- IHostTaskManager.LeaveRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::LeaveRuntime
helpviewer_keywords:
- IHostTaskManager::LeaveRuntime method [.NET Framework hosting]
- LeaveRuntime method [.NET Framework hosting]
ms.assetid: 43689cc4-e48e-46e5-a22d-bafd768b8759
topic_type:
- apiref
ms.openlocfilehash: 855f8a5d3582bbad59301a344d8a51198c40a051
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673041"
---
# <a name="ihosttaskmanagerleaveruntime-method"></a><span data-ttu-id="7901c-102">IHostTaskManager::LeaveRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="7901c-102">IHostTaskManager::LeaveRuntime Method</span></span>

<span data-ttu-id="7901c-103">通知宿主当前正在执行的任务即将使公共语言运行时 (CLR) 并输入非托管代码。</span><span class="sxs-lookup"><span data-stu-id="7901c-103">Notifies the host that the currently executing task is about to leave the common language runtime (CLR) and enter unmanaged code.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="7901c-104">对应的对 [IHostTaskManager：： EnterRuntime](ihosttaskmanager-enterruntime-method.md) 的调用会通知宿主当前正在执行的任务是重新进入托管代码。</span><span class="sxs-lookup"><span data-stu-id="7901c-104">A corresponding call to [IHostTaskManager::EnterRuntime](ihosttaskmanager-enterruntime-method.md) notifies the host that the currently executing task is reentering managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7901c-105">语法</span><span class="sxs-lookup"><span data-stu-id="7901c-105">Syntax</span></span>  
  
```cpp  
HRESULT LeaveRuntime (  
    [in] SIZE_T target  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7901c-106">参数</span><span class="sxs-lookup"><span data-stu-id="7901c-106">Parameters</span></span>  

 `target`  
 <span data-ttu-id="7901c-107">中要调用的非托管函数的映射可移植可执行文件中的地址。</span><span class="sxs-lookup"><span data-stu-id="7901c-107">[in] The address within the mapped portable executable file of the unmanaged function to be called.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7901c-108">返回值</span><span class="sxs-lookup"><span data-stu-id="7901c-108">Return Value</span></span>  
  
|<span data-ttu-id="7901c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7901c-109">HRESULT</span></span>|<span data-ttu-id="7901c-110">说明</span><span class="sxs-lookup"><span data-stu-id="7901c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7901c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7901c-111">S_OK</span></span>|<span data-ttu-id="7901c-112">`LeaveRuntime` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="7901c-112">`LeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="7901c-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7901c-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7901c-114">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="7901c-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7901c-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7901c-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7901c-116">调用超时。</span><span class="sxs-lookup"><span data-stu-id="7901c-116">The call timed out.</span></span>|  
|<span data-ttu-id="7901c-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7901c-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7901c-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="7901c-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7901c-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7901c-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7901c-120">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="7901c-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7901c-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7901c-121">E_FAIL</span></span>|<span data-ttu-id="7901c-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="7901c-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7901c-123">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="7901c-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7901c-124">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="7901c-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7901c-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="7901c-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="7901c-126">没有足够的内存可用来完成请求的分配。</span><span class="sxs-lookup"><span data-stu-id="7901c-126">Not enough memory is available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7901c-127">注解</span><span class="sxs-lookup"><span data-stu-id="7901c-127">Remarks</span></span>  

 <span data-ttu-id="7901c-128">与非托管代码之间的调用序列可以嵌套。</span><span class="sxs-lookup"><span data-stu-id="7901c-128">Call sequences to and from unmanaged code can be nested.</span></span> <span data-ttu-id="7901c-129">例如，下面的列表描述了一种假设的情况，在这种情况下 `LeaveRuntime` ，对、 [IHostTaskManager：： ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md)、 [IHostTaskManager：： ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md)的调用序列，并 `IHostTaskManager::EnterRuntime` 允许主机标识嵌套层。</span><span class="sxs-lookup"><span data-stu-id="7901c-129">For example, the list below describes a hypothetical situation in which the sequence of calls to `LeaveRuntime`, [IHostTaskManager::ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager::ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md), and `IHostTaskManager::EnterRuntime` allows the host to identify the nested layers.</span></span>  
  
|<span data-ttu-id="7901c-130">操作</span><span class="sxs-lookup"><span data-stu-id="7901c-130">Action</span></span>|<span data-ttu-id="7901c-131">对应的方法调用</span><span class="sxs-lookup"><span data-stu-id="7901c-131">Corresponding Method Call</span></span>|  
|------------|-------------------------------|  
|<span data-ttu-id="7901c-132">托管 Visual Basic 可执行文件使用平台调用来调用以 C 编写的非托管函数。</span><span class="sxs-lookup"><span data-stu-id="7901c-132">A managed Visual Basic executable calls an unmanaged function written in C by using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="7901c-133">非托管 C 函数在用 c # 编写的托管 DLL 中调用方法。</span><span class="sxs-lookup"><span data-stu-id="7901c-133">The unmanaged C function calls a method in a managed DLL written in C#.</span></span>|`IHostTaskManager::ReverseEnterRuntime`|  
|<span data-ttu-id="7901c-134">托管 c # 函数调用另一个用 C 编写的非托管函数，同时也使用平台调用。</span><span class="sxs-lookup"><span data-stu-id="7901c-134">The managed C# function calls another unmanaged function written in C, also using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="7901c-135">第二个非托管函数向 c # 函数返回执行。</span><span class="sxs-lookup"><span data-stu-id="7901c-135">The second unmanaged function returns execution to the C# function.</span></span>|`IHostTaskManager::EnterRuntime`|  
|<span data-ttu-id="7901c-136">C # 函数返回第一个非托管函数的执行。</span><span class="sxs-lookup"><span data-stu-id="7901c-136">The C# function returns execution to the first unmanaged function.</span></span>|`IHostTaskManager::ReverseLeaveRuntime`|  
|<span data-ttu-id="7901c-137">第一个非托管函数会将执行返回到 Visual Basic 程序。</span><span class="sxs-lookup"><span data-stu-id="7901c-137">The first unmanaged function returns execution to the Visual Basic program.</span></span>|`IHostTaskManager::EnterRuntime`|  
  
## <a name="requirements"></a><span data-ttu-id="7901c-138">要求</span><span class="sxs-lookup"><span data-stu-id="7901c-138">Requirements</span></span>  

 <span data-ttu-id="7901c-139">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7901c-139">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7901c-140">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="7901c-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7901c-141">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7901c-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7901c-142">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7901c-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7901c-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7901c-143">See also</span></span>

- [<span data-ttu-id="7901c-144">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="7901c-144">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="7901c-145">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="7901c-145">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="7901c-146">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="7901c-146">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="7901c-147">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="7901c-147">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
