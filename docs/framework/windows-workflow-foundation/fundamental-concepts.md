---
title: Windows 工作流基础概念
description: 本文介绍了某些开发人员可能不熟悉的 .NET Framework 4.6.1 中的工作流开发中的一些概念。
ms.date: 03/30/2017
ms.assetid: 0e930e80-5060-45d2-8a7a-95c0690105d4
ms.openlocfilehash: a7683791c7aed54beed9256ab08010dfeebe9936
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265292"
---
# <a name="fundamental-windows-workflow-concepts"></a><span data-ttu-id="1d568-103">Windows 工作流基础概念</span><span class="sxs-lookup"><span data-stu-id="1d568-103">Fundamental Windows Workflow Concepts</span></span>

<span data-ttu-id="1d568-104">[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]的工作流开发中会运用一些开发人员可能还不熟悉的概念。</span><span class="sxs-lookup"><span data-stu-id="1d568-104">Workflow development in the [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] uses concepts that may be new to some developers.</span></span> <span data-ttu-id="1d568-105">本主题介绍其中的一些概念以及如何实现这些概念。</span><span class="sxs-lookup"><span data-stu-id="1d568-105">This topic describes some of the concepts and how they are implemented.</span></span>  
  
## <a name="workflows-and-activities"></a><span data-ttu-id="1d568-106">工作流和活动</span><span class="sxs-lookup"><span data-stu-id="1d568-106">Workflows and Activities</span></span>  

 <span data-ttu-id="1d568-107">工作流是构成进程模型的操作的结构化集合。</span><span class="sxs-lookup"><span data-stu-id="1d568-107">A workflow is a structured collection of actions that models a process.</span></span> <span data-ttu-id="1d568-108">工作流中的每个操作都建模为一个活动。</span><span class="sxs-lookup"><span data-stu-id="1d568-108">Each action in the workflow is modeled as an activity.</span></span> <span data-ttu-id="1d568-109">宿主通过使用 <xref:System.Activities.WorkflowInvoker> 将工作流作为方法调用，使用 <xref:System.Activities.WorkflowApplication> 对单个工作流实例的执行进行显式控制，并使用 <xref:System.ServiceModel.WorkflowServiceHost> 在多实例方案中进行基于消息的交互，从而实现与工作流的交互。</span><span class="sxs-lookup"><span data-stu-id="1d568-109">A host interacts with a workflow by using <xref:System.Activities.WorkflowInvoker> for invoking a workflow as if it were a method,  <xref:System.Activities.WorkflowApplication> for explicit control over the execution of a single workflow instance, and <xref:System.ServiceModel.WorkflowServiceHost> for message-based interactions in multi-instance scenarios.</span></span> <span data-ttu-id="1d568-110">由于工作流的步骤定义为活动的层次结构，因此层次结构中最顶层的活动可以认为是定义工作流本身。</span><span class="sxs-lookup"><span data-stu-id="1d568-110">Because steps of the workflow are defined as a hierarchy of activities, the topmost activity in the hierarchy can be said to define the workflow itself.</span></span> <span data-ttu-id="1d568-111">此层次结构模型替代以前版本中的显式 `SequentialWorkflow` 和 `StateMachineWorkflow` 类。</span><span class="sxs-lookup"><span data-stu-id="1d568-111">This hierarchy model takes the place of the explicit `SequentialWorkflow` and `StateMachineWorkflow` classes from previous versions.</span></span> <span data-ttu-id="1d568-112">活动自身可作为其他活动的集合（使用 <xref:System.Activities.Activity> 类作为基础，通常使用 XAML 定义）开发；或者使用 <xref:System.Activities.CodeActivity> 类或 <xref:System.Activities.NativeActivity> 类进行自定义创建，前者可以使用运行时进行数据访问，而后者则向活动作者公开工作流运行时范围。</span><span class="sxs-lookup"><span data-stu-id="1d568-112">Activities themselves are developed as collections of other activities (using the <xref:System.Activities.Activity> class as a base, usually defined by using XAML) or are custom created by using the <xref:System.Activities.CodeActivity> class, which can use the runtime for data access, or by using the <xref:System.Activities.NativeActivity> class, which exposes the breadth of the workflow runtime to the activity author.</span></span> <span data-ttu-id="1d568-113">使用 <xref:System.Activities.CodeActivity> 和 <xref:System.Activities.NativeActivity> 类开发的活动是使用符合 CLR 的语言（如 C#）创建的。</span><span class="sxs-lookup"><span data-stu-id="1d568-113">Activities developed by using <xref:System.Activities.CodeActivity> and <xref:System.Activities.NativeActivity> are created by using CLR-compliant languages such as C#.</span></span>  
  
