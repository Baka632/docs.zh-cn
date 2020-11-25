---
title: ICorDebugFunction::GetCurrentVersionNumber 方法
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetCurrentVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetCurrentVersionNumber
helpviewer_keywords:
- GetCurrentVersionNumber method [.NET Framework debugging]
- ICorDebugFunction::GetCurrentVersionNumber method [.NET Framework debugging]
ms.assetid: c3af1575-cbe6-457a-bc08-c53460edcbc8
topic_type:
- apiref
ms.openlocfilehash: 14579d4c84be9bb225e618715b3a7d45ccaac0a9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728142"
---
# <a name="icordebugfunctiongetcurrentversionnumber-method"></a><span data-ttu-id="31dfa-102">ICorDebugFunction::GetCurrentVersionNumber 方法</span><span class="sxs-lookup"><span data-stu-id="31dfa-102">ICorDebugFunction::GetCurrentVersionNumber Method</span></span>

<span data-ttu-id="31dfa-103">获取对此 ICorDebugFunction 对象所表示的函数进行的最新编辑的版本号。</span><span class="sxs-lookup"><span data-stu-id="31dfa-103">Gets the version number of the latest edit made to the function represented by this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31dfa-104">语法</span><span class="sxs-lookup"><span data-stu-id="31dfa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentVersionNumber (  
    [out] ULONG32 *pnCurrentVersion  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31dfa-105">参数</span><span class="sxs-lookup"><span data-stu-id="31dfa-105">Parameters</span></span>  

 `pnCurrentVersion`  
 <span data-ttu-id="31dfa-106">弄指向整数值的指针，该整数值是对此函数进行的最新编辑的版本号。</span><span class="sxs-lookup"><span data-stu-id="31dfa-106">[out] A pointer to an integer value that is the version number of the latest edit made to this function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31dfa-107">注解</span><span class="sxs-lookup"><span data-stu-id="31dfa-107">Remarks</span></span>  

 <span data-ttu-id="31dfa-108">对此函数进行的最新编辑的版本号可能大于函数本身的版本号。</span><span class="sxs-lookup"><span data-stu-id="31dfa-108">The version number of the latest edit made to this function may be greater than the version number of the function itself.</span></span> <span data-ttu-id="31dfa-109">使用 [ICorDebugFunction2：： GetVersionNumber](icordebugfunction2-getversionnumber-method.md) 方法或 [ICorDebugCode：： GetVersionNumber](icordebugcode-getversionnumber-method.md) 方法检索函数的版本号。</span><span class="sxs-lookup"><span data-stu-id="31dfa-109">Use either the [ICorDebugFunction2::GetVersionNumber](icordebugfunction2-getversionnumber-method.md) method or the [ICorDebugCode::GetVersionNumber](icordebugcode-getversionnumber-method.md) method to retrieve the version number of the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31dfa-110">要求</span><span class="sxs-lookup"><span data-stu-id="31dfa-110">Requirements</span></span>  

 <span data-ttu-id="31dfa-111">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="31dfa-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31dfa-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="31dfa-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="31dfa-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31dfa-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="31dfa-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31dfa-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
