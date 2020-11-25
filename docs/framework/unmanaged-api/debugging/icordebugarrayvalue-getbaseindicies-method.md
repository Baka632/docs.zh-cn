---
title: ICorDebugArrayValue::GetBaseIndicies 方法
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetBaseIndicies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetBaseIndicies
helpviewer_keywords:
- ICorDebugArrayValue::GetBaseIndicies method [.NET Framework debugging]
- GetBaseIndicies method [.NET Framework debugging]
ms.assetid: 868b339b-acdb-4fe0-91c7-b85f4fba99eb
topic_type:
- apiref
ms.openlocfilehash: ea5c5a728afb9ac90f8599c833caab11fd0c65fe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731457"
---
# <a name="icordebugarrayvaluegetbaseindicies-method"></a><span data-ttu-id="699c4-102">ICorDebugArrayValue::GetBaseIndicies 方法</span><span class="sxs-lookup"><span data-stu-id="699c4-102">ICorDebugArrayValue::GetBaseIndicies Method</span></span>

<span data-ttu-id="699c4-103">获取数组中每个维的基索引。</span><span class="sxs-lookup"><span data-stu-id="699c4-103">Gets the base index of each dimension in the array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="699c4-104">语法</span><span class="sxs-lookup"><span data-stu-id="699c4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseIndicies (  
    [in] ULONG32          cdim,  
    [out, size_is(cdim), length_is(cdim)]
        ULONG32           indicies[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="699c4-105">参数</span><span class="sxs-lookup"><span data-stu-id="699c4-105">Parameters</span></span>  

 `cdim`  
 <span data-ttu-id="699c4-106">中此对象的维度数 `ICorDebugArrayValue` 。</span><span class="sxs-lookup"><span data-stu-id="699c4-106">[in] The number of dimensions of this `ICorDebugArrayValue` object.</span></span> <span data-ttu-id="699c4-107">此值也是数组的大小， `indicies` 因为其大小等于对象的维度数 `ICorDebugArrayValue` 。</span><span class="sxs-lookup"><span data-stu-id="699c4-107">This value is also the size of the `indicies` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `indicies`  
 <span data-ttu-id="699c4-108">弄整数数组，其中每个都是基索引 (，即此对象的维度的起始索引) `ICorDebugArrayValue` 。</span><span class="sxs-lookup"><span data-stu-id="699c4-108">[out] An array of integers, each of which is the base index (that is, the starting index) of a dimension of this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="699c4-109">要求</span><span class="sxs-lookup"><span data-stu-id="699c4-109">Requirements</span></span>  

 <span data-ttu-id="699c4-110">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="699c4-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="699c4-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="699c4-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="699c4-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="699c4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="699c4-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="699c4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
