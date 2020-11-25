---
title: IMetaDataImport::GetScopeProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetScopeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetScopeProps
helpviewer_keywords:
- IMetaDataImport::GetScopeProps method [.NET Framework metadata]
- GetScopeProps method [.NET Framework metadata]
ms.assetid: c8ba42d2-d9fa-43cb-bbc0-f33e1e592cb6
topic_type:
- apiref
ms.openlocfilehash: 5a89d1406daa9a2416a708b63d88fd9005234015
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729195"
---
# <a name="imetadataimportgetscopeprops-method"></a><span data-ttu-id="748bc-102">IMetaDataImport::GetScopeProps 方法</span><span class="sxs-lookup"><span data-stu-id="748bc-102">IMetaDataImport::GetScopeProps Method</span></span>

<span data-ttu-id="748bc-103">获取当前元数据范围内的程序集或模块的名称和版本标识符（可选）。</span><span class="sxs-lookup"><span data-stu-id="748bc-103">Gets the name and optionally the version identifier of the assembly or module in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="748bc-104">语法</span><span class="sxs-lookup"><span data-stu-id="748bc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScopeProps (  
   [out] LPWSTR           szName,  
   [in]  ULONG            cchName,  
   [out] ULONG            *pchName,  
   [out, optional] GUID   *pmvid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="748bc-105">参数</span><span class="sxs-lookup"><span data-stu-id="748bc-105">Parameters</span></span>  

 `szName`  
 <span data-ttu-id="748bc-106">弄程序集或模块名称的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="748bc-106">[out] A buffer for the assembly or module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="748bc-107">中的大小（以宽字符为大小） `szName` 。</span><span class="sxs-lookup"><span data-stu-id="748bc-107">[in] The size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="748bc-108">弄返回的宽字符数 `szName` 。</span><span class="sxs-lookup"><span data-stu-id="748bc-108">[out] The number of wide characters returned in `szName`.</span></span>  
  
 `pmvid`  
 <span data-ttu-id="748bc-109">[out，optional]一个指向 GUID 的指针，该 GUID 用于唯一标识程序集或模块的版本。</span><span class="sxs-lookup"><span data-stu-id="748bc-109">[out, optional] A pointer to a GUID that uniquely identifies the version of the assembly or module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="748bc-110">注解</span><span class="sxs-lookup"><span data-stu-id="748bc-110">Remarks</span></span>  

 <span data-ttu-id="748bc-111">使用 [IMetaDataEmit：： SetModuleProps](imetadataemit-setmoduleprops-method.md) 方法设置这些属性。</span><span class="sxs-lookup"><span data-stu-id="748bc-111">The [IMetaDataEmit::SetModuleProps](imetadataemit-setmoduleprops-method.md) method is used to set these properties.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="748bc-112">要求</span><span class="sxs-lookup"><span data-stu-id="748bc-112">Requirements</span></span>  

 <span data-ttu-id="748bc-113">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="748bc-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="748bc-114">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="748bc-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="748bc-115">**库：** 作为中的资源包含 MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="748bc-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="748bc-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="748bc-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="748bc-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="748bc-117">See also</span></span>

- [<span data-ttu-id="748bc-118">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="748bc-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="748bc-119">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="748bc-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
