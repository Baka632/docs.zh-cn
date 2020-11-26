---
title: 自定义通道调度程序
ms.date: 03/30/2017
ms.assetid: 813acf03-9661-4d57-a3c7-eeab497321c6
ms.openlocfilehash: 38d39cbba15c95a43444108d634d3c30524c70f4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96241767"
---
# <a name="custom-channel-dispatcher"></a><span data-ttu-id="60c08-102">自定义通道调度程序</span><span class="sxs-lookup"><span data-stu-id="60c08-102">Custom Channel Dispatcher</span></span>

<span data-ttu-id="60c08-103">此示例演示如何通过直接实现 <xref:System.ServiceModel.ServiceHostBase> 以自定义方式生成通道堆栈，以及如何在 Web 宿主环境中创建自定义通道调度程序。</span><span class="sxs-lookup"><span data-stu-id="60c08-103">This sample demonstrates how to build the channel stack in a custom way by implementing <xref:System.ServiceModel.ServiceHostBase> directly and how to create a custom channel dispatcher in Web host environment.</span></span> <span data-ttu-id="60c08-104">通道调度程序与 <xref:System.ServiceModel.Channels.IChannelListener> 交互以接受通道并从通道堆栈中检索消息。</span><span class="sxs-lookup"><span data-stu-id="60c08-104">The channel dispatcher interacts with <xref:System.ServiceModel.Channels.IChannelListener> to accept channels and retrieves messages from the channel stack.</span></span> <span data-ttu-id="60c08-105">此示例还提供一个基本示例，用于演示如何使用 <xref:System.ServiceModel.Activation.VirtualPathExtension> 在 Web 宿主环境中生成通道堆栈。</span><span class="sxs-lookup"><span data-stu-id="60c08-105">This sample also provides a basic sample to show how to build a channel stack in a Web host environment by using <xref:System.ServiceModel.Activation.VirtualPathExtension>.</span></span>  
  
## <a name="custom-servicehostbase"></a><span data-ttu-id="60c08-106">自定义 ServiceHostBase</span><span class="sxs-lookup"><span data-stu-id="60c08-106">Custom ServiceHostBase</span></span>  

 <span data-ttu-id="60c08-107">此示例实现基类型， <xref:System.ServiceModel.ServiceHostBase> 而不是 <xref:System.ServiceModel.ServiceHost> 以演示如何将 WINDOWS COMMUNICATION FOUNDATION (WCF) stack 实现替换为在通道堆栈顶部使用自定义消息处理层。</span><span class="sxs-lookup"><span data-stu-id="60c08-107">This sample implements the base type <xref:System.ServiceModel.ServiceHostBase> instead of <xref:System.ServiceModel.ServiceHost> to demonstrate how to replace the Windows Communication Foundation (WCF) stack implementation with a custom message handling layer on top of the channel stack.</span></span> <span data-ttu-id="60c08-108">重写虚拟方法 <xref:System.ServiceModel.ServiceHostBase.InitializeRuntime%2A> 可生成通道侦听器和通道调度程序。</span><span class="sxs-lookup"><span data-stu-id="60c08-108">You override the virtual method <xref:System.ServiceModel.ServiceHostBase.InitializeRuntime%2A> to build channel listeners and the channel dispatcher.</span></span>  
  
 <span data-ttu-id="60c08-109">若要实现 Web 承载的服务，请从 <xref:System.ServiceModel.Activation.VirtualPathExtension> 集合获取服务扩展 <xref:System.ServiceModel.ServiceHostBase.Extensions%2A> 并将其添加到 <xref:System.ServiceModel.Channels.BindingParameterCollection>，以便传输层知道如何基于宿主环境设置（即，Internet 信息服务 (IIS)/Windows 进程激活服务 (WAS) 设置）来配置通道侦听器。</span><span class="sxs-lookup"><span data-stu-id="60c08-109">To implement a Web-hosted service, get the service extension <xref:System.ServiceModel.Activation.VirtualPathExtension> from the <xref:System.ServiceModel.ServiceHostBase.Extensions%2A> collection and add it to the <xref:System.ServiceModel.Channels.BindingParameterCollection> so that the transport layer knows how to configure the channel listener based on the hosting environment settings, that is, the Internet Information Services (IIS)/Windows Process Activation Service (WAS) settings.</span></span>  
  
