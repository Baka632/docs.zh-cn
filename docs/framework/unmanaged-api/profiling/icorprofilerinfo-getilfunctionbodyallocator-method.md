---
title: ICorProfilerInfo::GetILFunctionBodyAllocator 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILFunctionBodyAllocator
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBodyAllocator
helpviewer_keywords:
- GetILFunctionBodyAllocator method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBodyAllocator method [.NET Framework profiling]
ms.assetid: 5da1bf3d-dddf-4892-b266-578ee54d570b
topic_type:
- apiref
ms.openlocfilehash: b18de87cf89985e0f7ec11edf58b43d67720251c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718015"
---
# <a name="icorprofilerinfogetilfunctionbodyallocator-method"></a><span data-ttu-id="24917-102">ICorProfilerInfo::GetILFunctionBodyAllocator 方法</span><span class="sxs-lookup"><span data-stu-id="24917-102">ICorProfilerInfo::GetILFunctionBodyAllocator Method</span></span>

<span data-ttu-id="24917-103">获取一个接口，该接口提供一种方法，用于分配内存，以用于在 Microsoft 中间语言 (MSIL) 代码中交换方法体。</span><span class="sxs-lookup"><span data-stu-id="24917-103">Gets an interface that provides a method to allocate memory to be used for swapping out the body of a method in Microsoft intermediate language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24917-104">语法</span><span class="sxs-lookup"><span data-stu-id="24917-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILFunctionBodyAllocator(  
    [in]  ModuleID      moduleId,  
    [out] IMethodMalloc **ppMalloc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24917-105">参数</span><span class="sxs-lookup"><span data-stu-id="24917-105">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="24917-106">中方法所在的模块的 ID。</span><span class="sxs-lookup"><span data-stu-id="24917-106">[in] The ID of the module in which the method resides.</span></span>  
  
 `ppMalloc`  
 <span data-ttu-id="24917-107">弄指向 [IMethodMalloc](imethodmalloc-interface.md) 接口的指针，该接口提供分配内存的方法。</span><span class="sxs-lookup"><span data-stu-id="24917-107">[out] A pointer to an [IMethodMalloc](imethodmalloc-interface.md) interface that provides a method to allocate the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24917-108">注解</span><span class="sxs-lookup"><span data-stu-id="24917-108">Remarks</span></span>  

 <span data-ttu-id="24917-109">MSIL 代码中的方法体必须位于 RVA)  (RVA 上（相对于已加载的模块），这意味着它遵循 4 GB 内的模块。</span><span class="sxs-lookup"><span data-stu-id="24917-109">A method body in MSIL code must be located as a relative virtual address (RVA), relative to the loaded module, which means that it follows the module within 4 GB.</span></span> <span data-ttu-id="24917-110">为了使工具能够更轻松地调换方法的主体， `GetILFunctionBodyAllocator` 方法可确保在该范围内分配内存。</span><span class="sxs-lookup"><span data-stu-id="24917-110">To make it easier for a tool to swap out the body of a method, the `GetILFunctionBodyAllocator` method ensures that memory is allocated within that range.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24917-111">要求</span><span class="sxs-lookup"><span data-stu-id="24917-111">Requirements</span></span>  

 <span data-ttu-id="24917-112">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="24917-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24917-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="24917-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="24917-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24917-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24917-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24917-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24917-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24917-116">See also</span></span>

- [<span data-ttu-id="24917-117">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="24917-117">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
