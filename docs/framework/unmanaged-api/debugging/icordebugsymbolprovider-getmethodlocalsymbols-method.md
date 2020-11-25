---
title: ICorDebugSymbolProvider::GetMethodLocalSymbols 方法
ms.date: 03/30/2017
ms.assetid: 8b989e38-e779-49d1-9e90-f1f920484b08
ms.openlocfilehash: c5a21436c939ddfca0219618efe64d9e0e40aef4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730846"
---
# <a name="icordebugsymbolprovidergetmethodlocalsymbols-method"></a><span data-ttu-id="42221-102">ICorDebugSymbolProvider::GetMethodLocalSymbols 方法</span><span class="sxs-lookup"><span data-stu-id="42221-102">ICorDebugSymbolProvider::GetMethodLocalSymbols Method</span></span>

<span data-ttu-id="42221-103">给定方法的相对虚拟地址 (RVA)，获取该方法的本地符号。</span><span class="sxs-lookup"><span data-stu-id="42221-103">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42221-104">语法</span><span class="sxs-lookup"><span data-stu-id="42221-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodLocalSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42221-105">参数</span><span class="sxs-lookup"><span data-stu-id="42221-105">Parameters</span></span>  

 `nativeRVA`  
 <span data-ttu-id="42221-106">[in] 方法的本机相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="42221-106">[in] The native relative virtual address of the method.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="42221-107">[in] 请求的本地符号数。</span><span class="sxs-lookup"><span data-stu-id="42221-107">[in] The number of local symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="42221-108">[out] 一个指针，指向由方法检索的符号的数量。</span><span class="sxs-lookup"><span data-stu-id="42221-108">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="42221-109">弄指向包含方法的本地符号的 [ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md) 数组的指针。</span><span class="sxs-lookup"><span data-stu-id="42221-109">[out] A pointer to an [ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md) array that contains the method's local symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42221-110">注解</span><span class="sxs-lookup"><span data-stu-id="42221-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="42221-111">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="42221-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42221-112">要求</span><span class="sxs-lookup"><span data-stu-id="42221-112">Requirements</span></span>  

 <span data-ttu-id="42221-113">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="42221-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42221-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="42221-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="42221-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42221-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42221-116">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42221-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42221-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="42221-117">See also</span></span>

- [<span data-ttu-id="42221-118">GetMethodParameterSymbols 方法</span><span class="sxs-lookup"><span data-stu-id="42221-118">GetMethodParameterSymbols Method</span></span>](icordebugsymbolprovider-getmethodparametersymbols-method.md)
- [<span data-ttu-id="42221-119">ICorDebugSymbolProvider 接口</span><span class="sxs-lookup"><span data-stu-id="42221-119">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="42221-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="42221-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
