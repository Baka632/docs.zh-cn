---
title: ICorDebugCode3::GetReturnValueLiveOffset 方法
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugCode3.GetReturnValueLiveOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode3::GetReturnValueLiveOffset
helpviewer_keywords:
- ICorDebugCode3::GetReturnValueLiveOffset method [.NET Framework debugging]
- GetReturnValueLiveOffset method [.NET Framework debugging]
ms.assetid: 8c2ff5d8-8c04-4423-b1e1-e1c8764b36d3
topic_type:
- apiref
ms.openlocfilehash: 6153ebf24ae939a50d71cad2d4323090aa905851
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720810"
---
# <a name="icordebugcode3getreturnvalueliveoffset-method"></a><span data-ttu-id="ba85c-102">ICorDebugCode3::GetReturnValueLiveOffset 方法</span><span class="sxs-lookup"><span data-stu-id="ba85c-102">ICorDebugCode3::GetReturnValueLiveOffset Method</span></span>

<span data-ttu-id="ba85c-103">对于指定的 IL 偏移量，获取应放置断点的本机偏移量，以便调试器可以从函数中获取返回值。</span><span class="sxs-lookup"><span data-stu-id="ba85c-103">For a specified IL offset, gets the native offsets where a breakpoint should be placed so that the debugger can obtain the return value from a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba85c-104">语法</span><span class="sxs-lookup"><span data-stu-id="ba85c-104">Syntax</span></span>  
  
