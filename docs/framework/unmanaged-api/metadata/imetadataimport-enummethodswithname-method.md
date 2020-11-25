---
title: IMetaDataImport::EnumMethodsWithName 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodsWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodsWithName
helpviewer_keywords:
- IMetaDataImport::EnumMethodsWithName method [.NET Framework metadata]
- EnumMethodsWithName method [.NET Framework metadata]
ms.assetid: a8624913-2e23-46ad-a0c1-bb8eccbbf20f
topic_type:
- apiref
ms.openlocfilehash: 5b5345fc4819716dc6c2a00323f94546cfc67f32
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720927"
---
# <a name="imetadataimportenummethodswithname-method"></a><span data-ttu-id="fa232-102">IMetaDataImport::EnumMethodsWithName 方法</span><span class="sxs-lookup"><span data-stu-id="fa232-102">IMetaDataImport::EnumMethodsWithName Method</span></span>

<span data-ttu-id="fa232-103">枚举具有指定名称并且由指定的 TypeDef 标记所引用的类型定义的方法。</span><span class="sxs-lookup"><span data-stu-id="fa232-103">Enumerates methods that have the specified name and that are defined by the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa232-104">语法</span><span class="sxs-lookup"><span data-stu-id="fa232-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodsWithName (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdTypeDef       cl,  
   [in]  LPCWSTR         szName,  
   [out] mdMethodDef     rMethods[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa232-105">参数</span><span class="sxs-lookup"><span data-stu-id="fa232-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="fa232-106">[in，out]指向枚举器的指针。</span><span class="sxs-lookup"><span data-stu-id="fa232-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="fa232-107">第一次调用此方法时，此值必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="fa232-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="fa232-108">中一个 TypeDef 标记，表示其方法要枚举的类型。</span><span class="sxs-lookup"><span data-stu-id="fa232-108">[in] A TypeDef token representing the type whose methods to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="fa232-109">中限制枚举的作用域的名称。</span><span class="sxs-lookup"><span data-stu-id="fa232-109">[in] The name that limits the scope of the enumeration.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="fa232-110">弄用于存储 MethodDef 标记的数组。</span><span class="sxs-lookup"><span data-stu-id="fa232-110">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="fa232-111">[in] `rMethods` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="fa232-111">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="fa232-112">弄中返回的 MethodDef 标记的数目 `rMethods` 。</span><span class="sxs-lookup"><span data-stu-id="fa232-112">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa232-113">注解</span><span class="sxs-lookup"><span data-stu-id="fa232-113">Remarks</span></span>  

 <span data-ttu-id="fa232-114">此方法枚举字段和方法，而不是属性或事件。</span><span class="sxs-lookup"><span data-stu-id="fa232-114">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="fa232-115">与 [IMetaDataImport：： EnumMethods](imetadataimport-enummethods-method.md)不同，会 `EnumMethodsWithName` 丢弃所有不具有指定名称的方法标记。</span><span class="sxs-lookup"><span data-stu-id="fa232-115">Unlike [IMetaDataImport::EnumMethods](imetadataimport-enummethods-method.md), `EnumMethodsWithName` discards all method tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa232-116">返回值</span><span class="sxs-lookup"><span data-stu-id="fa232-116">Return Value</span></span>  
  
|<span data-ttu-id="fa232-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fa232-117">HRESULT</span></span>|<span data-ttu-id="fa232-118">说明</span><span class="sxs-lookup"><span data-stu-id="fa232-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="fa232-119">`EnumMethodsWithName` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="fa232-119">`EnumMethodsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="fa232-120">没有要枚举的令牌。</span><span class="sxs-lookup"><span data-stu-id="fa232-120">There are no tokens to enumerate.</span></span> <span data-ttu-id="fa232-121">在这种情况下， `pcTokens` 为零。</span><span class="sxs-lookup"><span data-stu-id="fa232-121">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fa232-122">要求</span><span class="sxs-lookup"><span data-stu-id="fa232-122">Requirements</span></span>  

 <span data-ttu-id="fa232-123">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fa232-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa232-124">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="fa232-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fa232-125">**库：** 作为中的资源包含 MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fa232-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fa232-126">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa232-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa232-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fa232-127">See also</span></span>

- [<span data-ttu-id="fa232-128">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="fa232-128">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="fa232-129">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="fa232-129">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
