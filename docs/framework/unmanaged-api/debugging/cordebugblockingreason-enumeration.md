---
title: CorDebugBlockingReason 枚举
ms.date: 03/30/2017
api_name:
- CorDebugBlockingReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingReason
helpviewer_keywords:
- CorDebugBlockingReason enumeration [.NET Framework debugging]
ms.assetid: a6ac2531-ddfe-46fd-88fe-8b1eabe0b255
topic_type:
- apiref
ms.openlocfilehash: ddd03d70656ad52fd9d577beedc60b51c7b305d5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672846"
---
# <a name="cordebugblockingreason-enumeration"></a><span data-ttu-id="f7978-102">CorDebugBlockingReason 枚举</span><span class="sxs-lookup"><span data-stu-id="f7978-102">CorDebugBlockingReason Enumeration</span></span>

<span data-ttu-id="f7978-103">指定线程可能在给定对象上受到阻塞的原因。</span><span class="sxs-lookup"><span data-stu-id="f7978-103">Specifies the reasons why a thread may become blocked on a given object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7978-104">语法</span><span class="sxs-lookup"><span data-stu-id="f7978-104">Syntax</span></span>  
  
```cpp  
Typedef enum CorDebugBlockingReason  
{  
   BLOCKING_NONE = 0  
   BLOCKING_MONITOR_CRITICAL_SECTION = 1  
   BLOCKING_MONITOR_EVENT = 2  
}  CorDebugBlockingReason;  
```  
  
## <a name="members"></a><span data-ttu-id="f7978-105">成员</span><span class="sxs-lookup"><span data-stu-id="f7978-105">Members</span></span>  
  
|<span data-ttu-id="f7978-106">成员</span><span class="sxs-lookup"><span data-stu-id="f7978-106">Member</span></span>|<span data-ttu-id="f7978-107">说明</span><span class="sxs-lookup"><span data-stu-id="f7978-107">Description</span></span>|  
|------------|-----------------|  
|`BLOCKING_NONE`|<span data-ttu-id="f7978-108">仅限内部使用。</span><span class="sxs-lookup"><span data-stu-id="f7978-108">Internal use only.</span></span>|  
|`BLOCKING_MONITOR_CRITICAL_SECTION`|<span data-ttu-id="f7978-109">线程尝试获取与对象上的监视器锁关联的临界区。</span><span class="sxs-lookup"><span data-stu-id="f7978-109">A thread is trying to acquire the critical section that is associated with the monitor lock on an object.</span></span> <span data-ttu-id="f7978-110">通常，在调用或方法之一时，会发生这种情况 <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="f7978-110">Typically, this occurs when you call one of the <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> or <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> methods.</span></span>|  
|`BLOCKING_MONITOR_EVENT`|<span data-ttu-id="f7978-111">线程正在等待与对象的监视器锁关联的事件。</span><span class="sxs-lookup"><span data-stu-id="f7978-111">A thread is waiting on the event that is associated with a monitor lock for an object.</span></span> <span data-ttu-id="f7978-112">通常情况下，当调用其中一个方法时，会发生这种情况 <xref:System.Threading.Monitor?displayProperty=nameWithType> `Wait` 。</span><span class="sxs-lookup"><span data-stu-id="f7978-112">Typically, this occurs when you call one of the <xref:System.Threading.Monitor?displayProperty=nameWithType>`Wait` methods.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7978-113">注解</span><span class="sxs-lookup"><span data-stu-id="f7978-113">Remarks</span></span>  

 <span data-ttu-id="f7978-114">当 `BLOCKING_MONITOR_CRITICAL_SECTION` `BLOCKING_MONITOR_EVENT` 在 [CorDebugBlockingObject](cordebugblockingobject-structure.md) 结构中使用或成员时，结构的 `pBlockingObject` 成员指向一个 "ICorDebugValue" 接口，该接口表示正在输入的对象。</span><span class="sxs-lookup"><span data-stu-id="f7978-114">When the `BLOCKING_MONITOR_CRITICAL_SECTION` or `BLOCKING_MONITOR_EVENT` member is used in a [CorDebugBlockingObject](cordebugblockingobject-structure.md) structure, the `pBlockingObject` member of the structure points to an "ICorDebugValue" interface that represents the object that is being entered.</span></span> <span data-ttu-id="f7978-115">还保证实现 [ICorDebugHeapValue3](icordebugheapvalue3-interface.md) 接口。</span><span class="sxs-lookup"><span data-stu-id="f7978-115">It is also guaranteed to implement the [ICorDebugHeapValue3](icordebugheapvalue3-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7978-116">要求</span><span class="sxs-lookup"><span data-stu-id="f7978-116">Requirements</span></span>  

 <span data-ttu-id="f7978-117">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f7978-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7978-118">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f7978-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f7978-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7978-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7978-120">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7978-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7978-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f7978-121">See also</span></span>

- [<span data-ttu-id="f7978-122">调试枚举</span><span class="sxs-lookup"><span data-stu-id="f7978-122">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="f7978-123">调试</span><span class="sxs-lookup"><span data-stu-id="f7978-123">Debugging</span></span>](index.md)
