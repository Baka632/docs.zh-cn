---
title: IMetaDataEmit::TranslateSigWithScope 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.TranslateSigWithScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::TranslateSigWithScope
helpviewer_keywords:
- TranslateSigWithScope method [.NET Framework metadata]
- IMetaDataEmit::TranslateSigWithScope method [.NET Framework metadata]
ms.assetid: 47915d33-b7bf-409e-b484-4ee1df15de22
topic_type:
- apiref
ms.openlocfilehash: 80d33da2eb2a7f0cfbe5dcb7279fff9973dada2e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712919"
---
# <a name="imetadataemittranslatesigwithscope-method"></a><span data-ttu-id="aaf99-102">IMetaDataEmit::TranslateSigWithScope 方法</span><span class="sxs-lookup"><span data-stu-id="aaf99-102">IMetaDataEmit::TranslateSigWithScope Method</span></span>

<span data-ttu-id="aaf99-103">将程序集导入到当前作用域中，并为合并的作用域获取新的元数据签名。</span><span class="sxs-lookup"><span data-stu-id="aaf99-103">Imports an assembly into the current scope and gets a new metadata signature for the merged scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aaf99-104">语法</span><span class="sxs-lookup"><span data-stu-id="aaf99-104">Syntax</span></span>  
  
```cpp  
HRESULT TranslateSigWithScope (
    [in]  IMetaDataAssemblyImport   *pAssemImport,
    [in]  const void                *pbHashValue,
    [in]  ULONG                     cbHashValue,
    [in]  IMetaDataImport           *import,
    [in]  PCCOR_SIGNATURE           pbSigBlob,
    [in]  ULONG                     cbSigBlob,  
    [in]  IMetaDataAssemblyEmit     *pAssemEmit,
    [in]  IMetaDataEmit             *emit,
    [out] PCOR_SIGNATURE            pvTranslatedSig,
    [in]  ULONG                     cbTranslatedSigMax,
    [out] ULONG                     *pcbTranslatedSig
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aaf99-105">参数</span><span class="sxs-lookup"><span data-stu-id="aaf99-105">Parameters</span></span>  

 `pAssemImport`  
 <span data-ttu-id="aaf99-106">中导入程序集 (的接口) 在其中定义签名。</span><span class="sxs-lookup"><span data-stu-id="aaf99-106">[in] The interface for import assembly (where the signature is defined).</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="aaf99-107">中程序集的哈希 blob。</span><span class="sxs-lookup"><span data-stu-id="aaf99-107">[in] The hash blob for the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="aaf99-108">中中的字节数 `pbHashValue` 。</span><span class="sxs-lookup"><span data-stu-id="aaf99-108">[in] The count of bytes in `pbHashValue`.</span></span>  
  
 `import`  
 <span data-ttu-id="aaf99-109">中导入元数据范围的接口。</span><span class="sxs-lookup"><span data-stu-id="aaf99-109">[in] The interface for import metadata scope.</span></span>  
  
 `pbSigBlob`  
 <span data-ttu-id="aaf99-110">中要导入的签名。</span><span class="sxs-lookup"><span data-stu-id="aaf99-110">[in] The signature to be imported.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="aaf99-111">中的大小（以字节为单位） `pbSigBlob` 。</span><span class="sxs-lookup"><span data-stu-id="aaf99-111">[in] The size, in bytes, of `pbSigBlob`.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="aaf99-112">中导出程序集的接口。</span><span class="sxs-lookup"><span data-stu-id="aaf99-112">[in] The interface for export assembly.</span></span>  
  
 `emit`  
 <span data-ttu-id="aaf99-113">中导出元数据范围的接口。</span><span class="sxs-lookup"><span data-stu-id="aaf99-113">[in] The interface for export metadata scope.</span></span>  
  
 `pvTranslatedSig`  
 <span data-ttu-id="aaf99-114">弄用于保存已转换的签名 blob 的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="aaf99-114">[out] The buffer to hold the translated signature blob.</span></span>  
  
 `cbTranslatedSigMax`  
 <span data-ttu-id="aaf99-115">中的容量（以字节为单位） `pvTranslatedSig` 。</span><span class="sxs-lookup"><span data-stu-id="aaf99-115">[in] The capacity, in bytes, of `pvTranslatedSig`.</span></span>  
  
 `pcbTranslatedSig`  
 <span data-ttu-id="aaf99-116">弄已翻译签名中的实际字节数。</span><span class="sxs-lookup"><span data-stu-id="aaf99-116">[out] The number of actual bytes in the translated signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aaf99-117">要求</span><span class="sxs-lookup"><span data-stu-id="aaf99-117">Requirements</span></span>  

 <span data-ttu-id="aaf99-118">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="aaf99-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aaf99-119">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="aaf99-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="aaf99-120">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="aaf99-120">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aaf99-121">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aaf99-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaf99-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aaf99-122">See also</span></span>

- [<span data-ttu-id="aaf99-123">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="aaf99-123">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="aaf99-124">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="aaf99-124">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
- [<span data-ttu-id="aaf99-125">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="aaf99-125">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="aaf99-126">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="aaf99-126">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="aaf99-127">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="aaf99-127">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
