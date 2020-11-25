---
title: IMetaDataImport2::EnumGenericParamConstraints 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumGenericParamConstraints
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumGenericParamConstraints
helpviewer_keywords:
- EnumGenericParamConstraints method [.NET Framework metadata]
- IMetaDataImport2::EnumGenericParamConstraints method [.NET Framework metadata]
ms.assetid: 8a7d4e40-28fe-4e14-b801-4049880130e7
topic_type:
- apiref
ms.openlocfilehash: 27c3ec349cf6c83f6783e252e6c5af5e99fa4b37
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702831"
---
# <a name="imetadataimport2enumgenericparamconstraints-method"></a><span data-ttu-id="d6022-102">IMetaDataImport2::EnumGenericParamConstraints 方法</span><span class="sxs-lookup"><span data-stu-id="d6022-102">IMetaDataImport2::EnumGenericParamConstraints Method</span></span>

<span data-ttu-id="d6022-103">获取与指定标记表示的泛型参数关联的泛型参数约束数组的枚举器。</span><span class="sxs-lookup"><span data-stu-id="d6022-103">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6022-104">语法</span><span class="sxs-lookup"><span data-stu-id="d6022-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumGenericParamConstraints (  
    [in, out] HCORENUM                *phEnum,  
    [in]  mdGenericParam              tk,  
    [out] mdGenericParamConstraint    rGenericParamConstraints[],  
    [in]  ULONG                       cMax,  
    [out] ULONG                       *pcGenericParamConstraints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6022-105">参数</span><span class="sxs-lookup"><span data-stu-id="d6022-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="d6022-106">[in，out]指向枚举器的指针。</span><span class="sxs-lookup"><span data-stu-id="d6022-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="d6022-107">中  一个标记，表示要枚举其约束的泛型参数。</span><span class="sxs-lookup"><span data-stu-id="d6022-107">[in]   A token that represents the generic parameter whose constraints are to be enumerated.</span></span>  
  
 `rGenericParamConstraints`  
 <span data-ttu-id="d6022-108">弄要枚举的泛型参数约束的数组。</span><span class="sxs-lookup"><span data-stu-id="d6022-108">[out] The array of generic parameter constraints to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="d6022-109">中  要放入的请求的最大数量 `rGenericParamConstraints` 。</span><span class="sxs-lookup"><span data-stu-id="d6022-109">[in]   The requested maximum number of tokens to place in `rGenericParamConstraints`.</span></span>  
  
 `pcGenericParamConstraints`  
 <span data-ttu-id="d6022-110">弄一个指针，指向中放置的标记数 `rGenericParamConstraints` 。</span><span class="sxs-lookup"><span data-stu-id="d6022-110">[out] A pointer to the number of tokens placed in `rGenericParamConstraints`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d6022-111">返回值</span><span class="sxs-lookup"><span data-stu-id="d6022-111">Return Value</span></span>  
  
|<span data-ttu-id="d6022-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d6022-112">HRESULT</span></span>|<span data-ttu-id="d6022-113">说明</span><span class="sxs-lookup"><span data-stu-id="d6022-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="d6022-114">`EnumGenericParameterConstraints` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="d6022-114">`EnumGenericParameterConstraints` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="d6022-115">`phEnum` 没有成员元素。</span><span class="sxs-lookup"><span data-stu-id="d6022-115">`phEnum` has no member elements.</span></span> <span data-ttu-id="d6022-116">在这种情况下， `pcGenericParameterConstraints` 设置为 0 (零) 。</span><span class="sxs-lookup"><span data-stu-id="d6022-116">In this case, `pcGenericParameterConstraints` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d6022-117">要求</span><span class="sxs-lookup"><span data-stu-id="d6022-117">Requirements</span></span>  

 <span data-ttu-id="d6022-118">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d6022-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6022-119">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="d6022-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d6022-120">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d6022-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d6022-121">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6022-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6022-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6022-122">See also</span></span>

- [<span data-ttu-id="d6022-123">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="d6022-123">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="d6022-124">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="d6022-124">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
