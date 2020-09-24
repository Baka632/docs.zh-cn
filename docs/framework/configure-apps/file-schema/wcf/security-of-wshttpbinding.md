---
title: <security> 的 <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 8658b162-2ddf-4162-a869-aa517a42288a
ms.openlocfilehash: 9f984759fb52242bf8030a101b567c14627dd314
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158690"
---
# <a name="security-of-wshttpbinding"></a><span data-ttu-id="1f2ce-102">\<security> 的 \<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="1f2ce-102">\<security> of \<wsHttpBinding></span></span>

<span data-ttu-id="1f2ce-103">表示的安全功能 [\<wsHttpBinding>](wshttpbinding.md) 。</span><span class="sxs-lookup"><span data-stu-id="1f2ce-103">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsHttpBinding>**](wshttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="1f2ce-104">语法</span><span class="sxs-lookup"><span data-stu-id="1f2ce-104">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithMessageCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="String"
             defaultClientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             defaultProxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             defaultRealm="String" />
  <message clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           establishSecurityContext="Boolean"
           negotiateServiceCredential="Boolean" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1f2ce-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1f2ce-105">Attributes and Elements</span></span>  

 <span data-ttu-id="1f2ce-106">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1f2ce-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1f2ce-107">特性</span><span class="sxs-lookup"><span data-stu-id="1f2ce-107">Attributes</span></span>  
  
|<span data-ttu-id="1f2ce-108">属性</span><span class="sxs-lookup"><span data-stu-id="1f2ce-108">Attribute</span></span>|<span data-ttu-id="1f2ce-109">描述</span><span class="sxs-lookup"><span data-stu-id="1f2ce-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1f2ce-110">mode</span><span class="sxs-lookup"><span data-stu-id="1f2ce-110">mode</span></span>|<span data-ttu-id="1f2ce-111">可有可无.</span><span class="sxs-lookup"><span data-stu-id="1f2ce-111">-   Optional.</span></span> <span data-ttu-id="1f2ce-112">指定所应用的安全类型。</span><span class="sxs-lookup"><span data-stu-id="1f2ce-112">Specifies the type of security that is applied.</span></span> <span data-ttu-id="1f2ce-113">默认为 `Message`。</span><span class="sxs-lookup"><span data-stu-id="1f2ce-113">The default is `Message`.</span></span><br /><span data-ttu-id="1f2ce-114">-此属性的类型为 <xref:System.ServiceModel.SecurityMode> 。</span><span class="sxs-lookup"><span data-stu-id="1f2ce-114">-   This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="1f2ce-115">Mode 属性</span><span class="sxs-lookup"><span data-stu-id="1f2ce-115">Mode Attribute</span></span>  
  
|<span data-ttu-id="1f2ce-116">值</span><span class="sxs-lookup"><span data-stu-id="1f2ce-116">Value</span></span>|<span data-ttu-id="1f2ce-117">描述</span><span class="sxs-lookup"><span data-stu-id="1f2ce-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1f2ce-118">无</span><span class="sxs-lookup"><span data-stu-id="1f2ce-118">None</span></span>|<span data-ttu-id="1f2ce-119">禁用安全性。</span><span class="sxs-lookup"><span data-stu-id="1f2ce-119">Security is disabled.</span></span>|  
|<span data-ttu-id="1f2ce-120">传输</span><span class="sxs-lookup"><span data-stu-id="1f2ce-120">Transport</span></span>|<span data-ttu-id="1f2ce-121">使用 HTTPS 提供安全性。</span><span class="sxs-lookup"><span data-stu-id="1f2ce-121">Security is provided using HTTPS.</span></span> <span data-ttu-id="1f2ce-122">此服务需要使用 SSL 证书进行配置。</span><span class="sxs-lookup"><span data-stu-id="1f2ce-122">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="1f2ce-123">消息使用 HTTPS 得到了全面保护，客户端使用服务的 SSL 证书对消息进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="1f2ce-123">The message is entirely secured using HTTPS and is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="1f2ce-124">客户端身份验证通过</span><span class="sxs-lookup"><span data-stu-id="1f2ce-124">The client authentication is controlled through the `ClientCredentials` attribute.</span></span> <span data-ttu-id="1f2ce-125">的 [\<transport>](transport-of-wshttpbinding.md) 。</span><span class="sxs-lookup"><span data-stu-id="1f2ce-125">of the [\<transport>](transport-of-wshttpbinding.md).</span></span>|  
|<span data-ttu-id="1f2ce-126">消息</span><span class="sxs-lookup"><span data-stu-id="1f2ce-126">Message</span></span>|<span data-ttu-id="1f2ce-127">使用 SOAP 消息安全提供安全性。</span><span class="sxs-lookup"><span data-stu-id="1f2ce-127">Security is provided using SOAP message security.</span></span> <span data-ttu-id="1f2ce-128">默认情况下，将对 SOAP 正文进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="1f2ce-128">By default, the SOAP body is Encrypted and Signed.</span></span> <span data-ttu-id="1f2ce-129">此模式提供了各种各样的功能，例如服务凭据在带外客户端是否可用、要使用的算法套件以及通过 Security.Message 属性要应用于消息正文的保护级别。</span><span class="sxs-lookup"><span data-stu-id="1f2ce-129">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the Security.Message property.</span></span> <span data-ttu-id="1f2ce-130">每个会话将执行一次客户端身份验证，身份验证的结果在会话过程中将被缓存。</span><span class="sxs-lookup"><span data-stu-id="1f2ce-130">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="1f2ce-131">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="1f2ce-131">TransportWithMessageCredential</span></span>|<span data-ttu-id="1f2ce-132">在此模式下，HTTPS 将提供完整性、保密性和服务器身份验证，SOAP 消息安全将提供客户端身份验证。</span><span class="sxs-lookup"><span data-stu-id="1f2ce-132">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="1f2ce-133">默认情况下，每个会话将执行一次客户端身份验证，身份验证的结果在会话过程中将被缓存。</span><span class="sxs-lookup"><span data-stu-id="1f2ce-133">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1f2ce-134">子元素</span><span class="sxs-lookup"><span data-stu-id="1f2ce-134">Child Elements</span></span>  
  
|<span data-ttu-id="1f2ce-135">元素</span><span class="sxs-lookup"><span data-stu-id="1f2ce-135">Element</span></span>|<span data-ttu-id="1f2ce-136">描述</span><span class="sxs-lookup"><span data-stu-id="1f2ce-136">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-wshttpbinding.md)|<span data-ttu-id="1f2ce-137">定义传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="1f2ce-137">Defines the transport security settings.</span></span> <span data-ttu-id="1f2ce-138">此元素与 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> 类型相对应。</span><span class="sxs-lookup"><span data-stu-id="1f2ce-138">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
|[\<message>](message-of-wshttpbinding.md)|<span data-ttu-id="1f2ce-139">定义消息的安全设置。</span><span class="sxs-lookup"><span data-stu-id="1f2ce-139">Defines the security settings for the message.</span></span> <span data-ttu-id="1f2ce-140">此元素与 <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> 类型相对应。</span><span class="sxs-lookup"><span data-stu-id="1f2ce-140">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1f2ce-141">父元素</span><span class="sxs-lookup"><span data-stu-id="1f2ce-141">Parent Elements</span></span>  
  
