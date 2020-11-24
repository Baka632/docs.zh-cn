---
title: ICorProfilerCallback::RemotingServerReceivingMessage 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerReceivingMessage
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage
helpviewer_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage method [.NET Framework profiling]
- RemotingServerReceivingMessage method [.NET Framework profiling]
ms.assetid: 5604d21f-e6b7-490e-b469-42122a7568e1
topic_type:
- apiref
ms.openlocfilehash: 0fc84a15d3250d5103c1dbc6486960f0ea780a2b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676811"
---
# <a name="icorprofilercallbackremotingserverreceivingmessage-method"></a><span data-ttu-id="b4438-102">ICorProfilerCallback::RemotingServerReceivingMessage 方法</span><span class="sxs-lookup"><span data-stu-id="b4438-102">ICorProfilerCallback::RemotingServerReceivingMessage Method</span></span>

<span data-ttu-id="b4438-103">通知探查器进程已收到远程方法调用或激活请求。</span><span class="sxs-lookup"><span data-stu-id="b4438-103">Notifies the profiler that the process has received a remote method invocation or activation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4438-104">语法</span><span class="sxs-lookup"><span data-stu-id="b4438-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4438-105">参数</span><span class="sxs-lookup"><span data-stu-id="b4438-105">Parameters</span></span>  

 `pCookie`  
 <span data-ttu-id="b4438-106">中与以下条件下的 [ICorProfilerCallback：： RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md) 中提供的值对应的值：</span><span class="sxs-lookup"><span data-stu-id="b4438-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="b4438-107">远程处理 GUID cookie 处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="b4438-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="b4438-108">通道成功传输消息。</span><span class="sxs-lookup"><span data-stu-id="b4438-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="b4438-109">GUID cookie 在客户端进程中处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="b4438-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="b4438-110">这样就可以轻松地配对远程调用和逻辑调用堆栈的创建。</span><span class="sxs-lookup"><span data-stu-id="b4438-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="b4438-111">中 `true` 如果调用是异步的，则该值为; 否则为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="b4438-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4438-112">注解</span><span class="sxs-lookup"><span data-stu-id="b4438-112">Remarks</span></span>  

 <span data-ttu-id="b4438-113">如果消息请求是异步的，则该请求可由任意线程提供服务。</span><span class="sxs-lookup"><span data-stu-id="b4438-113">If the message request is asynchronous, the request can be serviced by any arbitrary thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4438-114">要求</span><span class="sxs-lookup"><span data-stu-id="b4438-114">Requirements</span></span>  

 <span data-ttu-id="b4438-115">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b4438-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4438-116">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b4438-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b4438-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4438-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4438-118">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4438-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4438-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b4438-119">See also</span></span>

- [<span data-ttu-id="b4438-120">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="b4438-120">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
