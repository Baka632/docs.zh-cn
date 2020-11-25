---
title: ICorProfilerCallback3 接口
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3
helpviewer_keywords:
- ICorProfilerCallback3 interface [.NET Framework profiling]
ms.assetid: be83af41-3dec-4c77-8529-9dd6b8042af6
topic_type:
- apiref
ms.openlocfilehash: fd482bfe8e95a53cafd1530c88f09df146a1b150
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729429"
---
# <a name="icorprofilercallback3-interface"></a><span data-ttu-id="fde64-102">ICorProfilerCallback3 接口</span><span class="sxs-lookup"><span data-stu-id="fde64-102">ICorProfilerCallback3 Interface</span></span>

<span data-ttu-id="fde64-103">提供公共语言运行时 (CLR) 用来向探查器传达附加和分离状态信息的回调方法。</span><span class="sxs-lookup"><span data-stu-id="fde64-103">Provides callback methods that the common language runtime (CLR) uses to communicate attach and detach state information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fde64-104">方法</span><span class="sxs-lookup"><span data-stu-id="fde64-104">Methods</span></span>  
  
|<span data-ttu-id="fde64-105">方法</span><span class="sxs-lookup"><span data-stu-id="fde64-105">Method</span></span>|<span data-ttu-id="fde64-106">说明</span><span class="sxs-lookup"><span data-stu-id="fde64-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fde64-107">InitializeForAttach 方法</span><span class="sxs-lookup"><span data-stu-id="fde64-107">InitializeForAttach Method</span></span>](icorprofilercallback3-initializeforattach-method.md)|<span data-ttu-id="fde64-108">由 CLR 调用，以使探查器能够在附加操作后初始化其状态。</span><span class="sxs-lookup"><span data-stu-id="fde64-108">Called by the CLR to give the profiler an opportunity to initialize its state after an attach operation.</span></span>|  
|[<span data-ttu-id="fde64-109">ProfilerAttachComplete 方法</span><span class="sxs-lookup"><span data-stu-id="fde64-109">ProfilerAttachComplete Method</span></span>](icorprofilercallback3-profilerattachcomplete-method.md)|<span data-ttu-id="fde64-110">由 CLR 调用以指示探查器现在可以调用追赶方法。</span><span class="sxs-lookup"><span data-stu-id="fde64-110">Called by the CLR to indicate that the profiler can now call the catch-up methods.</span></span>|  
|[<span data-ttu-id="fde64-111">ProfilerDetachSucceeded 方法</span><span class="sxs-lookup"><span data-stu-id="fde64-111">ProfilerDetachSucceeded Method</span></span>](icorprofilercallback3-profilerdetachsucceeded-method.md)|<span data-ttu-id="fde64-112">通知探查器公共语言运行时 (CLR) 将要卸载探查器 DLL。</span><span class="sxs-lookup"><span data-stu-id="fde64-112">Notifies the profiler that the common language runtime (CLR) is about to unload the profiler DLL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fde64-113">备注</span><span class="sxs-lookup"><span data-stu-id="fde64-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fde64-114">要求</span><span class="sxs-lookup"><span data-stu-id="fde64-114">Requirements</span></span>  

 <span data-ttu-id="fde64-115">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fde64-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fde64-116">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fde64-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fde64-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fde64-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fde64-118">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fde64-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fde64-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fde64-119">See also</span></span>

- [<span data-ttu-id="fde64-120">分析接口</span><span class="sxs-lookup"><span data-stu-id="fde64-120">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="fde64-121">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="fde64-121">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="fde64-122">ICorProfilerCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="fde64-122">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
- [<span data-ttu-id="fde64-123">ICorProfilerCallback4 接口</span><span class="sxs-lookup"><span data-stu-id="fde64-123">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
