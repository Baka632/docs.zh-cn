---
title: ICorProfilerFunctionControl 接口
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl
helpviewer_keywords:
- ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 4e3d3141-4662-4166-8f05-bc857c1b4216
topic_type:
- apiref
ms.openlocfilehash: 733a8f0bc7e8c19823827297a50f9c6906614ca7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698372"
---
# <a name="icorprofilerfunctioncontrol-interface"></a><span data-ttu-id="009ff-102">ICorProfilerFunctionControl 接口</span><span class="sxs-lookup"><span data-stu-id="009ff-102">ICorProfilerFunctionControl Interface</span></span>

<span data-ttu-id="009ff-103">提供允许代码探查器与公共语言运行时 (CLR) 进行通信的方法，从而在重新编译特定方法时控制 JIT 探查器应生成代码的方式。</span><span class="sxs-lookup"><span data-stu-id="009ff-103">Provides methods that allow a code profiler to communicate with the common language runtime (CLR) to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="009ff-104">方法</span><span class="sxs-lookup"><span data-stu-id="009ff-104">Methods</span></span>  
  
|<span data-ttu-id="009ff-105">方法</span><span class="sxs-lookup"><span data-stu-id="009ff-105">Method</span></span>|<span data-ttu-id="009ff-106">说明</span><span class="sxs-lookup"><span data-stu-id="009ff-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="009ff-107">SetCodegenFlags 方法</span><span class="sxs-lookup"><span data-stu-id="009ff-107">SetCodegenFlags Method</span></span>](icorprofilerfunctioncontrol-setcodegenflags-method.md)|<span data-ttu-id="009ff-108">设置 [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) 枚举中的一个或多个标志，以控制实时 (JIT) 重新编译函数的代码生成。</span><span class="sxs-lookup"><span data-stu-id="009ff-108">Sets one or more flags from the [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) enumeration to control code generation for a just-in-time (JIT) recompiled function.</span></span>|  
|[<span data-ttu-id="009ff-109">SetILFunctionBody 方法</span><span class="sxs-lookup"><span data-stu-id="009ff-109">SetILFunctionBody Method</span></span>](icorprofilerfunctioncontrol-setilfunctionbody-method.md)|<span data-ttu-id="009ff-110">替换方法的公共中间语言 (CIL) 主体。</span><span class="sxs-lookup"><span data-stu-id="009ff-110">Replaces the Common Intermediate Language (CIL) body of the method.</span></span>|  
|[<span data-ttu-id="009ff-111">SetILInstrumentedCodeMap 方法</span><span class="sxs-lookup"><span data-stu-id="009ff-111">SetILInstrumentedCodeMap Method</span></span>](icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md)|<span data-ttu-id="009ff-112">使用指定的公共中间语言 (CIL) 映射项为指定的函数设置代码图。</span><span class="sxs-lookup"><span data-stu-id="009ff-112">Sets a code map for the specified function by using the specified Common Intermediate Language (CIL) map entries.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="009ff-113">注解</span><span class="sxs-lookup"><span data-stu-id="009ff-113">Remarks</span></span>  

 <span data-ttu-id="009ff-114">`ICorProfilerFunctionControl` 接口提供了用于控制单个重新编译函数的代码生成的方法。</span><span class="sxs-lookup"><span data-stu-id="009ff-114">The `ICorProfilerFunctionControl` interface provides methods for controlling code generation for a single recompiled function.</span></span> <span data-ttu-id="009ff-115">探查器通过 [ICorProfilerCallback4：： GetReJITParameters](icorprofilercallback4-getrejitparameters-method.md) 回调获取此接口的实例。</span><span class="sxs-lookup"><span data-stu-id="009ff-115">The profiler obtains an instance of this interface through the [ICorProfilerCallback4::GetReJITParameters](icorprofilercallback4-getrejitparameters-method.md) callback.</span></span> <span data-ttu-id="009ff-116">`ICorProfilerFunctionControl` 的每个实例都可控制一个函数的所有实例。</span><span class="sxs-lookup"><span data-stu-id="009ff-116">Each instance of `ICorProfilerFunctionControl` controls all instances of one function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="009ff-117">要求</span><span class="sxs-lookup"><span data-stu-id="009ff-117">Requirements</span></span>  

 <span data-ttu-id="009ff-118">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="009ff-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="009ff-119">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="009ff-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="009ff-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="009ff-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="009ff-121">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="009ff-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="009ff-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="009ff-122">See also</span></span>

- [<span data-ttu-id="009ff-123">ICorProfilerInfo4 接口</span><span class="sxs-lookup"><span data-stu-id="009ff-123">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="009ff-124">分析接口</span><span class="sxs-lookup"><span data-stu-id="009ff-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="009ff-125">EnumJITedFunctions2 方法</span><span class="sxs-lookup"><span data-stu-id="009ff-125">EnumJITedFunctions2 Method</span></span>](icorprofilerinfo4-enumjitedfunctions2-method.md)
