---
title: ICorProfilerCallback8 接口
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 22a133d02bb69026190428905379323362943d40
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732380"
---
# <a name="icorprofilercallback8-interface"></a><span data-ttu-id="5356d-102">ICorProfilerCallback8 接口</span><span class="sxs-lookup"><span data-stu-id="5356d-102">ICorProfilerCallback8 Interface</span></span>

<span data-ttu-id="5356d-103">[.NET Framework 4.7 及更高版本中支持]</span><span class="sxs-lookup"><span data-stu-id="5356d-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  

 <span data-ttu-id="5356d-104">提供回调方法的 [ICorProfilerCallback7](icorprofilercallback7-interface.md) 的子类，公共语言运行时使用该方法通知探查器动态方法的 JIT 编译已开始和完成。</span><span class="sxs-lookup"><span data-stu-id="5356d-104">A subclass of [ICorProfilerCallback7](icorprofilercallback7-interface.md) that provides callback methods used by the common language runtime to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span>
  
## <a name="methods"></a><span data-ttu-id="5356d-105">方法</span><span class="sxs-lookup"><span data-stu-id="5356d-105">Methods</span></span>  
  
|<span data-ttu-id="5356d-106">方法</span><span class="sxs-lookup"><span data-stu-id="5356d-106">Method</span></span>|<span data-ttu-id="5356d-107">说明</span><span class="sxs-lookup"><span data-stu-id="5356d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5356d-108">DynamicMethodJITCompilationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="5356d-108">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|<span data-ttu-id="5356d-109">通知探查器已经开始对动态方法进行 JIT 编译。</span><span class="sxs-lookup"><span data-stu-id="5356d-109">Notifies the profiler that JIT compilation of a dynamic method has started.</span></span>|  
|[<span data-ttu-id="5356d-110">DynamicMethodJITCompilationFinished 方法</span><span class="sxs-lookup"><span data-stu-id="5356d-110">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|<span data-ttu-id="5356d-111">通知探查器已完成动态方法的 JIT 编译。</span><span class="sxs-lookup"><span data-stu-id="5356d-111">Notifies the profiler that JIT compilation of a dynamic method has finished.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5356d-112">要求</span><span class="sxs-lookup"><span data-stu-id="5356d-112">Requirements</span></span>  

 <span data-ttu-id="5356d-113">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5356d-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5356d-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5356d-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="5356d-115">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5356d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="5356d-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5356d-116">See also</span></span>

- [<span data-ttu-id="5356d-117">分析接口</span><span class="sxs-lookup"><span data-stu-id="5356d-117">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="5356d-118">ICorProfilerCallback9 接口</span><span class="sxs-lookup"><span data-stu-id="5356d-118">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
