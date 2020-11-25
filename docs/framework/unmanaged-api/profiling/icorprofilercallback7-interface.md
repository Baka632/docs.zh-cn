---
title: ICorProfilerCallback7 接口
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: a0be019e-aaa1-4036-990f-565f114d4b5c
ms.openlocfilehash: e9c7186b3217c29805327e6c1d6b10f580c3a9e9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725451"
---
# <a name="icorprofilercallback7-interface"></a><span data-ttu-id="60496-102">ICorProfilerCallback7 接口</span><span class="sxs-lookup"><span data-stu-id="60496-102">ICorProfilerCallback7 Interface</span></span>

<span data-ttu-id="60496-103">[仅在 .NET Framework 4.6.1 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="60496-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="60496-104">提供回调方法的 [ICorProfilerCallback6](icorprofilercallback6-interface.md) 的子类，公共语言运行时使用该方法通知探查器已更新与内存中模块关联的符号流。</span><span class="sxs-lookup"><span data-stu-id="60496-104">A subclass of [ICorProfilerCallback6](icorprofilercallback6-interface.md) that provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="60496-105">方法</span><span class="sxs-lookup"><span data-stu-id="60496-105">Methods</span></span>  
  
|<span data-ttu-id="60496-106">方法</span><span class="sxs-lookup"><span data-stu-id="60496-106">Method</span></span>|<span data-ttu-id="60496-107">说明</span><span class="sxs-lookup"><span data-stu-id="60496-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="60496-108">ModuleInMemorySymbolsUpdated 方法</span><span class="sxs-lookup"><span data-stu-id="60496-108">ModuleInMemorySymbolsUpdated Method</span></span>](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md)|<span data-ttu-id="60496-109">通知探查器已更新与内存中模块关联的符号流。</span><span class="sxs-lookup"><span data-stu-id="60496-109">Notifies the profiler that the symbol stream associated with an in-memory module is updated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="60496-110">要求</span><span class="sxs-lookup"><span data-stu-id="60496-110">Requirements</span></span>  

 <span data-ttu-id="60496-111">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="60496-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60496-112">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="60496-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="60496-113">**.NET Framework 版本：**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60496-113">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60496-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="60496-114">See also</span></span>

- [<span data-ttu-id="60496-115">分析接口</span><span class="sxs-lookup"><span data-stu-id="60496-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
