---
title: ICorDebugThread2 接口
ms.date: 03/30/2017
api_name:
- ICorDebugThread2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2
helpviewer_keywords:
- ICorDebugThread2 interface [.NET Framework debugging]
ms.assetid: 678f89f9-cce7-46d1-af87-5e989abaa93c
topic_type:
- apiref
ms.openlocfilehash: fd4ad536d7d3df2b8f91f206459122cf083c8b9c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95691131"
---
# <a name="icordebugthread2-interface"></a><span data-ttu-id="b2a93-102">ICorDebugThread2 接口</span><span class="sxs-lookup"><span data-stu-id="b2a93-102">ICorDebugThread2 Interface</span></span>

<span data-ttu-id="b2a93-103">用作 ICorDebugThread 接口的逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="b2a93-103">Serves as a logical extension to the ICorDebugThread interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b2a93-104">方法</span><span class="sxs-lookup"><span data-stu-id="b2a93-104">Methods</span></span>  
  
|<span data-ttu-id="b2a93-105">方法</span><span class="sxs-lookup"><span data-stu-id="b2a93-105">Method</span></span>|<span data-ttu-id="b2a93-106">说明</span><span class="sxs-lookup"><span data-stu-id="b2a93-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b2a93-107">GetActiveFunctions 方法</span><span class="sxs-lookup"><span data-stu-id="b2a93-107">GetActiveFunctions Method</span></span>](icordebugthread2-getactivefunctions-method.md)|<span data-ttu-id="b2a93-108">获取 COR_ACTIVE_FUNCTION 实例的数组，这些实例包含有关线程帧中的活动函数的数据。</span><span class="sxs-lookup"><span data-stu-id="b2a93-108">Gets an array of COR_ACTIVE_FUNCTION instances that contain data about the active functions in a thread's frames.</span></span>|  
|[<span data-ttu-id="b2a93-109">GetConnectionID 方法</span><span class="sxs-lookup"><span data-stu-id="b2a93-109">GetConnectionID Method</span></span>](icordebugthread2-getconnectionid-method.md)|<span data-ttu-id="b2a93-110">获取此的连接标识符 `ICorDebugThread2` 。</span><span class="sxs-lookup"><span data-stu-id="b2a93-110">Gets a connection identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="b2a93-111">GetTaskID 方法</span><span class="sxs-lookup"><span data-stu-id="b2a93-111">GetTaskID Method</span></span>](icordebugthread2-gettaskid-method.md)|<span data-ttu-id="b2a93-112">获取此的任务标识符 `ICorDebugThread2` 。</span><span class="sxs-lookup"><span data-stu-id="b2a93-112">Gets a task identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="b2a93-113">GetVolatileOSThreadID 方法</span><span class="sxs-lookup"><span data-stu-id="b2a93-113">GetVolatileOSThreadID Method</span></span>](icordebugthread2-getvolatileosthreadid-method.md)|<span data-ttu-id="b2a93-114">获取此的操作系统线程标识符 `ICorDebugThread2` 。</span><span class="sxs-lookup"><span data-stu-id="b2a93-114">Gets the operating system thread identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="b2a93-115">InterceptCurrentException 方法</span><span class="sxs-lookup"><span data-stu-id="b2a93-115">InterceptCurrentException Method</span></span>](icordebugthread2-interceptcurrentexception-method.md)|<span data-ttu-id="b2a93-116">允许调试器截获线程上的当前异常。</span><span class="sxs-lookup"><span data-stu-id="b2a93-116">Allows a debugger to intercept the current exception on a thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2a93-117">注解</span><span class="sxs-lookup"><span data-stu-id="b2a93-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b2a93-118">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="b2a93-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2a93-119">要求</span><span class="sxs-lookup"><span data-stu-id="b2a93-119">Requirements</span></span>  

 <span data-ttu-id="b2a93-120">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b2a93-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2a93-121">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2a93-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2a93-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2a93-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2a93-123">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2a93-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2a93-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b2a93-124">See also</span></span>

- [<span data-ttu-id="b2a93-125">调试接口</span><span class="sxs-lookup"><span data-stu-id="b2a93-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
