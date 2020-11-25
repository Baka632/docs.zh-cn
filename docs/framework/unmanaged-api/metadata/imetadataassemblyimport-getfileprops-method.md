---
title: IMetaDataAssemblyImport::GetFileProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetFileProps
helpviewer_keywords:
- GetFileProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetFileProps method [.NET Framework metadata]
ms.assetid: c5e6216f-ae3d-4697-9688-66b69c1251ec
topic_type:
- apiref
ms.openlocfilehash: 0b9ff2716cc0bc32c81fe6fcdd4e6c367d4d835f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718171"
---
# <a name="imetadataassemblyimportgetfileprops-method"></a><span data-ttu-id="42612-102">IMetaDataAssemblyImport::GetFileProps 方法</span><span class="sxs-lookup"><span data-stu-id="42612-102">IMetaDataAssemblyImport::GetFileProps Method</span></span>

<span data-ttu-id="42612-103">获取具有指定的元数据签名的文件的属性。</span><span class="sxs-lookup"><span data-stu-id="42612-103">Gets the properties of the file with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42612-104">语法</span><span class="sxs-lookup"><span data-stu-id="42612-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileProps (  
    [in]  mdFile      mdf,
    [out] LPWSTR      szName,
    [in]  ULONG       cchName,
    [out] ULONG       *pchName,
    [out] const void  **ppbHashValue,
    [out] ULONG       *pcbHashValue,
    [out] DWORD       *pdwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42612-105">参数</span><span class="sxs-lookup"><span data-stu-id="42612-105">Parameters</span></span>  

 `mdf`  
 <span data-ttu-id="42612-106">中 `mdFile` 表示要获取其属性的文件的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="42612-106">[in] The `mdFile` metadata token that represents the file for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="42612-107">弄文件的简单名称。</span><span class="sxs-lookup"><span data-stu-id="42612-107">[out] The simple name of the file.</span></span>  
  
 `cchName`  
 <span data-ttu-id="42612-108">中的大小（宽字符） `szName` 。</span><span class="sxs-lookup"><span data-stu-id="42612-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="42612-109">弄中实际返回的宽字符数 `szName` 。</span><span class="sxs-lookup"><span data-stu-id="42612-109">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="42612-110">弄指向哈希值的指针。</span><span class="sxs-lookup"><span data-stu-id="42612-110">[out] A pointer to the hash value.</span></span> <span data-ttu-id="42612-111">这是文件的哈希，使用 SHA-1 算法。</span><span class="sxs-lookup"><span data-stu-id="42612-111">This is the hash, using the SHA-1 algorithm, of the file.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="42612-112">弄返回的哈希值中的宽字符数。</span><span class="sxs-lookup"><span data-stu-id="42612-112">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwFileFlags`  
 <span data-ttu-id="42612-113">弄一个指针，指向描述应用于文件的元数据的标志。</span><span class="sxs-lookup"><span data-stu-id="42612-113">[out] A pointer to the flags that describe the metadata applied to a file.</span></span> <span data-ttu-id="42612-114">Flags 值是一个或多个 [CorFileFlags](corfileflags-enumeration.md) 值的组合。</span><span class="sxs-lookup"><span data-stu-id="42612-114">The flags value is a combination of one or more [CorFileFlags](corfileflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42612-115">要求</span><span class="sxs-lookup"><span data-stu-id="42612-115">Requirements</span></span>  

 <span data-ttu-id="42612-116">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="42612-116">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42612-117">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="42612-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="42612-118">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="42612-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="42612-119">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42612-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42612-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="42612-120">See also</span></span>

- [<span data-ttu-id="42612-121">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="42612-121">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
