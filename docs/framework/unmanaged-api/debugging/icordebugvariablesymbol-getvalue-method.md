---
title: ICorDebugVariableSymbol::GetValue 方法
ms.date: 03/30/2017
ms.assetid: 90abece1-392e-4ade-94a1-30c75b0f7074
ms.openlocfilehash: 0a57b1a31e1ef4b0db317012b25bc65ecbbaf011
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725958"
---
# <a name="icordebugvariablesymbolgetvalue-method"></a><span data-ttu-id="18aed-102">ICorDebugVariableSymbol::GetValue 方法</span><span class="sxs-lookup"><span data-stu-id="18aed-102">ICorDebugVariableSymbol::GetValue Method</span></span>

<span data-ttu-id="18aed-103">获取作为字节数组的变量的值。</span><span class="sxs-lookup"><span data-stu-id="18aed-103">Gets the value of a variable as a byte array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18aed-104">语法</span><span class="sxs-lookup"><span data-stu-id="18aed-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue(  
   [in] ULONG32 offset,  
   [in] ULONG32 cbContext,  
   [in, size_is(cbContext)] BYTE context[],  
   [in] ULONG32 cbValue,  
   [out] ULONG32 *pcbValue,  
   [out, size_is(cbValue), length_is(*pcbValue)] BYTE pValue[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18aed-105">参数</span><span class="sxs-lookup"><span data-stu-id="18aed-105">Parameters</span></span>  

 `offset`  
 <span data-ttu-id="18aed-106">[in] 从其读取值的变量中的起始偏移量。</span><span class="sxs-lookup"><span data-stu-id="18aed-106">[in] The starting offset in the variable from which to read the value.</span></span> <span data-ttu-id="18aed-107">读取对象中的成员字段时使用此参数。</span><span class="sxs-lookup"><span data-stu-id="18aed-107">This parameter is used when reading member fields in an object.</span></span>  
  
 `cbContext`  
 <span data-ttu-id="18aed-108">[in] `context` 参数的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="18aed-108">[in] The size in bytes of the `context` argument.</span></span>  
  
 `context`  
 <span data-ttu-id="18aed-109">[in] 用于读取值的线程上下文。</span><span class="sxs-lookup"><span data-stu-id="18aed-109">[in] The thread context used to read the value.</span></span>  
  
 `cbValue`  
 <span data-ttu-id="18aed-110">[in] `pValue` 缓冲区的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="18aed-110">[in] The size in bytes of the `pValue` buffer.</span></span>  
  
 `pcbValue`  
 <span data-ttu-id="18aed-111">[out] 实际写入 `pValue` 缓冲区的字节数。</span><span class="sxs-lookup"><span data-stu-id="18aed-111">[out] The number of bytes actually written to the `pValue` buffer.</span></span>  
  
 `pValue`  
 <span data-ttu-id="18aed-112">[out] 包含变量值的字节数组。</span><span class="sxs-lookup"><span data-stu-id="18aed-112">[out] A byte array that contains the value of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18aed-113">注解</span><span class="sxs-lookup"><span data-stu-id="18aed-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="18aed-114">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="18aed-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18aed-115">要求</span><span class="sxs-lookup"><span data-stu-id="18aed-115">Requirements</span></span>  

 <span data-ttu-id="18aed-116">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="18aed-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18aed-117">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="18aed-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="18aed-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18aed-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18aed-119">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18aed-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18aed-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="18aed-120">See also</span></span>

- [<span data-ttu-id="18aed-121">ICorDebugVariableSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="18aed-121">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="18aed-122">调试接口</span><span class="sxs-lookup"><span data-stu-id="18aed-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
