---
title: ICorPublishEnum::GetCount 方法
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.GetCount
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::GetCount
helpviewer_keywords:
- GetCount method, ICorPublishEnum interface [.NET Framework debugging]
- ICorPublishEnum::GetCount method [.NET Framework debugging]
ms.assetid: d228f684-2be3-4029-93ae-31fe02213c1f
topic_type:
- apiref
ms.openlocfilehash: a23d61da2913d8732c3860a44eb58ffadab48315
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677929"
---
# <a name="icorpublishenumgetcount-method"></a><span data-ttu-id="7eff4-102">ICorPublishEnum::GetCount 方法</span><span class="sxs-lookup"><span data-stu-id="7eff4-102">ICorPublishEnum::GetCount Method</span></span>

<span data-ttu-id="7eff4-103">获取枚举中的项数。</span><span class="sxs-lookup"><span data-stu-id="7eff4-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7eff4-104">语法</span><span class="sxs-lookup"><span data-stu-id="7eff4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7eff4-105">参数</span><span class="sxs-lookup"><span data-stu-id="7eff4-105">Parameters</span></span>  

 `pcelt`  
 <span data-ttu-id="7eff4-106">弄一个指针，指向枚举中的项数。</span><span class="sxs-lookup"><span data-stu-id="7eff4-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7eff4-107">要求</span><span class="sxs-lookup"><span data-stu-id="7eff4-107">Requirements</span></span>  

 <span data-ttu-id="7eff4-108">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7eff4-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7eff4-109">**标头：** CorPub，CorPub</span><span class="sxs-lookup"><span data-stu-id="7eff4-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="7eff4-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7eff4-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7eff4-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7eff4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eff4-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7eff4-112">See also</span></span>

- [<span data-ttu-id="7eff4-113">ICorPublishEnum 接口</span><span class="sxs-lookup"><span data-stu-id="7eff4-113">ICorPublishEnum Interface</span></span>](icorpublishenum-interface.md)
