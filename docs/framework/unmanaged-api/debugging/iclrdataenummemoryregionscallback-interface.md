---
title: ICLRDataEnumMemoryRegionsCallback 接口
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegionsCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegionsCallback
helpviewer_keywords:
- ICLRDataEnumMemoryRegionsCallback interface [.NET Framework debugging]
ms.assetid: 3f1af8b0-8478-48e0-a7ec-3e90e0b97649
topic_type:
- apiref
ms.openlocfilehash: f080d852b190346740a3629f3b5d46a9f3808293
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703624"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="e08e0-102">ICLRDataEnumMemoryRegionsCallback 接口</span><span class="sxs-lookup"><span data-stu-id="e08e0-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>

<span data-ttu-id="e08e0-103">为 [ICLRDataEnumMemoryRegions：： EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) 提供回调方法，以便向调试器报告尝试枚举指定的内存区域的结果。</span><span class="sxs-lookup"><span data-stu-id="e08e0-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e08e0-104">方法</span><span class="sxs-lookup"><span data-stu-id="e08e0-104">Methods</span></span>  
  
|<span data-ttu-id="e08e0-105">方法</span><span class="sxs-lookup"><span data-stu-id="e08e0-105">Method</span></span>|<span data-ttu-id="e08e0-106">说明</span><span class="sxs-lookup"><span data-stu-id="e08e0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e08e0-107">EnumMemoryRegion 方法</span><span class="sxs-lookup"><span data-stu-id="e08e0-107">EnumMemoryRegion Method</span></span>](iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="e08e0-108">由调用 `ICLRDataEnumMemoryRegions::EnumMemoryRegions` ，以向调试器报告尝试枚举指定的内存区域的结果。</span><span class="sxs-lookup"><span data-stu-id="e08e0-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e08e0-109">要求</span><span class="sxs-lookup"><span data-stu-id="e08e0-109">Requirements</span></span>  

 <span data-ttu-id="e08e0-110">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e08e0-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e08e0-111">**标头：** ClrData，ClrData</span><span class="sxs-lookup"><span data-stu-id="e08e0-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="e08e0-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e08e0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e08e0-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e08e0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e08e0-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e08e0-114">See also</span></span>

- [<span data-ttu-id="e08e0-115">调试接口</span><span class="sxs-lookup"><span data-stu-id="e08e0-115">Debugging Interfaces</span></span>](debugging-interfaces.md)
