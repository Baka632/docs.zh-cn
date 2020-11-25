---
title: ICLRRuntimeInfo 接口
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo
helpviewer_keywords:
- ICLRRuntimeInfo interface [.NET Framework hosting]
ms.assetid: 287e5ede-b3a7-4ef8-a756-4fca3f285a82
topic_type:
- apiref
ms.openlocfilehash: 9f485728ddb050abf815bf8ba26c69be9c909785
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714964"
---
# <a name="iclrruntimeinfo-interface"></a><span data-ttu-id="c2c61-102">ICLRRuntimeInfo 接口</span><span class="sxs-lookup"><span data-stu-id="c2c61-102">ICLRRuntimeInfo Interface</span></span>

<span data-ttu-id="c2c61-103">提供一些方法，这些方法可返回有关特定公共语言运行时 (CLR) 的信息，包括版本、目录和加载状态。</span><span class="sxs-lookup"><span data-stu-id="c2c61-103">Provides methods that return information about a specific common language runtime (CLR), including version, directory, and load status.</span></span> <span data-ttu-id="c2c61-104">此接口还提供了特定于运行时的功能，而无需初始化运行时。</span><span class="sxs-lookup"><span data-stu-id="c2c61-104">This interface also provides runtime-specific functionality without initializing the runtime.</span></span> <span data-ttu-id="c2c61-105">它包括运行时相对 [LoadLibrary](iclrruntimeinfo-loadlibrary-method.md) 方法、运行时模块特定的 [GetProcAddress](iclrruntimeinfo-getprocaddress-method.md) 方法和通过 [GetInterface](iclrruntimeinfo-getinterface-method.md) 方法提供的运行时提供的接口。</span><span class="sxs-lookup"><span data-stu-id="c2c61-105">It includes the runtime-relative [LoadLibrary](iclrruntimeinfo-loadlibrary-method.md) method, the runtime module-specific [GetProcAddress](iclrruntimeinfo-getprocaddress-method.md) method, and runtime-provided interfaces through the [GetInterface](iclrruntimeinfo-getinterface-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c2c61-106">方法</span><span class="sxs-lookup"><span data-stu-id="c2c61-106">Methods</span></span>  
  
|<span data-ttu-id="c2c61-107">方法</span><span class="sxs-lookup"><span data-stu-id="c2c61-107">Method</span></span>|<span data-ttu-id="c2c61-108">说明</span><span class="sxs-lookup"><span data-stu-id="c2c61-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c2c61-109">BindAsLegacyV2Runtime 方法</span><span class="sxs-lookup"><span data-stu-id="c2c61-109">BindAsLegacyV2Runtime Method</span></span>](iclrruntimeinfo-bindaslegacyv2runtime-method.md)|<span data-ttu-id="c2c61-110">为所有旧版 CLR 版本2激活策略决策绑定此运行时。</span><span class="sxs-lookup"><span data-stu-id="c2c61-110">Binds this runtime for all legacy CLR version 2 activation policy decisions.</span></span>|  
|[<span data-ttu-id="c2c61-111">GetDefaultStartupFlags 方法</span><span class="sxs-lookup"><span data-stu-id="c2c61-111">GetDefaultStartupFlags Method</span></span>](iclrruntimeinfo-getdefaultstartupflags-method.md)|<span data-ttu-id="c2c61-112">获取 CLR 启动标志和主机配置文件。</span><span class="sxs-lookup"><span data-stu-id="c2c61-112">Gets the CLR startup flags and host configuration file.</span></span>|  
|[<span data-ttu-id="c2c61-113">GetInterface 方法</span><span class="sxs-lookup"><span data-stu-id="c2c61-113">GetInterface Method</span></span>](iclrruntimeinfo-getinterface-method.md)|<span data-ttu-id="c2c61-114">将 CLR 加载到当前进程并返回运行时接口指针，如 [ICLRRuntimeHost](iclrruntimehost-interface.md)、 [ICLRStrongName](iclrstrongname-interface.md) 和 [IMetaDataDispenser](../metadata/imetadatadispenser-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="c2c61-114">Loads the CLR into the current process and returns runtime interface pointers, such as [ICLRRuntimeHost](iclrruntimehost-interface.md), [ICLRStrongName](iclrstrongname-interface.md) and [IMetaDataDispenser](../metadata/imetadatadispenser-interface.md).</span></span> <span data-ttu-id="c2c61-115">此方法将取代所有 `CorBindTo*` 函数。</span><span class="sxs-lookup"><span data-stu-id="c2c61-115">This method supersedes all the `CorBindTo*` functions.</span></span>|  
|[<span data-ttu-id="c2c61-116">GetProcAddress 方法</span><span class="sxs-lookup"><span data-stu-id="c2c61-116">GetProcAddress Method</span></span>](iclrruntimeinfo-getprocaddress-method.md)|<span data-ttu-id="c2c61-117">获取从与此接口关联的 CLR 导出的指定函数的地址。</span><span class="sxs-lookup"><span data-stu-id="c2c61-117">Gets the address of a specified function that was exported from the CLR associated with this interface.</span></span> <span data-ttu-id="c2c61-118">此方法取代了 [GetRealProcAddress](getrealprocaddress-function.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="c2c61-118">This method supersedes the [GetRealProcAddress](getrealprocaddress-function.md) method.</span></span>|  
|[<span data-ttu-id="c2c61-119">GetRuntimeDirectory 方法</span><span class="sxs-lookup"><span data-stu-id="c2c61-119">GetRuntimeDirectory Method</span></span>](iclrruntimeinfo-getruntimedirectory-method.md)|<span data-ttu-id="c2c61-120">获取与此接口关联的 CLR 的安装目录。</span><span class="sxs-lookup"><span data-stu-id="c2c61-120">Gets the installation directory of the CLR associated with this interface.</span></span> <span data-ttu-id="c2c61-121">此方法取代了 [GetCORSystemDirectory](getcorsystemdirectory-function.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="c2c61-121">This method supersedes the [GetCORSystemDirectory](getcorsystemdirectory-function.md) method.</span></span>|  
|[<span data-ttu-id="c2c61-122">GetVersionString 方法</span><span class="sxs-lookup"><span data-stu-id="c2c61-122">GetVersionString Method</span></span>](iclrruntimeinfo-getversionstring-method.md)|<span data-ttu-id="c2c61-123">获取公共语言运行时 (CLR) 版本信息与给定的 [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) 接口相关联。</span><span class="sxs-lookup"><span data-stu-id="c2c61-123">Gets common language runtime (CLR) version information associated with a given [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface.</span></span> <span data-ttu-id="c2c61-124">此方法取代了 [GetRequestedRuntimeInfo](getrequestedruntimeinfo-function.md) 和 [GetRequestedRuntimeVersion](getrequestedruntimeversion-function.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="c2c61-124">This method supersedes the [GetRequestedRuntimeInfo](getrequestedruntimeinfo-function.md) and [GetRequestedRuntimeVersion](getrequestedruntimeversion-function.md) methods.</span></span>|  
|[<span data-ttu-id="c2c61-125">IsLoadable 方法</span><span class="sxs-lookup"><span data-stu-id="c2c61-125">IsLoadable Method</span></span>](iclrruntimeinfo-isloadable-method.md)|<span data-ttu-id="c2c61-126">指示是否可将与此接口关联的运行时加载到当前进程，并考虑可能已加载到进程中的其他运行时。</span><span class="sxs-lookup"><span data-stu-id="c2c61-126">Indicates whether the runtime associated with this interface can be loaded into the current process, taking into account other runtimes that might already be loaded into the process.</span></span>|  
|[<span data-ttu-id="c2c61-127">IsLoaded 方法</span><span class="sxs-lookup"><span data-stu-id="c2c61-127">IsLoaded Method</span></span>](iclrruntimeinfo-isloaded-method.md)|<span data-ttu-id="c2c61-128">指示与 [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) 接口关联的 CLR 是否已加载到进程中。</span><span class="sxs-lookup"><span data-stu-id="c2c61-128">Indicates whether the CLR associated with the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface is loaded into a process.</span></span>|  
|[<span data-ttu-id="c2c61-129">IsStarted 方法</span><span class="sxs-lookup"><span data-stu-id="c2c61-129">IsStarted Method</span></span>](iclrruntimeinfo-isstarted-method.md)|<span data-ttu-id="c2c61-130">指示与 [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) 接口关联的 CLR 是否已启动。</span><span class="sxs-lookup"><span data-stu-id="c2c61-130">Indicates whether the CLR that is associated with the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface has been started.</span></span>|  
|[<span data-ttu-id="c2c61-131">LoadErrorString 方法</span><span class="sxs-lookup"><span data-stu-id="c2c61-131">LoadErrorString Method</span></span>](iclrruntimeinfo-loaderrorstring-method.md)|<span data-ttu-id="c2c61-132">将 HRESULT 值转换为指定区域性的适当错误消息。</span><span class="sxs-lookup"><span data-stu-id="c2c61-132">Translates an HRESULT value into an appropriate error message for the specified culture.</span></span> <span data-ttu-id="c2c61-133">此方法取代了 [LoadStringRC](loadstringrc-function.md) 和 [LoadStringRCEx](loadstringrcex-function.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="c2c61-133">This method supersedes the [LoadStringRC](loadstringrc-function.md) and [LoadStringRCEx](loadstringrcex-function.md) methods.</span></span>|  
|[<span data-ttu-id="c2c61-134">LoadLibrary 方法</span><span class="sxs-lookup"><span data-stu-id="c2c61-134">LoadLibrary Method</span></span>](iclrruntimeinfo-loadlibrary-method.md)|<span data-ttu-id="c2c61-135">从 [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) 接口所表示的 CLR 的框架目录加载库。</span><span class="sxs-lookup"><span data-stu-id="c2c61-135">Loads a library from the framework directory of the CLR represented by an [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface.</span></span> <span data-ttu-id="c2c61-136">此方法取代了 [LoadLibraryShim](loadlibraryshim-function.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="c2c61-136">This method supersedes the [LoadLibraryShim](loadlibraryshim-function.md) method.</span></span>|  
|[<span data-ttu-id="c2c61-137">SetDefaultStartupFlags 方法</span><span class="sxs-lookup"><span data-stu-id="c2c61-137">SetDefaultStartupFlags Method</span></span>](iclrruntimeinfo-setdefaultstartupflags-method.md)|<span data-ttu-id="c2c61-138">设置 CLR 启动标志和主机配置文件。</span><span class="sxs-lookup"><span data-stu-id="c2c61-138">Sets the CLR startup flags and host configuration file.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c2c61-139">要求</span><span class="sxs-lookup"><span data-stu-id="c2c61-139">Requirements</span></span>  

 <span data-ttu-id="c2c61-140">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c2c61-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2c61-141">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="c2c61-141">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c2c61-142">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c2c61-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c2c61-143">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2c61-143">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2c61-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c2c61-144">See also</span></span>

- [<span data-ttu-id="c2c61-145">承载接口</span><span class="sxs-lookup"><span data-stu-id="c2c61-145">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="c2c61-146">承载</span><span class="sxs-lookup"><span data-stu-id="c2c61-146">Hosting</span></span>](index.md)
