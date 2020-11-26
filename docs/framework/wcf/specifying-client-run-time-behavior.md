---
title: 指定客户端运行时行为
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- behaviors [WCF], system-provided client
ms.assetid: d16d3405-be70-4edb-8f62-b5f614ddeca5
ms.openlocfilehash: 17031f2100c6760cd14aae57cd4efab7428eb362
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96235891"
---
# <a name="specifying-client-run-time-behavior"></a><span data-ttu-id="9122b-102">指定客户端运行时行为</span><span class="sxs-lookup"><span data-stu-id="9122b-102">Specifying Client Run-Time Behavior</span></span>

<span data-ttu-id="9122b-103">Windows Communication Foundation 可以将 (WCF) 客户端（如 Windows Communication Foundation (WCF) services）配置为修改运行时行为，以适合客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="9122b-103">Windows Communication Foundation (WCF) clients, like Windows Communication Foundation (WCF) services, can be configured to modify the run-time behavior to suit the client application.</span></span> <span data-ttu-id="9122b-104">有三个属性可用于指定客户端运行时行为。</span><span class="sxs-lookup"><span data-stu-id="9122b-104">Three attributes are available for specifying client run-time behavior.</span></span> <span data-ttu-id="9122b-105">双工客户端回调对象可以使用 <xref:System.ServiceModel.CallbackBehaviorAttribute> 和 <xref:System.ServiceModel.Description.CallbackDebugBehavior> 属性修改其运行时行为。</span><span class="sxs-lookup"><span data-stu-id="9122b-105">Duplex client callback objects can use the <xref:System.ServiceModel.CallbackBehaviorAttribute> and <xref:System.ServiceModel.Description.CallbackDebugBehavior> attributes to modify their run-time behavior.</span></span> <span data-ttu-id="9122b-106">另一个属性 <xref:System.ServiceModel.Description.ClientViaBehavior> 可用于将逻辑目标与直接网络目标分开。</span><span class="sxs-lookup"><span data-stu-id="9122b-106">The other attribute, <xref:System.ServiceModel.Description.ClientViaBehavior>, can be used to separate the logical destination from the immediate network destination.</span></span> <span data-ttu-id="9122b-107">此外，双工客户端回调类型可以使用某些服务端行为。</span><span class="sxs-lookup"><span data-stu-id="9122b-107">In addition, duplex client callback types can use some of the service-side behaviors.</span></span> <span data-ttu-id="9122b-108">有关详细信息，请参阅 [指定服务 Run-Time 行为](specifying-service-run-time-behavior.md)。</span><span class="sxs-lookup"><span data-stu-id="9122b-108">For more information, see [Specifying Service Run-Time Behavior](specifying-service-run-time-behavior.md).</span></span>  
  
