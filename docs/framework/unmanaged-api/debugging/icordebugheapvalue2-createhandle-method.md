---
title: ICorDebugHeapValue2::CreateHandle 方法
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue2.CreateHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue2::CreateHandle
helpviewer_keywords:
- CreateHandle method [.NET Framework debugging]
- ICorDebugHeapValue2::CreateHandle method [.NET Framework debugging]
ms.assetid: fbc418e8-fa22-420d-84ec-e0e1800db041
topic_type:
- apiref
ms.openlocfilehash: 278120c6e1bc87a061a3f81f71bdb7b89cd421be
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726556"
---
# <a name="icordebugheapvalue2createhandle-method"></a><span data-ttu-id="0b299-102">ICorDebugHeapValue2::CreateHandle 方法</span><span class="sxs-lookup"><span data-stu-id="0b299-102">ICorDebugHeapValue2::CreateHandle Method</span></span>

<span data-ttu-id="0b299-103">为此 ICorDebugHeapValue2 对象表示的堆值创建指定类型的句柄。</span><span class="sxs-lookup"><span data-stu-id="0b299-103">Creates a handle of the specified type for the heap value represented by this ICorDebugHeapValue2 object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b299-104">语法</span><span class="sxs-lookup"><span data-stu-id="0b299-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateHandle (  
    [in] CorDebugHandleType      type,
    [out] ICorDebugHandleValue   **ppHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b299-105">参数</span><span class="sxs-lookup"><span data-stu-id="0b299-105">Parameters</span></span>  

 `type`  
 <span data-ttu-id="0b299-106">中CorDebugHandleType 枚举的一个值，该值指定要创建的句柄的类型。</span><span class="sxs-lookup"><span data-stu-id="0b299-106">[in] A value of the CorDebugHandleType enumeration that specifies the type of handle to be created.</span></span>  
  
 `ppHandle`  
 <span data-ttu-id="0b299-107">弄指向 ICorDebugHandleValue 对象的地址的指针，该对象表示此堆值的新句柄。</span><span class="sxs-lookup"><span data-stu-id="0b299-107">[out] A pointer to the address of an ICorDebugHandleValue object that represents the new handle for this heap value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b299-108">注解</span><span class="sxs-lookup"><span data-stu-id="0b299-108">Remarks</span></span>  

 <span data-ttu-id="0b299-109">该句柄将在与堆值相关联的应用程序域中创建，如果应用程序域已卸载，则将变为无效。</span><span class="sxs-lookup"><span data-stu-id="0b299-109">The handle will be created in the application domain that is associated with the heap value, and will become invalid if the application domain gets unloaded.</span></span>  
  
 <span data-ttu-id="0b299-110">对于同一堆值多次调用此函数会创建多个句柄。</span><span class="sxs-lookup"><span data-stu-id="0b299-110">Multiple calls to this function for the same heap value will create multiple handles.</span></span> <span data-ttu-id="0b299-111">因为句柄会影响垃圾回收器的性能，所以调试程序应将自身限制为相对较少数量的句柄， (每次处于活动状态的 256) 。</span><span class="sxs-lookup"><span data-stu-id="0b299-111">Because handles affect the performance of the garbage collector, the debugger should limit itself to a relatively small number of handles (about 256) that are active at a time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b299-112">要求</span><span class="sxs-lookup"><span data-stu-id="0b299-112">Requirements</span></span>  

 <span data-ttu-id="0b299-113">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0b299-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b299-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0b299-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0b299-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0b299-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0b299-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b299-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
