---
title: 企业采购过程
ms.date: 03/30/2017
ms.assetid: a5e57336-4290-41ea-936d-435593d97055
ms.openlocfilehash: aa2ca2577eb68204ffcb755ce1b16b9354348ee3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293463"
---
# <a name="corporate-purchase-process"></a><span data-ttu-id="b6887-102">企业采购过程</span><span class="sxs-lookup"><span data-stu-id="b6887-102">Corporate Purchase Process</span></span>

<span data-ttu-id="b6887-103">此示例演示如何使用自动最佳建议书选择来创建基于购买过程的非常基本的征求建议书 (RFP)。</span><span class="sxs-lookup"><span data-stu-id="b6887-103">This sample shows how to create a very basic Request for Proposals (RFP) based purchase process with automatic best proposal selection.</span></span> <span data-ttu-id="b6887-104">它将 <xref:System.Activities.Statements.Parallel>、<xref:System.Activities.Statements.ParallelForEach%601>、<xref:System.Activities.Statements.ForEach%601> 和一个自定义活动组合在一起来创建一个表示该过程的工作流。</span><span class="sxs-lookup"><span data-stu-id="b6887-104">It combines <xref:System.Activities.Statements.Parallel>, <xref:System.Activities.Statements.ParallelForEach%601>, and <xref:System.Activities.Statements.ForEach%601> and a custom activity to create a workflow that represents the process.</span></span>

 <span data-ttu-id="b6887-105">此示例包含一个 ASP.NET 客户端应用程序，该应用程序允许与原始请求者或特定供应商)  (不同的参与者进行交互。</span><span class="sxs-lookup"><span data-stu-id="b6887-105">This sample contains an ASP.NET client application that allows interacting with the process as different participants (as the original requester or a particular vendor).</span></span>

## <a name="requirements"></a><span data-ttu-id="b6887-106">要求</span><span class="sxs-lookup"><span data-stu-id="b6887-106">Requirements</span></span>

- <span data-ttu-id="b6887-107">Visual Studio 2012。</span><span class="sxs-lookup"><span data-stu-id="b6887-107">Visual Studio 2012.</span></span>

- [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]<span data-ttu-id="b6887-108">.</span><span class="sxs-lookup"><span data-stu-id="b6887-108">.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="b6887-109">演示</span><span class="sxs-lookup"><span data-stu-id="b6887-109">Demonstrates</span></span>

- <span data-ttu-id="b6887-110">自定义活动。</span><span class="sxs-lookup"><span data-stu-id="b6887-110">Custom activities.</span></span>

- <span data-ttu-id="b6887-111">活动的构成。</span><span class="sxs-lookup"><span data-stu-id="b6887-111">Composition of activities.</span></span>

- <span data-ttu-id="b6887-112">书签。</span><span class="sxs-lookup"><span data-stu-id="b6887-112">Bookmarks.</span></span>

- <span data-ttu-id="b6887-113">持久性。</span><span class="sxs-lookup"><span data-stu-id="b6887-113">Persistence.</span></span>

- <span data-ttu-id="b6887-114">程式化的持久性。</span><span class="sxs-lookup"><span data-stu-id="b6887-114">Schematized persistence.</span></span>

- <span data-ttu-id="b6887-115">追踪。</span><span class="sxs-lookup"><span data-stu-id="b6887-115">Tracing.</span></span>

- <span data-ttu-id="b6887-116">跟踪。</span><span class="sxs-lookup"><span data-stu-id="b6887-116">Tracking.</span></span>

- <span data-ttu-id="b6887-117">[!INCLUDE[wf1](../../../../includes/wf1-md.md)]在不同的客户端中承载 (ASP.NET Web 应用程序和 WinForms 应用程序) 。</span><span class="sxs-lookup"><span data-stu-id="b6887-117">Hosting [!INCLUDE[wf1](../../../../includes/wf1-md.md)] in different clients (ASP.NET Web applications and WinForms applications).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b6887-118">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="b6887-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b6887-119">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="b6887-119">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="b6887-120">如果此目录不存在，请参阅[Windows Communication Foundation (wcf) ，并 Windows Workflow Foundation (的 WF](https://www.microsoft.com/download/details.aspx?id=21459)) .NET Framework Windows Communication Foundation ([!INCLUDE[wf1](../../../../includes/wf1-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6887-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b6887-121">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="b6887-121">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Application\PurchaseProcess`  
  
## <a name="description-of-the-process"></a><span data-ttu-id="b6887-122">流程说明</span><span class="sxs-lookup"><span data-stu-id="b6887-122">Description of the Process</span></span>  

 <span data-ttu-id="b6887-123">此示例演示如何实现 Windows Workflow Foundation (WF) 程序，以便从供应商处为一般公司收集建议。</span><span class="sxs-lookup"><span data-stu-id="b6887-123">This sample shows an implementation of a Windows Workflow Foundation (WF) program to gather proposals from vendors for a generic company.</span></span>  
  
1. <span data-ttu-id="b6887-124">公司 X 的一名员工创建了一份征求建议书 (RFP)。</span><span class="sxs-lookup"><span data-stu-id="b6887-124">An employee of Company X creates a Request for Proposal (RFP).</span></span>  
  
    1. <span data-ttu-id="b6887-125">该员工键入 RFP 标题和说明。</span><span class="sxs-lookup"><span data-stu-id="b6887-125">The employee types in the RFP title and description.</span></span>  
  
    2. <span data-ttu-id="b6887-126">员工选择他们想要邀请的供应商提交建议。</span><span class="sxs-lookup"><span data-stu-id="b6887-126">The employee selects the vendors that they want to invite to submit proposals.</span></span>  
  
2. <span data-ttu-id="b6887-127">该员工提交建议书。</span><span class="sxs-lookup"><span data-stu-id="b6887-127">The employee submits the proposal.</span></span>  
  
    1. <span data-ttu-id="b6887-128">创建一个工作流实例。</span><span class="sxs-lookup"><span data-stu-id="b6887-128">An instance of the workflow is created.</span></span>  
  
    2. <span data-ttu-id="b6887-129">工作流正在等待所有供应商提交其建议书。</span><span class="sxs-lookup"><span data-stu-id="b6887-129">The workflow is waiting for all vendors to submit their proposals.</span></span>  
  
3. <span data-ttu-id="b6887-130">在收到所有建议书后，工作流将循环访问所有收到的建议书并选择最佳建议书。</span><span class="sxs-lookup"><span data-stu-id="b6887-130">After all proposals are received, the workflow iterates through all the received proposals and selects the best one.</span></span>  
  
    1. <span data-ttu-id="b6887-131">每个供应商都具有一个信誉（此示例将信誉列表存储在 VendorRepository.cs 中）。</span><span class="sxs-lookup"><span data-stu-id="b6887-131">Each vendor has a reputation (this sample stores the reputation list in VendorRepository.cs).</span></span>  
  
    2. <span data-ttu-id="b6887-132">将（供应商键入的值）\*（记录的供应商信誉）/100 来计算出建议书的总值。</span><span class="sxs-lookup"><span data-stu-id="b6887-132">The total value of the proposal is determined by (The value typed in by the vendor) \* (The vendor's recorded reputation) / 100.</span></span>  
  
4. <span data-ttu-id="b6887-133">原始请求方可以查看所有提交的建议书。</span><span class="sxs-lookup"><span data-stu-id="b6887-133">The original requester can see all the submitted proposals.</span></span> <span data-ttu-id="b6887-134">最佳建议书将在报告的某个特殊部分中显示。</span><span class="sxs-lookup"><span data-stu-id="b6887-134">The best proposal is presented in a special section in the report.</span></span>  
  
## <a name="process-definition"></a><span data-ttu-id="b6887-135">过程定义</span><span class="sxs-lookup"><span data-stu-id="b6887-135">Process Definition</span></span>  

 <span data-ttu-id="b6887-136">示例的核心逻辑使用一个 <xref:System.Activities.Statements.ParallelForEach%601> 活动，该活动等待每个供应商的报价（使用创建书签的自定义活动）并将供应商的建议书注册为 RFP（使用 <xref:System.Activities.Statements.InvokeMethod> 活动）。</span><span class="sxs-lookup"><span data-stu-id="b6887-136">The core logic of the sample uses a <xref:System.Activities.Statements.ParallelForEach%601> activity that waits for the offers from each vendor (using a custom activity that creates a bookmark), and registers the vendor proposal as an RFP (using an <xref:System.Activities.Statements.InvokeMethod> activity).</span></span>  
  
 <span data-ttu-id="b6887-137">然后，此示例循环访问存储在 `RfpRepository` 中的所有收到的建议书，计算调整后的值（使用 <xref:System.Activities.Statements.Assign> 活动和 <xref:System.Activities.Expressions> 活动）；如果调整后的值比先前的最佳报价更可取，则将该新值指定为最佳报价（使用 <xref:System.Activities.Statements.If> 和 <xref:System.Activities.Statements.Assign> 活动）。</span><span class="sxs-lookup"><span data-stu-id="b6887-137">The sample then iterates through all of the received proposals stored in the `RfpRepository`, calculating the adjusted value (using an <xref:System.Activities.Statements.Assign> activity and <xref:System.Activities.Expressions> activities), and if the adjusted value is better than the previous best offer, assigns the new value as the best offer (using <xref:System.Activities.Statements.If> and <xref:System.Activities.Statements.Assign> activities).</span></span>  
  
## <a name="projects-in-this-sample"></a><span data-ttu-id="b6887-138">此示例中的项目</span><span class="sxs-lookup"><span data-stu-id="b6887-138">Projects in this Sample</span></span>  

 <span data-ttu-id="b6887-139">此示例包含以下项目。</span><span class="sxs-lookup"><span data-stu-id="b6887-139">This sample contains the following projects.</span></span>  
  
|<span data-ttu-id="b6887-140">项目</span><span class="sxs-lookup"><span data-stu-id="b6887-140">Project</span></span>|<span data-ttu-id="b6887-141">说明</span><span class="sxs-lookup"><span data-stu-id="b6887-141">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b6887-142">通用</span><span class="sxs-lookup"><span data-stu-id="b6887-142">Common</span></span>|<span data-ttu-id="b6887-143">过程中使用的实体对象（征求建议书、供应商和供应商建议书）。</span><span class="sxs-lookup"><span data-stu-id="b6887-143">The entity objects used within the process (Request for Proposal, Vendor, and Vendor Proposal).</span></span>|  
|<span data-ttu-id="b6887-144">WfDefinition</span><span class="sxs-lookup"><span data-stu-id="b6887-144">WfDefinition</span></span>|<span data-ttu-id="b6887-145">客户端应用程序用来创建和使用购买过程工作流实例的过程（作为 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 程序）和主机 (`PurchaseProcessHost`) 的定义。</span><span class="sxs-lookup"><span data-stu-id="b6887-145">The definition of the process (as a [!INCLUDE[wf1](../../../../includes/wf1-md.md)] program) and host (`PurchaseProcessHost`) used by client applications for creating and using instances of the purchase process workflow.</span></span>|  
|<span data-ttu-id="b6887-146">WebClient</span><span class="sxs-lookup"><span data-stu-id="b6887-146">WebClient</span></span>|<span data-ttu-id="b6887-147">ASP.NET 客户端应用程序，允许用户创建和参与购买过程的实例。</span><span class="sxs-lookup"><span data-stu-id="b6887-147">An ASP.NET client application that allows the users to create and participate in instances of the purchase process.</span></span> <span data-ttu-id="b6887-148">此应用程序使用自定义创建的主机与工作流引擎进行交互。</span><span class="sxs-lookup"><span data-stu-id="b6887-148">It uses a custom-created host to interact with the workflow engine.</span></span>|  
|<span data-ttu-id="b6887-149">WinFormsClient</span><span class="sxs-lookup"><span data-stu-id="b6887-149">WinFormsClient</span></span>|<span data-ttu-id="b6887-150">一个 Windows 窗体客户端应用程序，它允许用户创建和参与购买过程的实例。</span><span class="sxs-lookup"><span data-stu-id="b6887-150">A Windows Forms client application that allows the users to create and participate in instances of the purchase process.</span></span> <span data-ttu-id="b6887-151">此应用程序使用自定义创建的主机与工作流引擎进行交互。</span><span class="sxs-lookup"><span data-stu-id="b6887-151">It uses a custom-created host to interact with the workflow engine.</span></span>|  
  
### <a name="wfdefinition"></a><span data-ttu-id="b6887-152">WfDefinition</span><span class="sxs-lookup"><span data-stu-id="b6887-152">WfDefinition</span></span>  

 <span data-ttu-id="b6887-153">下表包含对 WfDefinition 项目中最重要文件的说明。</span><span class="sxs-lookup"><span data-stu-id="b6887-153">The following table contains a description of the most important files in the WfDefinition project.</span></span>  
  
|<span data-ttu-id="b6887-154">文件</span><span class="sxs-lookup"><span data-stu-id="b6887-154">File</span></span>|<span data-ttu-id="b6887-155">描述</span><span class="sxs-lookup"><span data-stu-id="b6887-155">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="b6887-156">IPurchaseProcessHost.cs</span><span class="sxs-lookup"><span data-stu-id="b6887-156">IPurchaseProcessHost.cs</span></span>|<span data-ttu-id="b6887-157">工作流主机的接口。</span><span class="sxs-lookup"><span data-stu-id="b6887-157">Interface for the host of the workflow.</span></span>|  
|<span data-ttu-id="b6887-158">PurchaseProcessHost.cs</span><span class="sxs-lookup"><span data-stu-id="b6887-158">PurchaseProcessHost.cs</span></span>|<span data-ttu-id="b6887-159">工作流主机的实现。</span><span class="sxs-lookup"><span data-stu-id="b6887-159">Implementation of a host for the workflow.</span></span> <span data-ttu-id="b6887-160">该主机提取工作流运行时的详细信息，并在所有客户端应用程序中用于加载和运行 `PurchaseProcess` 工作流实例并与其进行交互。</span><span class="sxs-lookup"><span data-stu-id="b6887-160">The host abstracts the details of the workflow runtime and is used in all the client applications to load, run, and interact with `PurchaseProcess` workflow instances.</span></span>|  
|<span data-ttu-id="b6887-161">PurchaseProcessWorkflow.cs</span><span class="sxs-lookup"><span data-stu-id="b6887-161">PurchaseProcessWorkflow.cs</span></span>|<span data-ttu-id="b6887-162">一个包含购买过程工作流定义的活动（派生自 <xref:System.Activities.Activity>）。</span><span class="sxs-lookup"><span data-stu-id="b6887-162">An activity that contains the definition of the Purchase Process workflow (derives from <xref:System.Activities.Activity>).</span></span><br /><br /> <span data-ttu-id="b6887-163">派生自 <xref:System.Activities.Activity> 的活动通过组合现有自定义活动和来自 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] 活动库的活动来组合功能。</span><span class="sxs-lookup"><span data-stu-id="b6887-163">Activities that derive from <xref:System.Activities.Activity> compose functionality by assembling existing custom activities and activities from the [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] activity library.</span></span> <span data-ttu-id="b6887-164">组合这些活动是创建自定义功能的最基本方法。</span><span class="sxs-lookup"><span data-stu-id="b6887-164">Assembling these activities is the most basic way to create custom functionality.</span></span>|  
|<span data-ttu-id="b6887-165">WaitForVendorProposal.cs</span><span class="sxs-lookup"><span data-stu-id="b6887-165">WaitForVendorProposal.cs</span></span>|<span data-ttu-id="b6887-166">此自定义活动派生自 <xref:System.Activities.NativeActivity>，并将在提交建议书时创建一个稍后必须由供应商恢复的命名书签。</span><span class="sxs-lookup"><span data-stu-id="b6887-166">This custom activity derives from <xref:System.Activities.NativeActivity> and creates a named bookmark that must be resumed later by a vendor when submitting the proposal.</span></span><br /><br /> <span data-ttu-id="b6887-167">从 <xref:System.Activities.NativeActivity> 派生的活动，与从 <xref:System.Activities.CodeActivity> 派生的活动一样，可通过重写 <xref:System.Activities.NativeActivity.Execute%2A> 来创建命令性功能，除此之外还可以通过传递给 <xref:System.Activities.ActivityContext> 方法的 `Execute` 访问工作流运行时的所有功能。</span><span class="sxs-lookup"><span data-stu-id="b6887-167">Activities that derive from <xref:System.Activities.NativeActivity>, like those that derive from <xref:System.Activities.CodeActivity>, create imperative functionality by overriding <xref:System.Activities.NativeActivity.Execute%2A>, but also have access to all of the functionality of the workflow runtime through the <xref:System.Activities.ActivityContext> that gets passed into the `Execute` method.</span></span> <span data-ttu-id="b6887-168">此上下文支持安排和取消子活动、设置非持久性区域 (执行块，在此过程中，运行时不会保留工作流的数据，例如在原子事务) 中，以及 <xref:System.Activities.Bookmark> 用于恢复暂停的工作流) 的对象 (的句柄。</span><span class="sxs-lookup"><span data-stu-id="b6887-168">This context has support for scheduling and canceling child activities, setting up no-persist zones (execution blocks during which the runtime does not persist the workflow's data, such as within atomic transactions), and <xref:System.Activities.Bookmark> objects (handles for resuming paused workflows).</span></span>|  
|<span data-ttu-id="b6887-169">TrackingParticipant.cs</span><span class="sxs-lookup"><span data-stu-id="b6887-169">TrackingParticipant.cs</span></span>|<span data-ttu-id="b6887-170">一个 <xref:System.Activities.Tracking.TrackingParticipant>，它接收所有跟踪事件并将这些事件保存到一个文本文件中。</span><span class="sxs-lookup"><span data-stu-id="b6887-170">A <xref:System.Activities.Tracking.TrackingParticipant> that receives all tracking events and saves them to a text file.</span></span><br /><br /> <span data-ttu-id="b6887-171">跟踪参与者将作为扩展添加到工作流实例中。</span><span class="sxs-lookup"><span data-stu-id="b6887-171">Tracking participants are added to workflow instance as Extensions.</span></span>|  
|<span data-ttu-id="b6887-172">XmlWorkflowInstanceStore.cs</span><span class="sxs-lookup"><span data-stu-id="b6887-172">XmlWorkflowInstanceStore.cs</span></span>|<span data-ttu-id="b6887-173">一个自定义 <xref:System.Runtime.DurableInstancing.InstanceStore>，它将工作流应用程序保存到 XML 文件中。</span><span class="sxs-lookup"><span data-stu-id="b6887-173">A custom <xref:System.Runtime.DurableInstancing.InstanceStore> that saves workflow applications to XML files.</span></span>|  
|<span data-ttu-id="b6887-174">XmlPersistenceParticipant.cs</span><span class="sxs-lookup"><span data-stu-id="b6887-174">XmlPersistenceParticipant.cs</span></span>|<span data-ttu-id="b6887-175">一个自定义 <xref:System.Activities.Persistence.PersistenceParticipant>，它将征求建议书实例保存到 XML 文件中。</span><span class="sxs-lookup"><span data-stu-id="b6887-175">A custom <xref:System.Activities.Persistence.PersistenceParticipant> that saves an instance of request for proposal to an XML file.</span></span>|  
|<span data-ttu-id="b6887-176">AsyncResult.cs / CompletedAsyncResult.cs</span><span class="sxs-lookup"><span data-stu-id="b6887-176">AsyncResult.cs / CompletedAsyncResult.cs</span></span>|<span data-ttu-id="b6887-177">用于在持久性组件中实现异步模式的帮助器类。</span><span class="sxs-lookup"><span data-stu-id="b6887-177">Helper classes for implementing the asynchronous pattern in the persistence components.</span></span>|  
  
### <a name="common"></a><span data-ttu-id="b6887-178">通用</span><span class="sxs-lookup"><span data-stu-id="b6887-178">Common</span></span>  

 <span data-ttu-id="b6887-179">下表包含对 Common 项目中最重要的类的说明。</span><span class="sxs-lookup"><span data-stu-id="b6887-179">The following table contains a description of the most important classes in the Common project.</span></span>  
  
|<span data-ttu-id="b6887-180">实例</span><span class="sxs-lookup"><span data-stu-id="b6887-180">Class</span></span>|<span data-ttu-id="b6887-181">说明</span><span class="sxs-lookup"><span data-stu-id="b6887-181">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b6887-182">供应商</span><span class="sxs-lookup"><span data-stu-id="b6887-182">Vendor</span></span>|<span data-ttu-id="b6887-183">在征求建议书中提交建议书的供应商。</span><span class="sxs-lookup"><span data-stu-id="b6887-183">A vendor that submits proposals in a Request for Proposals.</span></span>|  
|<span data-ttu-id="b6887-184">RequestForProposal</span><span class="sxs-lookup"><span data-stu-id="b6887-184">RequestForProposal</span></span>|<span data-ttu-id="b6887-185">征求建议书 (RFP) 是一份邀请，旨在请求供应商提交有关特定商品或服务的建议书。</span><span class="sxs-lookup"><span data-stu-id="b6887-185">A request for proposals (RFP) is an invitation for vendors to submit proposals on a specific commodity or service.</span></span>|  
|<span data-ttu-id="b6887-186">VendorProposal</span><span class="sxs-lookup"><span data-stu-id="b6887-186">VendorProposal</span></span>|<span data-ttu-id="b6887-187">供应商针对具体的 RFP 提交的建议书。</span><span class="sxs-lookup"><span data-stu-id="b6887-187">A proposal submitted by a vendor to a concrete RFP.</span></span>|  
|<span data-ttu-id="b6887-188">VendorRepository</span><span class="sxs-lookup"><span data-stu-id="b6887-188">VendorRepository</span></span>|<span data-ttu-id="b6887-189">供应商的储存库。</span><span class="sxs-lookup"><span data-stu-id="b6887-189">The repository of Vendors.</span></span> <span data-ttu-id="b6887-190">此实现包含一个内存中的集合，其中包括供应商实例和用于公开这些实例的方法。</span><span class="sxs-lookup"><span data-stu-id="b6887-190">This implementation contains an in-memory collection of instances of Vendor and methods for exposing those instances.</span></span>|  
|<span data-ttu-id="b6887-191">RfpRepository</span><span class="sxs-lookup"><span data-stu-id="b6887-191">RfpRepository</span></span>|<span data-ttu-id="b6887-192">征求建议书的储存库。</span><span class="sxs-lookup"><span data-stu-id="b6887-192">The repository of Requests for Proposals.</span></span> <span data-ttu-id="b6887-193">此实现将使用 Linq to XML 来查询由程式化的持久性所生成的征求建议书的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="b6887-193">This implementation contains uses Linq to XML to query the XML file of Requests for Proposal generated by the schematized persistence.</span></span> |  
|<span data-ttu-id="b6887-194">IOHelper</span><span class="sxs-lookup"><span data-stu-id="b6887-194">IOHelper</span></span>|<span data-ttu-id="b6887-195">此类处理所有与 I/O 有关的问题（文件夹、路径等。）</span><span class="sxs-lookup"><span data-stu-id="b6887-195">This class handles all I/O-related issues (folders, paths, and so on.)</span></span>|  
  
### <a name="web-client"></a><span data-ttu-id="b6887-196">Web 客户端</span><span class="sxs-lookup"><span data-stu-id="b6887-196">Web Client</span></span>  

 <span data-ttu-id="b6887-197">下表包含对 Web Client 项目中最重要网页的说明。</span><span class="sxs-lookup"><span data-stu-id="b6887-197">The following table contains a description of the most important Web pages in the Web Client project.</span></span>  
  
|<span data-ttu-id="b6887-198">文件</span><span class="sxs-lookup"><span data-stu-id="b6887-198">File</span></span>|<span data-ttu-id="b6887-199">描述</span><span class="sxs-lookup"><span data-stu-id="b6887-199">Description</span></span>|  
|-|-|  
|<span data-ttu-id="b6887-200">CreateRfp.aspx</span><span class="sxs-lookup"><span data-stu-id="b6887-200">CreateRfp.aspx</span></span>|<span data-ttu-id="b6887-201">创建和提交新的征求建议书。</span><span class="sxs-lookup"><span data-stu-id="b6887-201">Creates and submits a new Request for Proposals.</span></span>|  
|<span data-ttu-id="b6887-202">Default.aspx</span><span class="sxs-lookup"><span data-stu-id="b6887-202">Default.aspx</span></span>|<span data-ttu-id="b6887-203">显示所有活动的和已完成的征求建议书。</span><span class="sxs-lookup"><span data-stu-id="b6887-203">Shows all active and completed Requests for Proposals.</span></span>|  
|<span data-ttu-id="b6887-204">GetVendorProposal.aspx</span><span class="sxs-lookup"><span data-stu-id="b6887-204">GetVendorProposal.aspx</span></span>|<span data-ttu-id="b6887-205">从具体的征求建议书中获取来自供应商的建议。</span><span class="sxs-lookup"><span data-stu-id="b6887-205">Gets a proposal from a vendor in a concrete Request for Proposals.</span></span> <span data-ttu-id="b6887-206">此页仅由供应商使用。</span><span class="sxs-lookup"><span data-stu-id="b6887-206">This page is used only by vendors.</span></span>|  
|<span data-ttu-id="b6887-207">ShowRfp.aspx</span><span class="sxs-lookup"><span data-stu-id="b6887-207">ShowRfp.aspx</span></span>|<span data-ttu-id="b6887-208">显示有关征求建议书的所有信息（收到的建议书、日期、值和其他信息）。</span><span class="sxs-lookup"><span data-stu-id="b6887-208">Show all the information about a Request for Proposals (received proposals, dates, values, and other information).</span></span> <span data-ttu-id="b6887-209">此页仅供征求建议书的创建者使用。</span><span class="sxs-lookup"><span data-stu-id="b6887-209">This page is only used by the creator of the Request for Proposal.</span></span>|  
  
### <a name="winforms-client"></a><span data-ttu-id="b6887-210">WinForms Client</span><span class="sxs-lookup"><span data-stu-id="b6887-210">WinForms Client</span></span>  

 <span data-ttu-id="b6887-211">下表包含对 Win Forms 项目中最重要的窗体的说明。</span><span class="sxs-lookup"><span data-stu-id="b6887-211">The following table contains a description of the most important forms in the Win Forms project.</span></span>  
  
|<span data-ttu-id="b6887-212">窗体</span><span class="sxs-lookup"><span data-stu-id="b6887-212">Form</span></span>|<span data-ttu-id="b6887-213">描述</span><span class="sxs-lookup"><span data-stu-id="b6887-213">Description</span></span>|  
|-|-|  
|<span data-ttu-id="b6887-214">NewRfp</span><span class="sxs-lookup"><span data-stu-id="b6887-214">NewRfp</span></span>|<span data-ttu-id="b6887-215">创建和提交新的征求建议书。</span><span class="sxs-lookup"><span data-stu-id="b6887-215">Creates and submits a new Request for Proposals.</span></span>|  
|<span data-ttu-id="b6887-216">ShowProposals</span><span class="sxs-lookup"><span data-stu-id="b6887-216">ShowProposals</span></span>|<span data-ttu-id="b6887-217">显示所有活动的和已完成的征求建议书。</span><span class="sxs-lookup"><span data-stu-id="b6887-217">Show all active and finished Requests for Proposals.</span></span> <span data-ttu-id="b6887-218">**注意：**  你可能需要单击 UI 中的 " **刷新** " 按钮，才能在创建或修改建议请求后查看该屏幕中的更改。</span><span class="sxs-lookup"><span data-stu-id="b6887-218">**Note:**  You may need to click the **Refresh** button in the UI to see changes in that screen after you create or modify a Request for Proposal.</span></span>|  
|<span data-ttu-id="b6887-219">SubmitProposal</span><span class="sxs-lookup"><span data-stu-id="b6887-219">SubmitProposal</span></span>|<span data-ttu-id="b6887-220">从具体的征求建议书中获取来自供应商的建议。</span><span class="sxs-lookup"><span data-stu-id="b6887-220">Get a proposal from a vendor in a concrete Request for Proposals.</span></span> <span data-ttu-id="b6887-221">此窗口仅由供应商使用。</span><span class="sxs-lookup"><span data-stu-id="b6887-221">This window is used only by vendors.</span></span>|  
|<span data-ttu-id="b6887-222">ViewRfp</span><span class="sxs-lookup"><span data-stu-id="b6887-222">ViewRfp</span></span>|<span data-ttu-id="b6887-223">显示有关征求建议书的所有信息（收到的建议书、日期、值和其他信息）。</span><span class="sxs-lookup"><span data-stu-id="b6887-223">Show all the information about a Request for Proposals (received proposals, dates, values, and other information).</span></span> <span data-ttu-id="b6887-224">此窗口仅供征求建议书的创建者使用。</span><span class="sxs-lookup"><span data-stu-id="b6887-224">This window  is only used by the creator of the Request for Proposals.</span></span>|  
  
### <a name="persistence-files"></a><span data-ttu-id="b6887-225">持久性文件</span><span class="sxs-lookup"><span data-stu-id="b6887-225">Persistence Files</span></span>  

 <span data-ttu-id="b6887-226">下表显示由永久性提供程序 (`XmlPersistenceProvider`) 生成的文件，这些文件位于当前系统的临时文件夹下的路径（使用 <xref:System.IO.Path.GetTempPath%2A>）中。</span><span class="sxs-lookup"><span data-stu-id="b6887-226">The following table shows the files generated by the persistence provider (`XmlPersistenceProvider`) are located in the path of the current system's temporary folder (using <xref:System.IO.Path.GetTempPath%2A>).</span></span> <span data-ttu-id="b6887-227">在当前执行路径中创建跟踪文件。</span><span class="sxs-lookup"><span data-stu-id="b6887-227">The tracing file is created in the current execution path.</span></span>  
  
|<span data-ttu-id="b6887-228">文件名</span><span class="sxs-lookup"><span data-stu-id="b6887-228">File Name</span></span>|<span data-ttu-id="b6887-229">说明</span><span class="sxs-lookup"><span data-stu-id="b6887-229">Description</span></span>|<span data-ttu-id="b6887-230">路径</span><span class="sxs-lookup"><span data-stu-id="b6887-230">Path</span></span>|  
|-|-|-|  
|<span data-ttu-id="b6887-231">rfps.xml</span><span class="sxs-lookup"><span data-stu-id="b6887-231">rfps.xml</span></span>|<span data-ttu-id="b6887-232">具有所有活动的和已完成的征求建议书的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="b6887-232">The XML file with all the active and finished Requests for Proposals.</span></span>|<xref:System.IO.Path.GetTempPath%2A>|  
|<span data-ttu-id="b6887-233">[instanceid]</span><span class="sxs-lookup"><span data-stu-id="b6887-233">[instanceid]</span></span>|<span data-ttu-id="b6887-234">此文件包含有关工作流实例的所有信息。</span><span class="sxs-lookup"><span data-stu-id="b6887-234">This file contains all the information about a workflow instance.</span></span><br /><br /> <span data-ttu-id="b6887-235">此文件由程式化的持久性实现生成（XmlPersistenceProvider 中的 PersistenceParticipant）。</span><span class="sxs-lookup"><span data-stu-id="b6887-235">This file is generated by the schematized persistence implementation (PersistenceParticipant in XmlPersistenceProvider).</span></span>|<xref:System.IO.Path.GetTempPath%2A>|  
|<span data-ttu-id="b6887-236">[instanceId].tracking</span><span class="sxs-lookup"><span data-stu-id="b6887-236">[instanceId].tracking</span></span>|<span data-ttu-id="b6887-237">一个包含具体实例中发生的所有事件的文本文件。</span><span class="sxs-lookup"><span data-stu-id="b6887-237">A text file with all the events that occurred within a concrete instance.</span></span><br /><br /> <span data-ttu-id="b6887-238">此文件由 TrackingParticipant 生成。</span><span class="sxs-lookup"><span data-stu-id="b6887-238">This file is generated by TrackingParticipant.</span></span>|<xref:System.IO.Path.GetTempPath%2A>|  
|<span data-ttu-id="b6887-239">PurchaseProcess.Tracing.TraceLog.txt</span><span class="sxs-lookup"><span data-stu-id="b6887-239">PurchaseProcess.Tracing.TraceLog.txt</span></span>|<span data-ttu-id="b6887-240">由基于 App.config 文件或 Web.config 文件中的配置参数的工作流生成的跟踪文件。</span><span class="sxs-lookup"><span data-stu-id="b6887-240">The tracing file generated by the workflow based on the configuration parameters in the App.config or Web.config files.</span></span>|<span data-ttu-id="b6887-241">当前执行路径</span><span class="sxs-lookup"><span data-stu-id="b6887-241">Current execution path</span></span>|  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="b6887-242">使用此示例</span><span class="sxs-lookup"><span data-stu-id="b6887-242">To use this sample</span></span>  
  
1. <span data-ttu-id="b6887-243">使用 Visual Studio 2010 打开 PurchaseProcess 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="b6887-243">Using Visual Studio 2010, open the PurchaseProcess.sln solution file.</span></span>  
  
2. <span data-ttu-id="b6887-244">若要执行 Web 客户端项目，请打开 **解决方案资源管理器** 并右键单击 " **Web 客户端** " 项目。</span><span class="sxs-lookup"><span data-stu-id="b6887-244">To execute the Web Client project, open **Solution Explorer** and right-click the **Web Client** project.</span></span> <span data-ttu-id="b6887-245">选择 " **设置为启动项目**"。</span><span class="sxs-lookup"><span data-stu-id="b6887-245">Select **Set as Startup Project**.</span></span>  
  
3. <span data-ttu-id="b6887-246">若要执行 WinForms 客户端项目，请打开 **解决方案资源管理器** 并右键单击 " **WinForms" 客户端** 项目。</span><span class="sxs-lookup"><span data-stu-id="b6887-246">To execute the WinForms Client project, open **Solution Explorer** and right-click the **WinForms Client** project.</span></span> <span data-ttu-id="b6887-247">选择 " **设置为启动项目**"。</span><span class="sxs-lookup"><span data-stu-id="b6887-247">Select **Set as Startup Project**.</span></span>  
  
4. <span data-ttu-id="b6887-248">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="b6887-248">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
5. <span data-ttu-id="b6887-249">若要运行解决方案，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="b6887-249">To run the solution, press CTRL+F5.</span></span>  
  
### <a name="web-client-options"></a><span data-ttu-id="b6887-250">Web Client 选项</span><span class="sxs-lookup"><span data-stu-id="b6887-250">Web Client Options</span></span>  
  
- <span data-ttu-id="b6887-251">**创建新的 RFP**： (RFP) 创建新的提议请求并启动购买过程工作流。</span><span class="sxs-lookup"><span data-stu-id="b6887-251">**Create a new RFP**: Creates a new Request for Proposals (RFP) and starts a Purchase Process workflow.</span></span>  
  
- <span data-ttu-id="b6887-252">**刷新**：刷新主窗口中活动的和已完成的 rfp 的列表。</span><span class="sxs-lookup"><span data-stu-id="b6887-252">**Refresh**: Refreshes the list of Active and Finished RFPs in the main window.</span></span>  
  
- <span data-ttu-id="b6887-253">**视图**：显示现有 RFP 的内容。</span><span class="sxs-lookup"><span data-stu-id="b6887-253">**View**: Shows the content of an existing RFP.</span></span> <span data-ttu-id="b6887-254">供应商可提交其建议书（如果受到邀请或 RFP 尚未完成）。</span><span class="sxs-lookup"><span data-stu-id="b6887-254">Vendors can submit their proposals (if invited or the RFP is not finished).</span></span>  
  
- <span data-ttu-id="b6887-255">查看为：用户可以通过在 "活动 Rfp" 网格中的 " **视图** " 中选择所需的参与者，使用不同的标识访问 RFP。</span><span class="sxs-lookup"><span data-stu-id="b6887-255">View As: The user can access the RFP using different identities by selecting the desired participant in the **View as** combo box in the active RFPs grid.</span></span>  
  
### <a name="winforms-client-options"></a><span data-ttu-id="b6887-256">WinForms Client 选项</span><span class="sxs-lookup"><span data-stu-id="b6887-256">WinForms Client Options</span></span>  
  
- <span data-ttu-id="b6887-257">**创建 rfp**： (RFP) 创建新的提议请求并启动购买过程工作流。</span><span class="sxs-lookup"><span data-stu-id="b6887-257">**Create RFP**: Creates a new Request for Proposals (RFP) and starts a Purchase Process workflow.</span></span>  
  
- <span data-ttu-id="b6887-258">**刷新**：刷新主窗口中活动的和已完成的 rfp 的列表。</span><span class="sxs-lookup"><span data-stu-id="b6887-258">**Refresh**: Refreshes the list of Active and Finished RFPs in the main window.</span></span>  
  
- <span data-ttu-id="b6887-259">**查看 rfp**：显示现有 RFP 的内容。</span><span class="sxs-lookup"><span data-stu-id="b6887-259">**View RFP**: Shows the content of an existing RFP.</span></span> <span data-ttu-id="b6887-260">供应商可提交其建议书（如果受到邀请或 RFP 尚未完成）。</span><span class="sxs-lookup"><span data-stu-id="b6887-260">Vendors can submit their proposals (if invited or the RFP is not finished)</span></span>  
  
- <span data-ttu-id="b6887-261">**连接身份**：通过在活动的 rfp 网格的 " **视图为** " 组合框中选择所需的参与者，用户可以使用不同的标识访问 RFP。</span><span class="sxs-lookup"><span data-stu-id="b6887-261">**Connect As**: The user can access the RFP using different identities by selecting the desired participant in the **View as** combo box in the active RFPs grid.</span></span>
