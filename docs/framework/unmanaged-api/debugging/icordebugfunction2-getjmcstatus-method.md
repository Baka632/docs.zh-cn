---
title: ICorDebugFunction2::GetJMCStatus 方法
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::GetJMCStatus method [.NET Framework debugging]
- GetJMCStatus method [.NET Framework debugging]
ms.assetid: 840a71ed-bf5a-4f5e-8ed6-762222b34493
topic_type:
- apiref
ms.openlocfilehash: 747f165a98dfd1264ea58d61aaa1615c6d71e073
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726283"
---
# <a name="icordebugfunction2getjmcstatus-method"></a><span data-ttu-id="c3715-102">ICorDebugFunction2::GetJMCStatus 方法</span><span class="sxs-lookup"><span data-stu-id="c3715-102">ICorDebugFunction2::GetJMCStatus Method</span></span>

<span data-ttu-id="c3715-103">获取一个值，该值指示此 ICorDebugFunction2 对象表示的函数是否被标记为 "用户代码"。</span><span class="sxs-lookup"><span data-stu-id="c3715-103">Gets a value that indicates whether the function that is represented by this ICorDebugFunction2 object is marked as user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3715-104">语法</span><span class="sxs-lookup"><span data-stu-id="c3715-104">Syntax</span></span>  
  
```cpp  
HRESULT GetJMCStatus (  
    [out] BOOL   *pbIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3715-105">参数</span><span class="sxs-lookup"><span data-stu-id="c3715-105">Parameters</span></span>  

 `pbIsJustMyCode`  
 <span data-ttu-id="c3715-106">弄 `true`如果此函数标记为用户代码，则为指向布尔值的指针; 否则，该值为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="c3715-106">[out] A pointer to a Boolean value that is `true`, if this function is marked as user code; otherwise, the value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3715-107">注解</span><span class="sxs-lookup"><span data-stu-id="c3715-107">Remarks</span></span>  

 <span data-ttu-id="c3715-108">如果此表示的函数 `ICorDebugFunction2` 无法调试， `pbIsJustMyCode` 将始终为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="c3715-108">If the function represented by this `ICorDebugFunction2` cannot be debugged, `pbIsJustMyCode` will always be `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3715-109">要求</span><span class="sxs-lookup"><span data-stu-id="c3715-109">Requirements</span></span>  

 <span data-ttu-id="c3715-110">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c3715-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3715-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c3715-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c3715-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3715-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3715-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3715-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
