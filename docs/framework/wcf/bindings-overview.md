---
title: Windows Communication Foundation 绑定概述
description: 了解绑定，该绑定指定如何连接到 WCF 服务，其中包括绑定的元素，以及如何指定服务终结点的绑定。
ms.date: 03/30/2017
helpviewer_keywords:
- bindings [WCF], overview
ms.assetid: cfb5842f-e0f9-4c56-a015-f2b33f258232
ms.openlocfilehash: e918844342a20e7b6c22ef6a9fd3c01fe27db059
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272470"
---
# <a name="windows-communication-foundation-bindings-overview"></a><span data-ttu-id="ecb9e-103">Windows Communication Foundation 绑定概述</span><span class="sxs-lookup"><span data-stu-id="ecb9e-103">Windows Communication Foundation Bindings Overview</span></span>

<span data-ttu-id="ecb9e-104">绑定是用于指定连接到 Windows Communication Foundation (WCF) 服务的终结点所需的通信详细信息的对象。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-104">Bindings are objects that are used to specify the communication details that are required to connect to the endpoint of a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="ecb9e-105">WCF 服务中的每个端点都需要一个具体指定的绑定。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-105">Each endpoint in a WCF service requires a binding to be well-specified.</span></span> <span data-ttu-id="ecb9e-106">本主题概述绑定定义的通信详细信息的类型、绑定的元素、WCF 中包含的绑定以及如何为终结点指定绑定。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-106">This topic outlines the types of communication details that the bindings define, the elements of a binding, what bindings are included in WCF, and how a binding can be specified for an endpoint.</span></span>  
  
## <a name="what-a-binding-defines"></a><span data-ttu-id="ecb9e-107">绑定所定义的内容</span><span class="sxs-lookup"><span data-stu-id="ecb9e-107">What a Binding Defines</span></span>  

 <span data-ttu-id="ecb9e-108">绑定中的信息可能非常基本，也可能非常复杂。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-108">The information in a binding can be very basic, or very complex.</span></span> <span data-ttu-id="ecb9e-109">最基本的绑定仅指定连接终结点所必需的传输协议（如 HTTP）。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-109">The most basic binding specifies only the transport protocol (such as HTTP) that must be used to connect to the endpoint.</span></span> <span data-ttu-id="ecb9e-110">一般来说，绑定包含的有关如何连接到终结点的信息属于以下类别之一：</span><span class="sxs-lookup"><span data-stu-id="ecb9e-110">More generally, the information a binding contains about how to connect to an endpoint falls into one of the following categories:</span></span>  
  
 <span data-ttu-id="ecb9e-111">**协议**</span><span class="sxs-lookup"><span data-stu-id="ecb9e-111">**Protocols**</span></span>  
 <span data-ttu-id="ecb9e-112">确定要使用的安全机制：可靠消息传递功能或事务上下文流设置。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-112">Determines the security mechanism being used: either reliable messaging capability or transaction context flow settings.</span></span>  
  
 <span data-ttu-id="ecb9e-113">**编码**</span><span class="sxs-lookup"><span data-stu-id="ecb9e-113">**Encoding**</span></span>  
 <span data-ttu-id="ecb9e-114">确定消息编码（例如，文本或二进制）。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-114">Determines the message encoding (for example, text or binary).</span></span>  
  
 <span data-ttu-id="ecb9e-115">**Transport**</span><span class="sxs-lookup"><span data-stu-id="ecb9e-115">**Transport**</span></span>  
 <span data-ttu-id="ecb9e-116">确定要使用的基础传输协议（例如，TCP 或 HTTP）。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-116">Determines the underlying transport protocol to use (for example, TCP or HTTP).</span></span>  
  
