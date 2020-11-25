---
title: IMetaDataAssemblyImport::GetExportedTypeProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetExportedTypeProps
helpviewer_keywords:
- GetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 25ca7623-5a55-4f09-b44a-36b03d142278
topic_type:
- apiref
ms.openlocfilehash: 32224431051b958a3f01ffeb15cdb6db1dae2657
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722097"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a><span data-ttu-id="4a0a0-102">IMetaDataAssemblyImport::GetExportedTypeProps 方法</span><span class="sxs-lookup"><span data-stu-id="4a0a0-102">IMetaDataAssemblyImport::GetExportedTypeProps Method</span></span>

<span data-ttu-id="4a0a0-103">获取具有指定元数据签名的导出类型的属性集。</span><span class="sxs-lookup"><span data-stu-id="4a0a0-103">Gets the set of properties of the exported type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a0a0-104">语法</span><span class="sxs-lookup"><span data-stu-id="4a0a0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExportedTypeProps (  
    [in]  mdExportedType    mdct,
    [out] LPWSTR            szName,
    [in]  ULONG             cchName,
    [out] ULONG             *pchName,
    [out] mdToken           *ptkImplementation,
    [out] mdTypeDef         *ptkTypeDef,
    [out] DWORD             *pdwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a0a0-105">参数</span><span class="sxs-lookup"><span data-stu-id="4a0a0-105">Parameters</span></span>  

 `mdct`  
 <span data-ttu-id="4a0a0-106">中 `mdExportedType` 表示导出类型的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="4a0a0-106">[in] An `mdExportedType` metadata token that represents the exported type.</span></span>  
  
 `szName`  
 <span data-ttu-id="4a0a0-107">弄导出的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="4a0a0-107">[out] The name of the exported type.</span></span>  
  
 `cchName`  
 <span data-ttu-id="4a0a0-108">中的大小（宽字符） `szName` 。</span><span class="sxs-lookup"><span data-stu-id="4a0a0-108">[in] The size, in wide characters, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="4a0a0-109">弄实际返回的宽字符数 `szName`</span><span class="sxs-lookup"><span data-stu-id="4a0a0-109">[out] The number of wide characters actually returned in `szName`</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="4a0a0-110">弄 `mdFile`、或 `mdAssemblyRef` `mdExportedType` 元数据标记，其中包含或允许访问导出的类型的属性。</span><span class="sxs-lookup"><span data-stu-id="4a0a0-110">[out] An `mdFile`, `mdAssemblyRef`, or `mdExportedType` metadata token that contains or allows access to the properties of the exported type.</span></span>  
  
 `ptkTypeDef`  
 <span data-ttu-id="4a0a0-111">弄一个指针，指向 `mdTypeDef` 表示文件中的类型的标记。</span><span class="sxs-lookup"><span data-stu-id="4a0a0-111">[out] A pointer to an `mdTypeDef` token that represents a type in the file.</span></span>  
  
 `pdwExportedTypeFlags`  
 <span data-ttu-id="4a0a0-112">弄一个指针，指向用于描述应用于导出类型的元数据的标志。</span><span class="sxs-lookup"><span data-stu-id="4a0a0-112">[out] A pointer to the flags that describe the metadata applied to the exported type.</span></span> <span data-ttu-id="4a0a0-113">Flags 值可以是一个或多个 [CorTypeAttr](cortypeattr-enumeration.md) 值。</span><span class="sxs-lookup"><span data-stu-id="4a0a0-113">The flags value can be one or more [CorTypeAttr](cortypeattr-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a0a0-114">要求</span><span class="sxs-lookup"><span data-stu-id="4a0a0-114">Requirements</span></span>  

 <span data-ttu-id="4a0a0-115">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4a0a0-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a0a0-116">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="4a0a0-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4a0a0-117">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4a0a0-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4a0a0-118">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a0a0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a0a0-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a0a0-119">See also</span></span>

- [<span data-ttu-id="4a0a0-120">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="4a0a0-120">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
