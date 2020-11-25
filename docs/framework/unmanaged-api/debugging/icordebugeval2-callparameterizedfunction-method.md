---
title: ICorDebugEval2::CallParameterizedFunction 方法
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.CallParameterizedFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::CallParameterizedFunction
helpviewer_keywords:
- ICorDebugEval2::CallParameterizedFunction method [.NET Framework debugging]
- CallParameterizedFunction method [.NET Framework debugging]
ms.assetid: 72f54a45-dbe6-4bb4-8c99-e879a27368e5
topic_type:
- apiref
ms.openlocfilehash: c36dec80b6885b0ee56670b94dbd0b155a9710b4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729702"
---
# <a name="icordebugeval2callparameterizedfunction-method"></a><span data-ttu-id="4da06-102">ICorDebugEval2::CallParameterizedFunction 方法</span><span class="sxs-lookup"><span data-stu-id="4da06-102">ICorDebugEval2::CallParameterizedFunction Method</span></span>

<span data-ttu-id="4da06-103">设置对指定 ICorDebugFunction 的调用，此调用可以嵌套在构造函数采用参数的类中 <xref:System.Type> ，也可以采用 <xref:System.Type> 参数。</span><span class="sxs-lookup"><span data-stu-id="4da06-103">Sets up a call to the specified ICorDebugFunction, which can be nested inside a class whose constructor takes <xref:System.Type> parameters, or can itself take <xref:System.Type> parameters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4da06-104">语法</span><span class="sxs-lookup"><span data-stu-id="4da06-104">Syntax</span></span>  
  
```cpp  
HRESULT CallParameterizedFunction (  
    [in] ICorDebugFunction     *pFunction,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4da06-105">参数</span><span class="sxs-lookup"><span data-stu-id="4da06-105">Parameters</span></span>  

 `pFunction`  
 <span data-ttu-id="4da06-106">中指向 `ICorDebugFunction` 对象的指针，该对象表示要调用的函数。</span><span class="sxs-lookup"><span data-stu-id="4da06-106">[in] A pointer to an `ICorDebugFunction` object that represents the function to be called.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="4da06-107">中函数所采用的参数的数目。</span><span class="sxs-lookup"><span data-stu-id="4da06-107">[in] The number of arguments that the function takes.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="4da06-108">中指针的数组，其中每个都指向表示函数参数的 ICorDebugType 对象。</span><span class="sxs-lookup"><span data-stu-id="4da06-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a function argument.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="4da06-109">中函数中传递的值的数目。</span><span class="sxs-lookup"><span data-stu-id="4da06-109">[in] The number of values passed in the function.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="4da06-110">中指针的数组，其中每个都指向表示在函数参数中传递的值的 ICorDebugValue 对象。</span><span class="sxs-lookup"><span data-stu-id="4da06-110">[in] An array of pointers, each of which points to an ICorDebugValue object that represents a value passed in a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4da06-111">注解</span><span class="sxs-lookup"><span data-stu-id="4da06-111">Remarks</span></span>  

 <span data-ttu-id="4da06-112">`CallParameterizedFunction` 类似于 [ICorDebugEval：： CallFunction](icordebugeval-callfunction-method.md) ，只不过该函数可能位于具有类型参数的类中，可能本身采用类型参数或同时采用这两者。</span><span class="sxs-lookup"><span data-stu-id="4da06-112">`CallParameterizedFunction` is like [ICorDebugEval::CallFunction](icordebugeval-callfunction-method.md) except that the function may be inside a class with type parameters, may itself take type parameters, or both.</span></span> <span data-ttu-id="4da06-113">应该首先为类提供类型参数，然后为函数指定。</span><span class="sxs-lookup"><span data-stu-id="4da06-113">The type arguments should be given first for the class, and then for the function.</span></span>  
  
 <span data-ttu-id="4da06-114">如果函数在不同的应用程序域中，则会发生转换。</span><span class="sxs-lookup"><span data-stu-id="4da06-114">If the function is in a different application domain, a transition will occur.</span></span> <span data-ttu-id="4da06-115">但是，所有类型和值参数都必须在目标应用程序域中。</span><span class="sxs-lookup"><span data-stu-id="4da06-115">However, all type and value arguments must be in the target application domain.</span></span>  
  
 <span data-ttu-id="4da06-116">仅在有限的情况下才能执行函数求值。</span><span class="sxs-lookup"><span data-stu-id="4da06-116">Function evaluation can be performed only in limited scenarios.</span></span> <span data-ttu-id="4da06-117">如果 `CallParameterizedFunction` 或 `ICorDebugEval::CallFunction` 失败，则返回的 HRESULT 将指示失败的最常见原因。</span><span class="sxs-lookup"><span data-stu-id="4da06-117">If `CallParameterizedFunction` or `ICorDebugEval::CallFunction` fails, the returned HRESULT will indicate the most general possible reason for failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4da06-118">要求</span><span class="sxs-lookup"><span data-stu-id="4da06-118">Requirements</span></span>  

 <span data-ttu-id="4da06-119">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4da06-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4da06-120">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4da06-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4da06-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4da06-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4da06-122">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4da06-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
