---
title: ICorDebugProcess::GetThreadContext 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetThreadContext
helpviewer_keywords:
- ICorDebugProcess::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: 5b132ef1-8d4b-4525-89b3-54123596c194
topic_type:
- apiref
ms.openlocfilehash: 3be689e5c1474bcbfbca72a14a298762dc2e7a90
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724541"
---
# <a name="icordebugprocessgetthreadcontext-method"></a><span data-ttu-id="37b09-102">ICorDebugProcess::GetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="37b09-102">ICorDebugProcess::GetThreadContext Method</span></span>

<span data-ttu-id="37b09-103">获取此进程中给定线程的上下文。</span><span class="sxs-lookup"><span data-stu-id="37b09-103">Gets the context for the given thread in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37b09-104">语法</span><span class="sxs-lookup"><span data-stu-id="37b09-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37b09-105">参数</span><span class="sxs-lookup"><span data-stu-id="37b09-105">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="37b09-106">中要为其检索上下文的线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="37b09-106">[in] The ID of the thread for which to retrieve the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="37b09-107">[in] `context` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="37b09-107">[in] The size of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="37b09-108">[in，out]用于描述线程上下文的字节数组。</span><span class="sxs-lookup"><span data-stu-id="37b09-108">[in, out] An array of bytes that describe the thread's context.</span></span>  
  
 <span data-ttu-id="37b09-109">上下文指定正在执行线程的处理器的体系结构。</span><span class="sxs-lookup"><span data-stu-id="37b09-109">The context specifies the architecture of the processor on which the thread is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37b09-110">注解</span><span class="sxs-lookup"><span data-stu-id="37b09-110">Remarks</span></span>  

 <span data-ttu-id="37b09-111">调试器应调用此方法而不是 Win32 `GetThreadContext` 方法，因为该线程实际可能处于 "被劫持" 状态，在该状态下，其上下文已暂时更改。</span><span class="sxs-lookup"><span data-stu-id="37b09-111">The debugger should call this method rather than the Win32 `GetThreadContext` method, because the thread may actually be in a "hijacked" state, in which its context has been temporarily changed.</span></span> <span data-ttu-id="37b09-112">仅当线程在本机代码中时，才应使用此方法。</span><span class="sxs-lookup"><span data-stu-id="37b09-112">This method should be used only when a thread is in native code.</span></span> <span data-ttu-id="37b09-113">在托管代码中对线程使用 [ICorDebugRegisterSet](icordebugregisterset-interface.md) 。</span><span class="sxs-lookup"><span data-stu-id="37b09-113">Use [ICorDebugRegisterSet](icordebugregisterset-interface.md) for threads in managed code.</span></span>  
  
 <span data-ttu-id="37b09-114">返回的数据是当前平台的上下文结构。</span><span class="sxs-lookup"><span data-stu-id="37b09-114">The data returned is a context structure for the current platform.</span></span> <span data-ttu-id="37b09-115">与 Win32 `GetThreadContext` 方法一样，调用方应在 `context` 调用此方法之前初始化参数。</span><span class="sxs-lookup"><span data-stu-id="37b09-115">Just as with the Win32 `GetThreadContext` method, the caller should initialize the `context` parameter before calling this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37b09-116">要求</span><span class="sxs-lookup"><span data-stu-id="37b09-116">Requirements</span></span>  

 <span data-ttu-id="37b09-117">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="37b09-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37b09-118">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="37b09-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="37b09-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37b09-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="37b09-120">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37b09-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