## <a name="activity-data-model"></a><span data-ttu-id="1d568-114">活动数据模型</span><span class="sxs-lookup"><span data-stu-id="1d568-114">Activity Data Model</span></span>  

 <span data-ttu-id="1d568-115">活动使用下表中所示的类型存储和共享数据。</span><span class="sxs-lookup"><span data-stu-id="1d568-115">Activities store and share data by using the types shown in the following table.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1d568-116">变量</span><span class="sxs-lookup"><span data-stu-id="1d568-116">Variable</span></span>|<span data-ttu-id="1d568-117">存储活动中的数据。</span><span class="sxs-lookup"><span data-stu-id="1d568-117">Stores data in an activity.</span></span>|  
|<span data-ttu-id="1d568-118">参数</span><span class="sxs-lookup"><span data-stu-id="1d568-118">Argument</span></span>|<span data-ttu-id="1d568-119">在活动中移入和移出数据。</span><span class="sxs-lookup"><span data-stu-id="1d568-119">Moves data into and out of an activity.</span></span>|  
|<span data-ttu-id="1d568-120">Expression</span><span class="sxs-lookup"><span data-stu-id="1d568-120">Expression</span></span>|<span data-ttu-id="1d568-121">带有在参数绑定中使用的提升的返回值的活动。</span><span class="sxs-lookup"><span data-stu-id="1d568-121">An activity with an elevated return value used in argument bindings.</span></span>|  
  
## <a name="workflow-runtime"></a><span data-ttu-id="1d568-122">工作流运行时</span><span class="sxs-lookup"><span data-stu-id="1d568-122">Workflow Runtime</span></span>  

 <span data-ttu-id="1d568-123">工作流运行时是工作流在其中执行的环境。 </span><span class="sxs-lookup"><span data-stu-id="1d568-123">The workflow runtime is the environment in which workflows execute.</span></span> <span data-ttu-id="1d568-124"><xref:System.Activities.WorkflowInvoker> 是执行工作流的最简单方法。</span><span class="sxs-lookup"><span data-stu-id="1d568-124"><xref:System.Activities.WorkflowInvoker> is the simplest way to execute a workflow.</span></span> <span data-ttu-id="1d568-125">宿主为以下操作使用 <xref:System.Activities.WorkflowInvoker>：</span><span class="sxs-lookup"><span data-stu-id="1d568-125">The host uses <xref:System.Activities.WorkflowInvoker> for the following:</span></span>  
  
- <span data-ttu-id="1d568-126">以同步方式调用工作流。</span><span class="sxs-lookup"><span data-stu-id="1d568-126">To synchronously invoke a workflow.</span></span>  
  
- <span data-ttu-id="1d568-127">向工作流提供输入或检索工作流的输出。</span><span class="sxs-lookup"><span data-stu-id="1d568-127">To provide input to, or retrieve output from a workflow.</span></span>  
  
- <span data-ttu-id="1d568-128">添加供活动使用的扩展。</span><span class="sxs-lookup"><span data-stu-id="1d568-128">To add extensions to be used by activities.</span></span>  
  
 <span data-ttu-id="1d568-129"><xref:System.Activities.ActivityInstance> 是线程安全的代理，宿主可以使用该代理与运行时进行交互。</span><span class="sxs-lookup"><span data-stu-id="1d568-129"><xref:System.Activities.ActivityInstance> is the thread-safe proxy that hosts can use to interact with the runtime.</span></span> <span data-ttu-id="1d568-130">宿主为以下操作使用 <xref:System.Activities.ActivityInstance>：</span><span class="sxs-lookup"><span data-stu-id="1d568-130">The host uses <xref:System.Activities.ActivityInstance> for the following:</span></span>  
  
