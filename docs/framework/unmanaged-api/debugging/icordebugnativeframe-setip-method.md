---
title: ICorDebugNativeFrame::SetIP 方法
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::SetIP
helpviewer_keywords:
- ICorDebugNativeFrame::SetIP method [.NET Framework debugging]
- SetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 57784a51-c76d-48f8-9392-584d0e1946d9
topic_type:
- apiref
ms.openlocfilehash: 65de42a0b86e4b4593b7880e9dc290ce00007a40
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709253"
---
# <a name="icordebugnativeframesetip-method"></a><span data-ttu-id="5ccff-102">ICorDebugNativeFrame::SetIP 方法</span><span class="sxs-lookup"><span data-stu-id="5ccff-102">ICorDebugNativeFrame::SetIP Method</span></span>

<span data-ttu-id="5ccff-103">将指令指针设置为本机代码中的指定偏移位置。</span><span class="sxs-lookup"><span data-stu-id="5ccff-103">Sets the instruction pointer to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ccff-104">语法</span><span class="sxs-lookup"><span data-stu-id="5ccff-104">Syntax</span></span>  
  
```cpp  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ccff-105">参数</span><span class="sxs-lookup"><span data-stu-id="5ccff-105">Parameters</span></span>  

 `nOffset`  
 <span data-ttu-id="5ccff-106">中本机代码中的偏移位置。</span><span class="sxs-lookup"><span data-stu-id="5ccff-106">[in] The offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ccff-107">注解</span><span class="sxs-lookup"><span data-stu-id="5ccff-107">Remarks</span></span>  

 <span data-ttu-id="5ccff-108">调用将 `SetIP` 立即使当前线程的所有帧和链无效。</span><span class="sxs-lookup"><span data-stu-id="5ccff-108">Calls to `SetIP` immediately invalidate all frames and chains for the current thread.</span></span> <span data-ttu-id="5ccff-109">如果在调用后调试器需要帧信息 `SetIP` ，则它必须执行新的堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="5ccff-109">If the debugger needs frame information after a call to `SetIP`, it must perform a new stack trace.</span></span>  
  
 <span data-ttu-id="5ccff-110">[ICorDebug](icordebug-interface.md) 将尝试保持堆栈帧处于有效状态。</span><span class="sxs-lookup"><span data-stu-id="5ccff-110">[ICorDebug](icordebug-interface.md) will attempt to keep the stack frame in a valid state.</span></span> <span data-ttu-id="5ccff-111">但是，即使帧处于有效状态，在运行时也是如此，但仍存在一些问题，如未初始化的局部变量等。</span><span class="sxs-lookup"><span data-stu-id="5ccff-111">However, even if the frame is in a valid state, as far as the runtime is concerned, there still may be problems, such as uninitialized local variables, and so on.</span></span> <span data-ttu-id="5ccff-112">调用方负责确保正在运行的程序的一致性。</span><span class="sxs-lookup"><span data-stu-id="5ccff-112">The caller is responsible for insuring coherency of the running program.</span></span>  
  
 <span data-ttu-id="5ccff-113">在64位平台上，指令指针不能移出 `catch` 或 `finally` 块。</span><span class="sxs-lookup"><span data-stu-id="5ccff-113">On 64-bit platforms, the instruction pointer cannot be moved out of a `catch` or `finally` block.</span></span> <span data-ttu-id="5ccff-114">如果 `SetIP` 调用来在64位平台上进行此类移动，则它将返回一个指示失败的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="5ccff-114">If `SetIP` is called to make such a move on a 64-bit platform, it will return an HRESULT indicating failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ccff-115">要求</span><span class="sxs-lookup"><span data-stu-id="5ccff-115">Requirements</span></span>  

 <span data-ttu-id="5ccff-116">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5ccff-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ccff-117">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5ccff-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5ccff-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ccff-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ccff-119">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ccff-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ccff-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5ccff-120">See also</span></span>
