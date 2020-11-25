---
title: ICorDebugReferenceValue::Dereference 方法
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.Dereference
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::Dereference
helpviewer_keywords:
- ICorDebugReferenceValue::Dereference method [.NET Framework debugging]
- Dereference method [.NET Framework debugging]
ms.assetid: 5ec8cf76-3deb-4ce6-9a49-77a4c35d80b9
topic_type:
- apiref
ms.openlocfilehash: cbcee923ecbb1106bb129f05d2e602a0fd17258d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732477"
---
# <a name="icordebugreferencevaluedereference-method"></a><span data-ttu-id="729cd-102">ICorDebugReferenceValue::Dereference 方法</span><span class="sxs-lookup"><span data-stu-id="729cd-102">ICorDebugReferenceValue::Dereference Method</span></span>

<span data-ttu-id="729cd-103">获取所引用的对象。</span><span class="sxs-lookup"><span data-stu-id="729cd-103">Gets the object that is referenced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="729cd-104">语法</span><span class="sxs-lookup"><span data-stu-id="729cd-104">Syntax</span></span>  
  
```cpp  
HRESULT Dereference (  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="729cd-105">参数</span><span class="sxs-lookup"><span data-stu-id="729cd-105">Parameters</span></span>  

 `ppValue`  
 <span data-ttu-id="729cd-106">弄一个指针，指向表示此 ICorDebugReferenceValue 对象指向的对象的 ICorDebugValue 的地址。</span><span class="sxs-lookup"><span data-stu-id="729cd-106">[out] A pointer to the address of an ICorDebugValue that represents the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="729cd-107">注解</span><span class="sxs-lookup"><span data-stu-id="729cd-107">Remarks</span></span>  

 <span data-ttu-id="729cd-108">此 `ICorDebugValue` 对象仅在其引用尚未禁用时有效。</span><span class="sxs-lookup"><span data-stu-id="729cd-108">The `ICorDebugValue` object is valid only while its reference has not yet been disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="729cd-109">要求</span><span class="sxs-lookup"><span data-stu-id="729cd-109">Requirements</span></span>  

 <span data-ttu-id="729cd-110">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="729cd-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="729cd-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="729cd-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="729cd-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="729cd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="729cd-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="729cd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
