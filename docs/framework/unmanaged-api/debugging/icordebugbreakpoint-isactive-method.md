---
title: ICorDebugBreakpoint::IsActive 方法
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint::IsActive
helpviewer_keywords:
- ICorDebugBreakpoint::IsActive method [.NET Framework debugging]
- IsActive method, ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: 06e583d6-d88a-4ff5-bb95-5c48618a461c
topic_type:
- apiref
ms.openlocfilehash: 064f9727b221dd64a58f8cd5e103271e37020786
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730170"
---
# <a name="icordebugbreakpointisactive-method"></a><span data-ttu-id="ce7aa-102">ICorDebugBreakpoint::IsActive 方法</span><span class="sxs-lookup"><span data-stu-id="ce7aa-102">ICorDebugBreakpoint::IsActive Method</span></span>

<span data-ttu-id="ce7aa-103">获取一个值，该值指示此是否处于 `ICorDebugBreakpoint` 活动状态。</span><span class="sxs-lookup"><span data-stu-id="ce7aa-103">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce7aa-104">语法</span><span class="sxs-lookup"><span data-stu-id="ce7aa-104">Syntax</span></span>  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce7aa-105">参数</span><span class="sxs-lookup"><span data-stu-id="ce7aa-105">Parameters</span></span>  

 `pbActive`  
 <span data-ttu-id="ce7aa-106">[out] `true` 如果此断点处于活动状态，则为;否则为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="ce7aa-106">[out] `true` if this breakpoint is active; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce7aa-107">要求</span><span class="sxs-lookup"><span data-stu-id="ce7aa-107">Requirements</span></span>  

 <span data-ttu-id="ce7aa-108">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ce7aa-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce7aa-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ce7aa-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ce7aa-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce7aa-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce7aa-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce7aa-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