## <a name="using-the-callbackbehaviorattribute"></a><span data-ttu-id="9122b-109">使用 CallbackBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="9122b-109">Using the CallbackBehaviorAttribute</span></span>  

 <span data-ttu-id="9122b-110">可以使用 <xref:System.ServiceModel.CallbackBehaviorAttribute> 类来配置或扩展客户端应用程序中回调协定实现的执行行为。</span><span class="sxs-lookup"><span data-stu-id="9122b-110">You can configure or extend the execution behavior of a callback contract implementation in a client application by using the <xref:System.ServiceModel.CallbackBehaviorAttribute> class.</span></span> <span data-ttu-id="9122b-111">此属性为回调类和 <xref:System.ServiceModel.ServiceBehaviorAttribute> 类执行相似的功能，不同之处在于实例化行为和事务设置。</span><span class="sxs-lookup"><span data-stu-id="9122b-111">This attribute performs a similar function for the callback class as the <xref:System.ServiceModel.ServiceBehaviorAttribute> class, with the exception of instancing behavior and transaction settings.</span></span>  
  
 <span data-ttu-id="9122b-112">必须将 <xref:System.ServiceModel.CallbackBehaviorAttribute> 类应用于实现回调协定的类。</span><span class="sxs-lookup"><span data-stu-id="9122b-112">The <xref:System.ServiceModel.CallbackBehaviorAttribute> class must be applied to the class that implements the callback contract.</span></span> <span data-ttu-id="9122b-113">如果将其应用于非双工协定实现，则会在运行时引发 <xref:System.InvalidOperationException> 异常。</span><span class="sxs-lookup"><span data-stu-id="9122b-113">If applied to a nonduplex contract implementation, an <xref:System.InvalidOperationException> exception is thrown at run time.</span></span> <span data-ttu-id="9122b-114">下面的代码示例演示回调对象上的一个 <xref:System.ServiceModel.CallbackBehaviorAttribute> 类，该类使用 <xref:System.Threading.SynchronizationContext> 对象确定要封送到的线程，使用 <xref:System.ServiceModel.CallbackBehaviorAttribute.ValidateMustUnderstand%2A> 属性强制执行消息验证，并使用 <xref:System.ServiceModel.CallbackBehaviorAttribute.IncludeExceptionDetailInFaults%2A> 属性将异常作为 <xref:System.ServiceModel.FaultException> 对象返回给服务以便进行调试。</span><span class="sxs-lookup"><span data-stu-id="9122b-114">The following code example shows a <xref:System.ServiceModel.CallbackBehaviorAttribute> class on a callback object that uses the <xref:System.Threading.SynchronizationContext> object to determine the thread to marshal to, the <xref:System.ServiceModel.CallbackBehaviorAttribute.ValidateMustUnderstand%2A> property to enforce message validation, and the <xref:System.ServiceModel.CallbackBehaviorAttribute.IncludeExceptionDetailInFaults%2A> property to return exceptions as <xref:System.ServiceModel.FaultException> objects to the service for debugging purposes.</span></span>  
  
 [!code-csharp[CallbackBehaviorAttribute#3](../../../samples/snippets/csharp/VS_Snippets_CFX/callbackbehaviorattribute/cs/client.cs#3)]
 [!code-vb[CallbackBehaviorAttribute#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/callbackbehaviorattribute/vb/client.vb#3)]  
  
## <a name="using-callbackdebugbehavior-to-enable-the-flow-of-managed-exception-information"></a><span data-ttu-id="9122b-115">使用 CallbackDebugBehavior 启用托管异常信息流</span><span class="sxs-lookup"><span data-stu-id="9122b-115">Using CallbackDebugBehavior to Enable the Flow of Managed Exception Information</span></span>  

 <span data-ttu-id="9122b-116">可以在客户端回调对象中启用托管异常信息流，使异常信息流回到服务以便进行调试，方法是以编程方式或从应用程序配置文件中将 <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="9122b-116">You can enable the flow of managed exception information in a client callback object back to the service for debugging purposes by setting the <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A> property to `true` either programmatically or from an application configuration file.</span></span>  
  
 <span data-ttu-id="9122b-117">将托管异常信息返回到服务可能存在安全风险，因为异常详细信息会公开与内部客户端实现有关的信息，而未经授权的服务可能会使用这些信息。</span><span class="sxs-lookup"><span data-stu-id="9122b-117">Returning managed exception information to services can be a security risk because exception details expose information about the internal client implementation that  unauthorized services could use.</span></span> <span data-ttu-id="9122b-118">此外，虽然 <xref:System.ServiceModel.Description.CallbackDebugBehavior> 属性也可以通过编程方式进行设置，但在部署时容易忘记禁用 <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A>。</span><span class="sxs-lookup"><span data-stu-id="9122b-118">In addition, although the <xref:System.ServiceModel.Description.CallbackDebugBehavior> properties can also be set programmatically, it can be easy to forget to disable <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A> when deploying.</span></span>  
  
 <span data-ttu-id="9122b-119">由于涉及到一些安全问题，因此强烈建议您：</span><span class="sxs-lookup"><span data-stu-id="9122b-119">Because of the security issues involved, it is strongly recommended that:</span></span>  
  
- <span data-ttu-id="9122b-120">使用应用程序配置文件将 <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A> 属性的值设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="9122b-120">You use an application configuration file to set the value of the <xref:System.ServiceModel.Description.CallbackDebugBehavior.IncludeExceptionDetailInFaults%2A> property to `true`.</span></span>  
  
- <span data-ttu-id="9122b-121">仅在受控调试方案中才能这样做。</span><span class="sxs-lookup"><span data-stu-id="9122b-121">You do so only in controlled debugging scenarios.</span></span>  
  
 <span data-ttu-id="9122b-122">下面的代码示例演示一个客户端配置文件，该文件指示 WCF 从 SOAP 消息中的客户端回调对象返回托管异常信息。</span><span class="sxs-lookup"><span data-stu-id="9122b-122">The following code example shows a client configuration file that instructs WCF to return managed exception information from a client callback object in SOAP messages.</span></span>  
  
 [!code-xml[SCA.CallbackContract#4](../../../samples/snippets/csharp/VS_Snippets_CFX/sca.callbackcontract/cs/client.exe.config#4)]  

## <a name="using-the-clientviabehavior-behavior"></a><span data-ttu-id="9122b-123">使用 ClientViaBehavior 行为</span><span class="sxs-lookup"><span data-stu-id="9122b-123">Using the ClientViaBehavior Behavior</span></span>  

 <span data-ttu-id="9122b-124">可以使用 <xref:System.ServiceModel.Description.ClientViaBehavior> 行为指定应为其创建传输通道的统一资源标识符。</span><span class="sxs-lookup"><span data-stu-id="9122b-124">You can use the <xref:System.ServiceModel.Description.ClientViaBehavior> behavior to specify the Uniform Resource Identifier for which the transport channel should be created.</span></span> <span data-ttu-id="9122b-125">当直接网络目标不是消息的预期处理者时，可使用此行为。</span><span class="sxs-lookup"><span data-stu-id="9122b-125">Use this behavior when the immediate network destination is not the intended processor of the message.</span></span> <span data-ttu-id="9122b-126">当调用应用程序不需要知道最终目标时，或者当目标 `Via` 标头不是地址时，使用此行为可启用多跃点对话。</span><span class="sxs-lookup"><span data-stu-id="9122b-126">This enables multiple-hop conversations when the calling application does not necessarily know the ultimate destination or when the destination `Via` header is not an address.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9122b-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9122b-127">See also</span></span>

- [<span data-ttu-id="9122b-128">指定服务运行时行为</span><span class="sxs-lookup"><span data-stu-id="9122b-128">Specifying Service Run-Time Behavior</span></span>](specifying-service-run-time-behavior.md)
