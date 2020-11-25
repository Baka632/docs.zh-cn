---
title: ICorDebugChain::IsManaged 方法
ms.date: 03/30/2017
api_name:
- ICorDebugChain.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::IsManaged
helpviewer_keywords:
- ICorDebugChain::IsManaged method [.NET Framework debugging]
- IsManaged method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 17b389a0-1a4d-4e8a-8613-9bc1769930f9
topic_type:
- apiref
ms.openlocfilehash: cfe884c3d26e7a52618eb9945f0af9a167132f05
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724372"
---
# <a name="icordebugchainismanaged-method"></a><span data-ttu-id="f0d36-102">ICorDebugChain::IsManaged 方法</span><span class="sxs-lookup"><span data-stu-id="f0d36-102">ICorDebugChain::IsManaged Method</span></span>

<span data-ttu-id="f0d36-103">获取一个值，该值指示此链是否正在运行托管代码。</span><span class="sxs-lookup"><span data-stu-id="f0d36-103">Gets a value that indicates whether this chain is running managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0d36-104">语法</span><span class="sxs-lookup"><span data-stu-id="f0d36-104">Syntax</span></span>  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL               *pManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0d36-105">参数</span><span class="sxs-lookup"><span data-stu-id="f0d36-105">Parameters</span></span>  

 `pManaged`  
 <span data-ttu-id="f0d36-106">[out] `true` 如果此链正在运行托管代码，则为;否则为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="f0d36-106">[out] `true` if this chain is running managed code; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0d36-107">要求</span><span class="sxs-lookup"><span data-stu-id="f0d36-107">Requirements</span></span>  

 <span data-ttu-id="f0d36-108">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f0d36-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0d36-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0d36-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0d36-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0d36-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0d36-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0d36-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
