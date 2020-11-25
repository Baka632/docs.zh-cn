---
title: ICorDebugThread3::GetActiveInternalFrames 方法
ms.date: 03/30/2017
api_name:
- ICorDebugThread3.GetActiveInternalFrames Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3::GetActiveInternalFrames
helpviewer_keywords:
- ICorDebugThread3::GetActiveInternalFrames method [.NET Framework debugging]
- GetActiveInternalFrames method [.NET Framework debugging]
ms.assetid: d69796b4-5b6d-457c-85f6-2cf42e8a8773
topic_type:
- apiref
ms.openlocfilehash: 2ca3bf94298b45e404c930ffe52e101085ee482d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726205"
---
# <a name="icordebugthread3getactiveinternalframes-method"></a><span data-ttu-id="58cb6-102">ICorDebugThread3::GetActiveInternalFrames 方法</span><span class="sxs-lookup"><span data-stu-id="58cb6-102">ICorDebugThread3::GetActiveInternalFrames Method</span></span>

<span data-ttu-id="58cb6-103">返回堆栈 ([ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) 对象) 内部帧的数组。</span><span class="sxs-lookup"><span data-stu-id="58cb6-103">Returns an array of internal frames ([ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) objects) on the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58cb6-104">语法</span><span class="sxs-lookup"><span data-stu-id="58cb6-104">Syntax</span></span>  
  
```cpp
HRESULT GetActiveInternalFrames  
      (  
      [in] ULONG32 cInternalFrames,  
      [out] ULONG32 *pcInternalFrames,  
      [in, out,size_is(cInternalFrames), length_is(*pcInternalFrames)]  
            ICorDebugInternalFrame2 * ppInternalFrames[]  
      );  
```  
  
## <a name="parameters"></a><span data-ttu-id="58cb6-105">参数</span><span class="sxs-lookup"><span data-stu-id="58cb6-105">Parameters</span></span>  

 `cInternalFrames`  
 <span data-ttu-id="58cb6-106">中中所需的内部帧的数目 `ppInternalFrames` 。</span><span class="sxs-lookup"><span data-stu-id="58cb6-106">[in] The number of internal frames expected in `ppInternalFrames`.</span></span>  
  
 `pcInternalFrames`  
 <span data-ttu-id="58cb6-107">弄指向的指针 `ULONG32` ，该指针包含堆栈上的内部帧的数目。</span><span class="sxs-lookup"><span data-stu-id="58cb6-107">[out] A pointer to a `ULONG32` that contains the number of internal frames on the stack.</span></span>  
  
 `ppInternalFrames`  
 <span data-ttu-id="58cb6-108">[in，out]一个指针，指向堆栈上内部帧的数组的地址。</span><span class="sxs-lookup"><span data-stu-id="58cb6-108">[in, out] A pointer to the address of an array of internal frames on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="58cb6-109">返回值</span><span class="sxs-lookup"><span data-stu-id="58cb6-109">Return Value</span></span>  

 <span data-ttu-id="58cb6-110">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="58cb6-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="58cb6-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="58cb6-111">HRESULT</span></span>|<span data-ttu-id="58cb6-112">说明</span><span class="sxs-lookup"><span data-stu-id="58cb6-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="58cb6-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="58cb6-113">S_OK</span></span>|<span data-ttu-id="58cb6-114">已成功创建 [ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="58cb6-114">The [ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) object was successfully created.</span></span>|  
|<span data-ttu-id="58cb6-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="58cb6-115">E_INVALIDARG</span></span>|<span data-ttu-id="58cb6-116">`cInternalFrames` 不为零，并且 `ppInternalFrames` 为 `null` 或 `pcInternalFrames` 为 `null` 。</span><span class="sxs-lookup"><span data-stu-id="58cb6-116">`cInternalFrames` is not zero and `ppInternalFrames` is `null`, or `pcInternalFrames` is `null`.</span></span>|  
|<span data-ttu-id="58cb6-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="58cb6-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="58cb6-118">`ppInternalFrames` 小于内部帧的计数。</span><span class="sxs-lookup"><span data-stu-id="58cb6-118">`ppInternalFrames` is smaller than the count of internal frames.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="58cb6-119">例外</span><span class="sxs-lookup"><span data-stu-id="58cb6-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58cb6-120">备注</span><span class="sxs-lookup"><span data-stu-id="58cb6-120">Remarks</span></span>  

 <span data-ttu-id="58cb6-121">内部帧是由运行时推送到堆栈上的数据结构，用于存储临时数据。</span><span class="sxs-lookup"><span data-stu-id="58cb6-121">Internal frames are data structures pushed onto the stack by the runtime to store temporary data.</span></span>  
  
 <span data-ttu-id="58cb6-122">第一次调用时 `GetActiveInternalFrames` ，应将 `cInternalFrames` 参数设置为 0 (零) ，将参数设置 `ppInternalFrames` 为 null。</span><span class="sxs-lookup"><span data-stu-id="58cb6-122">When you first call `GetActiveInternalFrames`, you should set the `cInternalFrames` parameter to 0 (zero), and the `ppInternalFrames` parameter to null.</span></span> <span data-ttu-id="58cb6-123">`GetActiveInternalFrames`第一次返回时， `pcInternalFrames` 包含堆栈上内部帧的计数。</span><span class="sxs-lookup"><span data-stu-id="58cb6-123">When `GetActiveInternalFrames` first returns, `pcInternalFrames` contains the count of the internal frames on the stack.</span></span>  
  
 <span data-ttu-id="58cb6-124">`GetActiveInternalFrames` 然后，应再次调用。</span><span class="sxs-lookup"><span data-stu-id="58cb6-124">`GetActiveInternalFrames` should then be called a second time.</span></span> <span data-ttu-id="58cb6-125">应在参数中传递正确的计数 (`pcInternalFrames`) `cInternalFrames` ，并在中指定一个指向适当大小的数组的指针 `ppInternalFrames` 。</span><span class="sxs-lookup"><span data-stu-id="58cb6-125">You should pass the proper count (`pcInternalFrames`) in the `cInternalFrames` parameter, and specify a pointer to an appropriately sized array in `ppInternalFrames`.</span></span>  
  
 <span data-ttu-id="58cb6-126">使用 [ICorDebugStackWalk：： GetFrame](icordebugthread3-getactiveinternalframes-method.md) 方法返回实际的堆栈帧。</span><span class="sxs-lookup"><span data-stu-id="58cb6-126">Use the [ICorDebugStackWalk::GetFrame](icordebugthread3-getactiveinternalframes-method.md) method to return actual stack frames.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58cb6-127">要求</span><span class="sxs-lookup"><span data-stu-id="58cb6-127">Requirements</span></span>  

 <span data-ttu-id="58cb6-128">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="58cb6-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58cb6-129">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="58cb6-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="58cb6-130">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58cb6-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58cb6-131">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58cb6-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58cb6-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58cb6-132">See also</span></span>

- [<span data-ttu-id="58cb6-133">调试接口</span><span class="sxs-lookup"><span data-stu-id="58cb6-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="58cb6-134">调试</span><span class="sxs-lookup"><span data-stu-id="58cb6-134">Debugging</span></span>](index.md)
