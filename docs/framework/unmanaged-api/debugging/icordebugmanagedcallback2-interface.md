---
title: ICorDebugManagedCallback2 接口
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2
helpviewer_keywords:
- ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: cf7b7cfa-1c4b-4d8c-be70-4f9ed15a788b
topic_type:
- apiref
ms.openlocfilehash: 937a2fb322eb63461d90e215635e1b10ab6afd09
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689779"
---
# <a name="icordebugmanagedcallback2-interface"></a><span data-ttu-id="ee19d-102">ICorDebugManagedCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="ee19d-102">ICorDebugManagedCallback2 Interface</span></span>

<span data-ttu-id="ee19d-103">提供支持调试器异常处理和托管调试助手 (MDA) 的方法。</span><span class="sxs-lookup"><span data-stu-id="ee19d-103">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="ee19d-104">`ICorDebugManagedCallback2` 是 [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) 接口的逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="ee19d-104">`ICorDebugManagedCallback2` is a logical extension of the [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ee19d-105">方法</span><span class="sxs-lookup"><span data-stu-id="ee19d-105">Methods</span></span>  
  
|<span data-ttu-id="ee19d-106">方法</span><span class="sxs-lookup"><span data-stu-id="ee19d-106">Method</span></span>|<span data-ttu-id="ee19d-107">说明</span><span class="sxs-lookup"><span data-stu-id="ee19d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ee19d-108">ChangeConnection 方法</span><span class="sxs-lookup"><span data-stu-id="ee19d-108">ChangeConnection Method</span></span>](icordebugmanagedcallback2-changeconnection-method.md)|<span data-ttu-id="ee19d-109">通知调试器与指定连接关联的任务集已更改。</span><span class="sxs-lookup"><span data-stu-id="ee19d-109">Notifies the debugger that the set of tasks associated with the specified connection has changed.</span></span>|  
|[<span data-ttu-id="ee19d-110">CreateConnection 方法</span><span class="sxs-lookup"><span data-stu-id="ee19d-110">CreateConnection Method</span></span>](icordebugmanagedcallback2-createconnection-method.md)|<span data-ttu-id="ee19d-111">通知调试器已创建新连接。</span><span class="sxs-lookup"><span data-stu-id="ee19d-111">Notifies the debugger that a new connection has been created.</span></span>|  
|[<span data-ttu-id="ee19d-112">DestroyConnection 方法</span><span class="sxs-lookup"><span data-stu-id="ee19d-112">DestroyConnection Method</span></span>](icordebugmanagedcallback2-destroyconnection-method.md)|<span data-ttu-id="ee19d-113">通知调试器指定的连接已终止。</span><span class="sxs-lookup"><span data-stu-id="ee19d-113">Notifies the debugger that the specified connection has been terminated.</span></span>|  
|[<span data-ttu-id="ee19d-114">Exception 方法</span><span class="sxs-lookup"><span data-stu-id="ee19d-114">Exception Method</span></span>](icordebugmanagedcallback2-exception-method.md)|<span data-ttu-id="ee19d-115">通知调试器已开始搜索异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="ee19d-115">Notifies the debugger that a search for an exception handler has started.</span></span>|  
|[<span data-ttu-id="ee19d-116">ExceptionUnwind 方法</span><span class="sxs-lookup"><span data-stu-id="ee19d-116">ExceptionUnwind Method</span></span>](icordebugmanagedcallback2-exceptionunwind-method.md)|<span data-ttu-id="ee19d-117">在异常展开过程中提供状态通知。</span><span class="sxs-lookup"><span data-stu-id="ee19d-117">Provides a status notification during the exception unwinding process.</span></span>|  
|[<span data-ttu-id="ee19d-118">FunctionRemapComplete 方法</span><span class="sxs-lookup"><span data-stu-id="ee19d-118">FunctionRemapComplete Method</span></span>](icordebugmanagedcallback2-functionremapcomplete-method.md)|<span data-ttu-id="ee19d-119">通知调试器，代码执行已切换到已编辑函数的新版本。</span><span class="sxs-lookup"><span data-stu-id="ee19d-119">Notifies the debugger that code execution has switched to a new version of an edited function.</span></span>|  
|[<span data-ttu-id="ee19d-120">FunctionRemapOpportunity 方法</span><span class="sxs-lookup"><span data-stu-id="ee19d-120">FunctionRemapOpportunity Method</span></span>](icordebugmanagedcallback2-functionremapopportunity-method.md)|<span data-ttu-id="ee19d-121">通知调试程序代码执行已到达已编辑函数的较早版本中的序列点。</span><span class="sxs-lookup"><span data-stu-id="ee19d-121">Notifies the debugger that code execution has reached a sequence point in an older version of an edited function.</span></span>|  
|[<span data-ttu-id="ee19d-122">MDANotification 方法</span><span class="sxs-lookup"><span data-stu-id="ee19d-122">MDANotification Method</span></span>](icordebugmanagedcallback2-mdanotification-method.md)|<span data-ttu-id="ee19d-123">提供通知，指出代码执行 (MDA) 消息中发生了托管调试助手。</span><span class="sxs-lookup"><span data-stu-id="ee19d-123">Provides notification that code execution has encountered a managed debugging assistant (MDA) message.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee19d-124">注解</span><span class="sxs-lookup"><span data-stu-id="ee19d-124">Remarks</span></span>  

 <span data-ttu-id="ee19d-125">`ICorDebugManagedCallback2`接口扩展 `ICorDebugManagedCallback` 接口以处理 .NET Framework 版本2.0 中引入的新调试事件。</span><span class="sxs-lookup"><span data-stu-id="ee19d-125">The `ICorDebugManagedCallback2` interface extends the `ICorDebugManagedCallback` interface to handle new debug events introduced in the .NET Framework version 2.0.</span></span>  
  
 <span data-ttu-id="ee19d-126">调试程序在 `ICorDebugManagedCallback2` 调试 .NET Framework 2.0 应用程序时必须实现。</span><span class="sxs-lookup"><span data-stu-id="ee19d-126">A debugger must implement `ICorDebugManagedCallback2` if it is debugging .NET Framework 2.0 applications.</span></span> <span data-ttu-id="ee19d-127">或的实例 `ICorDebugManagedCallback` `ICorDebugManagedCallback2` 作为回调对象传递给 [ICorDebug：： SetManagedHandler](icordebug-setmanagedhandler-method.md)。</span><span class="sxs-lookup"><span data-stu-id="ee19d-127">An instance of `ICorDebugManagedCallback` or `ICorDebugManagedCallback2` is passed as the callback object to [ICorDebug::SetManagedHandler](icordebug-setmanagedhandler-method.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ee19d-128">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="ee19d-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee19d-129">要求</span><span class="sxs-lookup"><span data-stu-id="ee19d-129">Requirements</span></span>  

 <span data-ttu-id="ee19d-130">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ee19d-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee19d-131">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ee19d-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ee19d-132">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee19d-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee19d-133">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee19d-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee19d-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee19d-134">See also</span></span>

- [<span data-ttu-id="ee19d-135">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="ee19d-135">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="ee19d-136">调试接口</span><span class="sxs-lookup"><span data-stu-id="ee19d-136">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="ee19d-137">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="ee19d-137">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
