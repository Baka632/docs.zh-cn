---
title: COR_SEGMENT 结构
ms.date: 03/30/2017
api_name:
- COR_SEGMENT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_SEGMENT
helpviewer_keywords:
- COR_SEGMENT structure [.NET Framework debugging]
ms.assetid: 93aeecb9-7fef-4545-8daf-f566dfc47084
topic_type:
- apiref
ms.openlocfilehash: 738e29fa15340c76b055b608140f3c3bfbd29611
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726348"
---
# <a name="cor_segment-structure"></a><span data-ttu-id="2e51e-102">COR_SEGMENT 结构</span><span class="sxs-lookup"><span data-stu-id="2e51e-102">COR_SEGMENT Structure</span></span>

<span data-ttu-id="2e51e-103">包含有关托管堆中的内存区域的信息。</span><span class="sxs-lookup"><span data-stu-id="2e51e-103">Contains information about a region of memory in the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e51e-104">语法</span><span class="sxs-lookup"><span data-stu-id="2e51e-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_SEGMENT {  
    CORDB_ADDRESS start;
    CORDB_ADDRESS end;
    CorDebugGenerationTypes gen;
    ULONG heap;
} COR_SEGMENT;  
```  
  
## <a name="members"></a><span data-ttu-id="2e51e-105">成员</span><span class="sxs-lookup"><span data-stu-id="2e51e-105">Members</span></span>  
  
|<span data-ttu-id="2e51e-106">成员</span><span class="sxs-lookup"><span data-stu-id="2e51e-106">Member</span></span>|<span data-ttu-id="2e51e-107">说明</span><span class="sxs-lookup"><span data-stu-id="2e51e-107">Description</span></span>|  
|------------|-----------------|  
|`start`|<span data-ttu-id="2e51e-108">内存区域的起始地址。</span><span class="sxs-lookup"><span data-stu-id="2e51e-108">The starting address of the memory region.</span></span>|  
|`end`|<span data-ttu-id="2e51e-109">内存区域的结束地址。</span><span class="sxs-lookup"><span data-stu-id="2e51e-109">The ending address of the memory region.</span></span>|  
|`gen`|<span data-ttu-id="2e51e-110">显示内存区域生成的 [CorDebugGenerationTypes](cordebuggenerationtypes-enumeration.md) 枚举成员。</span><span class="sxs-lookup"><span data-stu-id="2e51e-110">A [CorDebugGenerationTypes](cordebuggenerationtypes-enumeration.md) enumeration member that indicates the generation of the memory region.</span></span>|  
|`heap`|<span data-ttu-id="2e51e-111">内存区域驻留的堆数。</span><span class="sxs-lookup"><span data-stu-id="2e51e-111">The heap number in which the memory region resides.</span></span> <span data-ttu-id="2e51e-112">有关详细信息，请参阅备注部分。</span><span class="sxs-lookup"><span data-stu-id="2e51e-112">See the Remarks section for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e51e-113">注解</span><span class="sxs-lookup"><span data-stu-id="2e51e-113">Remarks</span></span>  

 <span data-ttu-id="2e51e-114">`COR_SEGMENTS` 结构表示托管堆中的内存区域。</span><span class="sxs-lookup"><span data-stu-id="2e51e-114">The `COR_SEGMENTS` structure represents a region of memory in the managed heap.</span></span>  <span data-ttu-id="2e51e-115">`COR_SEGMENTS` 对象是 [ICorDebugHeapRegionEnum](icordebugheapsegmentenum-interface.md) 集合对象的成员，通过调用 [ICorDebugProcess5::EnumerateHeapRegions](icordebugprocess5-enumerateheapregions-method.md) 方法填充。</span><span class="sxs-lookup"><span data-stu-id="2e51e-115">`COR_SEGMENTS` objects are members of the [ICorDebugHeapRegionEnum](icordebugheapsegmentenum-interface.md) collection object, which is populated by calling the [ICorDebugProcess5::EnumerateHeapRegions](icordebugprocess5-enumerateheapregions-method.md) method.</span></span>  
  
 <span data-ttu-id="2e51e-116">`heap` 字段是处理器编号，对应报告的堆。</span><span class="sxs-lookup"><span data-stu-id="2e51e-116">The `heap` field is the processor number, which corresponds to the heap being reported.</span></span> <span data-ttu-id="2e51e-117">对于工作站垃圾回收器，其值始终为零，因为工作站仅有一个垃圾回收堆。</span><span class="sxs-lookup"><span data-stu-id="2e51e-117">For workstation garbage collectors, its value is always zero, because workstations have only one garbage collection heap.</span></span> <span data-ttu-id="2e51e-118">对于服务器垃圾回收器，其值对应于堆附加到的处理器。</span><span class="sxs-lookup"><span data-stu-id="2e51e-118">For server garbage collectors, its value corresponds to the processor the heap is attached to.</span></span> <span data-ttu-id="2e51e-119">请注意，根据垃圾回收器的实现细节，垃圾回收堆可能多于或少于实际的处理器。</span><span class="sxs-lookup"><span data-stu-id="2e51e-119">Note that there may be more or fewer garbage collection heaps than there are actual processors due to the implementation details of the garbage collector.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e51e-120">要求</span><span class="sxs-lookup"><span data-stu-id="2e51e-120">Requirements</span></span>  

 <span data-ttu-id="2e51e-121">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2e51e-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e51e-122">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2e51e-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2e51e-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e51e-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e51e-124">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e51e-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e51e-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e51e-125">See also</span></span>

- [<span data-ttu-id="2e51e-126">调试结构</span><span class="sxs-lookup"><span data-stu-id="2e51e-126">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="2e51e-127">调试</span><span class="sxs-lookup"><span data-stu-id="2e51e-127">Debugging</span></span>](index.md)