## <a name="the-elements-of-a-binding"></a><span data-ttu-id="ecb9e-117">绑定的元素</span><span class="sxs-lookup"><span data-stu-id="ecb9e-117">The Elements of a Binding</span></span>  

 <span data-ttu-id="ecb9e-118">绑定基本上由绑定元素的有序堆栈组成，其中每个元素都指定了连接到服务终结点所必需的通信信息的一部分。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-118">A binding basically consists of an ordered stack of binding elements, each of which specifies part of the communication information required to connect to a service endpoint.</span></span> <span data-ttu-id="ecb9e-119">该堆栈中最底下的两层都是必需的。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-119">The two lowest layers in the stack are both required.</span></span> <span data-ttu-id="ecb9e-120">该堆栈的最底层为传输绑定元素，而紧挨着它的上面一层为包含消息编码规范的元素。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-120">At the base of the stack is the transport binding element and just above this is the element that contains the message encoding specifications.</span></span> <span data-ttu-id="ecb9e-121">用于指定其他通信协议的可选绑定元素位于这两个必需元素的上面。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-121">The optional binding elements that specify the other communication protocols are layered above these two required elements.</span></span> <span data-ttu-id="ecb9e-122">有关这些绑定元素及其正确排序的详细信息，请参阅 [自定义绑定](./extending/custom-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-122">For more information about these binding elements and their correct ordering, see [Custom Bindings](./extending/custom-bindings.md).</span></span>  
  
## <a name="system-provided-bindings"></a><span data-ttu-id="ecb9e-123">系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="ecb9e-123">System-Provided Bindings</span></span>  

 <span data-ttu-id="ecb9e-124">绑定中的信息可能十分复杂，而且某些设置可能与其他设置不兼容。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-124">The information in a binding can be complex, and some settings may not be compatible with others.</span></span> <span data-ttu-id="ecb9e-125">出于此原因，WCF 包含一组系统提供的绑定。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-125">For this reason, WCF includes a set of system-provided bindings.</span></span> <span data-ttu-id="ecb9e-126">这些绑定旨在满足大多数应用程序需求。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-126">These bindings are designed to cover most application requirements.</span></span> <span data-ttu-id="ecb9e-127">下面的类表示系统提供的绑定的一些示例：</span><span class="sxs-lookup"><span data-stu-id="ecb9e-127">The following classes represent some examples of system-provided bindings:</span></span>  
  
- <span data-ttu-id="ecb9e-128"><xref:System.ServiceModel.BasicHttpBinding>：一个 HTTP 协议绑定，适用于连接到符合 WS-I 基本配置文件规范的 Web 服务（例如，基于 ASP.NET Web 服务的服务）。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-128"><xref:System.ServiceModel.BasicHttpBinding>: An HTTP protocol binding suitable for connecting to Web services that conforms to the WS-I Basic Profile specification (for example, ASP.NET Web services-based services).</span></span>  
  
- <span data-ttu-id="ecb9e-129"><xref:System.ServiceModel.WSHttpBinding>：一个可互操作的绑定，适用于连接到符合 WS-\* 协议的终结点。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-129"><xref:System.ServiceModel.WSHttpBinding>: An interoperable binding suitable for connecting to endpoints that conform to the WS-\* protocols.</span></span>  
  
- <span data-ttu-id="ecb9e-130"><xref:System.ServiceModel.NetNamedPipeBinding>：使用 .NET Framework 连接到同一计算机上的其他 WCF 终结点。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-130"><xref:System.ServiceModel.NetNamedPipeBinding>: Uses the .NET Framework to connect to other WCF endpoints on the same machine.</span></span>  
  
- <span data-ttu-id="ecb9e-131"><xref:System.ServiceModel.NetMsmqBinding>：使用 .NET Framework 创建与其他 WCF 终结点的排队消息连接。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-131"><xref:System.ServiceModel.NetMsmqBinding>: Uses the .NET Framework to create queued message connections with other WCF endpoints.</span></span>  

- <span data-ttu-id="ecb9e-132"><xref:System.ServiceModel.NetTcpBinding>：此绑定提供比 HTTP 绑定更高的性能，非常适合在本地网络中使用。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-132"><xref:System.ServiceModel.NetTcpBinding>: This binding offers higher performance than HTTP bindings and is ideal for use in a local network.</span></span>
  
 <span data-ttu-id="ecb9e-133">有关 WCF 提供的所有绑定的完整列表，请参阅 [系统提供的绑定](system-provided-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-133">For a complete list, with descriptions, of all the WCF-provided bindings, see [System-Provided Bindings](system-provided-bindings.md).</span></span>  
  
## <a name="using-your-own-bindings"></a><span data-ttu-id="ecb9e-134">使用自己的绑定</span><span class="sxs-lookup"><span data-stu-id="ecb9e-134">Using Your Own Bindings</span></span>  

 <span data-ttu-id="ecb9e-135">如果系统提供的绑定都不具有服务应用程序所需的正确功能组合，则可以创建自己的绑定。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-135">If none of the system-provided bindings included has the right combination of features that a service application requires, you can create your own binding.</span></span> <span data-ttu-id="ecb9e-136">可通过两种方式来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-136">There are two ways to do this.</span></span> <span data-ttu-id="ecb9e-137">您可以使用 <xref:System.ServiceModel.Channels.CustomBinding> 对象从预先存在的绑定元素创建新的绑定，也可以通过从 <xref:System.ServiceModel.Channels.Binding> 绑定派生来创建完全由用户定义的绑定。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-137">You can either create a new binding from pre-existing binding elements using a <xref:System.ServiceModel.Channels.CustomBinding> object or you can create a completely user-defined binding by deriving from the <xref:System.ServiceModel.Channels.Binding> binding.</span></span> <span data-ttu-id="ecb9e-138">有关使用这两种方法创建自己的绑定的详细信息，请参阅 [自定义绑定](./extending/custom-bindings.md) 和 [创建 User-Defined 绑定](./extending/creating-user-defined-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-138">For more information about creating your own binding using these two approaches, see [Custom Bindings](./extending/custom-bindings.md) and [Creating User-Defined Bindings](./extending/creating-user-defined-bindings.md).</span></span>  
  
## <a name="using-bindings"></a><span data-ttu-id="ecb9e-139">使用绑定</span><span class="sxs-lookup"><span data-stu-id="ecb9e-139">Using Bindings</span></span>  

 <span data-ttu-id="ecb9e-140">使用绑定需要执行两个基本步骤：</span><span class="sxs-lookup"><span data-stu-id="ecb9e-140">Using bindings entails two basic steps:</span></span>  
  
1. <span data-ttu-id="ecb9e-141">选择或定义绑定。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-141">Select or define a binding.</span></span> <span data-ttu-id="ecb9e-142">最简单的方法是选择 WCF 中包含的系统提供的绑定之一，并将其与默认设置一起使用。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-142">The easiest method is to choose one of the system-provided bindings included with WCF and use it with its default settings.</span></span> <span data-ttu-id="ecb9e-143">您还可以选择一个系统提供的绑定，然后根据您的要求重新设置它的属性值。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-143">You can also choose a system-provided binding and reset its property values to suit your requirements.</span></span> <span data-ttu-id="ecb9e-144">或者，你可以创建一个自定义绑定或用户定义的绑定，以实现更高程度的控制和自定义。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-144">Alternatively, you can create a custom binding or a user-defined binding to have higher degrees of control and customization.</span></span>  
  
2. <span data-ttu-id="ecb9e-145">创建一个使用所选择或定义的绑定的终结点。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-145">Create an endpoint that uses the binding selected or defined.</span></span>  
  
## <a name="code-and-configuration"></a><span data-ttu-id="ecb9e-146">代码和配置</span><span class="sxs-lookup"><span data-stu-id="ecb9e-146">Code and Configuration</span></span>  

 <span data-ttu-id="ecb9e-147">可以通过两种方式来定义绑定：通过代码或通过配置。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-147">You can define bindings in two ways: through code or through configuration.</span></span> <span data-ttu-id="ecb9e-148">这两种方法与你使用的是系统提供的绑定还是自定义绑定无关。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-148">These two approaches do not depend on whether you are using a system-provided binding or a custom binding.</span></span> <span data-ttu-id="ecb9e-149">通常，使用代码可以使你在设计时对绑定的定义拥有完全的控制。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-149">In general, using code gives you complete control over the definition of a binding at design time.</span></span> <span data-ttu-id="ecb9e-150">另一方面，使用配置允许系统管理员或 WCF 服务或客户端的用户更改绑定的参数，而无需重新编译服务应用程序。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-150">Using configuration, on the other hand, allows a system administrator or the user of a WCF service or client to change the parameters of a binding without having to recompile the service application.</span></span> <span data-ttu-id="ecb9e-151">这种灵活性通常是必需的，因为无法预测要在其上部署 WCF 应用程序的特定计算机要求。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-151">This flexibility is often desirable because there is no way to predict specific machine requirements on which a WCF application is to be deployed.</span></span> <span data-ttu-id="ecb9e-152">通过将绑定（和寻址）信息保持在代码外部，人们可以更改这些信息，而不必重新编译或重新部署应用程序。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-152">Keeping the binding (and the addressing) information out of the code allows them to change without requiring recompilation or redeployment of the application.</span></span> <span data-ttu-id="ecb9e-153">请注意，代码中定义的绑定是在配置中指定的绑定之后创建的，这使得代码定义的绑定可以覆盖配置中定义的任何绑定。</span><span class="sxs-lookup"><span data-stu-id="ecb9e-153">Note that bindings defined in code are created after bindings specified in configuration, allowing the code-defined bindings to overwrite any configuration-defined bindings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecb9e-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ecb9e-154">See also</span></span>

- [<span data-ttu-id="ecb9e-155">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="ecb9e-155">Using Bindings to Configure Services and Clients</span></span>](using-bindings-to-configure-services-and-clients.md)
