---
title: ICorDebugInstanceFieldSymbol::GetName 方法
ms.date: 03/30/2017
ms.assetid: d9c12b1f-9c1d-4943-8e9e-93b55faf085f
ms.openlocfilehash: e466a62761cc6dd1f1fc0a54f05d54f85c190d07
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724931"
---
# <a name="icordebuginstancefieldsymbolgetname-method"></a><span data-ttu-id="a0b5b-102">ICorDebugInstanceFieldSymbol::GetName 方法</span><span class="sxs-lookup"><span data-stu-id="a0b5b-102">ICorDebugInstanceFieldSymbol::GetName Method</span></span>

<span data-ttu-id="a0b5b-103">获取实例字段的名称。</span><span class="sxs-lookup"><span data-stu-id="a0b5b-103">Gets the name of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0b5b-104">语法</span><span class="sxs-lookup"><span data-stu-id="a0b5b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0b5b-105">参数</span><span class="sxs-lookup"><span data-stu-id="a0b5b-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="a0b5b-106">[in] `szName` 缓冲区中的字符数。</span><span class="sxs-lookup"><span data-stu-id="a0b5b-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="a0b5b-107">[out] 指向实际写入 `szName` 缓冲区的字符数。缓冲区的字符数的指针。</span><span class="sxs-lookup"><span data-stu-id="a0b5b-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="a0b5b-108">[out] 用于存储返回名称的字符数组。</span><span class="sxs-lookup"><span data-stu-id="a0b5b-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0b5b-109">注解</span><span class="sxs-lookup"><span data-stu-id="a0b5b-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a0b5b-110">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="a0b5b-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0b5b-111">要求</span><span class="sxs-lookup"><span data-stu-id="a0b5b-111">Requirements</span></span>  

 <span data-ttu-id="a0b5b-112">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a0b5b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0b5b-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a0b5b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0b5b-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0b5b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0b5b-115">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0b5b-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0b5b-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0b5b-116">See also</span></span>

- [<span data-ttu-id="a0b5b-117">ICorDebugInstanceFieldSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="a0b5b-117">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="a0b5b-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="a0b5b-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
