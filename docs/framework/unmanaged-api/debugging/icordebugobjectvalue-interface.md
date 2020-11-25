---
title: ICorDebugObjectValue 接口
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue
helpviewer_keywords:
- ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 937de6a0-6fbf-4ddc-80ea-a6217b73e62b
topic_type:
- apiref
ms.openlocfilehash: 2a5a618491bf2c624669728d97a690cca315bff8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724671"
---
# <a name="icordebugobjectvalue-interface"></a><span data-ttu-id="0ec54-102">ICorDebugObjectValue 接口</span><span class="sxs-lookup"><span data-stu-id="0ec54-102">ICorDebugObjectValue Interface</span></span>

<span data-ttu-id="0ec54-103">"ICorDebugValue" 的子类，表示包含对象的值。</span><span class="sxs-lookup"><span data-stu-id="0ec54-103">A subclass of "ICorDebugValue" that represents a value that contains an object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0ec54-104">方法</span><span class="sxs-lookup"><span data-stu-id="0ec54-104">Methods</span></span>  
  
|<span data-ttu-id="0ec54-105">方法</span><span class="sxs-lookup"><span data-stu-id="0ec54-105">Method</span></span>|<span data-ttu-id="0ec54-106">说明</span><span class="sxs-lookup"><span data-stu-id="0ec54-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0ec54-107">GetClass 方法</span><span class="sxs-lookup"><span data-stu-id="0ec54-107">GetClass Method</span></span>](icordebugobjectvalue-getclass-method.md)|<span data-ttu-id="0ec54-108">获取指向公共语言运行时的接口指针，该指针指向此引用的对象 (CLR) <xref:System.Type> `ICorDebugObjectValue` 。</span><span class="sxs-lookup"><span data-stu-id="0ec54-108">Gets an interface pointer to the common language runtime (CLR) <xref:System.Type> of the object that this `ICorDebugObjectValue` references.</span></span>|  
|[<span data-ttu-id="0ec54-109">GetContext 方法</span><span class="sxs-lookup"><span data-stu-id="0ec54-109">GetContext Method</span></span>](icordebugobjectvalue-getcontext-method.md)|<span data-ttu-id="0ec54-110">未实现。</span><span class="sxs-lookup"><span data-stu-id="0ec54-110">Not implemented.</span></span>|  
|[<span data-ttu-id="0ec54-111">GetFieldValue 方法</span><span class="sxs-lookup"><span data-stu-id="0ec54-111">GetFieldValue Method</span></span>](icordebugobjectvalue-getfieldvalue-method.md)|<span data-ttu-id="0ec54-112">获取一个指向 [ICorDebugValue](icordebugvalue-interface.md) 的接口指针，该指针表示指定类的指定字段的值。</span><span class="sxs-lookup"><span data-stu-id="0ec54-112">Gets an interface pointer to an [ICorDebugValue](icordebugvalue-interface.md) that represents the value of the specified field of the specified class.</span></span>|  
|[<span data-ttu-id="0ec54-113">GetManagedCopy 方法</span><span class="sxs-lookup"><span data-stu-id="0ec54-113">GetManagedCopy Method</span></span>](icordebugobjectvalue-getmanagedcopy-method.md)|<span data-ttu-id="0ec54-114">已过时。</span><span class="sxs-lookup"><span data-stu-id="0ec54-114">Obsolete.</span></span> <span data-ttu-id="0ec54-115">请勿调用此方法。</span><span class="sxs-lookup"><span data-stu-id="0ec54-115">Do not call this method.</span></span>|  
|[<span data-ttu-id="0ec54-116">GetVirtualMethod 方法</span><span class="sxs-lookup"><span data-stu-id="0ec54-116">GetVirtualMethod Method</span></span>](icordebugobjectvalue-getvirtualmethod-method.md)|<span data-ttu-id="0ec54-117">未实现。</span><span class="sxs-lookup"><span data-stu-id="0ec54-117">Not implemented.</span></span>|  
|[<span data-ttu-id="0ec54-118">IsValueClass 方法</span><span class="sxs-lookup"><span data-stu-id="0ec54-118">IsValueClass Method</span></span>](icordebugobjectvalue-isvalueclass-method.md)|<span data-ttu-id="0ec54-119">获取一个值，该值指示由此引用的对象是否 `ICorDebugObjectValue` 为值类型。</span><span class="sxs-lookup"><span data-stu-id="0ec54-119">Gets a value that indicates whether the object referenced by this `ICorDebugObjectValue` is a value type.</span></span>|  
|[<span data-ttu-id="0ec54-120">SetFromManagedCopy 方法</span><span class="sxs-lookup"><span data-stu-id="0ec54-120">SetFromManagedCopy Method</span></span>](icordebugobjectvalue-setfrommanagedcopy-method.md)|<span data-ttu-id="0ec54-121">已过时。</span><span class="sxs-lookup"><span data-stu-id="0ec54-121">Obsolete.</span></span> <span data-ttu-id="0ec54-122">请勿调用此方法。</span><span class="sxs-lookup"><span data-stu-id="0ec54-122">Do not call this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ec54-123">注解</span><span class="sxs-lookup"><span data-stu-id="0ec54-123">Remarks</span></span>  

 <span data-ttu-id="0ec54-124">在 `ICorDebugObjectValue` 继续进行调试之前，将一直有效。</span><span class="sxs-lookup"><span data-stu-id="0ec54-124">An `ICorDebugObjectValue` remains valid until the process being debugged is continued.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0ec54-125">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="0ec54-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ec54-126">要求</span><span class="sxs-lookup"><span data-stu-id="0ec54-126">Requirements</span></span>  

 <span data-ttu-id="0ec54-127">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0ec54-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ec54-128">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0ec54-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ec54-129">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ec54-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ec54-130">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ec54-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ec54-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0ec54-131">See also</span></span>

- [<span data-ttu-id="0ec54-132">调试接口</span><span class="sxs-lookup"><span data-stu-id="0ec54-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
