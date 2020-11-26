---
title: 访问 OperationContext
ms.date: 03/30/2017
ms.assetid: 4e92efe8-7e79-41f3-b50e-bdc38b9f41f8
ms.openlocfilehash: 5cffae101c5d39fcc9500aa7ccafde7a836a5023
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96245726"
---
# <a name="accessing-operationcontext"></a><span data-ttu-id="7b48b-102">访问 OperationContext</span><span class="sxs-lookup"><span data-stu-id="7b48b-102">Accessing OperationContext</span></span>

<span data-ttu-id="7b48b-103">此示例演示如何将消息传递活动 (<xref:System.ServiceModel.Activities.Receive> 和 <xref:System.ServiceModel.Activities.Send>) 与自定义范围活动一起使用，以便在 <xref:System.ServiceModel.OperationContext.Current%2A> 传出消息或传入消息中访问和附加或检索自定义消息标头。</span><span class="sxs-lookup"><span data-stu-id="7b48b-103">This sample demonstrates how the messaging activities (<xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.Send>) can be used with a custom scope activity to access <xref:System.ServiceModel.OperationContext.Current%2A> and attach or retrieve a custom message header within an outgoing or incoming message.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="7b48b-104">演示</span><span class="sxs-lookup"><span data-stu-id="7b48b-104">Demonstrates</span></span>  

 <span data-ttu-id="7b48b-105">消息传递活动、<xref:System.ServiceModel.Activities.ISendMessageCallback>、<xref:System.ServiceModel.Activities.IReceiveMessageCallback>。</span><span class="sxs-lookup"><span data-stu-id="7b48b-105">Messaging Activities, <xref:System.ServiceModel.Activities.ISendMessageCallback>, <xref:System.ServiceModel.Activities.IReceiveMessageCallback>.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="7b48b-106">讨论 (Discussion)</span><span class="sxs-lookup"><span data-stu-id="7b48b-106">Discussion</span></span>  

 <span data-ttu-id="7b48b-107">此示例演示如何使用消息传递活动中的扩展性点（<xref:System.ServiceModel.Activities.ISendMessageCallback> 和 <xref:System.ServiceModel.Activities.IReceiveMessageCallback>）来访问 <xref:System.ServiceModel.OperationContext.Current%2A>。</span><span class="sxs-lookup"><span data-stu-id="7b48b-107">This sample shows how to use extensibility points (<xref:System.ServiceModel.Activities.ISendMessageCallback>) <xref:System.ServiceModel.Activities.IReceiveMessageCallback>) in the messaging activities to access <xref:System.ServiceModel.OperationContext.Current%2A>.</span></span> <span data-ttu-id="7b48b-108">在工作流运行时中，将回调注册为由消息传递活动在执行后选取的 <xref:System.Activities.IExecutionProperty> 的实现。</span><span class="sxs-lookup"><span data-stu-id="7b48b-108">The callbacks are registered within the workflow runtime as an implementation of <xref:System.Activities.IExecutionProperty> that is picked up by the messaging activities upon execution.</span></span> <span data-ttu-id="7b48b-109">与该 <xref:System.Activities.IExecutionProperty> 实现处于同一范围内的任何消息传递活动都会受到影响。</span><span class="sxs-lookup"><span data-stu-id="7b48b-109">Any messaging activity in the same scope as that <xref:System.Activities.IExecutionProperty> implementation is affected.</span></span> <span data-ttu-id="7b48b-110">特别是，此示例使用自定义范围活动来强制实施回调行为。</span><span class="sxs-lookup"><span data-stu-id="7b48b-110">In particular, this sample uses a custom scope activity to enforce the callback behavior.</span></span> <span data-ttu-id="7b48b-111">在客户端工作流中使用 <xref:System.ServiceModel.Activities.ISendMessageCallback> 可将工作流的 <xref:System.Activities.WorkflowApplication.Id%2A> 作为传出 <xref:System.ServiceModel.Channels.MessageHeader> 包含。</span><span class="sxs-lookup"><span data-stu-id="7b48b-111">The <xref:System.ServiceModel.Activities.ISendMessageCallback> is used in the client workflow to include the workflow’s <xref:System.Activities.WorkflowApplication.Id%2A> as an outgoing <xref:System.ServiceModel.Channels.MessageHeader>.</span></span> <span data-ttu-id="7b48b-112">然后，在使用 <xref:System.ServiceModel.Activities.IReceiveMessageCallback> 的服务中选择此标头，并将此标头的值输出到控制台。</span><span class="sxs-lookup"><span data-stu-id="7b48b-112">This header is then picked up in the service using the <xref:System.ServiceModel.Activities.IReceiveMessageCallback> and the value of the header is printed out to the console.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="7b48b-113">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="7b48b-113">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="7b48b-114">此示例使用 HTTP 终结点公开一个工作流服务。</span><span class="sxs-lookup"><span data-stu-id="7b48b-114">This sample exposes a workflow service using HTTP endpoints.</span></span> <span data-ttu-id="7b48b-115">若要运行此示例，必须添加正确的 URL Acl (参阅 [配置 HTTP 和 HTTPS](../../wcf/feature-details/configuring-http-and-https.md) 以获取详细信息) ，方法是以管理员身份运行 Visual Studio，或在提升的提示符下执行以下命令来添加相应的 acl。</span><span class="sxs-lookup"><span data-stu-id="7b48b-115">To run this sample, proper URL ACLs must be added (see [Configuring HTTP and HTTPS](../../wcf/feature-details/configuring-http-and-https.md) for details), either by running Visual Studio as Administrator or by executing the following command at an elevated prompt to add the appropriate ACLs.</span></span> <span data-ttu-id="7b48b-116">确保替换了域和用户名。</span><span class="sxs-lookup"><span data-stu-id="7b48b-116">Ensure that your Domain and Username are substituted.</span></span>  
  
    ```console  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2. <span data-ttu-id="7b48b-117">在添加 URL ACL 后，请使用下列步骤。</span><span class="sxs-lookup"><span data-stu-id="7b48b-117">Once the URL ACLs are added, use the following steps.</span></span>  
  
    1. <span data-ttu-id="7b48b-118">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="7b48b-118">Build the solution.</span></span>  
  
    2. <span data-ttu-id="7b48b-119">通过右键单击解决方案并选择 " **设置启动项目**" 来设置多个启动项目。</span><span class="sxs-lookup"><span data-stu-id="7b48b-119">Set multiple start-up projects by right-clicking the solution and selecting **Set Startup Projects**.</span></span>  
  
    3. <span data-ttu-id="7b48b-120">将 **服务** 和 **客户端** (按顺序添加) 为多个启动项目。</span><span class="sxs-lookup"><span data-stu-id="7b48b-120">Add **Service** and **Client** (in that order) as multiple start-up projects.</span></span>  
  
    4. <span data-ttu-id="7b48b-121">运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="7b48b-121">Run the application.</span></span> <span data-ttu-id="7b48b-122">客户端控制台显示运行两次的工作流，而服务窗口显示这些工作流的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="7b48b-122">The client console shows a workflow running twice and the Service window shows the instance ID of those workflows.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="7b48b-123">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="7b48b-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="7b48b-124">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="7b48b-124">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="7b48b-125">如果此目录不存在，请参阅[Windows Communication Foundation (wcf) ，并 Windows Workflow Foundation (的 WF](https://www.microsoft.com/download/details.aspx?id=21459)) .NET Framework Windows Communication Foundation ([!INCLUDE[wf1](../../../../includes/wf1-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b48b-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7b48b-126">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="7b48b-126">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\Accessing Operation Context`
