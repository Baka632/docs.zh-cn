---
title: Windows Workflow Foundation 中的新增功能
description: 了解 .NET Framework 4 中的 Windows Workflow Foundation 更改。 工作流更易于创建、执行和维护。
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Workflow Foundation [WF], what's new
- WF [WF], what's new
ms.assetid: 11f96014-001e-41a0-bcc2-d0684a52fa43
ms.openlocfilehash: d6a3cda7b9334ca4710ada5aa0848eb5be815b0a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293827"
---
# <a name="whats-new-in-windows-workflow-foundation"></a><span data-ttu-id="5a83b-104">Windows Workflow Foundation 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="5a83b-104">What's New in Windows Workflow Foundation</span></span>

<span data-ttu-id="5a83b-105">.NET Framework 4 中 (WF) Windows Workflow Foundation 会更改以前版本中的多个开发范例。</span><span class="sxs-lookup"><span data-stu-id="5a83b-105">Windows Workflow Foundation (WF) in .NET Framework 4 changes several development paradigms from previous versions.</span></span> <span data-ttu-id="5a83b-106">现在，工作流可以更方便地创建、执行、维护和实现许多新功能。</span><span class="sxs-lookup"><span data-stu-id="5a83b-106">Workflows are now easier to create, execute, and maintain, and implement a host of new functionality.</span></span> <span data-ttu-id="5a83b-107">有关迁移 .NET Framework 3.0 和 .NET Framework 3.5 工作流应用程序以使用最新版本的详细信息，请参阅 [迁移指南](migration-guidance.md)。</span><span class="sxs-lookup"><span data-stu-id="5a83b-107">For more information about migrating .NET Framework 3.0 and .NET Framework 3.5 workflow applications to use the latest version, see [Migration Guidance](migration-guidance.md).</span></span>

## <a name="workflow-activity-model"></a><span data-ttu-id="5a83b-108">工作流活动模型</span><span class="sxs-lookup"><span data-stu-id="5a83b-108">Workflow Activity Model</span></span>

 <span data-ttu-id="5a83b-109">现在，活动是创建工作流的基本单元，它取代了使用的 <xref:System.Workflow.Activities.SequentialWorkflowActivity> 或 <xref:System.Workflow.Activities.StateMachineWorkflowActivity> 类。</span><span class="sxs-lookup"><span data-stu-id="5a83b-109">The activity is now the base unit of creating a workflow, rather than using the <xref:System.Workflow.Activities.SequentialWorkflowActivity> or <xref:System.Workflow.Activities.StateMachineWorkflowActivity> classes.</span></span> <span data-ttu-id="5a83b-110"><xref:System.Activities.Activity> 类提供工作流行为的抽象基类。</span><span class="sxs-lookup"><span data-stu-id="5a83b-110">The <xref:System.Activities.Activity> class provides the base abstraction of workflow behavior.</span></span> <span data-ttu-id="5a83b-111">然后，活动作者可以实现基本自定义活动的 <xref:System.Activities.CodeActivity> 功能，或实现使用运行时范围的自定义活动功能的 <xref:System.Activities.NativeActivity>。</span><span class="sxs-lookup"><span data-stu-id="5a83b-111">Activity authors can then implement either <xref:System.Activities.CodeActivity> for basic custom activity functionality, or <xref:System.Activities.NativeActivity> for custom activity functionality that uses the breadth of the runtime.</span></span> <span data-ttu-id="5a83b-112"><xref:System.Activities.Activity> 是活动创作者用来以声明方式表示其他、、或对象的新行为的类 <xref:System.Activities.NativeActivity> <xref:System.Activities.CodeActivity> <xref:System.Activities.AsyncCodeActivity> <xref:System.Activities.DynamicActivity> ，无论它们是自定义开发的，还是包含在 [内置活动库](net-framework-4-5-built-in-activity-library.md)中。</span><span class="sxs-lookup"><span data-stu-id="5a83b-112"><xref:System.Activities.Activity> is a class used by activity authors to express new behaviors declaratively in terms of other <xref:System.Activities.NativeActivity>, <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, or <xref:System.Activities.DynamicActivity> objects, whether they are custom-developed or included in the [Built-In Activity Library](net-framework-4-5-built-in-activity-library.md).</span></span>

