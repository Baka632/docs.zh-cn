---
title: ICorDebugFrame::GetFunction 方法
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetFunction method [.NET Framework debugging]
ms.assetid: 879d2311-0ff1-4616-a8b3-959ea5868b2e
topic_type:
- apiref
ms.openlocfilehash: 9f9a6238057f56459eb8dca2375da412c3cd569d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690312"
---
# <a name="icordebugframegetfunction-method"></a><span data-ttu-id="feb40-102">ICorDebugFrame::GetFunction 方法</span><span class="sxs-lookup"><span data-stu-id="feb40-102">ICorDebugFrame::GetFunction Method</span></span>

<span data-ttu-id="feb40-103">获取一个函数，该函数包含与此堆栈帧关联的代码。</span><span class="sxs-lookup"><span data-stu-id="feb40-103">Gets the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="feb40-104">语法</span><span class="sxs-lookup"><span data-stu-id="feb40-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="feb40-105">参数</span><span class="sxs-lookup"><span data-stu-id="feb40-105">Parameters</span></span>  

 `ppFunction`  
 <span data-ttu-id="feb40-106">弄指向 ICorDebugFunction 对象的地址的指针，该对象表示包含与此堆栈帧关联的代码的函数。</span><span class="sxs-lookup"><span data-stu-id="feb40-106">[out] A pointer to the address of an ICorDebugFunction object that represents the function containing the code associated with this stack frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="feb40-107">注解</span><span class="sxs-lookup"><span data-stu-id="feb40-107">Remarks</span></span>  

 <span data-ttu-id="feb40-108">`GetFunction`如果框架不与任何特定函数关联，则该方法可能会失败。</span><span class="sxs-lookup"><span data-stu-id="feb40-108">The `GetFunction` method may fail if the frame is not associated with any particular function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="feb40-109">要求</span><span class="sxs-lookup"><span data-stu-id="feb40-109">Requirements</span></span>  

 <span data-ttu-id="feb40-110">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="feb40-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="feb40-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="feb40-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="feb40-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="feb40-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="feb40-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="feb40-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
