---
title: 扩展性介绍
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], extensibility
- Windows Communication Foundation [WCF], extensibility
- extensibility [WCF]
ms.assetid: ef56c251-d63c-4b3f-944f-b0c67bfb0f68
ms.openlocfilehash: 8f4cc490df49a91e448c02fef370ce828536f907
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262718"
---
# <a name="introduction-to-extensibility"></a><span data-ttu-id="ec42d-102">扩展性介绍</span><span class="sxs-lookup"><span data-stu-id="ec42d-102">Introduction to Extensibility</span></span>

<span data-ttu-id="ec42d-103">Windows Communication Foundation (WCF) 应用程序模型设计用于解决任何分布式应用程序的通信要求的更大一部分。</span><span class="sxs-lookup"><span data-stu-id="ec42d-103">The Windows Communication Foundation (WCF) application model is designed to solve the greater part of the communication requirements of any distributed application.</span></span> <span data-ttu-id="ec42d-104">但是，总是会存在一些默认应用程序模型和系统提供的实现不支持的情况。</span><span class="sxs-lookup"><span data-stu-id="ec42d-104">But there are always scenarios that the default application model and system-provided implementations do not support.</span></span> <span data-ttu-id="ec42d-105">WCF 扩展性模型旨在支持自定义方案，使您可以在每个级别修改系统行为，甚至替换整个应用程序模型。</span><span class="sxs-lookup"><span data-stu-id="ec42d-105">The WCF extensibility model is intended to support custom scenarios by enabling you to modify system behavior at every level, even to the point of replacing the entire application model.</span></span> <span data-ttu-id="ec42d-106">本主题概述各个扩展范围并指出关于每个范围的更多信息。</span><span class="sxs-lookup"><span data-stu-id="ec42d-106">This topic outlines the various areas of extension and points to more information about each.</span></span>  
  
## <a name="areas-to-extend"></a><span data-ttu-id="ec42d-107">要扩展的范围</span><span class="sxs-lookup"><span data-stu-id="ec42d-107">Areas to Extend</span></span>  

 <span data-ttu-id="ec42d-108">可以扩展：</span><span class="sxs-lookup"><span data-stu-id="ec42d-108">You can extend:</span></span>  
  
- <span data-ttu-id="ec42d-109">应用程序运行库。</span><span class="sxs-lookup"><span data-stu-id="ec42d-109">The application runtime.</span></span> <span data-ttu-id="ec42d-110">这将扩展应用程序消息的调度和处理。</span><span class="sxs-lookup"><span data-stu-id="ec42d-110">This extends the dispatching and the processing of messages for the application.</span></span> <span data-ttu-id="ec42d-111">此范围还包括扩展安全系统、元数据系统、序列化系统以及将应用程序与基础通道系统相连的绑定和绑定元素。</span><span class="sxs-lookup"><span data-stu-id="ec42d-111">This area also includes extending the security system, the metadata system, the serialization system, and the bindings and binding elements that connect the application with the underlying channel system.</span></span>  
  
- <span data-ttu-id="ec42d-112">通道和通道运行库。</span><span class="sxs-lookup"><span data-stu-id="ec42d-112">The channel and channel runtime.</span></span> <span data-ttu-id="ec42d-113">这将扩展在消息级别运行的系统，用于提供协议、传输和编码支持。</span><span class="sxs-lookup"><span data-stu-id="ec42d-113">This extends the system that functions at the message level, providing protocol, transport, and encoding support.</span></span>  
  
- <span data-ttu-id="ec42d-114">主机运行库。</span><span class="sxs-lookup"><span data-stu-id="ec42d-114">The host runtime.</span></span> <span data-ttu-id="ec42d-115">此范围将主机应用程序域的关系扩展到通道和应用程序运行库。</span><span class="sxs-lookup"><span data-stu-id="ec42d-115">This extends the relationship of the hosting application domain to the channel and application runtime.</span></span>  
  
