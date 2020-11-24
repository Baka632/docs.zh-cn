---
title: ICLRGCManager 接口
ms.date: 03/30/2017
api_name:
- ICLRGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager
helpviewer_keywords:
- ICLRGCManager interface [.NET Framework hosting]
ms.assetid: fb511c9b-3fe4-41b0-822a-6ba4a079d1f5
topic_type:
- apiref
ms.openlocfilehash: dbe3df6bb20e5ad8f9eb534a366405eb9c33984f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678228"
---
# <a name="iclrgcmanager-interface"></a><span data-ttu-id="0f357-102">ICLRGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="0f357-102">ICLRGCManager Interface</span></span>

<span data-ttu-id="0f357-103">提供允许主机与公共语言运行时的垃圾回收系统交互的方法。</span><span class="sxs-lookup"><span data-stu-id="0f357-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0f357-104">从 .NET Framework 4.5 开始，你可以使用 [ICLRGCManager2：： SetGCStartupLimitsEx](iclrgcmanager2-setgcstartuplimitsex-method.md) 方法将垃圾回收段的大小和垃圾回收系统的第0代的最大大小设置为大于 `DWORD` [SetGCStartupLimits](iclrgcmanager-setgcstartuplimits-method.md) 方法施加的限制的值。</span><span class="sxs-lookup"><span data-stu-id="0f357-104">Starting with the .NET Framework 4.5, you can use the [ICLRGCManager2::SetGCStartupLimitsEx](iclrgcmanager2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](iclrgcmanager-setgcstartuplimits-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0f357-105">方法</span><span class="sxs-lookup"><span data-stu-id="0f357-105">Methods</span></span>  
  
|<span data-ttu-id="0f357-106">方法</span><span class="sxs-lookup"><span data-stu-id="0f357-106">Method</span></span>|<span data-ttu-id="0f357-107">说明</span><span class="sxs-lookup"><span data-stu-id="0f357-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0f357-108">Collect 方法</span><span class="sxs-lookup"><span data-stu-id="0f357-108">Collect Method</span></span>](iclrgcmanager-collect-method.md)|<span data-ttu-id="0f357-109">强制执行指定代的垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="0f357-109">Forces a garbage collection for the specified generation.</span></span>|  
|[<span data-ttu-id="0f357-110">GetStats 方法</span><span class="sxs-lookup"><span data-stu-id="0f357-110">GetStats Method</span></span>](iclrgcmanager-getstats-method.md)|<span data-ttu-id="0f357-111">获取有关垃圾回收系统的当前统计信息集。</span><span class="sxs-lookup"><span data-stu-id="0f357-111">Gets a set of current statistics about the garbage collection system.</span></span>|  
|[<span data-ttu-id="0f357-112">SetGCStartupLimits 方法</span><span class="sxs-lookup"><span data-stu-id="0f357-112">SetGCStartupLimits Method</span></span>](iclrgcmanager-setgcstartuplimits-method.md)|<span data-ttu-id="0f357-113">设置垃圾回收段的大小以及垃圾回收系统的第0代的最大大小。</span><span class="sxs-lookup"><span data-stu-id="0f357-113">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f357-114">注解</span><span class="sxs-lookup"><span data-stu-id="0f357-114">Remarks</span></span>  

 <span data-ttu-id="0f357-115">公共语言运行时 (CLR) 利用托管类型实现其垃圾回收机制 <xref:System.GC> 。</span><span class="sxs-lookup"><span data-stu-id="0f357-115">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="0f357-116">有关垃圾回收系统的详细信息，请参阅 [垃圾](../../../standard/garbage-collection/index.md)回收。</span><span class="sxs-lookup"><span data-stu-id="0f357-116">For more information about the garbage collection system, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f357-117">要求</span><span class="sxs-lookup"><span data-stu-id="0f357-117">Requirements</span></span>  

 <span data-ttu-id="0f357-118">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0f357-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f357-119">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="0f357-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0f357-120">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0f357-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0f357-121">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f357-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f357-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0f357-122">See also</span></span>

- [<span data-ttu-id="0f357-123">自动内存管理</span><span class="sxs-lookup"><span data-stu-id="0f357-123">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="0f357-124">COR_GC_STATS 结构</span><span class="sxs-lookup"><span data-stu-id="0f357-124">COR_GC_STATS Structure</span></span>](cor-gc-stats-structure.md)
- [<span data-ttu-id="0f357-125">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="0f357-125">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="0f357-126">CLR 承载接口</span><span class="sxs-lookup"><span data-stu-id="0f357-126">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)
- [<span data-ttu-id="0f357-127">承载接口</span><span class="sxs-lookup"><span data-stu-id="0f357-127">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="0f357-128">承载</span><span class="sxs-lookup"><span data-stu-id="0f357-128">Hosting</span></span>](index.md)
