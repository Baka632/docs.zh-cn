---
title: ICorDebugValue::GetType 方法
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetType
helpviewer_keywords:
- ICorDebugValue::GetType method [.NET Framework debugging]
- GetType method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: 41e2d503-e1f1-407b-abe0-6a29adb3e0d1
topic_type:
- apiref
ms.openlocfilehash: 06f403f0b653866428a41240f99833ec1180eb86
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731067"
---
# <a name="icordebugvaluegettype-method"></a><span data-ttu-id="1ab9d-102">ICorDebugValue::GetType 方法</span><span class="sxs-lookup"><span data-stu-id="1ab9d-102">ICorDebugValue::GetType Method</span></span>

<span data-ttu-id="1ab9d-103">获取此 "ICorDebugValue" 对象的基元类型。</span><span class="sxs-lookup"><span data-stu-id="1ab9d-103">Gets the primitive type of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ab9d-104">语法</span><span class="sxs-lookup"><span data-stu-id="1ab9d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ab9d-105">参数</span><span class="sxs-lookup"><span data-stu-id="1ab9d-105">Parameters</span></span>  

 `pType`  
 <span data-ttu-id="1ab9d-106">弄一个指针，指向 "CorElementType" 枚举的值，该值指示值的类型。</span><span class="sxs-lookup"><span data-stu-id="1ab9d-106">[out] A pointer to a value of the "CorElementType" enumeration that indicates the value's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ab9d-107">注解</span><span class="sxs-lookup"><span data-stu-id="1ab9d-107">Remarks</span></span>  

 <span data-ttu-id="1ab9d-108">如果对象是复杂的运行时类型，则可以通过接口的相应子类检查该类型 `ICorDebugValue` 。</span><span class="sxs-lookup"><span data-stu-id="1ab9d-108">If the object is a complex run-time type, that type may be examined through the appropriate subclasses of the `ICorDebugValue` interface.</span></span> <span data-ttu-id="1ab9d-109">例如，"ICorDebugObjectValue" 是从继承的，它 `ICorDebugValue` 表示一个复杂类型。</span><span class="sxs-lookup"><span data-stu-id="1ab9d-109">For example, "ICorDebugObjectValue", which inherits from `ICorDebugValue`, represents a complex type.</span></span>  
  
 <span data-ttu-id="1ab9d-110">`GetType`和[ICorDebugObjectValue：： GetClass](icordebugobjectvalue-getclass-method.md)方法各自返回值类型的相关信息。</span><span class="sxs-lookup"><span data-stu-id="1ab9d-110">The `GetType` and [ICorDebugObjectValue::GetClass](icordebugobjectvalue-getclass-method.md) methods each return information about the type of a value.</span></span> <span data-ttu-id="1ab9d-111">它们都是由识别泛型的 [ICorDebugValue2：： GetExactType](icordebugvalue2-getexacttype-method.md) 方法取代的。</span><span class="sxs-lookup"><span data-stu-id="1ab9d-111">They are both superseded by the generics-aware [ICorDebugValue2::GetExactType](icordebugvalue2-getexacttype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ab9d-112">要求</span><span class="sxs-lookup"><span data-stu-id="1ab9d-112">Requirements</span></span>  

 <span data-ttu-id="1ab9d-113">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1ab9d-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ab9d-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1ab9d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1ab9d-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ab9d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1ab9d-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ab9d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ab9d-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1ab9d-117">See also</span></span>
