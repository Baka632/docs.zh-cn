---
title: ICorProfilerFunctionEnum::Next 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.Next Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Next
helpviewer_keywords:
- ICorProfilerFunctionEnum::Next method [.NET Framework profiling]
- Next method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 5ed4aa83-ce56-4b9f-9237-5da7587787fe
topic_type:
- apiref
ms.openlocfilehash: 76e0fe011769217f3cecb40c8d2ba83904b26706
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95669219"
---
# <a name="icorprofilerfunctionenumnext-method"></a><span data-ttu-id="007fe-102">ICorProfilerFunctionEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="007fe-102">ICorProfilerFunctionEnum::Next Method</span></span>

<span data-ttu-id="007fe-103">从一个函数的顺序集合中获取指定数量的连续函数（从枚举器在序列中的当前位置开始）。</span><span class="sxs-lookup"><span data-stu-id="007fe-103">Gets the specified number of contiguous functions from a sequential collection of functions, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="007fe-104">语法</span><span class="sxs-lookup"><span data-stu-id="007fe-104">Syntax</span></span>  
  
```cpp  
HRESULT Next([in]  ULONG      celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                    COR_PRF_FUNCTION ids[],  
             [out] ULONG *   pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="007fe-105">参数</span><span class="sxs-lookup"><span data-stu-id="007fe-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="007fe-106">[in]要检索的函数数量。</span><span class="sxs-lookup"><span data-stu-id="007fe-106">[in] The number of functions to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="007fe-107">[out] `COR_PRF_FUNCTION` 值的数组，其中每个数组表示检索的函数。</span><span class="sxs-lookup"><span data-stu-id="007fe-107">[out] An array of `COR_PRF_FUNCTION` values, each of which represents a retrieved function.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="007fe-108">[out] 指向 `ids` 数组中实际返回的函数量的指针。</span><span class="sxs-lookup"><span data-stu-id="007fe-108">[out] A pointer to the number of functions actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="007fe-109">返回值</span><span class="sxs-lookup"><span data-stu-id="007fe-109">Return Value</span></span>  

 <span data-ttu-id="007fe-110">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="007fe-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="007fe-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="007fe-111">HRESULT</span></span>|<span data-ttu-id="007fe-112">说明</span><span class="sxs-lookup"><span data-stu-id="007fe-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="007fe-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="007fe-113">S_OK</span></span>|<span data-ttu-id="007fe-114">已返回 `celt` 元素。</span><span class="sxs-lookup"><span data-stu-id="007fe-114">`celt` elements were returned.</span></span>|  
|<span data-ttu-id="007fe-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="007fe-115">S_FALSE</span></span>|<span data-ttu-id="007fe-116">返回的元素少于 `celt` 个，表示枚举已完成。</span><span class="sxs-lookup"><span data-stu-id="007fe-116">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="007fe-117">要求</span><span class="sxs-lookup"><span data-stu-id="007fe-117">Requirements</span></span>  

 <span data-ttu-id="007fe-118">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="007fe-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="007fe-119">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="007fe-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="007fe-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="007fe-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="007fe-121">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="007fe-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="007fe-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="007fe-122">See also</span></span>

- [<span data-ttu-id="007fe-123">ICorProfilerFunctionEnum 接口</span><span class="sxs-lookup"><span data-stu-id="007fe-123">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="007fe-124">分析接口</span><span class="sxs-lookup"><span data-stu-id="007fe-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
