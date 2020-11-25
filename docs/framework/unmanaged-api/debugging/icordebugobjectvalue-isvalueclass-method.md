---
title: ICorDebugObjectValue::IsValueClass 方法
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.IsValueClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::IsValueClass
helpviewer_keywords:
- ICorDebugObjectValue::IsValueClass method [.NET Framework debugging]
- IsValueClass method [.NET Framework debugging]
ms.assetid: 13d89a4a-5d9d-4a79-9600-5e2a98c3d166
topic_type:
- apiref
ms.openlocfilehash: 7b637889986425767fd7e1166c73df3301075422
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695265"
---
# <a name="icordebugobjectvalueisvalueclass-method"></a><span data-ttu-id="43c69-102">ICorDebugObjectValue::IsValueClass 方法</span><span class="sxs-lookup"><span data-stu-id="43c69-102">ICorDebugObjectValue::IsValueClass Method</span></span>

<span data-ttu-id="43c69-103">获取一个值，该值指示此对象值是否为值类型。</span><span class="sxs-lookup"><span data-stu-id="43c69-103">Gets a value that indicates whether this object value is a value type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43c69-104">语法</span><span class="sxs-lookup"><span data-stu-id="43c69-104">Syntax</span></span>  
  
```cpp  
HRESULT IsValueClass (  
    [out] BOOL               *pbIsValueClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43c69-105">参数</span><span class="sxs-lookup"><span data-stu-id="43c69-105">Parameters</span></span>  

 `pbIsValueClass`  
 <span data-ttu-id="43c69-106">弄一个指向布尔值的指针， `true` 如果该对象值由此 "ICorDebugObjectValue" 表示，则为值类型而不是引用类型; 否则为 `pbIsValueClass` `false` 。</span><span class="sxs-lookup"><span data-stu-id="43c69-106">[out] A pointer to a Boolean value that is `true` if the object value, represented by this "ICorDebugObjectValue", is a value type rather than a reference type; otherwise, `pbIsValueClass` is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43c69-107">要求</span><span class="sxs-lookup"><span data-stu-id="43c69-107">Requirements</span></span>  

 <span data-ttu-id="43c69-108">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="43c69-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43c69-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43c69-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43c69-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43c69-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43c69-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43c69-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43c69-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="43c69-112">See also</span></span>