### <a name="extending-the-application-runtime"></a><span data-ttu-id="ec42d-116">扩展应用程序运行库</span><span class="sxs-lookup"><span data-stu-id="ec42d-116">Extending the Application Runtime</span></span>  

 <span data-ttu-id="ec42d-117">在 WCF 应用程序中，对于发送到相应通道的消息和发往应用程序本身的消息，会有区别。</span><span class="sxs-lookup"><span data-stu-id="ec42d-117">In WCF applications, there is a distinction between messages that are destined for a corresponding channel and messages that are destined for the application itself.</span></span> <span data-ttu-id="ec42d-118">通道消息支持某些与通道相关的功能，如建立安全对话或可靠会话。</span><span class="sxs-lookup"><span data-stu-id="ec42d-118">Channel messages support some channel-related functionality, such as establishing a secure conversation or establishing a reliable session.</span></span> <span data-ttu-id="ec42d-119">这些消息对于应用程序运行库不可用；涉及应用程序层之前，将处理这些消息。</span><span class="sxs-lookup"><span data-stu-id="ec42d-119">These messages are not available to the application runtime; they are processed before the application layer is involved.</span></span>  
  
 <span data-ttu-id="ec42d-120">应用程序消息中包含发往客户端或发往您或您的客户创建的服务操作的数据。</span><span class="sxs-lookup"><span data-stu-id="ec42d-120">Application messages contain data that is destined for a client or service operation that you or your customer has created.</span></span> <span data-ttu-id="ec42d-121">这些消息可用于采用消息或对象形式的应用程序级扩展系统，具体取决于您的需要。</span><span class="sxs-lookup"><span data-stu-id="ec42d-121">These messages are available to the application-level extension system in message or object form, depending upon your needs.</span></span>  
  
 <span data-ttu-id="ec42d-122">所有消息都通过通道系统传递；只有应用程序消息是从通道系统传入应用程序的。</span><span class="sxs-lookup"><span data-stu-id="ec42d-122">All messages pass through the channel system; only application messages are passed from the channel system into the application.</span></span> <span data-ttu-id="ec42d-123">若要创建新的通道级功能，必须扩展通道系统。</span><span class="sxs-lookup"><span data-stu-id="ec42d-123">To create new channel-level functionality, you must extend the channel system.</span></span> <span data-ttu-id="ec42d-124">若要创建新的应用程序级功能，必须扩展服务或客户端运行库（分别为调度程序和通道工厂）。</span><span class="sxs-lookup"><span data-stu-id="ec42d-124">To create new application-level functionality, you must extend the service or client runtime (dispatchers and channel factories, respectively).</span></span> <span data-ttu-id="ec42d-125">有关扩展应用程序运行时的详细信息，请参阅 [扩展 ServiceHost 和服务模型层](./extending/extending-servicehost-and-the-service-model-layer.md)。</span><span class="sxs-lookup"><span data-stu-id="ec42d-125">For more information about extending the application runtime, see [Extending ServiceHost and the Service Model Layer](./extending/extending-servicehost-and-the-service-model-layer.md).</span></span>  
  
#### <a name="extending-security"></a><span data-ttu-id="ec42d-126">扩展安全性</span><span class="sxs-lookup"><span data-stu-id="ec42d-126">Extending Security</span></span>  

 <span data-ttu-id="ec42d-127">若要生成自定义安全机制（如令牌和凭据），必须扩展安全系统。</span><span class="sxs-lookup"><span data-stu-id="ec42d-127">To build custom security mechanisms such as tokens and credentials, you must extend the security system.</span></span> <span data-ttu-id="ec42d-128">有关详细信息，请参阅 [扩展安全性](./extending/extending-security.md)。</span><span class="sxs-lookup"><span data-stu-id="ec42d-128">For more information, see [Extending Security](./extending/extending-security.md).</span></span>  
  
#### <a name="extending-metadata"></a><span data-ttu-id="ec42d-129">扩展元数据</span><span class="sxs-lookup"><span data-stu-id="ec42d-129">Extending Metadata</span></span>  

 <span data-ttu-id="ec42d-130">若要以非默认方式公开元数据，必须扩展元数据系统。</span><span class="sxs-lookup"><span data-stu-id="ec42d-130">To expose your metadata in differently than the default, you must extend the metadata system.</span></span> <span data-ttu-id="ec42d-131">有关详细信息，请参阅 [扩展元数据系统](./extending/extending-the-metadata-system.md)。</span><span class="sxs-lookup"><span data-stu-id="ec42d-131">For more information, see [Extending the Metadata System](./extending/extending-the-metadata-system.md).</span></span>  
  
