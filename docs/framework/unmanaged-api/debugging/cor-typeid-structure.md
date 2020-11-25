---
title: COR_TYPEID 结构
ms.date: 03/30/2017
api_name:
- COR_TYPEID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_TYPEID
helpviewer_keywords:
- COR_TYPEID structure [.NET Framework debugging]
ms.assetid: 1e172b14-ee22-4943-b3b8-3740e7bdcd2e
topic_type:
- apiref
ms.openlocfilehash: 5eeb5aef7edaa23385190a309144e1477da741e8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697436"
---
# <a name="cor_typeid-structure"></a><span data-ttu-id="81876-102">COR_TYPEID 结构</span><span class="sxs-lookup"><span data-stu-id="81876-102">COR_TYPEID Structure</span></span>

<span data-ttu-id="81876-103">包含类型标识符。</span><span class="sxs-lookup"><span data-stu-id="81876-103">Contains a type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81876-104">语法</span><span class="sxs-lookup"><span data-stu-id="81876-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_TYPEID{  
    UINT64 token1;  
    UINT64 token2;  
} COR_TYPEID;  
```  
  
## <a name="members"></a><span data-ttu-id="81876-105">成员</span><span class="sxs-lookup"><span data-stu-id="81876-105">Members</span></span>  
  
|<span data-ttu-id="81876-106">成员</span><span class="sxs-lookup"><span data-stu-id="81876-106">Member</span></span>|<span data-ttu-id="81876-107">说明</span><span class="sxs-lookup"><span data-stu-id="81876-107">Description</span></span>|  
|------------|-----------------|  
|`token1`|<span data-ttu-id="81876-108">第一个标记。</span><span class="sxs-lookup"><span data-stu-id="81876-108">The first token.</span></span>|  
|`token2`|<span data-ttu-id="81876-109">第二个标记。</span><span class="sxs-lookup"><span data-stu-id="81876-109">The second token.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81876-110">注解</span><span class="sxs-lookup"><span data-stu-id="81876-110">Remarks</span></span>  

 <span data-ttu-id="81876-111">`COR_TYPEID`结构由若干调试方法返回，这些方法提供有关要进行垃圾回收的对象的信息。</span><span class="sxs-lookup"><span data-stu-id="81876-111">The `COR_TYPEID` structure is returned by a number of debugging methods that provide information about objects to be garbage-collected.</span></span> <span data-ttu-id="81876-112">然后，可以将其作为参数传递给其他调试方法，这些方法提供了有关该项的附加信息。</span><span class="sxs-lookup"><span data-stu-id="81876-112">It can then be passed as an argument to other debugging methods that provide additional information about that item.</span></span> <span data-ttu-id="81876-113">例如，通过枚举 [ICorDebugHeapEnum](icordebugheapenum-interface.md) 对象，您可以检索单个 [COR_HEAPOBJECT](cor-heapobject-structure.md) 对象，这些对象表示托管堆上的单个对象。</span><span class="sxs-lookup"><span data-stu-id="81876-113">For example, by enumerating an [ICorDebugHeapEnum](icordebugheapenum-interface.md) object, you can retrieve individual [COR_HEAPOBJECT](cor-heapobject-structure.md) objects that represent individual objects on the managed heap.</span></span> <span data-ttu-id="81876-114">然后，可以将该 `COR_TYPEID` 字段中的值传递 `COR_HEAPOBJECT.type` 给 [ICorDebugProcess5：： GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md) 方法，以检索一个 ICorDebugType 对象，该对象提供有关对象的类型信息。</span><span class="sxs-lookup"><span data-stu-id="81876-114">You can then pass the `COR_TYPEID` value from the `COR_HEAPOBJECT.type` field to the [ICorDebugProcess5::GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md) method to retrieve an ICorDebugType object that provides type information about the object.</span></span>  
  
 <span data-ttu-id="81876-115">`COR_TYPEID`对象应是不透明的。</span><span class="sxs-lookup"><span data-stu-id="81876-115">A `COR_TYPEID` object is intended to be opaque.</span></span> <span data-ttu-id="81876-116">不应访问或操作其各个字段。</span><span class="sxs-lookup"><span data-stu-id="81876-116">Its individual fields should not be accessed or manipulated.</span></span> <span data-ttu-id="81876-117">其唯一用途是作为方法调用中的参数提供的标识符， `out` 而后者又可传递给其他方法以提供其他信息。</span><span class="sxs-lookup"><span data-stu-id="81876-117">Its sole use is as an identifier that is provided as an `out` parameter in a method call and that can, in turn, be passed to other methods to provide additional information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81876-118">要求</span><span class="sxs-lookup"><span data-stu-id="81876-118">Requirements</span></span>  

 <span data-ttu-id="81876-119">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="81876-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81876-120">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="81876-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="81876-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81876-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81876-122">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81876-122">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81876-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81876-123">See also</span></span>

- [<span data-ttu-id="81876-124">调试结构</span><span class="sxs-lookup"><span data-stu-id="81876-124">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="81876-125">调试</span><span class="sxs-lookup"><span data-stu-id="81876-125">Debugging</span></span>](index.md)
