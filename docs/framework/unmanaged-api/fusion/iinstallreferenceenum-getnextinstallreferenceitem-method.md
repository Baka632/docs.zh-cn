---
title: IInstallReferenceEnum::GetNextInstallReferenceItem 方法
ms.date: 03/30/2017
api_name:
- IInstallReferenceEnum.GetNextInstallReferenceItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceEnum::GetNextInstallReferenceItem
helpviewer_keywords:
- IInstallReferenceEnum::GetNextInstallReferenceItem method [.NET Framework fusion]
- GetNextInstallReferenceItem method [.NET Framework fusion]
ms.assetid: ce969c9d-6538-4c34-8784-148ffd99fe7a
topic_type:
- apiref
ms.openlocfilehash: e093de7d2c2388274cbe9ebbe46084ee6ae3ff8c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721096"
---
# <a name="iinstallreferenceenumgetnextinstallreferenceitem-method"></a><span data-ttu-id="fcd16-102">IInstallReferenceEnum::GetNextInstallReferenceItem 方法</span><span class="sxs-lookup"><span data-stu-id="fcd16-102">IInstallReferenceEnum::GetNextInstallReferenceItem Method</span></span>

<span data-ttu-id="fcd16-103">获取一个指针，该指针指向此[IInstallReferenceEnum](iinstallreferenceenum-interface.md)对象中包含的下一个[IInstallReferenceItem](iinstallreferenceitem-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="fcd16-103">Gets a pointer to the next [IInstallReferenceItem](iinstallreferenceitem-interface.md) object contained in this [IInstallReferenceEnum](iinstallreferenceenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcd16-104">语法</span><span class="sxs-lookup"><span data-stu-id="fcd16-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextInstallReferenceItem (  
    [out] IInstallReferenceItem **ppRefItem,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fcd16-105">参数</span><span class="sxs-lookup"><span data-stu-id="fcd16-105">Parameters</span></span>  

 `ppRefItem`  
 <span data-ttu-id="fcd16-106">弄返回的 `IInstallReferenceItem` 指针。</span><span class="sxs-lookup"><span data-stu-id="fcd16-106">[out] The returned `IInstallReferenceItem` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="fcd16-107">中保留以供将来进行扩展。</span><span class="sxs-lookup"><span data-stu-id="fcd16-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="fcd16-108">`dwFlags` 必须为 0 (零) 。</span><span class="sxs-lookup"><span data-stu-id="fcd16-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="fcd16-109">中保留以供将来进行扩展。</span><span class="sxs-lookup"><span data-stu-id="fcd16-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="fcd16-110">`pvReserved` 必须为空引用。</span><span class="sxs-lookup"><span data-stu-id="fcd16-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcd16-111">要求</span><span class="sxs-lookup"><span data-stu-id="fcd16-111">Requirements</span></span>  

 <span data-ttu-id="fcd16-112">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fcd16-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcd16-113">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="fcd16-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="fcd16-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcd16-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcd16-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fcd16-115">See also</span></span>

- [<span data-ttu-id="fcd16-116">IInstallReferenceItem 接口</span><span class="sxs-lookup"><span data-stu-id="fcd16-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
- [<span data-ttu-id="fcd16-117">IInstallReferenceEnum 接口</span><span class="sxs-lookup"><span data-stu-id="fcd16-117">IInstallReferenceEnum Interface</span></span>](iinstallreferenceenum-interface.md)
