---
title: IHostTaskManager::EnterRuntime 方法
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EnterRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EnterRuntime
helpviewer_keywords:
- IHostTaskManager::EnterRuntime method [.NET Framework hosting]
- EnterRuntime method [.NET Framework hosting]
ms.assetid: 1aa7a4b1-636a-4f5e-b834-b406d72f7120
topic_type:
- apiref
ms.openlocfilehash: 11515bbb5717222a0030c1953b4eab4eb1b83bb2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731639"
---
# <a name="ihosttaskmanagerenterruntime-method"></a><span data-ttu-id="30f1f-102">IHostTaskManager::EnterRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="30f1f-102">IHostTaskManager::EnterRuntime Method</span></span>

<span data-ttu-id="30f1f-103">通知宿主对非托管方法的调用（如平台调用方法）正在将执行控制返回到公共语言运行时 (CLR) 。</span><span class="sxs-lookup"><span data-stu-id="30f1f-103">Notifies the host that a call to an unmanaged method, such as a platform invoke method, is returning execution control to the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30f1f-104">语法</span><span class="sxs-lookup"><span data-stu-id="30f1f-104">Syntax</span></span>  
  
```cpp  
HRESULT EnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="30f1f-105">返回值</span><span class="sxs-lookup"><span data-stu-id="30f1f-105">Return Value</span></span>  
  
|<span data-ttu-id="30f1f-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="30f1f-106">HRESULT</span></span>|<span data-ttu-id="30f1f-107">说明</span><span class="sxs-lookup"><span data-stu-id="30f1f-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="30f1f-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="30f1f-108">S_OK</span></span>|<span data-ttu-id="30f1f-109">`EnterRuntime` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="30f1f-109">`EnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="30f1f-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="30f1f-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="30f1f-111">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="30f1f-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="30f1f-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="30f1f-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="30f1f-113">调用超时。</span><span class="sxs-lookup"><span data-stu-id="30f1f-113">The call timed out.</span></span>|  
|<span data-ttu-id="30f1f-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="30f1f-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="30f1f-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="30f1f-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="30f1f-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="30f1f-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="30f1f-117">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="30f1f-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="30f1f-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="30f1f-118">E_FAIL</span></span>|<span data-ttu-id="30f1f-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="30f1f-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="30f1f-120">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="30f1f-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="30f1f-121">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="30f1f-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="30f1f-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="30f1f-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="30f1f-123">没有足够的内存可用来完成请求的分配。</span><span class="sxs-lookup"><span data-stu-id="30f1f-123">Not enough memory was available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30f1f-124">注解</span><span class="sxs-lookup"><span data-stu-id="30f1f-124">Remarks</span></span>  

 <span data-ttu-id="30f1f-125">`EnterRuntime` 调用以通知宿主某个非托管函数（对该函数进行了之前对 [LeaveRuntime](ihosttaskmanager-leaveruntime-method.md) 方法的调用）已完成执行，并将执行控制返回到运行时。</span><span class="sxs-lookup"><span data-stu-id="30f1f-125">`EnterRuntime` is called to notify the host that an unmanaged function, for which an earlier call to the [LeaveRuntime](ihosttaskmanager-leaveruntime-method.md) method was made, has finished executing, and is returning execution control to the runtime.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="30f1f-126">调用[ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md)来通知主机，对其进行之前调用的非托管函数 `LeaveRuntime` 正在调用托管代码。</span><span class="sxs-lookup"><span data-stu-id="30f1f-126">[ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md) is called to notify the host that an unmanaged function, for which an earlier call to `LeaveRuntime` was made, is making a call into managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30f1f-127">要求</span><span class="sxs-lookup"><span data-stu-id="30f1f-127">Requirements</span></span>  

 <span data-ttu-id="30f1f-128">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="30f1f-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30f1f-129">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="30f1f-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="30f1f-130">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="30f1f-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="30f1f-131">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30f1f-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30f1f-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="30f1f-132">See also</span></span>

- <span data-ttu-id="30f1f-133">[高级 COM 互操作性](/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="30f1f-133">[Advanced COM Interoperability](/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span></span>
- [<span data-ttu-id="30f1f-134">如何：使用 PInvoke 从托管代码调用本机 Dll</span><span class="sxs-lookup"><span data-stu-id="30f1f-134">How to: Call Native DLLs from Managed Code Using PInvoke</span></span>](/cpp/dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke)
- [<span data-ttu-id="30f1f-135">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="30f1f-135">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="30f1f-136">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="30f1f-136">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="30f1f-137">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="30f1f-137">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="30f1f-138">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="30f1f-138">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="30f1f-139">LeaveRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="30f1f-139">LeaveRuntime Method</span></span>](ihosttaskmanager-leaveruntime-method.md)
