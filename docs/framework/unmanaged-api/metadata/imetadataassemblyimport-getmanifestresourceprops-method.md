---
title: IMetaDataAssemblyImport::GetManifestResourceProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetManifestResourceProps
helpviewer_keywords:
- GetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetManifestResourceProps method [.NET Framework metadata]
ms.assetid: 00be4789-ac63-4397-b2ec-1629a5c5a585
topic_type:
- apiref
ms.openlocfilehash: 585a9e39f529294841cd11389f03d763968a0f5e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723813"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a><span data-ttu-id="7d587-102">IMetaDataAssemblyImport::GetManifestResourceProps 方法</span><span class="sxs-lookup"><span data-stu-id="7d587-102">IMetaDataAssemblyImport::GetManifestResourceProps Method</span></span>

<span data-ttu-id="7d587-103">获取具有指定元数据签名的清单资源的属性集。</span><span class="sxs-lookup"><span data-stu-id="7d587-103">Gets the set of properties of the manifest resource with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d587-104">语法</span><span class="sxs-lookup"><span data-stu-id="7d587-104">Syntax</span></span>  
  
```cpp  
HRESULT GetManifestResourceProps (  
    [in]  mdManifestResource   mdmr,
    [out] LPWSTR               szName,
    [in]  ULONG                cchName,
    [out] ULONG                *pchName,
    [out] mdToken              *ptkImplementation,
    [out] DWORD                *pdwOffset,
    [out] DWORD                *pdwResourceFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d587-105">参数</span><span class="sxs-lookup"><span data-stu-id="7d587-105">Parameters</span></span>  

 `mdmr`  
 <span data-ttu-id="7d587-106">中一个 `mdManifestResource` 标记，表示要获取其属性的资源。</span><span class="sxs-lookup"><span data-stu-id="7d587-106">[in] An `mdManifestResource` token that represents the resource for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="7d587-107">弄资源的名称。</span><span class="sxs-lookup"><span data-stu-id="7d587-107">[out] The name of the resource.</span></span>  
  
 `cchName`  
 <span data-ttu-id="7d587-108">中的大小（宽字符） `szName` 。</span><span class="sxs-lookup"><span data-stu-id="7d587-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="7d587-109">弄一个指针，指向在中实际返回的宽字符数 `szName` 。</span><span class="sxs-lookup"><span data-stu-id="7d587-109">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="7d587-110">弄一个指针，该指针指向 `mdFile` 包含资源的标记或 `mdAssemblyRef` 表示文件或程序集的标记。</span><span class="sxs-lookup"><span data-stu-id="7d587-110">[out] A pointer to an `mdFile` token or an `mdAssemblyRef` token that represents the file or assembly, respectively, that contains the resource.</span></span>  
  
 `pdwOffset`  
 <span data-ttu-id="7d587-111">弄一个指向值的指针，该值指定文件中资源开始处的偏移量。</span><span class="sxs-lookup"><span data-stu-id="7d587-111">[out] A pointer to a value that specifies the offset to the beginning of the resource within the file.</span></span>  
  
 `pdwResourceFlags`  
 <span data-ttu-id="7d587-112">弄一个指针，指向用于描述应用于资源的元数据的标志。</span><span class="sxs-lookup"><span data-stu-id="7d587-112">[out] A pointer to flags that describe the metadata applied to a resource.</span></span> <span data-ttu-id="7d587-113">Flags 值是一个或多个 [CorManifestResourceFlags](cormanifestresourceflags-enumeration.md) 值的组合。</span><span class="sxs-lookup"><span data-stu-id="7d587-113">The flags value is a combination of one or more [CorManifestResourceFlags](cormanifestresourceflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d587-114">要求</span><span class="sxs-lookup"><span data-stu-id="7d587-114">Requirements</span></span>  

 <span data-ttu-id="7d587-115">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7d587-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d587-116">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="7d587-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7d587-117">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7d587-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7d587-118">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d587-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d587-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d587-119">See also</span></span>

- [<span data-ttu-id="7d587-120">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="7d587-120">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