## <a name="rich-composite-activity-options"></a><span data-ttu-id="5a83b-113">丰富的复合活动选项</span><span class="sxs-lookup"><span data-stu-id="5a83b-113">Rich Composite Activity Options</span></span>

 <span data-ttu-id="5a83b-114"><xref:System.Activities.Statements.Flowchart> 是一个功能强大的新控制流活动，作者可将其用于对任意循环和条件分支进行建模。</span><span class="sxs-lookup"><span data-stu-id="5a83b-114"><xref:System.Activities.Statements.Flowchart> is a powerful new control flow activity that allows authors to model arbitrary loops and conditional branching.</span></span> <span data-ttu-id="5a83b-115"><xref:System.Activities.Statements.Flowchart> 提供了一个由事件驱动的编程模型，该模型以前只能通过 <xref:System.Workflow.Activities.StateMachineWorkflowActivity> 来实现。</span><span class="sxs-lookup"><span data-stu-id="5a83b-115"><xref:System.Activities.Statements.Flowchart> provides an event-driven programming model that was previously only able to be implemented with <xref:System.Workflow.Activities.StateMachineWorkflowActivity>.</span></span> <span data-ttu-id="5a83b-116">程序工作流得益于对传统流控制结构进行建模的新增流控制活动，例如 <xref:System.Activities.Statements.TryCatch> 和 <xref:System.Activities.Statements.Switch%601>。</span><span class="sxs-lookup"><span data-stu-id="5a83b-116">Procedural workflows benefit from new flow-control activities that model traditional flow-control structures, such as <xref:System.Activities.Statements.TryCatch> and <xref:System.Activities.Statements.Switch%601>.</span></span>

## <a name="expanded-built-in-activity-library"></a><span data-ttu-id="5a83b-117">扩展的内置活动库</span><span class="sxs-lookup"><span data-stu-id="5a83b-117">Expanded Built-In Activity Library</span></span>

 <span data-ttu-id="5a83b-118">该活动库的新增功能包括：</span><span class="sxs-lookup"><span data-stu-id="5a83b-118">New features of the activity library include:</span></span>

- <span data-ttu-id="5a83b-119">新增流控制活动，例如 <xref:System.Activities.Statements.DoWhile>、<xref:System.Activities.Statements.Pick>、<xref:System.Activities.Statements.TryCatch>、<xref:System.Activities.Statements.ForEach%601>、<xref:System.Activities.Statements.Switch%601> 和 <xref:System.Activities.Statements.ParallelForEach%601>。</span><span class="sxs-lookup"><span data-stu-id="5a83b-119">New flow control activities, such as, <xref:System.Activities.Statements.DoWhile>, <xref:System.Activities.Statements.Pick>, <xref:System.Activities.Statements.TryCatch>, <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.Switch%601>, and <xref:System.Activities.Statements.ParallelForEach%601>.</span></span>

- <span data-ttu-id="5a83b-120">用于操作成员数据的活动，例如 <xref:System.Activities.Statements.Assign> 和集合活动（如 <xref:System.Activities.Statements.AddToCollection%601>）。</span><span class="sxs-lookup"><span data-stu-id="5a83b-120">Activities for manipulating member data, such as <xref:System.Activities.Statements.Assign> and collection activities such as <xref:System.Activities.Statements.AddToCollection%601>.</span></span>

- <span data-ttu-id="5a83b-121">用于控制事务的活动，例如 <xref:System.Activities.Statements.TransactionScope> 和 <xref:System.Activities.Statements.Compensate>。</span><span class="sxs-lookup"><span data-stu-id="5a83b-121">Activities for controlling transactions, such as <xref:System.Activities.Statements.TransactionScope> and <xref:System.Activities.Statements.Compensate>.</span></span>

- <span data-ttu-id="5a83b-122">新增消息传递活动，例如 <xref:System.ServiceModel.Activities.SendContent> 和 <xref:System.ServiceModel.Activities.ReceiveReply>。</span><span class="sxs-lookup"><span data-stu-id="5a83b-122">New messaging activities such as <xref:System.ServiceModel.Activities.SendContent> and <xref:System.ServiceModel.Activities.ReceiveReply>.</span></span>

## <a name="explicit-activity-data-model"></a><span data-ttu-id="5a83b-123">显式活动数据模型</span><span class="sxs-lookup"><span data-stu-id="5a83b-123">Explicit Activity Data Model</span></span>

 <span data-ttu-id="5a83b-124">.NET Framework 4 包含用于存储或移动数据的新选项。</span><span class="sxs-lookup"><span data-stu-id="5a83b-124">.NET Framework 4 includes new options for storing or moving data.</span></span> <span data-ttu-id="5a83b-125">可以使用 <xref:System.Activities.Variable> 在活动中存储数据。</span><span class="sxs-lookup"><span data-stu-id="5a83b-125">Data can be stored in an activity using <xref:System.Activities.Variable>.</span></span> <span data-ttu-id="5a83b-126">当在活动中移入和移出数据时，将使用专用参数类型来确定数据的移动方向。</span><span class="sxs-lookup"><span data-stu-id="5a83b-126">When moving data in and out of an activity, specialized argument types are used to determine which direction data is moving.</span></span> <span data-ttu-id="5a83b-127">这些类型包括 <xref:System.Activities.InArgument>、<xref:System.Activities.InOutArgument> 和 <xref:System.Activities.OutArgument>。</span><span class="sxs-lookup"><span data-stu-id="5a83b-127">These types are <xref:System.Activities.InArgument>, <xref:System.Activities.InOutArgument>, and <xref:System.Activities.OutArgument>.</span></span> <span data-ttu-id="5a83b-128">有关详细信息，请参阅 [Windows Workflow Foundation 数据模型](data-model.md)。</span><span class="sxs-lookup"><span data-stu-id="5a83b-128">For more information, see [Windows Workflow Foundation Data Model](data-model.md).</span></span>

