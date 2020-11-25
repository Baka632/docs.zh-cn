---
title: COR_PRF_CODEGEN_FLAGS 枚举
ms.date: 03/30/2017
api_name:
- COR_PRF_CODEGEN_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_CODEGEN_FLAGS
helpviewer_keywords:
- COR_PRF_CODEGEN_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 3e184022-0247-4824-a23d-6b29593d8d01
topic_type:
- apiref
ms.openlocfilehash: 3252e3b33da743c0e146e25f798c0e669aeb74ef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718600"
---
# <a name="cor_prf_codegen_flags-enumeration"></a><span data-ttu-id="e79c7-102">COR_PRF_CODEGEN_FLAGS 枚举</span><span class="sxs-lookup"><span data-stu-id="e79c7-102">COR_PRF_CODEGEN_FLAGS Enumeration</span></span>

<span data-ttu-id="e79c7-103">定义可以用 [ICorProfilerFunctionControl：： SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) 方法设置的代码生成标志。</span><span class="sxs-lookup"><span data-stu-id="e79c7-103">Defines the code generation flags that can be set with the [ICorProfilerFunctionControl::SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e79c7-104">语法</span><span class="sxs-lookup"><span data-stu-id="e79c7-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_CODEGEN_DISABLE_INLINING =          0x0001,  
    COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS = 0x0002,  
} COR_PRF_CODEGEN_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="e79c7-105">成员</span><span class="sxs-lookup"><span data-stu-id="e79c7-105">Members</span></span>  
  
|<span data-ttu-id="e79c7-106">成员</span><span class="sxs-lookup"><span data-stu-id="e79c7-106">Member</span></span>|<span data-ttu-id="e79c7-107">说明</span><span class="sxs-lookup"><span data-stu-id="e79c7-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CODEGEN_DISABLE_INLINING`|<span data-ttu-id="e79c7-108">不会将任何函数内联到此函数的主体中。</span><span class="sxs-lookup"><span data-stu-id="e79c7-108">No functions will be inlined into this function’s body.</span></span> <span data-ttu-id="e79c7-109">但是，函数本身可能会内联到其调用方。</span><span class="sxs-lookup"><span data-stu-id="e79c7-109">However, the function itself may be inlined into its callers.</span></span>|  
|`COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS`|<span data-ttu-id="e79c7-110">对于此函数的主体，将禁用所有优化。</span><span class="sxs-lookup"><span data-stu-id="e79c7-110">All optimizations will be disabled for this function’s body.</span></span> <span data-ttu-id="e79c7-111">但是，该函数本身可能仍会内联到其调用方。</span><span class="sxs-lookup"><span data-stu-id="e79c7-111">However, the function itself may still be inlined into its callers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e79c7-112">注解</span><span class="sxs-lookup"><span data-stu-id="e79c7-112">Remarks</span></span>  

 <span data-ttu-id="e79c7-113">`COR_PRF_CODEGEN_FLAGS` [ICorProfilerFunctionControl：： SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md)方法使用枚举来启用探查器，以控制 JIT 重新编译函数的代码生成。</span><span class="sxs-lookup"><span data-stu-id="e79c7-113">The `COR_PRF_CODEGEN_FLAGS` enumeration is used by the [ICorProfilerFunctionControl::SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) method to enable the profiler to control the code generation for the JIT-recompiled function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e79c7-114">要求</span><span class="sxs-lookup"><span data-stu-id="e79c7-114">Requirements</span></span>  

 <span data-ttu-id="e79c7-115">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e79c7-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e79c7-116">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e79c7-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e79c7-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e79c7-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e79c7-118">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e79c7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e79c7-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e79c7-119">See also</span></span>

- [<span data-ttu-id="e79c7-120">分析枚举</span><span class="sxs-lookup"><span data-stu-id="e79c7-120">Profiling Enumerations</span></span>](profiling-enumerations.md)