|<span data-ttu-id="1f2ce-142">元素</span><span class="sxs-lookup"><span data-stu-id="1f2ce-142">Element</span></span>|<span data-ttu-id="1f2ce-143">描述</span><span class="sxs-lookup"><span data-stu-id="1f2ce-143">Description</span></span>|  
|-------------|-----------------|  
|[\<wsHttpBinding>](wshttpbinding.md)|<span data-ttu-id="1f2ce-144">HTTP 传输应用程序的安全绑定。</span><span class="sxs-lookup"><span data-stu-id="1f2ce-144">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f2ce-145">备注</span><span class="sxs-lookup"><span data-stu-id="1f2ce-145">Remarks</span></span>  

 <span data-ttu-id="1f2ce-146">WSHttpBinding 类专用于与实现 WS-\* 规范的服务进行互操作。</span><span class="sxs-lookup"><span data-stu-id="1f2ce-146">The WSHttpBinding class is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="1f2ce-147">此绑定的传输安全为 HTTP 上的安全套接字层 (SSL)，即 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="1f2ce-147">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f2ce-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="1f2ce-148">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- [<span data-ttu-id="1f2ce-149">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="1f2ce-149">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="1f2ce-150">绑定</span><span class="sxs-lookup"><span data-stu-id="1f2ce-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="1f2ce-151">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="1f2ce-151">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="1f2ce-152">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="1f2ce-152">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
