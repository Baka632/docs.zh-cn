---
title: IMetaDataImport::EnumMethodImpls 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodImpls
helpviewer_keywords:
- EnumMethodImpls method [.NET Framework metadata]
- IMetaDataImport::EnumMethodImpls method [.NET Framework metadata]
ms.assetid: 4e0f865d-88b5-44bd-be35-492622e5e08e
topic_type:
- apiref
ms.openlocfilehash: 40ab610110e96018b1c598d04b24a762ecb50717
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690481"
---
# <a name="imetadataimportenummethodimpls-method"></a><span data-ttu-id="434cd-102">IMetaDataImport::EnumMethodImpls 方法</span><span class="sxs-lookup"><span data-stu-id="434cd-102">IMetaDataImport::EnumMethodImpls Method</span></span>

<span data-ttu-id="434cd-103">枚举表示指定类型的方法的 MethodBody 和 MethodDeclaration 标记。</span><span class="sxs-lookup"><span data-stu-id="434cd-103">Enumerates MethodBody and MethodDeclaration tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="434cd-104">语法</span><span class="sxs-lookup"><span data-stu-id="434cd-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodImpls (  
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   td,
   [out]     mdToken     rMethodBody[],
   [out]     mdToken     rMethodDecl[],
   [in]      ULONG       cMax,
   [in]      ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="434cd-105">参数</span><span class="sxs-lookup"><span data-stu-id="434cd-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="434cd-106">[in，out]指向枚举器的指针。</span><span class="sxs-lookup"><span data-stu-id="434cd-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="434cd-107">第一次调用此方法时，此值必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="434cd-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="434cd-108">中要枚举其方法实现的类型的 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="434cd-108">[in] A TypeDef token for the type whose method implementations to enumerate.</span></span>  
  
 `rMethodBody`  
 <span data-ttu-id="434cd-109">弄用于存储 MethodBody 标记的数组。</span><span class="sxs-lookup"><span data-stu-id="434cd-109">[out] The array to store the MethodBody tokens.</span></span>  
  
 `rMethodDecl`  
 <span data-ttu-id="434cd-110">弄用于存储 MethodDeclaration 标记的数组。</span><span class="sxs-lookup"><span data-stu-id="434cd-110">[out] The array to store the MethodDeclaration tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="434cd-111">中和数组的最大 `rMethodBody` 大小 `rMethodDecl` 。</span><span class="sxs-lookup"><span data-stu-id="434cd-111">[in] The maximum size of the `rMethodBody` and `rMethodDecl` arrays.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="434cd-112">中和中返回的实际方法数 `rMethodBody` `rMethodDecl` 。</span><span class="sxs-lookup"><span data-stu-id="434cd-112">[in] The actual number of methods returned in `rMethodBody` and `rMethodDecl`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="434cd-113">返回值</span><span class="sxs-lookup"><span data-stu-id="434cd-113">Return Value</span></span>  
  
|<span data-ttu-id="434cd-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="434cd-114">HRESULT</span></span>|<span data-ttu-id="434cd-115">说明</span><span class="sxs-lookup"><span data-stu-id="434cd-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="434cd-116">`EnumMethodImpls` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="434cd-116">`EnumMethodImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="434cd-117">没有要枚举的方法标记。</span><span class="sxs-lookup"><span data-stu-id="434cd-117">There are no method tokens to enumerate.</span></span> <span data-ttu-id="434cd-118">在这种情况下， `pcTokens` 为零。</span><span class="sxs-lookup"><span data-stu-id="434cd-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="434cd-119">要求</span><span class="sxs-lookup"><span data-stu-id="434cd-119">Requirements</span></span>  

 <span data-ttu-id="434cd-120">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="434cd-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="434cd-121">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="434cd-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="434cd-122">**库：** 作为中的资源包含 MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="434cd-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="434cd-123">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="434cd-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="434cd-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="434cd-124">See also</span></span>

- [<span data-ttu-id="434cd-125">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="434cd-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="434cd-126">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="434cd-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