## <a name="custom-channel-dispatcher"></a><span data-ttu-id="60c08-110">自定义通道调度程序</span><span class="sxs-lookup"><span data-stu-id="60c08-110">Custom Channel Dispatcher</span></span>  

 <span data-ttu-id="60c08-111">自定义通道调度程序可扩展 <xref:System.ServiceModel.Dispatcher.ChannelDispatcherBase> 类型。</span><span class="sxs-lookup"><span data-stu-id="60c08-111">The custom channel dispatcher extends the type <xref:System.ServiceModel.Dispatcher.ChannelDispatcherBase>.</span></span> <span data-ttu-id="60c08-112">此类型实现通道层编程逻辑。</span><span class="sxs-lookup"><span data-stu-id="60c08-112">This type implements the channel-layer programming logic.</span></span> <span data-ttu-id="60c08-113">在此示例中，请求-答复消息交换模式仅支持 <xref:System.ServiceModel.Channels.IReplyChannel>，但自定义通道调度程序可轻松扩展为其他通道类型。</span><span class="sxs-lookup"><span data-stu-id="60c08-113">In this sample, only <xref:System.ServiceModel.Channels.IReplyChannel> is supported for request-reply message exchange pattern, but the custom channel dispatcher can be easily extended to other channel types.</span></span>  
  
 <span data-ttu-id="60c08-114">调度程序首先打开通道侦听器，然后接受单一答复通道。</span><span class="sxs-lookup"><span data-stu-id="60c08-114">The dispatcher first opens the channel listener and then accepts the singleton reply channel.</span></span> <span data-ttu-id="60c08-115">通过该通道，调度程序开始在一个无限循环中发送消息（请求）。</span><span class="sxs-lookup"><span data-stu-id="60c08-115">With the channel, it starts to send messages (requests) in an infinite loop.</span></span> <span data-ttu-id="60c08-116">对于每个请求，它都会创建一条答复消息，并将其发送回客户端。</span><span class="sxs-lookup"><span data-stu-id="60c08-116">For each request, it creates a reply message and sends it back to the client.</span></span>  
  
