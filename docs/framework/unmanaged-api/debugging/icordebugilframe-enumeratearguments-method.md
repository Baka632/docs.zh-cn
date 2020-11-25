---
title: ICorDebugILFrame::EnumerateArguments 方法
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.EnumerateArguments
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateArguments
helpviewer_keywords:
- ICorDebugILFrame::EnumerateArguments method [.NET Framework debugging]
- EnumerateArguments method [.NET Framework debugging]
ms.assetid: 00ac81e2-a774-422a-bd88-54a4b3c99f73
topic_type:
- apiref
ms.openlocfilehash: 9b0bc59b67b5d4b2184733f22616433bf33be616
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703221"
---
# <a name="icordebugilframeenumeratearguments-method"></a><span data-ttu-id="90b0e-102">ICorDebugILFrame::EnumerateArguments 方法</span><span class="sxs-lookup"><span data-stu-id="90b0e-102">ICorDebugILFrame::EnumerateArguments Method</span></span>

<span data-ttu-id="90b0e-103">获取此帧中的参数的枚举数。</span><span class="sxs-lookup"><span data-stu-id="90b0e-103">Gets an enumerator for the arguments in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90b0e-104">语法</span><span class="sxs-lookup"><span data-stu-id="90b0e-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateArguments (  
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90b0e-105">参数</span><span class="sxs-lookup"><span data-stu-id="90b0e-105">Parameters</span></span>  

 `ppValueEnum`  
 <span data-ttu-id="90b0e-106">弄指向 ICorDebugValueEnum 对象地址的指针，该对象是此帧中自变量的枚举器。</span><span class="sxs-lookup"><span data-stu-id="90b0e-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the arguments in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90b0e-107">注解</span><span class="sxs-lookup"><span data-stu-id="90b0e-107">Remarks</span></span>  

 <span data-ttu-id="90b0e-108">`EnumerateArguments` 获取一个枚举器，该枚举数可以列出此 ICorDebugILFrame 对象所表示的调用帧中可用的参数。</span><span class="sxs-lookup"><span data-stu-id="90b0e-108">`EnumerateArguments` gets an enumerator that can list the arguments available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="90b0e-109">此列表将包含 [vararg](/cpp/windows/vararg) 参数 (即，可变数量的参数) 以及不是的参数 `vararg` 。</span><span class="sxs-lookup"><span data-stu-id="90b0e-109">The list will include arguments that are [vararg](/cpp/windows/vararg) (that is, a variable number of arguments) as well as arguments that are not `vararg`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90b0e-110">要求</span><span class="sxs-lookup"><span data-stu-id="90b0e-110">Requirements</span></span>  

 <span data-ttu-id="90b0e-111">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="90b0e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90b0e-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="90b0e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="90b0e-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90b0e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90b0e-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90b0e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
