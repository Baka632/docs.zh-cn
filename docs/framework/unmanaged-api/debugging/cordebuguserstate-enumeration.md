---
title: CorDebugUserState 枚举
ms.date: 03/30/2017
api_name:
- CorDebugUserState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugUserState
helpviewer_keywords:
- CorDebugUserState enumeration [.NET Framework debugging]
ms.assetid: 5f6c2bcd-8102-4e3b-abc5-86ab0bd62def
topic_type:
- apiref
ms.openlocfilehash: 968874a46279b7eac651d45c3890429a326651b2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726946"
---
# <a name="cordebuguserstate-enumeration"></a><span data-ttu-id="7b2a0-102">CorDebugUserState 枚举</span><span class="sxs-lookup"><span data-stu-id="7b2a0-102">CorDebugUserState Enumeration</span></span>

<span data-ttu-id="7b2a0-103">指示线程的用户状态。</span><span class="sxs-lookup"><span data-stu-id="7b2a0-103">Indicates the user state of a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b2a0-104">语法</span><span class="sxs-lookup"><span data-stu-id="7b2a0-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugUserState {  
    USER_STOP_REQUESTED     =  0x01,  
    USER_SUSPEND_REQUESTED  =  0x02,  
    USER_BACKGROUND         =  0x04,  
    USER_UNSTARTED          =  0x08,  
    USER_STOPPED            =  0x10,  
    USER_WAIT_SLEEP_JOIN    =  0x20,  
    USER_SUSPENDED          =  0x40,  
    USER_UNSAFE_POINT       =  0x80,  
    USER_THREADPOOL         = 0x100  
} CorDebugUserState;  
```  
  
## <a name="members"></a><span data-ttu-id="7b2a0-105">成员</span><span class="sxs-lookup"><span data-stu-id="7b2a0-105">Members</span></span>  
  
|<span data-ttu-id="7b2a0-106">Value</span><span class="sxs-lookup"><span data-stu-id="7b2a0-106">Value</span></span>|<span data-ttu-id="7b2a0-107">说明</span><span class="sxs-lookup"><span data-stu-id="7b2a0-107">Description</span></span>|  
|-----------|-----------------|  
|`USER_STOP_REQUESTED`|<span data-ttu-id="7b2a0-108">已请求终止线程。</span><span class="sxs-lookup"><span data-stu-id="7b2a0-108">A termination of the thread has been requested.</span></span>|  
|`USER_SUSPEND_REQUESTED`|<span data-ttu-id="7b2a0-109">已请求挂起线程。</span><span class="sxs-lookup"><span data-stu-id="7b2a0-109">A suspension of the thread has been requested.</span></span>|  
|`USER_BACKGROUND`|<span data-ttu-id="7b2a0-110">线程在后台运行。</span><span class="sxs-lookup"><span data-stu-id="7b2a0-110">The thread is running in the background.</span></span>|  
|`USER_UNSTARTED`|<span data-ttu-id="7b2a0-111">线程尚未开始执行。</span><span class="sxs-lookup"><span data-stu-id="7b2a0-111">The thread has not started executing.</span></span>|  
|`USER_STOPPED`|<span data-ttu-id="7b2a0-112">线程已终止。</span><span class="sxs-lookup"><span data-stu-id="7b2a0-112">The thread has been terminated.</span></span>|  
|`USER_WAIT_SLEEP_JOIN`|<span data-ttu-id="7b2a0-113">线程正在等待另一个线程完成任务。</span><span class="sxs-lookup"><span data-stu-id="7b2a0-113">The thread is waiting for another thread to complete a task.</span></span>|  
|`USER_SUSPENDED`|<span data-ttu-id="7b2a0-114">线程已挂起。</span><span class="sxs-lookup"><span data-stu-id="7b2a0-114">The thread has been suspended.</span></span>|  
|`USER_UNSAFE_POINT`|<span data-ttu-id="7b2a0-115">线程在不安全的点上。</span><span class="sxs-lookup"><span data-stu-id="7b2a0-115">The thread is at an unsafe point.</span></span> <span data-ttu-id="7b2a0-116">也就是说，线程在执行时可能会阻止垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="7b2a0-116">That is, the thread is at a point in execution where it may block garbage collection.</span></span><br /><br /> <span data-ttu-id="7b2a0-117">调试事件可以从不安全的点进行调度，但在不安全点挂起线程很有可能会导致死锁，直到线程恢复。</span><span class="sxs-lookup"><span data-stu-id="7b2a0-117">Debug events may be dispatched from unsafe points, but suspending a thread at an unsafe point  will very likely cause a deadlock until the thread is resumed.</span></span> <span data-ttu-id="7b2a0-118">安全点和不安全点由实时 (JIT) 和垃圾回收实现确定。</span><span class="sxs-lookup"><span data-stu-id="7b2a0-118">The safe and unsafe points are determined by the just-in-time (JIT) and garbage collection implementation.</span></span>|  
|`USER_THREADPOOL`|<span data-ttu-id="7b2a0-119">线程来自线程池。</span><span class="sxs-lookup"><span data-stu-id="7b2a0-119">The thread is from the thread pool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b2a0-120">注解</span><span class="sxs-lookup"><span data-stu-id="7b2a0-120">Remarks</span></span>  

 <span data-ttu-id="7b2a0-121">线程的用户状态是调试器在检查线程时具有的状态。</span><span class="sxs-lookup"><span data-stu-id="7b2a0-121">The user state of a thread is the state that the thread has when the debugger examines it.</span></span> <span data-ttu-id="7b2a0-122">一个线程可能会组合用户状态。</span><span class="sxs-lookup"><span data-stu-id="7b2a0-122">A thread may have a combination of user states.</span></span>  
  
 <span data-ttu-id="7b2a0-123">使用 [ICorDebugThread：： GetUserState](icordebugthread-getuserstate-method.md) 方法检索线程的用户状态。</span><span class="sxs-lookup"><span data-stu-id="7b2a0-123">Use the [ICorDebugThread::GetUserState](icordebugthread-getuserstate-method.md) method to retrieve a thread's user state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b2a0-124">要求</span><span class="sxs-lookup"><span data-stu-id="7b2a0-124">Requirements</span></span>  

 <span data-ttu-id="7b2a0-125">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7b2a0-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b2a0-126">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b2a0-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b2a0-127">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b2a0-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b2a0-128">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b2a0-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b2a0-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7b2a0-129">See also</span></span>

- [<span data-ttu-id="7b2a0-130">调试枚举</span><span class="sxs-lookup"><span data-stu-id="7b2a0-130">Debugging Enumerations</span></span>](debugging-enumerations.md)
