---
title: ICorDebugProcess2::GetReferenceValueFromGCHandle 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetReferenceValueFromGCHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetReferenceValueFromGCHandle
helpviewer_keywords:
- GetReferenceValueFromGCHandle method [.NET Framework debugging]
- ICorDebugProcess2::GetReferenceValueFromGCHandle method [.NET Framework debugging]
ms.assetid: 8bdd7f4c-19f2-4ede-875e-603773e8c128
topic_type:
- apiref
ms.openlocfilehash: a5b9d57aab834ba3ca72a2ea8576ec70cd88eb77
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713569"
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a><span data-ttu-id="92ef4-102">ICorDebugProcess2::GetReferenceValueFromGCHandle 方法</span><span class="sxs-lookup"><span data-stu-id="92ef4-102">ICorDebugProcess2::GetReferenceValueFromGCHandle Method</span></span>

<span data-ttu-id="92ef4-103">获取指向具有垃圾回收句柄的指定托管对象的引用指针。</span><span class="sxs-lookup"><span data-stu-id="92ef4-103">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92ef4-104">语法</span><span class="sxs-lookup"><span data-stu-id="92ef4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92ef4-105">参数</span><span class="sxs-lookup"><span data-stu-id="92ef4-105">Parameters</span></span>  

 `handle`  
 <span data-ttu-id="92ef4-106">中指向具有垃圾回收句柄的托管对象的指针。</span><span class="sxs-lookup"><span data-stu-id="92ef4-106">[in] A pointer to a managed object that has a garbage collection handle.</span></span> <span data-ttu-id="92ef4-107">此值是一个 <xref:System.IntPtr> 对象，可以从 <xref:System.Runtime.InteropServices.GCHandle> 托管对象的检索。</span><span class="sxs-lookup"><span data-stu-id="92ef4-107">This value is a <xref:System.IntPtr> object and can be retrieved from the <xref:System.Runtime.InteropServices.GCHandle> for the managed object.</span></span>  
  
 `pOutValue`  
 <span data-ttu-id="92ef4-108">弄指向 ICorDebugReferenceValue 对象的地址的指针，该对象表示对指定托管对象的引用。</span><span class="sxs-lookup"><span data-stu-id="92ef4-108">[out] A pointer to the address of an ICorDebugReferenceValue object that represents a reference to the specified managed object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92ef4-109">注解</span><span class="sxs-lookup"><span data-stu-id="92ef4-109">Remarks</span></span>  

 <span data-ttu-id="92ef4-110">不要将返回的引用值与垃圾回收引用值混淆。</span><span class="sxs-lookup"><span data-stu-id="92ef4-110">Do not confuse the returned reference value with a garbage collection reference value.</span></span>  
  
 <span data-ttu-id="92ef4-111">返回的引用的行为与常规引用相同。</span><span class="sxs-lookup"><span data-stu-id="92ef4-111">The returned reference behaves like a normal reference.</span></span> <span data-ttu-id="92ef4-112">当代码在断点后面继续执行时，它会被禁用。</span><span class="sxs-lookup"><span data-stu-id="92ef4-112">It is disabled when code execution continues after a breakpoint.</span></span> <span data-ttu-id="92ef4-113">目标对象的生存期不受引用值的生存期的影响。</span><span class="sxs-lookup"><span data-stu-id="92ef4-113">The lifetime of the target object is not affected by the lifetime of the reference value.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="92ef4-114">`GetReferenceValueFromGCHandle`方法不会验证句柄。</span><span class="sxs-lookup"><span data-stu-id="92ef4-114">The `GetReferenceValueFromGCHandle` method does not validate the handle.</span></span> <span data-ttu-id="92ef4-115">因此， `GetReferenceValueFromGCHandle` 如果传递的句柄无效，则该方法可能会损坏调试器和正在调试的代码。</span><span class="sxs-lookup"><span data-stu-id="92ef4-115">Therefore, the `GetReferenceValueFromGCHandle` method can potentially corrupt both the debugger and the code being debugged if an invalid handle is passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92ef4-116">要求</span><span class="sxs-lookup"><span data-stu-id="92ef4-116">Requirements</span></span>  

 <span data-ttu-id="92ef4-117">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="92ef4-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92ef4-118">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="92ef4-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="92ef4-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92ef4-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92ef4-120">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92ef4-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
