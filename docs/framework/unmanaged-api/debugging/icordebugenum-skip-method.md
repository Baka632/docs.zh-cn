---
title: ICorDebugEnum::Skip 方法
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.Skip
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::Skip
helpviewer_keywords:
- ICorDebugEnum::Skip method [.NET Framework debugging]
- Skip method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: e925d88a-67a5-4f76-88b8-09cedeed0232
topic_type:
- apiref
ms.openlocfilehash: ae88336b9640b68b97522d252b3e8334c20ed9bc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705860"
---
# <a name="icordebugenumskip-method"></a><span data-ttu-id="f7c5e-102">ICorDebugEnum::Skip 方法</span><span class="sxs-lookup"><span data-stu-id="f7c5e-102">ICorDebugEnum::Skip Method</span></span>

<span data-ttu-id="f7c5e-103">按指定的项数在枚举中向前移动光标。</span><span class="sxs-lookup"><span data-stu-id="f7c5e-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7c5e-104">语法</span><span class="sxs-lookup"><span data-stu-id="f7c5e-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7c5e-105">参数</span><span class="sxs-lookup"><span data-stu-id="f7c5e-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="f7c5e-106">中游标向前移动的项数。</span><span class="sxs-lookup"><span data-stu-id="f7c5e-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7c5e-107">要求</span><span class="sxs-lookup"><span data-stu-id="f7c5e-107">Requirements</span></span>  

 <span data-ttu-id="f7c5e-108">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f7c5e-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7c5e-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f7c5e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f7c5e-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7c5e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7c5e-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7c5e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7c5e-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f7c5e-112">See also</span></span>

- [<span data-ttu-id="f7c5e-113">ICorDebugEnum 接口</span><span class="sxs-lookup"><span data-stu-id="f7c5e-113">ICorDebugEnum Interface</span></span>](icordebugenum-interface1.md)
