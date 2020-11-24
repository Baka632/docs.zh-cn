---
title: COR_PRF_GC_ROOT_FLAGS 枚举
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_ROOT_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_ROOT_FLAGS
helpviewer_keywords:
- COR_PRF_GC_ROOT_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 4611ee6f-0f05-4d84-91e1-e83d5e7dd7e4
topic_type:
- apiref
ms.openlocfilehash: 6b4c71a099e1ddb03b8a5287b56b750f7119e34e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682349"
---
# <a name="cor_prf_gc_root_flags-enumeration"></a><span data-ttu-id="d25b0-102">COR_PRF_GC_ROOT_FLAGS 枚举</span><span class="sxs-lookup"><span data-stu-id="d25b0-102">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>

<span data-ttu-id="d25b0-103">指示垃圾回收根的属性。</span><span class="sxs-lookup"><span data-stu-id="d25b0-103">Indicates a property of a garbage collection root.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d25b0-104">语法</span><span class="sxs-lookup"><span data-stu-id="d25b0-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="d25b0-105">成员</span><span class="sxs-lookup"><span data-stu-id="d25b0-105">Members</span></span>  
  
|<span data-ttu-id="d25b0-106">成员</span><span class="sxs-lookup"><span data-stu-id="d25b0-106">Member</span></span>|<span data-ttu-id="d25b0-107">说明</span><span class="sxs-lookup"><span data-stu-id="d25b0-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|<span data-ttu-id="d25b0-108">根禁止垃圾回收移动对象。</span><span class="sxs-lookup"><span data-stu-id="d25b0-108">The root prevents a garbage collection from moving the object.</span></span>|  
|`COR_PRF_GC_ROOT_WEAKREF`|<span data-ttu-id="d25b0-109">根不会阻止垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="d25b0-109">The root does not prevent garbage collection.</span></span>|  
|`COR_PRF_GC_ROOT_INTERIOR`|<span data-ttu-id="d25b0-110">根引用的是对象的字段，而不是对象本身。</span><span class="sxs-lookup"><span data-stu-id="d25b0-110">The root refers to a field of the object rather than the object itself.</span></span>|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|<span data-ttu-id="d25b0-111">如果对象的引用计数为特定值，则根禁止垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="d25b0-111">The root prevents garbage collection if the reference count of the object is a certain value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d25b0-112">注解</span><span class="sxs-lookup"><span data-stu-id="d25b0-112">Remarks</span></span>  

 <span data-ttu-id="d25b0-113">`COR_PRF_GC_ROOT_FLAGS` 是一个位掩码，提供有关特殊根的附加信息。</span><span class="sxs-lookup"><span data-stu-id="d25b0-113">`COR_PRF_GC_ROOT_FLAGS` is a bitmask that provides additional information about special roots.</span></span> <span data-ttu-id="d25b0-114">但是，并非所有的根都是特殊的。</span><span class="sxs-lookup"><span data-stu-id="d25b0-114">However, not all roots are special.</span></span> <span data-ttu-id="d25b0-115">例如，某些根不是弱引用、内部指针、固定或引用计数的。</span><span class="sxs-lookup"><span data-stu-id="d25b0-115">For example, some roots are not weak references, interior pointers, pinned, or reference-counted.</span></span> <span data-ttu-id="d25b0-116">对于这类根，没有要传达的标志。</span><span class="sxs-lookup"><span data-stu-id="d25b0-116">For such roots, there are no flags to convey.</span></span> <span data-ttu-id="d25b0-117">因此，使用此枚举的方法（如 [ICorProfilerCallback2：： RootReferences2](icorprofilercallback2-rootreferences2-method.md) 方法）为标志位掩码发送0，指示所有标志都处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="d25b0-117">Therefore, methods that use this enumeration, such as the [ICorProfilerCallback2::RootReferences2](icorprofilercallback2-rootreferences2-method.md) method, send 0 for the flags bitmask, indicating that all flags are turned off.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d25b0-118">要求</span><span class="sxs-lookup"><span data-stu-id="d25b0-118">Requirements</span></span>  

 <span data-ttu-id="d25b0-119">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d25b0-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d25b0-120">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d25b0-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d25b0-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d25b0-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d25b0-122">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d25b0-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d25b0-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d25b0-123">See also</span></span>

- [<span data-ttu-id="d25b0-124">分析枚举</span><span class="sxs-lookup"><span data-stu-id="d25b0-124">Profiling Enumerations</span></span>](profiling-enumerations.md)
