---
title: ICorDebugStackWalk::GetFrame 方法
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.GetFrame Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::GetFrame
helpviewer_keywords:
- GetFrame method [.NET Framework debugging]
- ICorDebugStackWalk::GetFrame method [.NET Framework debugging]
ms.assetid: 4083b505-5b59-44fb-8c5d-129db6a96c10
topic_type:
- apiref
ms.openlocfilehash: 452635764794e01858baab10464a03c966a55271
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711931"
---
# <a name="icordebugstackwalkgetframe-method"></a><span data-ttu-id="e75eb-102">ICorDebugStackWalk::GetFrame 方法</span><span class="sxs-lookup"><span data-stu-id="e75eb-102">ICorDebugStackWalk::GetFrame Method</span></span>

<span data-ttu-id="e75eb-103">获取 [ICorDebugStackWalk](icordebugstackwalk-interface.md) 对象中的当前帧。</span><span class="sxs-lookup"><span data-stu-id="e75eb-103">Gets the current frame in the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e75eb-104">语法</span><span class="sxs-lookup"><span data-stu-id="e75eb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrame([out] ICorDebugFrame ** pFrame);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e75eb-105">参数</span><span class="sxs-lookup"><span data-stu-id="e75eb-105">Parameters</span></span>  

 `pFrame`  
 <span data-ttu-id="e75eb-106">中指向所创建的帧对象的地址的指针，该对象表示堆栈中的当前帧。</span><span class="sxs-lookup"><span data-stu-id="e75eb-106">[in] A pointer to the address of the created frame object that represents the current frame in the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e75eb-107">返回值</span><span class="sxs-lookup"><span data-stu-id="e75eb-107">Return Value</span></span>  

 <span data-ttu-id="e75eb-108">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="e75eb-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="e75eb-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e75eb-109">HRESULT</span></span>|<span data-ttu-id="e75eb-110">说明</span><span class="sxs-lookup"><span data-stu-id="e75eb-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e75eb-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e75eb-111">S_OK</span></span>|<span data-ttu-id="e75eb-112">运行时成功返回了当前帧。</span><span class="sxs-lookup"><span data-stu-id="e75eb-112">The runtime successfully returned the current frame.</span></span>|  
|<span data-ttu-id="e75eb-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e75eb-113">E_FAIL</span></span>|<span data-ttu-id="e75eb-114">当前帧未返回。</span><span class="sxs-lookup"><span data-stu-id="e75eb-114">The current frame was not returned.</span></span>|  
|<span data-ttu-id="e75eb-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="e75eb-115">S_FALSE</span></span>|<span data-ttu-id="e75eb-116">当前帧是本机堆栈帧。</span><span class="sxs-lookup"><span data-stu-id="e75eb-116">The current frame is a native stack frame.</span></span>|  
|<span data-ttu-id="e75eb-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="e75eb-117">E_INVALIDARG</span></span>|<span data-ttu-id="e75eb-118">`pFrame` 为 null。</span><span class="sxs-lookup"><span data-stu-id="e75eb-118">`pFrame` is null.</span></span>|  
|<span data-ttu-id="e75eb-119">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="e75eb-119">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="e75eb-120">帧指针已位于堆栈末尾;因此，不能访问其他帧。</span><span class="sxs-lookup"><span data-stu-id="e75eb-120">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="e75eb-121">例外</span><span class="sxs-lookup"><span data-stu-id="e75eb-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e75eb-122">备注</span><span class="sxs-lookup"><span data-stu-id="e75eb-122">Remarks</span></span>  

 <span data-ttu-id="e75eb-123">`ICorDebugStackWalk` 仅返回实际的堆栈帧。</span><span class="sxs-lookup"><span data-stu-id="e75eb-123">`ICorDebugStackWalk` returns only actual stack frames.</span></span> <span data-ttu-id="e75eb-124">使用 [ICorDebugThread3：： GetActiveInternalFrames](icordebugthread3-getactiveinternalframes-method.md) 方法返回内部帧。</span><span class="sxs-lookup"><span data-stu-id="e75eb-124">Use the [ICorDebugThread3::GetActiveInternalFrames](icordebugthread3-getactiveinternalframes-method.md) method to return internal frames.</span></span> <span data-ttu-id="e75eb-125"> (内部帧是由运行时推送到堆栈上的数据结构，用于存储临时数据。 ) </span><span class="sxs-lookup"><span data-stu-id="e75eb-125">(Internal frames are data structures pushed onto the stack by the runtime to store temporary data.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e75eb-126">要求</span><span class="sxs-lookup"><span data-stu-id="e75eb-126">Requirements</span></span>  

 <span data-ttu-id="e75eb-127">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e75eb-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e75eb-128">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e75eb-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e75eb-129">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e75eb-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e75eb-130">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e75eb-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e75eb-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e75eb-131">See also</span></span>

- [<span data-ttu-id="e75eb-132">ICorDebugStackWalk 接口</span><span class="sxs-lookup"><span data-stu-id="e75eb-132">ICorDebugStackWalk Interface</span></span>](icordebugstackwalk-interface.md)
- [<span data-ttu-id="e75eb-133">调试接口</span><span class="sxs-lookup"><span data-stu-id="e75eb-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e75eb-134">调试</span><span class="sxs-lookup"><span data-stu-id="e75eb-134">Debugging</span></span>](index.md)
