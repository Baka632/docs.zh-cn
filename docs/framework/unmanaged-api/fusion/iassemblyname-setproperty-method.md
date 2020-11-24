---
title: IAssemblyName::SetProperty 方法
ms.date: 03/30/2017
api_name:
- IAssemblyName.SetProperty
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::SetProperty
helpviewer_keywords:
- IAssemblyName::SetProperty method [.NET Framework fusion]
- SetProperty method [.NET Framework fusion]
ms.assetid: 496c3add-f60b-4073-943f-d1bcf33330cb
topic_type:
- apiref
ms.openlocfilehash: 04b3e73e2166efb2ec0821d21da3da4c53b0ca4b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688648"
---
# <a name="iassemblynamesetproperty-method"></a><span data-ttu-id="066eb-102">IAssemblyName::SetProperty 方法</span><span class="sxs-lookup"><span data-stu-id="066eb-102">IAssemblyName::SetProperty Method</span></span>

<span data-ttu-id="066eb-103">设置由指定的属性标识符引用的属性的值。</span><span class="sxs-lookup"><span data-stu-id="066eb-103">Sets the value of the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="066eb-104">语法</span><span class="sxs-lookup"><span data-stu-id="066eb-104">Syntax</span></span>  
  
```cpp  
HRESULT SetProperty (  
    [in] DWORD  PropertyId,  
    [in] LPVOID pvProperty,  
    [in] DWORD  cbProperty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="066eb-105">参数</span><span class="sxs-lookup"><span data-stu-id="066eb-105">Parameters</span></span>  

 `PropertyId`  
 <span data-ttu-id="066eb-106">中将设置其值的属性的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="066eb-106">[in] The unique identifier of the property whose value will be set.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="066eb-107">中要将引用的属性设置为的值 `PropertyId` 。</span><span class="sxs-lookup"><span data-stu-id="066eb-107">[in] The value to which to set the property referenced by `PropertyId`.</span></span>  
  
 `cbProperty`  
 <span data-ttu-id="066eb-108">中的大小（以字节为单位） `pvProperty` 。</span><span class="sxs-lookup"><span data-stu-id="066eb-108">[in] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="066eb-109">要求</span><span class="sxs-lookup"><span data-stu-id="066eb-109">Requirements</span></span>  

 <span data-ttu-id="066eb-110">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="066eb-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="066eb-111">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="066eb-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="066eb-112">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="066eb-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="066eb-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="066eb-113">See also</span></span>

- [<span data-ttu-id="066eb-114">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="066eb-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
