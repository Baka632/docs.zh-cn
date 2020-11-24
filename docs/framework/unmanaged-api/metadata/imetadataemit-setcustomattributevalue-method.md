---
title: IMetaDataEmit::SetCustomAttributeValue 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetCustomAttributeValue
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetCustomAttributeValue
helpviewer_keywords:
- SetCustomAttributeValue method [.NET Framework metadata]
- IMetaDataEmit::SetCustomAttributeValue method [.NET Framework metadata]
ms.assetid: f721c863-9642-4e64-917a-65f9e55c25b9
topic_type:
- apiref
ms.openlocfilehash: c4ea325a755ed05eed378d9201068de31ca8114f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681572"
---
# <a name="imetadataemitsetcustomattributevalue-method"></a><span data-ttu-id="a0465-102">IMetaDataEmit::SetCustomAttributeValue 方法</span><span class="sxs-lookup"><span data-stu-id="a0465-102">IMetaDataEmit::SetCustomAttributeValue Method</span></span>

<span data-ttu-id="a0465-103">设置或更新通过之前对 IMetaDataEmit 的调用定义的自定义特性的值 [：:D efinecustomattribute](imetadataemit-definecustomattribute-method.md)。</span><span class="sxs-lookup"><span data-stu-id="a0465-103">Sets or updates the value of a custom attribute defined by a prior call to [IMetaDataEmit::DefineCustomAttribute](imetadataemit-definecustomattribute-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0465-104">语法</span><span class="sxs-lookup"><span data-stu-id="a0465-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCustomAttributeValue (
    [in]  mdCustomAttribute       pcv,
    [in]  void const              *pCustomAttribute,
    [in]  ULONG                   cbCustomAttribute
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0465-105">参数</span><span class="sxs-lookup"><span data-stu-id="a0465-105">Parameters</span></span>  

 `pcv`  
 <span data-ttu-id="a0465-106">中目标自定义属性的标记。</span><span class="sxs-lookup"><span data-stu-id="a0465-106">[in] The token of the target custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="a0465-107">中指向包含自定义特性的数组的指针。</span><span class="sxs-lookup"><span data-stu-id="a0465-107">[in] A pointer to the array that contains the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="a0465-108">中自定义属性的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="a0465-108">[in] The size, in bytes, of the custom attribute.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0465-109">要求</span><span class="sxs-lookup"><span data-stu-id="a0465-109">Requirements</span></span>  

 <span data-ttu-id="a0465-110">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a0465-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0465-111">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="a0465-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a0465-112">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a0465-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a0465-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0465-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0465-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0465-114">See also</span></span>

- [<span data-ttu-id="a0465-115">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="a0465-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="a0465-116">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="a0465-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