#### <a name="extending-serialization"></a><span data-ttu-id="ec42d-132">扩展序列化</span><span class="sxs-lookup"><span data-stu-id="ec42d-132">Extending Serialization</span></span>  

 <span data-ttu-id="ec42d-133">若要生成自定义编码器、提供数据代理项或涉及自定义传输数据的其他工作，必须扩展序列化系统。</span><span class="sxs-lookup"><span data-stu-id="ec42d-133">To build custom encoders, provide data surrogates, or other work involving the customization of transferred data, you must extend the serialization system.</span></span> <span data-ttu-id="ec42d-134">有关详细信息，请参阅 [扩展编码器和序列化](./extending/extending-encoders-and-serializers.md)程序。</span><span class="sxs-lookup"><span data-stu-id="ec42d-134">For more information, see [Extending Encoders and Serializers](./extending/extending-encoders-and-serializers.md).</span></span>  
  
#### <a name="extending-bindings"></a><span data-ttu-id="ec42d-135">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="ec42d-135">Extending Bindings</span></span>  

 <span data-ttu-id="ec42d-136">若要将传输通道或协议通道与应用程序层关联，必须扩展绑定系统。</span><span class="sxs-lookup"><span data-stu-id="ec42d-136">To associate transport or protocol channels with the application layer, you must extend the binding system.</span></span> <span data-ttu-id="ec42d-137">有关详细信息，请参阅 [扩展绑定](./extending/extending-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="ec42d-137">For more information, see [Extending Bindings](./extending/extending-bindings.md).</span></span>  
  
### <a name="extending-the-channel-system"></a><span data-ttu-id="ec42d-138">扩展通道系统</span><span class="sxs-lookup"><span data-stu-id="ec42d-138">Extending the Channel System</span></span>  

 <span data-ttu-id="ec42d-139">若要创建支持自定义传输或协议功能的通道，请参阅 [扩展通道层](./extending/extending-the-channel-layer.md)。</span><span class="sxs-lookup"><span data-stu-id="ec42d-139">To create channels that support custom transports or protocol functionality, see [Extending the Channel Layer](./extending/extending-the-channel-layer.md).</span></span>  
  
### <a name="extending-the-service-hosting-system"></a><span data-ttu-id="ec42d-140">扩展服务主机系统</span><span class="sxs-lookup"><span data-stu-id="ec42d-140">Extending the Service Hosting System</span></span>  

 <span data-ttu-id="ec42d-141">若要修改服务范围的应用程序模型，必须扩展 <xref:System.ServiceModel.ServiceHostBase?displayProperty=nameWithType> 类。</span><span class="sxs-lookup"><span data-stu-id="ec42d-141">To modify the service-wide application model, you must extend <xref:System.ServiceModel.ServiceHostBase?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="ec42d-142">有关详细信息，请参阅 [扩展 ServiceHost 和服务模型层](./extending/extending-servicehost-and-the-service-model-layer.md)。</span><span class="sxs-lookup"><span data-stu-id="ec42d-142">For more information, see [Extending ServiceHost and the Service Model Layer](./extending/extending-servicehost-and-the-service-model-layer.md).</span></span>  
  
 <span data-ttu-id="ec42d-143">若要修改主机应用程序域和服务主机之间的关系，必须扩展 <xref:System.ServiceModel.Activation.ServiceHostFactory?displayProperty=nameWithType> 类。</span><span class="sxs-lookup"><span data-stu-id="ec42d-143">To modify the relationship between the hosting application domain and the service host, you must extend the <xref:System.ServiceModel.Activation.ServiceHostFactory?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="ec42d-144">有关详细信息，请参阅 [使用 ServiceHostFactory 扩展托管](./extending/extending-hosting-using-servicehostfactory.md)。</span><span class="sxs-lookup"><span data-stu-id="ec42d-144">For more information, see [Extending Hosting Using ServiceHostFactory](./extending/extending-hosting-using-servicehostfactory.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec42d-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec42d-145">See also</span></span>

- [<span data-ttu-id="ec42d-146">扩展 WCF</span><span class="sxs-lookup"><span data-stu-id="ec42d-146">Extending WCF</span></span>](./extending/index.md)