## <a name="enhanced-hosting-persistence-and-tracking-options"></a><span data-ttu-id="5a83b-129">增强的宿主、持久性和跟踪选项</span><span class="sxs-lookup"><span data-stu-id="5a83b-129">Enhanced Hosting, Persistence, and Tracking Options</span></span>

 <span data-ttu-id="5a83b-130">.NET Framework 4 包含持久性增强功能，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5a83b-130">.NET Framework 4 contains persistence enhancements such as the following:</span></span>

- <span data-ttu-id="5a83b-131">提供了更多用于运行工作流的选项，其中包括 <xref:System.ServiceModel.Activities.WorkflowServiceHost>、<xref:System.Activities.WorkflowApplication> 和 <xref:System.Activities.WorkflowInvoker>。</span><span class="sxs-lookup"><span data-stu-id="5a83b-131">There are more options for running workflows, including <xref:System.ServiceModel.Activities.WorkflowServiceHost>, <xref:System.Activities.WorkflowApplication>, and <xref:System.Activities.WorkflowInvoker>.</span></span>

- <span data-ttu-id="5a83b-132">可以使用 <xref:System.Activities.Statements.Persist> 活动显式保存工作流状态数据。</span><span class="sxs-lookup"><span data-stu-id="5a83b-132">Workflow state data can be explicitly persisted using the <xref:System.Activities.Statements.Persist> activity.</span></span>

- <span data-ttu-id="5a83b-133">主机可以保存 <xref:System.Activities.ActivityInstance>，而不必卸载它。</span><span class="sxs-lookup"><span data-stu-id="5a83b-133">A host can persist an <xref:System.Activities.ActivityInstance> without unloading it.</span></span>

- <span data-ttu-id="5a83b-134">当使用无法保存的数据时，工作流可以指定非保存区域，以便推迟保存，直到退出非保存区域为止。</span><span class="sxs-lookup"><span data-stu-id="5a83b-134">A workflow can specify no-persist zones while working with data that cannot be persisted, so that persistence is postponed until the no-persist zone exits.</span></span>

- <span data-ttu-id="5a83b-135">可以使用 <xref:System.Activities.Statements.TransactionScope> 使事务流入到工作流中。</span><span class="sxs-lookup"><span data-stu-id="5a83b-135">Transactions can be flowed into a workflow using <xref:System.Activities.Statements.TransactionScope>.</span></span>

- <span data-ttu-id="5a83b-136">使用 <xref:System.Activities.Tracking.TrackingParticipant> 可以更方便地完成跟踪。</span><span class="sxs-lookup"><span data-stu-id="5a83b-136">Tracking is more easily accomplished using <xref:System.Activities.Tracking.TrackingParticipant>.</span></span>

- <span data-ttu-id="5a83b-137">使用 <xref:System.Activities.Tracking.EtwTrackingParticipant> 可以提供对系统事件日志的跟踪。</span><span class="sxs-lookup"><span data-stu-id="5a83b-137">Tracking to the system event log is provided using <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>

- <span data-ttu-id="5a83b-138">现在可以使用 <xref:System.Activities.Bookmark> 对象管理对挂起的工作流的恢复。</span><span class="sxs-lookup"><span data-stu-id="5a83b-138">Resuming a pending workflow is now managed using a <xref:System.Activities.Bookmark> object.</span></span>

## <a name="easier-ability-to-extend-wf-designer-experience"></a><span data-ttu-id="5a83b-139">简化的 WF 设计器扩展体验功能</span><span class="sxs-lookup"><span data-stu-id="5a83b-139">Easier Ability to Extend WF Designer Experience</span></span>

 <span data-ttu-id="5a83b-140">新的 WF 设计器建立在 Windows Presentation Foundation (WPF) 上，并提供了一个更易于使用的模型，以便在 Visual Studio 外部重新承载 WF 设计器，还提供了更简单的创建自定义活动设计器的机制。</span><span class="sxs-lookup"><span data-stu-id="5a83b-140">The new WF Designer is built on Windows Presentation Foundation (WPF) and provides an easier model to use when rehosting the WF Designer outside of Visual Studio and also provides easier mechanisms for creating custom activity designers.</span></span> <span data-ttu-id="5a83b-141">有关详细信息，请参阅 [自定义工作流设计体验](customizing-the-workflow-design-experience.md)。</span><span class="sxs-lookup"><span data-stu-id="5a83b-141">For more information, see [Customizing the Workflow Design Experience](customizing-the-workflow-design-experience.md).</span></span>
