---
title: IMetaDataImport::GetMethodSemantics 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodSemantics
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodSemantics
helpviewer_keywords:
- GetMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::GetMethodSemantics method [.NET Framework metadata]
ms.assetid: 5e018eaa-d60e-4a0b-a2c5-8c36bd09d905
topic_type:
- apiref
ms.openlocfilehash: cc01a417c3246ad2554c506f21e37a3cbbdeb991
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733174"
---
# <a name="imetadataimportgetmethodsemantics-method"></a><span data-ttu-id="94733-102">IMetaDataImport::GetMethodSemantics 方法</span><span class="sxs-lookup"><span data-stu-id="94733-102">IMetaDataImport::GetMethodSemantics Method</span></span>

<span data-ttu-id="94733-103">获取指示指定的 MethodDef 标记所引用的方法与指定的 EventProp 标记所引用的成对属性和事件之间的关系的标志。</span><span class="sxs-lookup"><span data-stu-id="94733-103">Gets flags indicating the relationship between the method referenced by the specified MethodDef token and the paired property and event referenced by the specified EventProp token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94733-104">语法</span><span class="sxs-lookup"><span data-stu-id="94733-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodSemantics (  
   [in]  mdMethodDef   mb,  
   [in]  mdToken       tkEventProp,  
   [out] DWORD         *pdwSemanticsFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94733-105">参数</span><span class="sxs-lookup"><span data-stu-id="94733-105">Parameters</span></span>  

 `mb`  
 <span data-ttu-id="94733-106">中一个 MethodDef 标记，表示要获取其语义角色信息的方法。</span><span class="sxs-lookup"><span data-stu-id="94733-106">[in] A MethodDef token representing the method to get the semantic role information for.</span></span>  
  
 `tkEventProp`  
 <span data-ttu-id="94733-107">中一个标记，它表示要为其获取方法的角色的成对属性和事件。</span><span class="sxs-lookup"><span data-stu-id="94733-107">[in] A token representing the paired property and event for which to get the method's role.</span></span>  
  
 `pdwSemanticsFlags`  
 <span data-ttu-id="94733-108">弄指向关联语义标志的指针。</span><span class="sxs-lookup"><span data-stu-id="94733-108">[out] A pointer to the associated semantics flags.</span></span> <span data-ttu-id="94733-109">此值是 [CorMethodSemanticsAttr](cormethodsemanticsattr-enumeration.md) 枚举中的位掩码。</span><span class="sxs-lookup"><span data-stu-id="94733-109">This value is a bitmask from the [CorMethodSemanticsAttr](cormethodsemanticsattr-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94733-110">注解</span><span class="sxs-lookup"><span data-stu-id="94733-110">Remarks</span></span>  

 <span data-ttu-id="94733-111">[IMetaDataEmit：:D efineproperty](imetadataemit-defineproperty-method.md)方法设置方法的语义标志。</span><span class="sxs-lookup"><span data-stu-id="94733-111">The [IMetaDataEmit::DefineProperty](imetadataemit-defineproperty-method.md) method sets a method's semantics flags.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94733-112">要求</span><span class="sxs-lookup"><span data-stu-id="94733-112">Requirements</span></span>  

 <span data-ttu-id="94733-113">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="94733-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94733-114">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="94733-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="94733-115">**库：** 作为中的资源包含 MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="94733-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="94733-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94733-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94733-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94733-117">See also</span></span>

- [<span data-ttu-id="94733-118">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="94733-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="94733-119">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="94733-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