## <a name="creating-a-response-message"></a><span data-ttu-id="60c08-117">创建响应消息</span><span class="sxs-lookup"><span data-stu-id="60c08-117">Creating a Response Message</span></span>  

 <span data-ttu-id="60c08-118">消息处理是在 `MyServiceManager` 类型中实现的。</span><span class="sxs-lookup"><span data-stu-id="60c08-118">The message processing is implemented in the type `MyServiceManager`.</span></span> <span data-ttu-id="60c08-119">在 `HandleRequest` 方法中，将首先检查消息的 `Action` 标头以查看是否支持该请求。</span><span class="sxs-lookup"><span data-stu-id="60c08-119">In the `HandleRequest` method, the `Action` header of the message is first checked to see whether the request is supported.</span></span> <span data-ttu-id="60c08-120">定义了预定义的 SOAP 操作 " http://tempuri.org/HelloWorld/Hello " 以提供消息筛选。</span><span class="sxs-lookup"><span data-stu-id="60c08-120">A predefined SOAP action "http://tempuri.org/HelloWorld/Hello" is defined to provide message filtering.</span></span> <span data-ttu-id="60c08-121">这类似于的 WCF 实现中的服务协定概念 <xref:System.ServiceModel.ServiceHost> 。</span><span class="sxs-lookup"><span data-stu-id="60c08-121">This is similar to the service contract concept in the WCF implementation of <xref:System.ServiceModel.ServiceHost>.</span></span>  
  
 <span data-ttu-id="60c08-122">对于正确的 SOAP 操作情况，此示例将检索请求的消息数据，并生成一个与该请求对应的响应，类似于在 <xref:System.ServiceModel.ServiceHost> 示例中所看到的内容。</span><span class="sxs-lookup"><span data-stu-id="60c08-122">For the correct SOAP action case, the sample retrieves the requested message data and generates a corresponding response to the request similar to what is seen in the <xref:System.ServiceModel.ServiceHost> case.</span></span>  
  
 <span data-ttu-id="60c08-123">在此示例中，通过返回自定义 HTML 消息对 HTTP-GET 谓词进行了特殊处理，以便您可以通过浏览器来浏览服务，查看是否已正确编译该服务。</span><span class="sxs-lookup"><span data-stu-id="60c08-123">You specially handled the HTTP-GET verb by returning a custom HTML message, in this, case so that you can browse the service from a browser to see that it is compiled correctly.</span></span> <span data-ttu-id="60c08-124">如果 SOAP 操作不匹配，则发送回一条错误消息，指示不支持该请求。</span><span class="sxs-lookup"><span data-stu-id="60c08-124">If the SOAP action does not match, send a fault message back to indicate that the request is not supported.</span></span>  
  
 <span data-ttu-id="60c08-125">此示例的客户端是一个普通的 WCF 客户端，它不会假设来自服务的任何内容。</span><span class="sxs-lookup"><span data-stu-id="60c08-125">The client of this sample is a normal WCF client that does not assume anything from the service.</span></span> <span data-ttu-id="60c08-126">因此，该服务经过专门设计，可匹配从普通 WCF 实现获得的内容 <xref:System.ServiceModel.ServiceHost> 。</span><span class="sxs-lookup"><span data-stu-id="60c08-126">So, the service is specially designed to match what you get from a normal WCF<xref:System.ServiceModel.ServiceHost> implementation.</span></span> <span data-ttu-id="60c08-127">因此，在客户端上仅需要一个服务协定。</span><span class="sxs-lookup"><span data-stu-id="60c08-127">As a result, only a service contract is required on the client.</span></span>  
  
## <a name="using-the-sample"></a><span data-ttu-id="60c08-128">使用示例</span><span class="sxs-lookup"><span data-stu-id="60c08-128">Using the sample</span></span>  

 <span data-ttu-id="60c08-129">运行客户端应用程序将直接生成以下输出。</span><span class="sxs-lookup"><span data-stu-id="60c08-129">Running the client application directly produces the following output.</span></span>  
  
```output  
Client is talking to a request/reply WCF service.
Type what you want to say to the server: Howdy  
Server replied: You said: Howdy. Message id: 1  
Server replied: You said: Howdy. Message id: 2  
Server replied: You said: Howdy. Message id: 3  
Server replied: You said: Howdy. Message id: 4  
Server replied: You said: Howdy. Message id: 5  
```  
  
 <span data-ttu-id="60c08-130">还可以通过浏览器来浏览该服务，以便在服务器上处理 HTTP-GET 消息。</span><span class="sxs-lookup"><span data-stu-id="60c08-130">You can also browse the service from a browser so that an HTTP-GET message gets processed on the server.</span></span> <span data-ttu-id="60c08-131">这会让您获得一个格式合理的 HTML 文本。</span><span class="sxs-lookup"><span data-stu-id="60c08-131">This gets you well-formatted HTML text back.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="60c08-132">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="60c08-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="60c08-133">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="60c08-133">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="60c08-134">如果此目录不存在，请参阅[Windows Communication Foundation (wcf) ，并 Windows Workflow Foundation (的 WF](https://www.microsoft.com/download/details.aspx?id=21459)) .NET Framework Windows Communication Foundation ([!INCLUDE[wf1](../../../../includes/wf1-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60c08-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="60c08-135">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="60c08-135">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\CustomChannelDispatcher`
