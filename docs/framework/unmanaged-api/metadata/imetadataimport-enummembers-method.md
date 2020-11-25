---
title: IMetaDataImport::EnumMembers 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMembers
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMembers
helpviewer_keywords:
- IMetaDataImport::EnumMembers method [.NET Framework metadata]
- EnumMembers method [.NET Framework metadata]
ms.assetid: 3fb8e178-342b-4c89-9bcf-f7f834e6cb77
topic_type:
- apiref
ms.openlocfilehash: 92503df60ae44dfd44819fe3eda8e6a0549b2b66
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720980"
---
# <a name="imetadataimportenummembers-method"></a><span data-ttu-id="ae67a-102">IMetaDataImport::EnumMembers 方法</span><span class="sxs-lookup"><span data-stu-id="ae67a-102">IMetaDataImport::EnumMembers Method</span></span>

<span data-ttu-id="ae67a-103">枚举表示指定类型的成员的 MemberDef 标记。</span><span class="sxs-lookup"><span data-stu-id="ae67a-103">Enumerates MemberDef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae67a-104">语法</span><span class="sxs-lookup"><span data-stu-id="ae67a-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMembers (
   [in, out]  HCORENUM    *phEnum,
   [in]  mdTypeDef   cl,
   [out] mdToken     rMembers[],
   [in]  ULONG       cMax,
   [out] ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae67a-105">参数</span><span class="sxs-lookup"><span data-stu-id="ae67a-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="ae67a-106">[in，out]指向枚举器的指针。</span><span class="sxs-lookup"><span data-stu-id="ae67a-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="ae67a-107">中一个 TypeDef 标记，表示要枚举其成员的类型。</span><span class="sxs-lookup"><span data-stu-id="ae67a-107">[in] A TypeDef token representing the type whose members are to be enumerated.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="ae67a-108">弄用于保存 MemberDef 标记的数组。</span><span class="sxs-lookup"><span data-stu-id="ae67a-108">[out] The array used to hold the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ae67a-109">[in] `rMembers` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="ae67a-109">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="ae67a-110">弄中返回的 MemberDef 令牌的实际数量 `rMembers` 。</span><span class="sxs-lookup"><span data-stu-id="ae67a-110">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ae67a-111">返回值</span><span class="sxs-lookup"><span data-stu-id="ae67a-111">Return Value</span></span>  
  
|<span data-ttu-id="ae67a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ae67a-112">HRESULT</span></span>|<span data-ttu-id="ae67a-113">说明</span><span class="sxs-lookup"><span data-stu-id="ae67a-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="ae67a-114">`EnumMembers` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="ae67a-114">`EnumMembers` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="ae67a-115">没有要枚举的 MemberDef 令牌。</span><span class="sxs-lookup"><span data-stu-id="ae67a-115">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="ae67a-116">在这种情况下， `pcTokens` 为零。</span><span class="sxs-lookup"><span data-stu-id="ae67a-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae67a-117">注解</span><span class="sxs-lookup"><span data-stu-id="ae67a-117">Remarks</span></span>  

 <span data-ttu-id="ae67a-118">枚举类的成员集合时， `EnumMembers` 只会返回 (字段和方法的成员，但 **不会** 返回直接在类上定义的属性或事件) 。</span><span class="sxs-lookup"><span data-stu-id="ae67a-118">When enumerating collections of members for a class, `EnumMembers` returns only members (fields and methods, but **not** properties or events) defined directly on the class.</span></span> <span data-ttu-id="ae67a-119">即使该类为这些继承成员提供了实现，它也不会返回类继承的任何成员。</span><span class="sxs-lookup"><span data-stu-id="ae67a-119">It does not return any members that the class inherits, even if the class provides an implementation for those inherited members.</span></span> <span data-ttu-id="ae67a-120">若要枚举继承成员，调用方必须显式遍历继承链。</span><span class="sxs-lookup"><span data-stu-id="ae67a-120">To enumerate inherited members, the caller must explicitly walk the inheritance chain.</span></span> <span data-ttu-id="ae67a-121">请注意，根据发出原始元数据的语言或编译器，继承链的规则可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="ae67a-121">Note that the rules for the inheritance chain may vary depending on the language or compiler that emitted the original metadata.</span></span>

 <span data-ttu-id="ae67a-122">属性和事件不是由枚举的 `EnumMembers` 。</span><span class="sxs-lookup"><span data-stu-id="ae67a-122">Properties and events are not enumerated by `EnumMembers`.</span></span> <span data-ttu-id="ae67a-123">若要枚举这些枚举，请使用 [EnumProperties](imetadataimport-enumproperties-method.md) 或 [EnumEvents](imetadataimport-enumevents-method.md)。</span><span class="sxs-lookup"><span data-stu-id="ae67a-123">To enumerate those, use [EnumProperties](imetadataimport-enumproperties-method.md) or [EnumEvents](imetadataimport-enumevents-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="ae67a-124">要求</span><span class="sxs-lookup"><span data-stu-id="ae67a-124">Requirements</span></span>  

 <span data-ttu-id="ae67a-125">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ae67a-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae67a-126">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="ae67a-126">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ae67a-127">**库：** 作为中的资源包含 MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ae67a-127">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ae67a-128">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae67a-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae67a-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ae67a-129">See also</span></span>

- [<span data-ttu-id="ae67a-130">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="ae67a-130">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="ae67a-131">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="ae67a-131">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
