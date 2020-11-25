---
title: LockClrVersion 函数
ms.date: 03/30/2017
api_name:
- LockClrVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- LockClrVersion
helpviewer_keywords:
- LockClrVersion function [.NET Framework hosting]
ms.assetid: 1318ee37-c43b-40eb-bbe8-88fc46453d74
topic_type:
- apiref
ms.openlocfilehash: 2ff08ec8f194ccc9e968b3a7ee017afe788f4b03
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704924"
---
# <a name="lockclrversion-function"></a><span data-ttu-id="cc3b0-102">LockClrVersion 函数</span><span class="sxs-lookup"><span data-stu-id="cc3b0-102">LockClrVersion Function</span></span>

<span data-ttu-id="cc3b0-103">允许宿主在显式初始化 CLR 之前确定将在进程内使用的公共语言运行时)  (版本。</span><span class="sxs-lookup"><span data-stu-id="cc3b0-103">Allows the host to determine which version of the common language runtime (CLR) will be used within the process before explicitly initializing the CLR.</span></span>  
  
 <span data-ttu-id="cc3b0-104">此函数已在 .NET Framework 4 中弃用。</span><span class="sxs-lookup"><span data-stu-id="cc3b0-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc3b0-105">语法</span><span class="sxs-lookup"><span data-stu-id="cc3b0-105">Syntax</span></span>  
  
```cpp  
HRESULT LockClrVersion (  
    [in] FLockClrVersionCallback   hostCallback,  
    [in] FLockClrVersionCallback  *pBeginHostSetup,  
    [in] FLockClrVersionCallback  *pEndHostSetup  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc3b0-106">参数</span><span class="sxs-lookup"><span data-stu-id="cc3b0-106">Parameters</span></span>  

 `hostCallback`  
 <span data-ttu-id="cc3b0-107">中CLR 在初始化时调用的函数。</span><span class="sxs-lookup"><span data-stu-id="cc3b0-107">[in] The function to be called by the CLR upon initialization.</span></span>  
  
 `pBeginHostSetup`  
 <span data-ttu-id="cc3b0-108">中由宿主调用以通知 CLR 初始化正在启动的函数。</span><span class="sxs-lookup"><span data-stu-id="cc3b0-108">[in] The function to be called by the host to inform the CLR that initialization is starting.</span></span>  
  
 `pEndHostSetup`  
 <span data-ttu-id="cc3b0-109">中由宿主调用以通知 CLR 初始化已完成的函数。</span><span class="sxs-lookup"><span data-stu-id="cc3b0-109">[in] The function to be called by the host to inform the CLR that initialization is complete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cc3b0-110">返回值</span><span class="sxs-lookup"><span data-stu-id="cc3b0-110">Return Value</span></span>  

 <span data-ttu-id="cc3b0-111">除以下值外，此方法还返回 Winerror.h 中定义的标准 COM 错误代码。</span><span class="sxs-lookup"><span data-stu-id="cc3b0-111">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="cc3b0-112">返回代码</span><span class="sxs-lookup"><span data-stu-id="cc3b0-112">Return code</span></span>|<span data-ttu-id="cc3b0-113">说明</span><span class="sxs-lookup"><span data-stu-id="cc3b0-113">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="cc3b0-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="cc3b0-114">S_OK</span></span>|<span data-ttu-id="cc3b0-115">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="cc3b0-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="cc3b0-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="cc3b0-116">E_INVALIDARG</span></span>|<span data-ttu-id="cc3b0-117">一个或多个参数为 null。</span><span class="sxs-lookup"><span data-stu-id="cc3b0-117">One or more of the arguments is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc3b0-118">注解</span><span class="sxs-lookup"><span data-stu-id="cc3b0-118">Remarks</span></span>  

 <span data-ttu-id="cc3b0-119">宿主在 `LockClrVersion` 初始化 CLR 前调用。</span><span class="sxs-lookup"><span data-stu-id="cc3b0-119">The host calls `LockClrVersion` before initializing the CLR.</span></span> <span data-ttu-id="cc3b0-120">`LockClrVersion` 使用三个参数，所有这些参数都是 [FLockClrVersionCallback](flockclrversioncallback-function-pointer.md)类型的回调。</span><span class="sxs-lookup"><span data-stu-id="cc3b0-120">`LockClrVersion` takes three parameters, all of which are callbacks of type [FLockClrVersionCallback](flockclrversioncallback-function-pointer.md).</span></span> <span data-ttu-id="cc3b0-121">此类型的定义如下。</span><span class="sxs-lookup"><span data-stu-id="cc3b0-121">This type is defined as follows.</span></span>  
  
```cpp  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 <span data-ttu-id="cc3b0-122">在运行时初始化时执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="cc3b0-122">The following steps occur upon initialization of the runtime:</span></span>  
  
1. <span data-ttu-id="cc3b0-123">宿主调用 [CorBindToRuntimeEx](corbindtoruntimeex-function.md) 或其他运行时初始化函数之一。</span><span class="sxs-lookup"><span data-stu-id="cc3b0-123">The host calls [CorBindToRuntimeEx](corbindtoruntimeex-function.md) or one of the other runtime initialization functions.</span></span> <span data-ttu-id="cc3b0-124">或者，宿主可以使用 COM 对象激活来初始化运行时。</span><span class="sxs-lookup"><span data-stu-id="cc3b0-124">Alternatively, the host could initialize the runtime using COM object activation.</span></span>  
  
2. <span data-ttu-id="cc3b0-125">运行时调用由参数指定的函数 `hostCallback` 。</span><span class="sxs-lookup"><span data-stu-id="cc3b0-125">The runtime calls the function specified by the `hostCallback` parameter.</span></span>  
  
3. <span data-ttu-id="cc3b0-126">指定的函数将 `hostCallback` 执行以下序列调用：</span><span class="sxs-lookup"><span data-stu-id="cc3b0-126">The function specified by `hostCallback` then makes the following sequence of calls:</span></span>  
  
    - <span data-ttu-id="cc3b0-127">由参数指定的函数 `pBeginHostSetup` 。</span><span class="sxs-lookup"><span data-stu-id="cc3b0-127">The function specified by the `pBeginHostSetup` parameter.</span></span>  
  
    - <span data-ttu-id="cc3b0-128">`CorBindToRuntimeEx` (或另一个运行时初始化函数) 。</span><span class="sxs-lookup"><span data-stu-id="cc3b0-128">`CorBindToRuntimeEx` (or another runtime initialization function).</span></span>  
  
    - <span data-ttu-id="cc3b0-129">[ICLRRuntimeHost：： SetHostControl](iclrruntimehost-sethostcontrol-method.md)。</span><span class="sxs-lookup"><span data-stu-id="cc3b0-129">[ICLRRuntimeHost::SetHostControl](iclrruntimehost-sethostcontrol-method.md).</span></span>  
  
    - <span data-ttu-id="cc3b0-130">[ICLRRuntimeHost：： Start](iclrruntimehost-start-method.md)。</span><span class="sxs-lookup"><span data-stu-id="cc3b0-130">[ICLRRuntimeHost::Start](iclrruntimehost-start-method.md).</span></span>  
  
    - <span data-ttu-id="cc3b0-131">由参数指定的函数 `pEndHostSetup` 。</span><span class="sxs-lookup"><span data-stu-id="cc3b0-131">The function specified by the `pEndHostSetup` parameter.</span></span>  
  
 <span data-ttu-id="cc3b0-132">从到的所有 `pBeginHostSetup` 调用 `pEndHostSetup` 都必须在具有相同逻辑堆栈的单个线程或纤程上发生。</span><span class="sxs-lookup"><span data-stu-id="cc3b0-132">All the calls from `pBeginHostSetup` to `pEndHostSetup` must occur on a single thread or fiber, with the same logical stack.</span></span> <span data-ttu-id="cc3b0-133">此线程可以与调用的线程不同 `hostCallback` 。</span><span class="sxs-lookup"><span data-stu-id="cc3b0-133">This thread can be different from the thread upon which `hostCallback` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc3b0-134">要求</span><span class="sxs-lookup"><span data-stu-id="cc3b0-134">Requirements</span></span>  

 <span data-ttu-id="cc3b0-135">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cc3b0-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc3b0-136">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="cc3b0-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cc3b0-137">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cc3b0-137">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cc3b0-138">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc3b0-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc3b0-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cc3b0-139">See also</span></span>

- [<span data-ttu-id="cc3b0-140">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="cc3b0-140">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
