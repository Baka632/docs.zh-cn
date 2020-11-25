---
title: ICLRDebugManager 接口
ms.date: 03/30/2017
api_name:
- ICLRDebugManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager
helpviewer_keywords:
- ICLRDebugManager interface [.NET Framework hosting]
ms.assetid: e835062c-c7d6-4945-8a44-2de7ebf3928e
topic_type:
- apiref
ms.openlocfilehash: 3836bd349423670a19a19dda67eba75419507a29
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724281"
---
# <a name="iclrdebugmanager-interface"></a><span data-ttu-id="279d9-102">ICLRDebugManager 接口</span><span class="sxs-lookup"><span data-stu-id="279d9-102">ICLRDebugManager Interface</span></span>

<span data-ttu-id="279d9-103">提供允许主机将一组任务与标识符和友好名称关联的方法。</span><span class="sxs-lookup"><span data-stu-id="279d9-103">Provides methods that allow a host to associate a set of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="279d9-104">方法</span><span class="sxs-lookup"><span data-stu-id="279d9-104">Methods</span></span>  
  
|<span data-ttu-id="279d9-105">方法</span><span class="sxs-lookup"><span data-stu-id="279d9-105">Method</span></span>|<span data-ttu-id="279d9-106">说明</span><span class="sxs-lookup"><span data-stu-id="279d9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="279d9-107">BeginConnection 方法</span><span class="sxs-lookup"><span data-stu-id="279d9-107">BeginConnection Method</span></span>](iclrdebugmanager-beginconnection-method.md)|<span data-ttu-id="279d9-108">在宿主和调试器之间建立新的连接，以将任务与标识符和友好名称关联起来。</span><span class="sxs-lookup"><span data-stu-id="279d9-108">Establishes a new connection between the host and the debugger to associate tasks with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="279d9-109">EndConnection 方法</span><span class="sxs-lookup"><span data-stu-id="279d9-109">EndConnection Method</span></span>](iclrdebugmanager-endconnection-method.md)|<span data-ttu-id="279d9-110">删除任务列表与标识符和友好名称之间的关联。</span><span class="sxs-lookup"><span data-stu-id="279d9-110">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="279d9-111">GetDacl 方法</span><span class="sxs-lookup"><span data-stu-id="279d9-111">GetDacl Method</span></span>](iclrdebugmanager-getdacl-method.md)|<span data-ttu-id="279d9-112">未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="279d9-112">This method is not implemented.</span></span>|  
|[<span data-ttu-id="279d9-113">IsDebuggerAttached 方法</span><span class="sxs-lookup"><span data-stu-id="279d9-113">IsDebuggerAttached Method</span></span>](iclrdebugmanager-isdebuggerattached-method.md)|<span data-ttu-id="279d9-114">获取一个值，它指示调试器是否已附加到进程。</span><span class="sxs-lookup"><span data-stu-id="279d9-114">Gets a value that indicates whether a debugger is attached to the process.</span></span>|  
|[<span data-ttu-id="279d9-115">SetConnectionTasks 方法</span><span class="sxs-lookup"><span data-stu-id="279d9-115">SetConnectionTasks Method</span></span>](iclrdebugmanager-setconnectiontasks-method.md)|<span data-ttu-id="279d9-116">将 [ICLRTask](iclrtask-interface.md) 实例列表与标识符和友好名称关联。</span><span class="sxs-lookup"><span data-stu-id="279d9-116">Associates a list of [ICLRTask](iclrtask-interface.md) instances with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="279d9-117">SetDacl 方法</span><span class="sxs-lookup"><span data-stu-id="279d9-117">SetDacl Method</span></span>](iclrdebugmanager-setdacl-method.md)|<span data-ttu-id="279d9-118">未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="279d9-118">This method is not implemented.</span></span>|  
|[<span data-ttu-id="279d9-119">SetSymbolReadingPolicy 方法</span><span class="sxs-lookup"><span data-stu-id="279d9-119">SetSymbolReadingPolicy Method</span></span>](iclrdebugmanager-setsymbolreadingpolicy-method.md)|<span data-ttu-id="279d9-120">设置用于读取程序数据库 (PDB) 文件的策略。</span><span class="sxs-lookup"><span data-stu-id="279d9-120">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="279d9-121">策略确定有关行号和文件的信息是否包含在调用堆栈中。</span><span class="sxs-lookup"><span data-stu-id="279d9-121">The policy determines whether information about line numbers and files is included in call stacks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="279d9-122">注解</span><span class="sxs-lookup"><span data-stu-id="279d9-122">Remarks</span></span>  

 <span data-ttu-id="279d9-123">在调试方案中，主机可能需要根据任务自己的编程逻辑对任务进行分组。</span><span class="sxs-lookup"><span data-stu-id="279d9-123">In debugging scenarios, a host might want to group tasks according to its own programming logic.</span></span> <span data-ttu-id="279d9-124">例如，分组允许开发人员仅查看开发人员的 Api 所需的任务，而不是查看在进程中运行的每个任务。</span><span class="sxs-lookup"><span data-stu-id="279d9-124">For example, a grouping would allow a developer to see only the tasks required by the developer's APIs, instead of seeing every task running in the process.</span></span> <span data-ttu-id="279d9-125">`ICLRDebugManager` 允许宿主实现这种分组。</span><span class="sxs-lookup"><span data-stu-id="279d9-125">`ICLRDebugManager` allows the host to implement this kind of grouping.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="279d9-126">三个 `ICLRDebugManager` 方法（和）相互 `BeginConnection` `SetConnectionTasks` `EndConnection` 依赖。</span><span class="sxs-lookup"><span data-stu-id="279d9-126">Three `ICLRDebugManager` methods, `BeginConnection`, `SetConnectionTasks` and `EndConnection`, are dependent upon each other.</span></span> <span data-ttu-id="279d9-127">必须按给定顺序调用它们才能按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="279d9-127">They must be called in the given order to work as expected.</span></span>  
  
 <span data-ttu-id="279d9-128">分组以及宿主分配给分组的标识符和友好名称对于公共语言运行时 (CLR) 没有任何意义。</span><span class="sxs-lookup"><span data-stu-id="279d9-128">The grouping, and the identifiers and friendly names that the host assigns to the grouping, have no meaning for the common language runtime (CLR).</span></span> <span data-ttu-id="279d9-129">CLR 只会将信息传递到调试器。</span><span class="sxs-lookup"><span data-stu-id="279d9-129">The CLR merely passes the information along to the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="279d9-130">要求</span><span class="sxs-lookup"><span data-stu-id="279d9-130">Requirements</span></span>  

 <span data-ttu-id="279d9-131">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="279d9-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="279d9-132">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="279d9-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="279d9-133">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="279d9-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="279d9-134">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="279d9-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="279d9-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="279d9-135">See also</span></span>

- [<span data-ttu-id="279d9-136">承载接口</span><span class="sxs-lookup"><span data-stu-id="279d9-136">Hosting Interfaces</span></span>](hosting-interfaces.md)
