---
title: ICorDebugFunction2::GetVersionNumber 方法
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetVersionNumber
helpviewer_keywords:
- ICorDebugFunction2::GetVersionNumber method [.NET Framework debugging]
- GetVersionNumber method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: e3a1ce48-9bb9-4ed6-a5fe-5e1819a6333f
topic_type:
- apiref
ms.openlocfilehash: 88fb205235cfaf3566fbd74b05a4e9833058f4a0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696089"
---
# <a name="icordebugfunction2getversionnumber-method"></a><span data-ttu-id="25713-102">ICorDebugFunction2::GetVersionNumber 方法</span><span class="sxs-lookup"><span data-stu-id="25713-102">ICorDebugFunction2::GetVersionNumber Method</span></span>

<span data-ttu-id="25713-103">获取此函数的 "编辑并继续" 版本。</span><span class="sxs-lookup"><span data-stu-id="25713-103">Gets the Edit and Continue version of this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25713-104">语法</span><span class="sxs-lookup"><span data-stu-id="25713-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionNumber (  
    [out] ULONG32   *pnVersion  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25713-105">参数</span><span class="sxs-lookup"><span data-stu-id="25713-105">Parameters</span></span>  

 `pnVersion`  
 <span data-ttu-id="25713-106">弄指向一个整数的指针，该整数是此 ICorDebugFunction2 对象所表示的函数的版本号。</span><span class="sxs-lookup"><span data-stu-id="25713-106">[out] A pointer to an integer that is the version number of the function that is represented by this ICorDebugFunction2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25713-107">注解</span><span class="sxs-lookup"><span data-stu-id="25713-107">Remarks</span></span>  

 <span data-ttu-id="25713-108">运行时跟踪在调试会话期间对每个模块进行的编辑的次数。</span><span class="sxs-lookup"><span data-stu-id="25713-108">The runtime keeps track of the number of edits that have taken place to each module during a debug session.</span></span> <span data-ttu-id="25713-109">函数的版本号比引入函数的编辑次数多一个。</span><span class="sxs-lookup"><span data-stu-id="25713-109">The version number of a function is one more than the number of the edit that introduced the function.</span></span> <span data-ttu-id="25713-110">函数的原始版本是版本1。</span><span class="sxs-lookup"><span data-stu-id="25713-110">The function's original version is version 1.</span></span> <span data-ttu-id="25713-111">每次调用该模块上的 [ICorDebugModule2：： ApplyChanges](icordebugmodule2-applychanges-method.md) 时，模块的数字都会递增。</span><span class="sxs-lookup"><span data-stu-id="25713-111">The number is incremented for a module every time [ICorDebugModule2::ApplyChanges](icordebugmodule2-applychanges-method.md) is called on that module.</span></span> <span data-ttu-id="25713-112">因此，如果在第一次和第一次调用时已替换函数体，则 `ICorDebugModule2::ApplyChanges` `GetVersionNumber` 可能会为该函数返回版本1、2或4，但不返回版本3。</span><span class="sxs-lookup"><span data-stu-id="25713-112">Thus, if a function’s body was replaced in the first and third call to `ICorDebugModule2::ApplyChanges`, `GetVersionNumber` may return version 1, 2, or 4 for that function, but not version 3.</span></span> <span data-ttu-id="25713-113"> (该函数将没有版本3。 ) </span><span class="sxs-lookup"><span data-stu-id="25713-113">(That function would have no version 3.)</span></span>  
  
 <span data-ttu-id="25713-114">为每个模块单独跟踪版本号。</span><span class="sxs-lookup"><span data-stu-id="25713-114">The version number is tracked separately for each module.</span></span> <span data-ttu-id="25713-115">因此，如果在模块1上执行四个编辑，而在模块2上执行 "无"，则下一次编辑时，模块1将为模块1中的所有编辑函数分配6号。</span><span class="sxs-lookup"><span data-stu-id="25713-115">So, if you perform four edits on Module 1, and none on Module 2, your next edit on Module 1 will assign a version number of 6 to all the edited functions in Module 1.</span></span> <span data-ttu-id="25713-116">如果相同的编辑触及模块2，则模块2中的函数将获得版本号2。</span><span class="sxs-lookup"><span data-stu-id="25713-116">If the same edit touches Module 2, the functions in Module 2 will get a version number of 2.</span></span>  
  
 <span data-ttu-id="25713-117">方法获取的版本号 `GetVersionNumber` 可能低于 [ICorDebugFunction：： GetCurrentVersionNumber](icordebugfunction-getcurrentversionnumber-method.md)获取的版本号。</span><span class="sxs-lookup"><span data-stu-id="25713-117">The version number obtained by the `GetVersionNumber` method may be lower than that obtained by [ICorDebugFunction::GetCurrentVersionNumber](icordebugfunction-getcurrentversionnumber-method.md).</span></span>  
  
 <span data-ttu-id="25713-118">[ICorDebugCode：： GetVersionNumber](icordebugcode-getversionnumber-method.md)方法执行与相同的操作 `ICorDebugFunction2::GetVersionNumber` 。</span><span class="sxs-lookup"><span data-stu-id="25713-118">The [ICorDebugCode::GetVersionNumber](icordebugcode-getversionnumber-method.md) method performs the same operation as `ICorDebugFunction2::GetVersionNumber`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25713-119">要求</span><span class="sxs-lookup"><span data-stu-id="25713-119">Requirements</span></span>  

 <span data-ttu-id="25713-120">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="25713-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25713-121">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="25713-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="25713-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25713-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25713-123">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25713-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
