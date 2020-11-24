---
title: ICorDebugValueEnum::Next 方法
ms.date: 03/30/2017
api_name:
- ICorDebugValueEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueEnum::Next
helpviewer_keywords:
- ICorDebugValueEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugValueEnum interface [.NET Framework debugging]
ms.assetid: f5ef94dd-dfee-49d3-a398-b110f8906dd8
topic_type:
- apiref
ms.openlocfilehash: e1c8d94a90092b1497267c78d5fadf5a6e6de707
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684325"
---
# <a name="icordebugvalueenumnext-method"></a><span data-ttu-id="f9d1d-102">ICorDebugValueEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="f9d1d-102">ICorDebugValueEnum::Next Method</span></span>

<span data-ttu-id="f9d1d-103">从当前位置开始，从枚举中获取指定的 "ICorDebugValue" 实例数。</span><span class="sxs-lookup"><span data-stu-id="f9d1d-103">Gets the specified number of "ICorDebugValue" instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9d1d-104">语法</span><span class="sxs-lookup"><span data-stu-id="f9d1d-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugValue *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9d1d-105">参数</span><span class="sxs-lookup"><span data-stu-id="f9d1d-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="f9d1d-106">中 `ICorDebugValue` 要检索的实例数。</span><span class="sxs-lookup"><span data-stu-id="f9d1d-106">[in] The number of `ICorDebugValue` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="f9d1d-107">弄指针的数组，其中每个都指向一个 `ICorDebugValue` 对象。</span><span class="sxs-lookup"><span data-stu-id="f9d1d-107">[out] An array of pointers, each of which points to an `ICorDebugValue` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="f9d1d-108">弄一个指针，指向 `ICorDebugValue` 实际返回的实例数。</span><span class="sxs-lookup"><span data-stu-id="f9d1d-108">[out] Pointer to the number of `ICorDebugValue` instances actually returned.</span></span> <span data-ttu-id="f9d1d-109">如果为1，则此值可以为 null `celt` 。</span><span class="sxs-lookup"><span data-stu-id="f9d1d-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9d1d-110">要求</span><span class="sxs-lookup"><span data-stu-id="f9d1d-110">Requirements</span></span>  

 <span data-ttu-id="f9d1d-111">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f9d1d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9d1d-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f9d1d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f9d1d-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f9d1d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f9d1d-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9d1d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9d1d-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f9d1d-115">See also</span></span>
