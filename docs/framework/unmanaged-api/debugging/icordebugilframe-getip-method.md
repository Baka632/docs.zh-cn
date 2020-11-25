---
title: ICorDebugILFrame::GetIP 方法
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::GetIP method [.NET Framework debugging]
ms.assetid: 18217ba1-1776-4297-a3b9-f77e64b0fead
topic_type:
- apiref
ms.openlocfilehash: 314d2a06c8e246a42b315690dc9fe4b507db285a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703165"
---
# <a name="icordebugilframegetip-method"></a><span data-ttu-id="923ea-102">ICorDebugILFrame::GetIP 方法</span><span class="sxs-lookup"><span data-stu-id="923ea-102">ICorDebugILFrame::GetIP Method</span></span>

<span data-ttu-id="923ea-103">获取指令指针的值和按位组合值，它描述如何获取指令指针的值。</span><span class="sxs-lookup"><span data-stu-id="923ea-103">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="923ea-104">语法</span><span class="sxs-lookup"><span data-stu-id="923ea-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="923ea-105">参数</span><span class="sxs-lookup"><span data-stu-id="923ea-105">Parameters</span></span>  

 `pnOffset`  
 <span data-ttu-id="923ea-106">弄指令指针的值。</span><span class="sxs-lookup"><span data-stu-id="923ea-106">[out] The value of the instruction pointer.</span></span>  
  
 `pMappingResult`  
 <span data-ttu-id="923ea-107">弄一个指针，指向 CorDebugMappingResult 枚举值的按位组合，这些枚举值描述如何获取指令指针的值。</span><span class="sxs-lookup"><span data-stu-id="923ea-107">[out] A pointer to a bitwise combination of the CorDebugMappingResult enumeration values that describe how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="923ea-108">注解</span><span class="sxs-lookup"><span data-stu-id="923ea-108">Remarks</span></span>  

 <span data-ttu-id="923ea-109">指令指针的值是堆栈帧在函数的 Microsoft 中间语言 (MSIL) 代码的偏移量。</span><span class="sxs-lookup"><span data-stu-id="923ea-109">The value of the instruction pointer is the stack frame's offset into the function's Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="923ea-110">如果堆栈帧处于活动状态，则此地址为要执行的下一条指令。</span><span class="sxs-lookup"><span data-stu-id="923ea-110">If the stack frame is active, this address is the next instruction to execute.</span></span> <span data-ttu-id="923ea-111">如果堆栈帧不处于活动状态，则该地址是在重新激活堆栈帧时要执行的下一条指令。</span><span class="sxs-lookup"><span data-stu-id="923ea-111">If the stack frame is not active, this address is the next instruction to execute when the stack frame is reactivated.</span></span>  
  
 <span data-ttu-id="923ea-112">如果此帧是实时 (JIT) 编译的帧，则会通过从实际的本机指令指针反向映射来确定指令指针的值，因此该值可能只是近似的。</span><span class="sxs-lookup"><span data-stu-id="923ea-112">If this frame is a just-in-time (JIT) compiled frame, the value of the instruction pointer will be determined by mapping backwards from the actual native instruction pointer, so the value may be only approximate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="923ea-113">要求</span><span class="sxs-lookup"><span data-stu-id="923ea-113">Requirements</span></span>  

 <span data-ttu-id="923ea-114">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="923ea-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="923ea-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="923ea-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="923ea-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="923ea-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="923ea-117">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="923ea-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
