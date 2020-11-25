---
title: ICorDebugChain::GetPrevious 方法
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetPrevious
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetPrevious
helpviewer_keywords:
- ICorDebugChain::GetPrevious method [.NET Framework debugging]
- GetPrevious method [.NET Framework debugging]
ms.assetid: 58eed4c8-d80c-4c6a-a875-967a90dd926c
topic_type:
- apiref
ms.openlocfilehash: 326e170fa98c9e365f9b68bedb585f547ca207ed
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727700"
---
# <a name="icordebugchaingetprevious-method"></a><span data-ttu-id="91970-102">ICorDebugChain::GetPrevious 方法</span><span class="sxs-lookup"><span data-stu-id="91970-102">ICorDebugChain::GetPrevious Method</span></span>

<span data-ttu-id="91970-103">获取线程的上一个帧链。</span><span class="sxs-lookup"><span data-stu-id="91970-103">Gets the previous chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91970-104">语法</span><span class="sxs-lookup"><span data-stu-id="91970-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPrevious (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91970-105">参数</span><span class="sxs-lookup"><span data-stu-id="91970-105">Parameters</span></span>  

 `ppChain`  
 <span data-ttu-id="91970-106">弄指向 ICorDebugChain 对象的地址的指针，该对象表示此线程的上一个帧链。</span><span class="sxs-lookup"><span data-stu-id="91970-106">[out] A pointer to the address of an ICorDebugChain object that represents the previous chain of frames for this thread.</span></span> <span data-ttu-id="91970-107">如果此链是第一个链， `ppChain` 则为 null。</span><span class="sxs-lookup"><span data-stu-id="91970-107">If this chain is the first chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91970-108">要求</span><span class="sxs-lookup"><span data-stu-id="91970-108">Requirements</span></span>  

 <span data-ttu-id="91970-109">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="91970-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91970-110">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="91970-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="91970-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91970-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91970-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91970-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
