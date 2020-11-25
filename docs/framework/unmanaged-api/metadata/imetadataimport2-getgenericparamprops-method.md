---
title: IMetaDataImport2::GetGenericParamProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetGenericParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetGenericParamProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamProps method [.NET Framework metadata]
- GetGenericParamProps method [.NET Framework metadata]
ms.assetid: dbb21e67-712b-49e7-a27c-a1e73ffd46c5
topic_type:
- apiref
ms.openlocfilehash: 16f69d571ffed87a2e848124ce16ac942d319c37
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702675"
---
# <a name="imetadataimport2getgenericparamprops-method"></a><span data-ttu-id="fc848-102">IMetaDataImport2::GetGenericParamProps 方法</span><span class="sxs-lookup"><span data-stu-id="fc848-102">IMetaDataImport2::GetGenericParamProps Method</span></span>

<span data-ttu-id="fc848-103">获取与指定标记表示的泛型参数关联的元数据。</span><span class="sxs-lookup"><span data-stu-id="fc848-103">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc848-104">语法</span><span class="sxs-lookup"><span data-stu-id="fc848-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGenericParamProps (  
   [in]  mdGenericParam  gp,  
   [out] ULONG           *pulParamSeq,  
   [out] DWORD           *pdwParamFlags,  
   [out] mdToken         *ptOwner,  
   [out] DWORD           *reserved,  
   [out] LPWSTR          wzName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc848-105">参数</span><span class="sxs-lookup"><span data-stu-id="fc848-105">Parameters</span></span>  

 `gp`  
 <span data-ttu-id="fc848-106">中表示要为其返回元数据的泛型参数的标记。</span><span class="sxs-lookup"><span data-stu-id="fc848-106">[in] The token that represents the generic parameter for which to return metadata.</span></span>  
  
 `pulParamSeq`  
 <span data-ttu-id="fc848-107">弄 `Type` 参数在父构造函数或方法中的序号位置。</span><span class="sxs-lookup"><span data-stu-id="fc848-107">[out] The ordinal position of the `Type` parameter in the parent constructor or method.</span></span>  
  
 `pdwParamFlags`  
 <span data-ttu-id="fc848-108">弄用于描述泛型参数的的 [CorGenericParamAttr](corgenericparamattr-enumeration.md) 枚举的值 `Type` 。</span><span class="sxs-lookup"><span data-stu-id="fc848-108">[out] A value of the [CorGenericParamAttr](corgenericparamattr-enumeration.md) enumeration that describes the `Type` for the generic parameter.</span></span>  
  
 `ptOwner`  
 <span data-ttu-id="fc848-109">弄一个 TypeDef 或 MethodDef 标记，它表示参数的所有者。</span><span class="sxs-lookup"><span data-stu-id="fc848-109">[out] A TypeDef or MethodDef token that represents the owner of the parameter.</span></span>  
  
 `reserved`  
 <span data-ttu-id="fc848-110">弄保留以供将来进行扩展。</span><span class="sxs-lookup"><span data-stu-id="fc848-110">[out] Reserved for future extensibility.</span></span>  
  
 `wzName`  
 <span data-ttu-id="fc848-111">弄泛型参数的名称。</span><span class="sxs-lookup"><span data-stu-id="fc848-111">[out] The name of the generic parameter.</span></span>  
  
 `cchName`  
 <span data-ttu-id="fc848-112">中缓冲区的大小 `wzName` 。</span><span class="sxs-lookup"><span data-stu-id="fc848-112">[in] The size of the `wzName` buffer.</span></span>  
  
 `pchName`  
 <span data-ttu-id="fc848-113">弄以宽字符返回的名称的大小。</span><span class="sxs-lookup"><span data-stu-id="fc848-113">[out] The returned size of the name, in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc848-114">要求</span><span class="sxs-lookup"><span data-stu-id="fc848-114">Requirements</span></span>  

 <span data-ttu-id="fc848-115">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fc848-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc848-116">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="fc848-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fc848-117">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="fc848-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fc848-118">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc848-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc848-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fc848-119">See also</span></span>

- [<span data-ttu-id="fc848-120">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="fc848-120">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="fc848-121">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="fc848-121">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