```cpp
HRESULT GetReturnValueLiveOffset(  
    [in] ULONG32 ILoffset,  
    [in] ULONG32 bufferSize,
    [out] ULONG32 *pFetched,
    [out, size_is(buffersize), length_is(*pFetched)] ULong32 pOffsets[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba85c-105">参数</span><span class="sxs-lookup"><span data-stu-id="ba85c-105">Parameters</span></span>  

 `ILoffset`  
 <span data-ttu-id="ba85c-106">IL 偏移量。</span><span class="sxs-lookup"><span data-stu-id="ba85c-106">The IL offset.</span></span> <span data-ttu-id="ba85c-107">它必须是函数调用站点，否则函数调用将失败。</span><span class="sxs-lookup"><span data-stu-id="ba85c-107">It must be a function call site or the function call will fail.</span></span>  
  
 `bufferSize`  
 <span data-ttu-id="ba85c-108">可用于存储的字节数 `pOffsets` 。</span><span class="sxs-lookup"><span data-stu-id="ba85c-108">The number of bytes available to store `pOffsets`.</span></span>  
  
 `pFetched`  
 <span data-ttu-id="ba85c-109">指向实际返回的偏移量的指针。</span><span class="sxs-lookup"><span data-stu-id="ba85c-109">A pointer to the number of offsets actually returned.</span></span> <span data-ttu-id="ba85c-110">通常，其值为1，但单个 IL 指令可以映射到多个 `CALL` 程序集指令。</span><span class="sxs-lookup"><span data-stu-id="ba85c-110">Usually, its value is 1, but a single IL instruction can map to multiple `CALL` assembly instructions.</span></span>  
  
 `pOffsets`  
 <span data-ttu-id="ba85c-111">本机偏移量的数组。</span><span class="sxs-lookup"><span data-stu-id="ba85c-111">An array of native offsets.</span></span> <span data-ttu-id="ba85c-112">通常， `pOffsets` 包含单个偏移量，但单个 IL 指令可以映射到多个 `CALL` 程序集指令。</span><span class="sxs-lookup"><span data-stu-id="ba85c-112">Typically, `pOffsets` contains a single offset, although a single IL instruction can map to multiple map to multiple `CALL` assembly instructions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba85c-113">注解</span><span class="sxs-lookup"><span data-stu-id="ba85c-113">Remarks</span></span>  

 <span data-ttu-id="ba85c-114">此方法与 [ICorDebugILFrame3：： GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) 方法一起使用，以获取返回引用类型的方法的返回值。</span><span class="sxs-lookup"><span data-stu-id="ba85c-114">This method is used along with the [ICorDebugILFrame3::GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) method to get the return value of a method that returns a reference type.</span></span> <span data-ttu-id="ba85c-115">如果将 IL 偏移量传递给函数调用站点，此方法将返回一个或多个本机偏移量。</span><span class="sxs-lookup"><span data-stu-id="ba85c-115">Passing an IL offset to a function call site to this method returns one or more native offsets.</span></span> <span data-ttu-id="ba85c-116">然后，调试器可以在函数中的这些本机偏移量上设置断点。</span><span class="sxs-lookup"><span data-stu-id="ba85c-116">The debugger can then set breakpoints on these native offsets in the function.</span></span> <span data-ttu-id="ba85c-117">当调试器遇到其中一个断点时，可以将传递给此方法的同一 IL 偏移传递给 [ICorDebugILFrame3：： GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) 方法以获取返回值。</span><span class="sxs-lookup"><span data-stu-id="ba85c-117">When the debugger hits one of the breakpoints, you can then pass the same IL offset that you passed to this method to the [ICorDebugILFrame3::GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) method to get the return value.</span></span> <span data-ttu-id="ba85c-118">调试器随后应清除它所设置的所有断点。</span><span class="sxs-lookup"><span data-stu-id="ba85c-118">The debugger should then clear all the breakpoints that it set.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="ba85c-119">`ICorDebugCode3::GetReturnValueLiveOffset`和[ICorDebugILFrame3：： GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md)方法只允许获取引用类型的返回值信息。</span><span class="sxs-lookup"><span data-stu-id="ba85c-119">The `ICorDebugCode3::GetReturnValueLiveOffset` and [ICorDebugILFrame3::GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) methods allow you to get return value information for reference types only.</span></span> <span data-ttu-id="ba85c-120">从值类型检索返回值信息 (也就是说，不支持从) 派生的所有类型 <xref:System.ValueType> 。</span><span class="sxs-lookup"><span data-stu-id="ba85c-120">Retrieving return value information from value types (that is, all types that derive from <xref:System.ValueType>) is not supported.</span></span>  
  
 <span data-ttu-id="ba85c-121">函数将返回 `HRESULT` 下表中显示的值。</span><span class="sxs-lookup"><span data-stu-id="ba85c-121">The function returns the `HRESULT` values shown in the following table.</span></span>  
  
|<span data-ttu-id="ba85c-122">`HRESULT` 值</span><span class="sxs-lookup"><span data-stu-id="ba85c-122">`HRESULT` value</span></span>|<span data-ttu-id="ba85c-123">说明</span><span class="sxs-lookup"><span data-stu-id="ba85c-123">Description</span></span>|  
|---------------------|-----------------|  
|`S_OK`|<span data-ttu-id="ba85c-124">成功。</span><span class="sxs-lookup"><span data-stu-id="ba85c-124">Success.</span></span>|  
|`CORDBG_E_INVALID_OPCODE`|<span data-ttu-id="ba85c-125">给定的 IL 偏移量站点不是调用指令，或该函数返回 `void` 。</span><span class="sxs-lookup"><span data-stu-id="ba85c-125">The given IL offset site is not a call instruction, or the function returns `void`.</span></span>|  
|`CORDBG_E_UNSUPPORTED`|<span data-ttu-id="ba85c-126">给定的 IL 偏移量是正确的调用，但不支持返回类型来获取返回值。</span><span class="sxs-lookup"><span data-stu-id="ba85c-126">The given IL offset is a proper call, but the return type is unsupported for getting a return value.</span></span>|  
  
 <span data-ttu-id="ba85c-127">`ICorDebugCode3::GetReturnValueLiveOffset`方法仅适用于基于 x86 的和 AMD64 系统。</span><span class="sxs-lookup"><span data-stu-id="ba85c-127">The `ICorDebugCode3::GetReturnValueLiveOffset` method is available only on x86-based and AMD64 systems.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba85c-128">要求</span><span class="sxs-lookup"><span data-stu-id="ba85c-128">Requirements</span></span>  

 <span data-ttu-id="ba85c-129">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ba85c-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba85c-130">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ba85c-130">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ba85c-131">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ba85c-131">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ba85c-132">**.NET Framework 版本：**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba85c-132">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba85c-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ba85c-133">See also</span></span>

- [<span data-ttu-id="ba85c-134">GetReturnValueForILOffset 方法</span><span class="sxs-lookup"><span data-stu-id="ba85c-134">GetReturnValueForILOffset Method</span></span>](icordebugilframe3-getreturnvalueforiloffset-method.md)
- [<span data-ttu-id="ba85c-135">ICorDebugCode3 接口</span><span class="sxs-lookup"><span data-stu-id="ba85c-135">ICorDebugCode3 Interface</span></span>](icordebugcode3-interface.md)
