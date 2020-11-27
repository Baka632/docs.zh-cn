---
title: 如何：创建自定义客户端标识验证工具
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f2d34e43-fa8b-46d2-91cf-d2960e13e16b
ms.openlocfilehash: 84982aca06bacb5718855602872fe4dab2376a9d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256061"
---
# <a name="how-to-create-a-custom-client-identity-verifier"></a><span data-ttu-id="a9359-102">如何：创建自定义客户端标识验证工具</span><span class="sxs-lookup"><span data-stu-id="a9359-102">How to: Create a Custom Client Identity Verifier</span></span>

<span data-ttu-id="a9359-103">Windows Communication Foundation 的 *标识* 功能 (WCF) 使客户端能够预先指定服务的预期标识。</span><span class="sxs-lookup"><span data-stu-id="a9359-103">The *identity* feature of Windows Communication Foundation (WCF) enables a client to specify in advance the expected identity of the service.</span></span> <span data-ttu-id="a9359-104">无论服务器何时向客户端验证其自身身份，都将检查该标识是否为所需的标识。</span><span class="sxs-lookup"><span data-stu-id="a9359-104">Whenever a server authenticates itself to the client, the identity is checked against the expected identity.</span></span> <span data-ttu-id="a9359-105"> (有关标识及其工作原理的说明，请参阅 [服务标识和身份验证](../feature-details/service-identity-and-authentication.md)。 ) </span><span class="sxs-lookup"><span data-stu-id="a9359-105">(For an explanation of identity and how it works, see [Service Identity and Authentication](../feature-details/service-identity-and-authentication.md).)</span></span>  
  
 <span data-ttu-id="a9359-106">如果需要，可使用自定义标识验证工具自定义该验证。</span><span class="sxs-lookup"><span data-stu-id="a9359-106">If needed, the verification can be customized using a custom identity verifier.</span></span> <span data-ttu-id="a9359-107">例如，您可以执行其他服务标识验证检查。</span><span class="sxs-lookup"><span data-stu-id="a9359-107">For example, you can perform additional service identity verification checks.</span></span> <span data-ttu-id="a9359-108">在本示例中，自定义标识验证工具将检查从服务器返回的 X.509 证书中的其他声明。</span><span class="sxs-lookup"><span data-stu-id="a9359-108">In this example, the custom identity verifier checks additional claims in the X.509 certificate returned from the server.</span></span> <span data-ttu-id="a9359-109">有关示例应用程序，请参阅 [服务标识示例](../samples/service-identity-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="a9359-109">For a sample application, see [Service Identity Sample](../samples/service-identity-sample.md).</span></span>  
  
### <a name="to-extend-the-endpointidentity-class"></a><span data-ttu-id="a9359-110">扩展 EndpointIdentity 类</span><span class="sxs-lookup"><span data-stu-id="a9359-110">To extend the EndpointIdentity class</span></span>  
  
1. <span data-ttu-id="a9359-111">定义一个从 <xref:System.ServiceModel.EndpointIdentity> 类派生的新类。</span><span class="sxs-lookup"><span data-stu-id="a9359-111">Define a new class that derives from the <xref:System.ServiceModel.EndpointIdentity> class.</span></span> <span data-ttu-id="a9359-112">本示例将此扩展命名为 `OrgEndpointIdentity`。</span><span class="sxs-lookup"><span data-stu-id="a9359-112">This example names the extension `OrgEndpointIdentity`.</span></span>  
  
2. <span data-ttu-id="a9359-113">添加私有成员和属性，扩展的 <xref:System.ServiceModel.Security.IdentityVerifier> 类将使用这些属性根据从服务返回的安全令牌中的声明执行标识检查。</span><span class="sxs-lookup"><span data-stu-id="a9359-113">Add private members along with properties that will be used by the extended <xref:System.ServiceModel.Security.IdentityVerifier> class to perform the identity check against claims in the security token returned from the service.</span></span> <span data-ttu-id="a9359-114">本示例定义一个属性：`OrganizationClaim` 属性。</span><span class="sxs-lookup"><span data-stu-id="a9359-114">This example defines one property: the `OrganizationClaim` property.</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#6)]
     [!code-vb[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#6)]  
  
### <a name="to-extend-the-identityverifier-class"></a><span data-ttu-id="a9359-115">扩展 IdentityVerifier 类</span><span class="sxs-lookup"><span data-stu-id="a9359-115">To extend the IdentityVerifier class</span></span>  
  
1. <span data-ttu-id="a9359-116">定义一个从 <xref:System.ServiceModel.Security.IdentityVerifier> 派生的新类。</span><span class="sxs-lookup"><span data-stu-id="a9359-116">Define a new class that derives from <xref:System.ServiceModel.Security.IdentityVerifier>.</span></span> <span data-ttu-id="a9359-117">本示例将此扩展命名为 `CustomIdentityVerifier`。</span><span class="sxs-lookup"><span data-stu-id="a9359-117">This example names the extension `CustomIdentityVerifier`.</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#7)]
     [!code-vb[c_HowToSetCustomClientIdentity#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#7)]  
  
2. <span data-ttu-id="a9359-118">重写 <xref:System.ServiceModel.Security.IdentityVerifier.CheckAccess%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="a9359-118">Override the <xref:System.ServiceModel.Security.IdentityVerifier.CheckAccess%2A> method.</span></span> <span data-ttu-id="a9359-119">该方法确定标识检查是成功还是失败。</span><span class="sxs-lookup"><span data-stu-id="a9359-119">The method determines whether the identity check succeeded or failed.</span></span>  
  
3. <span data-ttu-id="a9359-120">`CheckAccess` 方法有两个参数。</span><span class="sxs-lookup"><span data-stu-id="a9359-120">The `CheckAccess` method has two parameters.</span></span> <span data-ttu-id="a9359-121">第一个参数是 <xref:System.ServiceModel.EndpointIdentity> 类的一个实例。</span><span class="sxs-lookup"><span data-stu-id="a9359-121">The first is an instance of the <xref:System.ServiceModel.EndpointIdentity> class.</span></span> <span data-ttu-id="a9359-122">第二个参数是 <xref:System.IdentityModel.Policy.AuthorizationContext> 类的一个实例。</span><span class="sxs-lookup"><span data-stu-id="a9359-122">The second is an instance of the <xref:System.IdentityModel.Policy.AuthorizationContext> class.</span></span>  
  
     <span data-ttu-id="a9359-123">在方法的实现过程中，检查 <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> 类的 <xref:System.IdentityModel.Policy.AuthorizationContext> 属性返回的声明集合，并根据需要执行身份验证检查。</span><span class="sxs-lookup"><span data-stu-id="a9359-123">In the method implementation, examine the collection of claims returned by the <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> property of the <xref:System.IdentityModel.Policy.AuthorizationContext> class, and perform authentication checks as required.</span></span> <span data-ttu-id="a9359-124">本示例首先查找类型为“可分辨名称”的任何声明，然后将此名称与 <xref:System.ServiceModel.EndpointIdentity> 扩展的名称 (`OrgEndpointIdentity`) 进行比较。</span><span class="sxs-lookup"><span data-stu-id="a9359-124">This example begins by finding any claim that is of type "Distinguished Name" and then compares the name to the extension of the <xref:System.ServiceModel.EndpointIdentity> (`OrgEndpointIdentity`).</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#1)]
     [!code-vb[c_HowToSetCustomClientIdentity#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#1)]  
  
### <a name="to-implement-the-trygetidentity-method"></a><span data-ttu-id="a9359-125">实现 TryGetIdentity 方法</span><span class="sxs-lookup"><span data-stu-id="a9359-125">To implement the TryGetIdentity method</span></span>  
  
1. <span data-ttu-id="a9359-126">实现 <xref:System.ServiceModel.Security.IdentityVerifier.TryGetIdentity%2A> 方法，该方法确定客户端是否可返回 <xref:System.ServiceModel.EndpointIdentity> 类的实例。</span><span class="sxs-lookup"><span data-stu-id="a9359-126">Implement the <xref:System.ServiceModel.Security.IdentityVerifier.TryGetIdentity%2A> method, which determines whether an instance of the <xref:System.ServiceModel.EndpointIdentity> class can be returned by the client.</span></span> <span data-ttu-id="a9359-127">WCF 基础结构首先调用方法的实现 `TryGetIdentity` 来从消息中检索服务的标识。</span><span class="sxs-lookup"><span data-stu-id="a9359-127">The WCF infrastructure calls the implementation of the `TryGetIdentity` method first to retrieve the service's identity from the message.</span></span> <span data-ttu-id="a9359-128">然后，该基础结构使用返回的 `CheckAccess` 和 `EndpointIdentity` 调用 <xref:System.IdentityModel.Policy.AuthorizationContext> 实现。</span><span class="sxs-lookup"><span data-stu-id="a9359-128">Next, the infrastructure calls the `CheckAccess` implementation with the returned `EndpointIdentity` and <xref:System.IdentityModel.Policy.AuthorizationContext>.</span></span>  
  
2. <span data-ttu-id="a9359-129">在 `TryGetIdentity` 方法中，添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="a9359-129">In the `TryGetIdentity` method, put the following code:</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#2)]
     [!code-vb[c_HowToSetCustomClientIdentity#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#2)]  
  
### <a name="to-implement-a-custom-binding-and-set-the-custom-identityverifier"></a><span data-ttu-id="a9359-130">实现自定义绑定并设置自定义标识验证工具</span><span class="sxs-lookup"><span data-stu-id="a9359-130">To implement a custom binding and set the custom IdentityVerifier</span></span>  
  
1. <span data-ttu-id="a9359-131">创建一个返回 <xref:System.ServiceModel.Channels.Binding> 对象的方法。</span><span class="sxs-lookup"><span data-stu-id="a9359-131">Create a method that returns a <xref:System.ServiceModel.Channels.Binding> object.</span></span> <span data-ttu-id="a9359-132">本示例首先创建 <xref:System.ServiceModel.WSHttpBinding> 类的一个实例，然后将其安全模式设置为 <xref:System.ServiceModel.SecurityMode.Message>，并且将其 <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> 设置为 <xref:System.ServiceModel.MessageCredentialType.None>。</span><span class="sxs-lookup"><span data-stu-id="a9359-132">This example begins creates an instance of the <xref:System.ServiceModel.WSHttpBinding> class and sets its security mode to <xref:System.ServiceModel.SecurityMode.Message>, and its <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> to <xref:System.ServiceModel.MessageCredentialType.None>.</span></span>  
  
2. <span data-ttu-id="a9359-133">使用 <xref:System.ServiceModel.Channels.BindingElementCollection> 方法创建一个 <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A>。</span><span class="sxs-lookup"><span data-stu-id="a9359-133">Create a <xref:System.ServiceModel.Channels.BindingElementCollection> using the <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A> method.</span></span>  
  
3. <span data-ttu-id="a9359-134">从集合返回 <xref:System.ServiceModel.Channels.SecurityBindingElement>，并将其强制转换为一个 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> 变量。</span><span class="sxs-lookup"><span data-stu-id="a9359-134">Return the <xref:System.ServiceModel.Channels.SecurityBindingElement> from the collection and cast it to a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> variable.</span></span>  
  
4. <span data-ttu-id="a9359-135">将 <xref:System.ServiceModel.Channels.LocalClientSecuritySettings.IdentityVerifier%2A> 类的 <xref:System.ServiceModel.Channels.LocalClientSecuritySettings> 属性设置为先前创建的 `CustomIdentityVerifier` 类的一个新实例。</span><span class="sxs-lookup"><span data-stu-id="a9359-135">Set the <xref:System.ServiceModel.Channels.LocalClientSecuritySettings.IdentityVerifier%2A> property of the <xref:System.ServiceModel.Channels.LocalClientSecuritySettings> class to a new instance of the `CustomIdentityVerifier` class created previously.</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#3)]
     [!code-vb[c_HowToSetCustomClientIdentity#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#3)]  
  
5. <span data-ttu-id="a9359-136">使用返回的自定义绑定创建客户端和类的一个实例。</span><span class="sxs-lookup"><span data-stu-id="a9359-136">The custom binding that is returned is used to create an instance of the client and class.</span></span> <span data-ttu-id="a9359-137">然后，客户端可执行服务的自定义标识验证检查，如以下代码中所示。</span><span class="sxs-lookup"><span data-stu-id="a9359-137">The client can then perform a custom identity verification check of the service as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#4)]
     [!code-vb[c_HowToSetCustomClientIdentity#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="a9359-138">示例</span><span class="sxs-lookup"><span data-stu-id="a9359-138">Example</span></span>  

 <span data-ttu-id="a9359-139">下面的示例演示 <xref:System.ServiceModel.Security.IdentityVerifier> 类的完整实现。</span><span class="sxs-lookup"><span data-stu-id="a9359-139">The following example shows a complete implementation of the <xref:System.ServiceModel.Security.IdentityVerifier> class.</span></span>  
  
 [!code-csharp[c_HowToSetCustomClientIdentity#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#5)]
 [!code-vb[c_HowToSetCustomClientIdentity#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="a9359-140">示例</span><span class="sxs-lookup"><span data-stu-id="a9359-140">Example</span></span>  

 <span data-ttu-id="a9359-141">下面的示例演示 <xref:System.ServiceModel.EndpointIdentity> 类的完整实现。</span><span class="sxs-lookup"><span data-stu-id="a9359-141">The following example shows a complete implementation of the <xref:System.ServiceModel.EndpointIdentity> class.</span></span>  
  
 [!code-csharp[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#6)]
 [!code-vb[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="a9359-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a9359-142">See also</span></span>

- <xref:System.ServiceModel.ServiceAuthorizationManager>
- <xref:System.ServiceModel.EndpointIdentity>
- <xref:System.ServiceModel.Security.IdentityVerifier>
- [<span data-ttu-id="a9359-143">服务标识示例</span><span class="sxs-lookup"><span data-stu-id="a9359-143">Service Identity Sample</span></span>](../samples/service-identity-sample.md)
- [<span data-ttu-id="a9359-144">授权策略</span><span class="sxs-lookup"><span data-stu-id="a9359-144">Authorization Policy</span></span>](../samples/authorization-policy.md)
