---
title: IMetaDataEmit::DefineField 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineField
helpviewer_keywords:
- IMetaDataEmit::DefineField method [.NET Framework metadata]
- DefineField method, IMetaDataEmit interface [.NET Framework metadata
ms.assetid: 6b5be4fc-2e86-499c-8b09-833160bca767
topic_type:
- apiref
ms.openlocfilehash: 2bc2b983171dc41d5ac37eda0359f1aaee4ebd6e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725750"
---
# <a name="imetadataemitdefinefield-method"></a><span data-ttu-id="64806-102">IMetaDataEmit::DefineField 方法</span><span class="sxs-lookup"><span data-stu-id="64806-102">IMetaDataEmit::DefineField Method</span></span>

<span data-ttu-id="64806-103">使用指定的元数据签名创建字段的定义，并获取该字段定义的标记。</span><span class="sxs-lookup"><span data-stu-id="64806-103">Creates a definition for a field with the specified metadata signature, and gets a token to that field definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64806-104">语法</span><span class="sxs-lookup"><span data-stu-id="64806-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineField (
    [in]  mdTypeDef   td,
    [in]  LPCWSTR     szName,
    [in]  DWORD       dwFieldFlags,
    [in]  PCCOR_SIGNATURE pvSigBlob,
    [in]  ULONG       cbSigBlob,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue,
    [out] mdFieldDef  *pmd
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64806-105">参数</span><span class="sxs-lookup"><span data-stu-id="64806-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="64806-106">中 `mdTypeDef` 封闭类或接口的标记。</span><span class="sxs-lookup"><span data-stu-id="64806-106">[in] The `mdTypeDef` token for the enclosing class or interface.</span></span>  
  
 `szName`  
 <span data-ttu-id="64806-107">中Unicode 中的字段名称。</span><span class="sxs-lookup"><span data-stu-id="64806-107">[in] The field name in Unicode.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="64806-108">中字段特性。</span><span class="sxs-lookup"><span data-stu-id="64806-108">[in] The field attributes.</span></span> <span data-ttu-id="64806-109">这是一个值的位掩码 `CorFieldAttr` 。</span><span class="sxs-lookup"><span data-stu-id="64806-109">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="64806-110">中作为 BLOB 的字段签名。</span><span class="sxs-lookup"><span data-stu-id="64806-110">[in] The field signature as a BLOB.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="64806-111">中中的字节数 `pvSigBlob` 。</span><span class="sxs-lookup"><span data-stu-id="64806-111">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="64806-112">中`ELEMENT_TYPE_` *\** 常数值的。</span><span class="sxs-lookup"><span data-stu-id="64806-112">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="64806-113">这是一个 `CorElementType` 值。</span><span class="sxs-lookup"><span data-stu-id="64806-113">This is a `CorElementType` value.</span></span> <span data-ttu-id="64806-114">如果没有为字段定义常数值，请使用 `ELEMENT_TYPE_END` 。</span><span class="sxs-lookup"><span data-stu-id="64806-114">If not defining a constant value for the field, use `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="64806-115">中字段的常数值。</span><span class="sxs-lookup"><span data-stu-id="64806-115">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="64806-116">中 (Unicode) 字符的大小 `pValue` 。</span><span class="sxs-lookup"><span data-stu-id="64806-116">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
 `pmd`  
 <span data-ttu-id="64806-117">弄 `mdFieldDef` 分配的令牌。</span><span class="sxs-lookup"><span data-stu-id="64806-117">[out] The `mdFieldDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64806-118">要求</span><span class="sxs-lookup"><span data-stu-id="64806-118">Requirements</span></span>  

 <span data-ttu-id="64806-119">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="64806-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64806-120">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="64806-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="64806-121">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="64806-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="64806-122">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64806-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64806-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="64806-123">See also</span></span>

- [<span data-ttu-id="64806-124">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="64806-124">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="64806-125">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="64806-125">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
