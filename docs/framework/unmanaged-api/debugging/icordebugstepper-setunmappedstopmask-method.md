---
title: ICorDebugStepper::SetUnmappedStopMask 方法
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetUnmappedStopMask
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetUnmappedStopMask
helpviewer_keywords:
- ICorDebugStepper::SetUnmappedStopMask method [.NET Framework debugging]
- SetUnmappedStopMask method [.NET Framework debugging]
ms.assetid: b1211981-e90c-4e05-8def-fa18d85ad9ab
topic_type:
- apiref
ms.openlocfilehash: 50fad8b38a6b33d0ddbb2f0f20676296c3d66737
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698723"
---
# <a name="icordebugsteppersetunmappedstopmask-method"></a><span data-ttu-id="c3548-102">ICorDebugStepper::SetUnmappedStopMask 方法</span><span class="sxs-lookup"><span data-stu-id="c3548-102">ICorDebugStepper::SetUnmappedStopMask Method</span></span>

<span data-ttu-id="c3548-103">设置一个值，该值指定执行过程中将暂停的未映射代码的类型。</span><span class="sxs-lookup"><span data-stu-id="c3548-103">Sets a value that specifies the type of unmapped code in which execution will halt.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3548-104">语法</span><span class="sxs-lookup"><span data-stu-id="c3548-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmappedStopMask (  
    [in] CorDebugUnmappedStop   mask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3548-105">参数</span><span class="sxs-lookup"><span data-stu-id="c3548-105">Parameters</span></span>  

 `mask`  
 <span data-ttu-id="c3548-106">中CorDebugUnmappedStop 枚举的一个值，该值指定调试器将在其中暂停执行的未映射代码的类型。</span><span class="sxs-lookup"><span data-stu-id="c3548-106">[in] A value of the CorDebugUnmappedStop enumeration that specifies the type of unmapped code in which the debugger will halt execution.</span></span>  
  
 <span data-ttu-id="c3548-107">默认值为 STOP_OTHER_UNMAPPED。</span><span class="sxs-lookup"><span data-stu-id="c3548-107">The default value is STOP_OTHER_UNMAPPED.</span></span> <span data-ttu-id="c3548-108">值 STOP_UNMANAGED 仅适用于互操作调试。</span><span class="sxs-lookup"><span data-stu-id="c3548-108">The value STOP_UNMANAGED is only valid with interop debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3548-109">注解</span><span class="sxs-lookup"><span data-stu-id="c3548-109">Remarks</span></span>  

 <span data-ttu-id="c3548-110">当调试器找到与 Microsoft 中间语言 (MSIL) 无对应映射的实时 (JIT) 编译时，如果指定了该类型的未映射代码的标志，则将暂停执行;否则，单步执行会透明地继续。</span><span class="sxs-lookup"><span data-stu-id="c3548-110">When the debugger finds a just-in-time (JIT) compilation that has no corresponding mapping to Microsoft intermediate language (MSIL), it halts execution if the flag specifying that type of unmapped code has been set; otherwise, stepping transparently continues.</span></span>  
  
 <span data-ttu-id="c3548-111">如果调试器不使用分档器来输入方法，则不一定要逐过程执行非映射代码。</span><span class="sxs-lookup"><span data-stu-id="c3548-111">If the debugger doesn't use a stepper to enter a method, then it won't necessarily step over unmapped code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3548-112">要求</span><span class="sxs-lookup"><span data-stu-id="c3548-112">Requirements</span></span>  

 <span data-ttu-id="c3548-113">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c3548-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3548-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c3548-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c3548-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3548-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3548-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3548-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