- <span data-ttu-id="1d568-131">通过创建实例或从实例存储区中加载实例的方法来获取实例。</span><span class="sxs-lookup"><span data-stu-id="1d568-131">To acquire an instance by creating it or loading it from an instance store.</span></span>  
  
- <span data-ttu-id="1d568-132">接收实例生命周期事件通知。</span><span class="sxs-lookup"><span data-stu-id="1d568-132">To be notified of instance life-cycle events.</span></span>  
  
- <span data-ttu-id="1d568-133">控制工作流执行。</span><span class="sxs-lookup"><span data-stu-id="1d568-133">To control workflow execution.</span></span>  
  
- <span data-ttu-id="1d568-134">向工作流提供输入或检索工作流的输出。</span><span class="sxs-lookup"><span data-stu-id="1d568-134">To provide input to, or retrieve output from a workflow.</span></span>  
  
- <span data-ttu-id="1d568-135">向工作流发出继续信号并将值传递到工作流中。</span><span class="sxs-lookup"><span data-stu-id="1d568-135">To signal a workflow continuation and pass values into the workflow.</span></span>  
  
- <span data-ttu-id="1d568-136">保存工作流数据。</span><span class="sxs-lookup"><span data-stu-id="1d568-136">To persist workflow data.</span></span>  
  
- <span data-ttu-id="1d568-137">添加供活动使用的扩展。</span><span class="sxs-lookup"><span data-stu-id="1d568-137">To add extensions to be used by activities.</span></span>  
  
 <span data-ttu-id="1d568-138">活动通过使用相应的 <xref:System.Activities.ActivityContext> 派生类（例如 <xref:System.Activities.NativeActivityContext> 或 <xref:System.Activities.CodeActivityContext>）获得访问工作流运行时环境的权限。</span><span class="sxs-lookup"><span data-stu-id="1d568-138">Activities gain access to the workflow runtime environment by using the appropriate <xref:System.Activities.ActivityContext> derived class, such as <xref:System.Activities.NativeActivityContext> or <xref:System.Activities.CodeActivityContext>.</span></span> <span data-ttu-id="1d568-139">这些元素使用此类来解析自变量和变量，以便安排子活动和实现多种其他用途。</span><span class="sxs-lookup"><span data-stu-id="1d568-139">They use this for resolving arguments and variables, for scheduling child activities, and for many other purposes.</span></span>  
  
