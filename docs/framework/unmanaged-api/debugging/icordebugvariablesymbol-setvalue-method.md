---
title: ICorDebugVariableSymbol::SetValue 方法
ms.date: 03/30/2017
ms.assetid: 4609418d-71fa-44bc-9618-4d529d25cabb
ms.openlocfilehash: 3ef9b9b9a095d6d6026ffc38873661355d660488
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707836"
---
# <a name="icordebugvariablesymbolsetvalue-method"></a><span data-ttu-id="4c9c6-102">ICorDebugVariableSymbol::SetValue 方法</span><span class="sxs-lookup"><span data-stu-id="4c9c6-102">ICorDebugVariableSymbol::SetValue Method</span></span>

<span data-ttu-id="4c9c6-103">将字节数组的值分配给变量。</span><span class="sxs-lookup"><span data-stu-id="4c9c6-103">Assigns the value of a byte array to a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c9c6-104">语法</span><span class="sxs-lookup"><span data-stu-id="4c9c6-104">Syntax</span></span>  
  
```cpp  
HRESULT SetValue(  
   [in] ULONG32 offset,  
   [in] DWORD threadID,  
   [in] ULONG32 cbContext,  
   [in, size_is(cbContext)] BYTE context[],  
   [in] ULONG32 cbValue,  
   [in, size_is(cbValue)] BYTE pValue[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c9c6-105">参数</span><span class="sxs-lookup"><span data-stu-id="4c9c6-105">Parameters</span></span>  

 `offset`  
 <span data-ttu-id="4c9c6-106">[in] 设置值时变量中的起始偏移量。</span><span class="sxs-lookup"><span data-stu-id="4c9c6-106">[in] The starting offset in the variable at which to set the value.</span></span> <span data-ttu-id="4c9c6-107">在对象中写入成员字段时，则使用此参数。</span><span class="sxs-lookup"><span data-stu-id="4c9c6-107">This parameter is used when writing to member fields in an object.</span></span>  
  
 `threadID`  
 <span data-ttu-id="4c9c6-108">[in] 其上下文必须更新以反映新值的线程的线程标识符。</span><span class="sxs-lookup"><span data-stu-id="4c9c6-108">[in] The thread identifier of the thread whose context must be updated to reflect the new value.</span></span>  
  
 `cbContext`  
 <span data-ttu-id="4c9c6-109">[in] 线程上下文的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="4c9c6-109">[in] The size in bytes of the thread context.</span></span>  
  
 `context`  
 <span data-ttu-id="4c9c6-110">[in] 用于写入值的线程上下文。</span><span class="sxs-lookup"><span data-stu-id="4c9c6-110">[in] The thread context used to write the value.</span></span>  
  
 `cbValue`  
 <span data-ttu-id="4c9c6-111">[in] `pValue` 缓冲区的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="4c9c6-111">[in] The size in bytes of the `pValue` buffer.</span></span>  
  
 `pValue`  
 <span data-ttu-id="4c9c6-112">[in] 包含要设置的值的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="4c9c6-112">[in] The buffer that contains the value to set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c9c6-113">注解</span><span class="sxs-lookup"><span data-stu-id="4c9c6-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4c9c6-114">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="4c9c6-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c9c6-115">要求</span><span class="sxs-lookup"><span data-stu-id="4c9c6-115">Requirements</span></span>  

 <span data-ttu-id="4c9c6-116">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4c9c6-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c9c6-117">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4c9c6-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4c9c6-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4c9c6-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4c9c6-119">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c9c6-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c9c6-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4c9c6-120">See also</span></span>

- [<span data-ttu-id="4c9c6-121">ICorDebugVariableSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="4c9c6-121">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="4c9c6-122">调试接口</span><span class="sxs-lookup"><span data-stu-id="4c9c6-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
