---
title: ICorDebugProcess5 接口
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5
helpviewer_keywords:
- ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 30a39d79-1f10-4328-9c5d-094ed824e2ba
topic_type:
- apiref
ms.openlocfilehash: cef69ac7e3572b67dd676ce8408e4210d93accf0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717573"
---
# <a name="icordebugprocess5-interface"></a><span data-ttu-id="029eb-102">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="029eb-102">ICorDebugProcess5 Interface</span></span>

<span data-ttu-id="029eb-103">扩展 ICorDebugProcess 接口以支持对托管堆的访问，以提供有关托管对象的垃圾回收的信息，以及确定调试器是否从应用程序本地本机映像缓存中加载图像。</span><span class="sxs-lookup"><span data-stu-id="029eb-103">Extends the ICorDebugProcess interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application local native image cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="029eb-104">方法</span><span class="sxs-lookup"><span data-stu-id="029eb-104">Methods</span></span>  
  
|<span data-ttu-id="029eb-105">方法</span><span class="sxs-lookup"><span data-stu-id="029eb-105">Method</span></span>|<span data-ttu-id="029eb-106">说明</span><span class="sxs-lookup"><span data-stu-id="029eb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="029eb-107">EnableNGenPolicy 方法</span><span class="sxs-lookup"><span data-stu-id="029eb-107">EnableNGenPolicy Method</span></span>](icordebugprocess5-enablengenpolicy-method.md)|<span data-ttu-id="029eb-108">设置一个值，该值确定应用程序在托管调试器下运行时如何加载本机映像。</span><span class="sxs-lookup"><span data-stu-id="029eb-108">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>|  
|[<span data-ttu-id="029eb-109">EnumerateGCReferences 方法</span><span class="sxs-lookup"><span data-stu-id="029eb-109">EnumerateGCReferences Method</span></span>](icordebugprocess5-enumerategcreferences-method.md)|<span data-ttu-id="029eb-110">获取一个枚举器，该枚举器用于进程中要进行垃圾回收的所有对象。</span><span class="sxs-lookup"><span data-stu-id="029eb-110">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>|  
|[<span data-ttu-id="029eb-111">EnumerateHandles 方法</span><span class="sxs-lookup"><span data-stu-id="029eb-111">EnumerateHandles Method</span></span>](icordebugprocess5-enumeratehandles-method.md)|<span data-ttu-id="029eb-112">获取进程中的对象句柄的枚举器。</span><span class="sxs-lookup"><span data-stu-id="029eb-112">Gets an enumerator for object handles in a process.</span></span>|  
|[<span data-ttu-id="029eb-113">EnumerateHeap 方法</span><span class="sxs-lookup"><span data-stu-id="029eb-113">EnumerateHeap Method</span></span>](icordebugprocess5-enumerateheap-method.md)|<span data-ttu-id="029eb-114">获取托管堆上的对象的枚举器。</span><span class="sxs-lookup"><span data-stu-id="029eb-114">Gets an enumerator for objects on the managed heap.</span></span>|  
|[<span data-ttu-id="029eb-115">EnumerateHeapRegions 方法</span><span class="sxs-lookup"><span data-stu-id="029eb-115">EnumerateHeapRegions Method</span></span>](icordebugprocess5-enumerateheapregions-method.md)|<span data-ttu-id="029eb-116">获取托管堆区域的枚举器。</span><span class="sxs-lookup"><span data-stu-id="029eb-116">Gets an enumerator for regions of the managed heap.</span></span>|  
|[<span data-ttu-id="029eb-117">GetArrayLayout 方法</span><span class="sxs-lookup"><span data-stu-id="029eb-117">GetArrayLayout Method</span></span>](icordebugprocess5-getarraylayout-method.md)|<span data-ttu-id="029eb-118">获取有关内存中数组的布局的信息。</span><span class="sxs-lookup"><span data-stu-id="029eb-118">Gets information about the layout of an array in memory.</span></span>|  
|[<span data-ttu-id="029eb-119">GetGCHeapInformation 方法</span><span class="sxs-lookup"><span data-stu-id="029eb-119">GetGCHeapInformation Method</span></span>](icordebugprocess5-getgcheapinformation-method.md)|<span data-ttu-id="029eb-120">获取一个指向 [COR_HEAPINFO](cor-heapinfo-structure.md) 结构的指针，该结构包含有关要在托管堆上进行垃圾回收的对象的信息。</span><span class="sxs-lookup"><span data-stu-id="029eb-120">Gets a pointer to a [COR_HEAPINFO](cor-heapinfo-structure.md) structure that contains information about objects that are to be garbage-collected on the managed heap.</span></span>|  
|[<span data-ttu-id="029eb-121">GetObject 方法</span><span class="sxs-lookup"><span data-stu-id="029eb-121">GetObject Method</span></span>](icordebugprocess5-getobject-method.md)|<span data-ttu-id="029eb-122">获取指向托管堆上的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="029eb-122">Gets a pointer to an object on the managed heap.</span></span>|  
|[<span data-ttu-id="029eb-123">GetTypeFields 方法</span><span class="sxs-lookup"><span data-stu-id="029eb-123">GetTypeFields Method</span></span>](icordebugprocess5-gettypefields-method.md)|<span data-ttu-id="029eb-124">获取一个指针，该指针指向一个数组，该数组包含基于类型标识符的类型的字段信息。</span><span class="sxs-lookup"><span data-stu-id="029eb-124">Gets a pointer to an array that contains field information for a type based on its type identifier.</span></span>|  
|[<span data-ttu-id="029eb-125">GetTypeForTypeID 方法</span><span class="sxs-lookup"><span data-stu-id="029eb-125">GetTypeForTypeID Method</span></span>](icordebugprocess5-gettypefortypeid-method.md)|<span data-ttu-id="029eb-126">获取一个类型对象，该对象基于其类型标识符提供有关对象的信息。</span><span class="sxs-lookup"><span data-stu-id="029eb-126">Gets a type object that provides information about an object based on its type identifiers.</span></span>|  
|[<span data-ttu-id="029eb-127">GetTypeID 方法</span><span class="sxs-lookup"><span data-stu-id="029eb-127">GetTypeID Method</span></span>](icordebugprocess5-gettypeid-method.md)|<span data-ttu-id="029eb-128">获取指定地址处的对象的类型标识符。</span><span class="sxs-lookup"><span data-stu-id="029eb-128">Gets the type identifier for the object at a specified address.</span></span>|  
|[<span data-ttu-id="029eb-129">GetTypeLayout 方法</span><span class="sxs-lookup"><span data-stu-id="029eb-129">GetTypeLayout Method</span></span>](icordebugprocess5-gettypelayout-method.md)|<span data-ttu-id="029eb-130">根据对象的类型标识符获取有关该对象在内存中的布局的信息。</span><span class="sxs-lookup"><span data-stu-id="029eb-130">Gets information about the layout of an object in memory based on its type identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="029eb-131">注解</span><span class="sxs-lookup"><span data-stu-id="029eb-131">Remarks</span></span>  

 <span data-ttu-id="029eb-132">此接口以逻辑方式扩展了 ICorDebugProcess、ICorDebugProcess2 和 [ICorDebugProcess3](icordebugprocess3-interface.md) 接口。</span><span class="sxs-lookup"><span data-stu-id="029eb-132">This interface logically extends the ICorDebugProcess, ICorDebugProcess2, and [ICorDebugProcess3](icordebugprocess3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="029eb-133">此接口不支持从另一台计算机或从其他进程进行远程调用。</span><span class="sxs-lookup"><span data-stu-id="029eb-133">This interface does not support being called remotely, either from another machine or from another process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="029eb-134">要求</span><span class="sxs-lookup"><span data-stu-id="029eb-134">Requirements</span></span>  

 <span data-ttu-id="029eb-135">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="029eb-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="029eb-136">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="029eb-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="029eb-137">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="029eb-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="029eb-138">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="029eb-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="029eb-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="029eb-139">See also</span></span>

- [<span data-ttu-id="029eb-140">调试接口</span><span class="sxs-lookup"><span data-stu-id="029eb-140">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="029eb-141">调试</span><span class="sxs-lookup"><span data-stu-id="029eb-141">Debugging</span></span>](index.md)