## <a name="services"></a><span data-ttu-id="1d568-140">服务</span><span class="sxs-lookup"><span data-stu-id="1d568-140">Services</span></span>  

 <span data-ttu-id="1d568-141">工作流提供一种自然的方式，以便使用消息活动实现和访问松耦合服务。</span><span class="sxs-lookup"><span data-stu-id="1d568-141">Workflows provide a natural way to implement and access loosely-coupled services, using messaging activities.</span></span> <span data-ttu-id="1d568-142">消息传递活动基于 WCF 建立，是用于将数据传入和传出工作流的主要机制。</span><span class="sxs-lookup"><span data-stu-id="1d568-142">Messaging activities are built on WCF and are the primary mechanism used to get data into and out of a workflow.</span></span> <span data-ttu-id="1d568-143">您可将消息活动组合在一起，以便对您想要的任何类型的消息交换模式进行建模。</span><span class="sxs-lookup"><span data-stu-id="1d568-143">You can compose messaging activities together to model any kind of message exchange pattern you wish.</span></span> <span data-ttu-id="1d568-144">有关详细信息，请参阅 [消息传递活动](../wcf/feature-details/messaging-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="1d568-144">For more information, see [Messaging Activities](../wcf/feature-details/messaging-activities.md).</span></span> <span data-ttu-id="1d568-145">使用 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 类承载工作流服务。</span><span class="sxs-lookup"><span data-stu-id="1d568-145">Workflow services are hosted using the <xref:System.ServiceModel.Activities.WorkflowServiceHost> class.</span></span> <span data-ttu-id="1d568-146">有关详细信息，请参阅 [宿主工作流服务概述](../wcf/feature-details/hosting-workflow-services-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="1d568-146">For more information, see [Hosting Workflow Services Overview](../wcf/feature-details/hosting-workflow-services-overview.md).</span></span> <span data-ttu-id="1d568-147">有关工作流服务的详细信息，请参阅 [工作流服务](../wcf/feature-details/workflow-services.md)</span><span class="sxs-lookup"><span data-stu-id="1d568-147">For more information about workflow services see [Workflow Services](../wcf/feature-details/workflow-services.md)</span></span>  
  
## <a name="persistence-unloading-and-long-running-workflows"></a><span data-ttu-id="1d568-148">持久性、卸载和长时间运行的工作流</span><span class="sxs-lookup"><span data-stu-id="1d568-148">Persistence, Unloading, and Long-Running Workflows</span></span>  

 <span data-ttu-id="1d568-149">Windows 工作流通过提供以下功能，简化了创作长时间运行的反应式程序的过程：</span><span class="sxs-lookup"><span data-stu-id="1d568-149">Windows Workflow simplifies the authoring of long-running reactive programs by providing:</span></span>  
  
- <span data-ttu-id="1d568-150">访问外部输入的活动。</span><span class="sxs-lookup"><span data-stu-id="1d568-150">Activities that access external input.</span></span>  
  
- <span data-ttu-id="1d568-151">能够创建可由宿主侦听程序恢复的 <xref:System.Activities.Bookmark> 对象。</span><span class="sxs-lookup"><span data-stu-id="1d568-151">The ability to create <xref:System.Activities.Bookmark> objects that can be resumed by a host listener.</span></span>  
  
- <span data-ttu-id="1d568-152">能够保存工作流数据并卸载工作流，然后作为对特定工作流中恢复 <xref:System.Activities.Bookmark> 对象的响应，重新加载和重新激活工作流。</span><span class="sxs-lookup"><span data-stu-id="1d568-152">The ability to persist a workflow’s data and unload the workflow, and then reload and reactivate the workflow in response to the resumption of <xref:System.Activities.Bookmark> objects in a particular workflow.</span></span>  
  
 <span data-ttu-id="1d568-153">工作流会持续地执行活动，直到没有任何要执行的活动或者所有当前正在执行的活动均在等待输入为止。</span><span class="sxs-lookup"><span data-stu-id="1d568-153">A workflow continuously executes activities until there are no more activities to execute or until all currently executing activities are waiting for input.</span></span> <span data-ttu-id="1d568-154">在后一种情况下，工作流处于空闲状态。</span><span class="sxs-lookup"><span data-stu-id="1d568-154">In this latter state, the workflow is idle.</span></span> <span data-ttu-id="1d568-155">通常宿主会卸载进入空闲状态的工作流，并且在消息到达时重新加载这些工作流以便继续执行。</span><span class="sxs-lookup"><span data-stu-id="1d568-155">It is common for a host to unload workflows that have gone idle and to reload them to continue execution when a message arrives.</span></span> <span data-ttu-id="1d568-156"><xref:System.ServiceModel.Activities.WorkflowServiceHost> 为此功能提供功能，并提供了可扩展的卸载策略。</span><span class="sxs-lookup"><span data-stu-id="1d568-156"><xref:System.ServiceModel.Activities.WorkflowServiceHost> provides functionality for this feature and provides an extensible unload policy.</span></span> <span data-ttu-id="1d568-157">对于使用可变状态数据或无法持久化的其他数据的执行块，活动可以使用 <xref:System.Activities.NoPersistHandle> 向宿主指示不应对其进行持久化。</span><span class="sxs-lookup"><span data-stu-id="1d568-157">For blocks of execution that use volatile state data or other data that cannot be persisted, an activity can indicate to a host that it should not be persisted by using the <xref:System.Activities.NoPersistHandle>.</span></span> <span data-ttu-id="1d568-158">工作流还可以使用 <xref:System.Activities.Statements.Persist> 活动将其数据显式保存到持久性存储介质中。</span><span class="sxs-lookup"><span data-stu-id="1d568-158">A workflow can also explicitly persist its data to a durable storage medium by using the <xref:System.Activities.Statements.Persist> activity.</span></span>
