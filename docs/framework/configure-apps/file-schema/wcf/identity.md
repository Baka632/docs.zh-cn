---
title: <identity>
ms.date: 03/30/2017
ms.assetid: c1d2ae56-e231-4a07-9c3f-9f13381dc0d8
ms.openlocfilehash: bb9468b6005361a2a480f7c0ebfb2cbb9e9199c2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157377"
---
# \<identity>

<span data-ttu-id="b39ac-101">标识元素允许客户端开发人员在设计时指定服务的期望标识。</span><span class="sxs-lookup"><span data-stu-id="b39ac-101">The identity element allows a client developer to specify at design time the expected identity of the service.</span></span> <span data-ttu-id="b39ac-102">在客户端与服务之间的握手过程中，Windows Communication Foundation (WCF) 基础结构将确保预期服务的标识与此元素的值相匹配，因而可以进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="b39ac-102">In the handshake process between the client and service, the Windows Communication Foundation (WCF) infrastructure will ensure that the identity of the expected service matches the values of this element, and thus can be authenticated.</span></span> <span data-ttu-id="b39ac-103">有关详细信息，请参阅 [服务标识和身份验证](../../../wcf/feature-details/service-identity-and-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="b39ac-103">For more information, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<identity>**  
  
## <a name="syntax"></a><span data-ttu-id="b39ac-104">语法</span><span class="sxs-lookup"><span data-stu-id="b39ac-104">Syntax</span></span>  
  
```xml  
<identity>
  <certificate encodedValue="String" />
  <certificateReference findValue="String"
                        isChainIncluded="Boolean"
                        storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                        storeLocation="LocalMachine/CurrentUser"
                        X509FindType="Enumeration" />
  <dns value="String" />
  <rsa value="String" />
  <servicePrincipalName value="String" />
  <userPrincipalName value="String" />
</identity>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b39ac-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b39ac-105">Attributes and Elements</span></span>  

 <span data-ttu-id="b39ac-106">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b39ac-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b39ac-107">特性</span><span class="sxs-lookup"><span data-stu-id="b39ac-107">Attributes</span></span>  

 <span data-ttu-id="b39ac-108">无。</span><span class="sxs-lookup"><span data-stu-id="b39ac-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b39ac-109">子元素</span><span class="sxs-lookup"><span data-stu-id="b39ac-109">Child Elements</span></span>  
  
|<span data-ttu-id="b39ac-110">元素</span><span class="sxs-lookup"><span data-stu-id="b39ac-110">Element</span></span>|<span data-ttu-id="b39ac-111">描述</span><span class="sxs-lookup"><span data-stu-id="b39ac-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b39ac-112">证书 (certificate)</span><span class="sxs-lookup"><span data-stu-id="b39ac-112">certificate</span></span>|<span data-ttu-id="b39ac-113">指定 X.509 证书的设置。</span><span class="sxs-lookup"><span data-stu-id="b39ac-113">Specifies settings of an X.509 certificate.</span></span> <span data-ttu-id="b39ac-114">此元素的类型为 <xref:System.ServiceModel.Configuration.CertificateElement>。</span><span class="sxs-lookup"><span data-stu-id="b39ac-114">This element is of type <xref:System.ServiceModel.Configuration.CertificateElement>.</span></span> <span data-ttu-id="b39ac-115">它包含一个 `encodedValue` 属性，该属性是一个字符串，用于指定此证书编码的值。</span><span class="sxs-lookup"><span data-stu-id="b39ac-115">It contains an attribute `encodedValue` that is a string, which specifies the value encoded by this certificate.</span></span>|  
|<span data-ttu-id="b39ac-116">certificateReference</span><span class="sxs-lookup"><span data-stu-id="b39ac-116">certificateReference</span></span>|<span data-ttu-id="b39ac-117">指定 X.509 证书验证的设置。</span><span class="sxs-lookup"><span data-stu-id="b39ac-117">Specifies settings for X.509 certificate validation.</span></span> <span data-ttu-id="b39ac-118">此元素的类型为 <xref:System.ServiceModel.Configuration.CertificateReferenceElement>。</span><span class="sxs-lookup"><span data-stu-id="b39ac-118">This element is of type <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span></span>|  
|<span data-ttu-id="b39ac-119">dns</span><span class="sxs-lookup"><span data-stu-id="b39ac-119">dns</span></span>|<span data-ttu-id="b39ac-120">指定用于对服务进行身份验证的 X.509 证书的 DNS。</span><span class="sxs-lookup"><span data-stu-id="b39ac-120">Specifies the DNS of an X.509 certificate used to authenticate a service.</span></span> <span data-ttu-id="b39ac-121">此元素包含一个字符串属性 `value`，并包含实际的标识。</span><span class="sxs-lookup"><span data-stu-id="b39ac-121">This element contains an attribute `value` that is a string, and contains the actual identity.</span></span>|  
|<span data-ttu-id="b39ac-122">rsa</span><span class="sxs-lookup"><span data-stu-id="b39ac-122">rsa</span></span>|<span data-ttu-id="b39ac-123">指定用于向客户端验证服务身份的 X.509 证书的 RSA 字段的值。</span><span class="sxs-lookup"><span data-stu-id="b39ac-123">Specifies the value of the RSA field of an X.509 certificate used to authenticate a service to a client.</span></span> <span data-ttu-id="b39ac-124">此元素包含一个字符串属性 `value`，并包含实际的标识。</span><span class="sxs-lookup"><span data-stu-id="b39ac-124">This element contains an attribute `value` that is a string, and contains the actual identity</span></span>|  
|<span data-ttu-id="b39ac-125">servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="b39ac-125">servicePrincipalName</span></span>|<span data-ttu-id="b39ac-126">指定服务器主体名称 (SPN) 标识，它是客户端用来唯一标识一个服务实例的主体名称。</span><span class="sxs-lookup"><span data-stu-id="b39ac-126">Specifies a server principal name (SPN) identity, which is the principal name used by a client to uniquely identify an instance of a service.</span></span> <span data-ttu-id="b39ac-127">此元素包含一个 `value` 属性，该属性是一个字符串，其中包含实际的主体名称。</span><span class="sxs-lookup"><span data-stu-id="b39ac-127">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="b39ac-128">此元素的类型为 <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>。</span><span class="sxs-lookup"><span data-stu-id="b39ac-128">This element is of type <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span></span>|  
|<span data-ttu-id="b39ac-129">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="b39ac-129">userPrincipalName</span></span>|<span data-ttu-id="b39ac-130">指定用户主体名称 (UPN) 标识，它是网络上的用户登录名类型。</span><span class="sxs-lookup"><span data-stu-id="b39ac-130">Specifies a user principal name (UPN) identity, which is the logon name type of a user on a network.</span></span> <span data-ttu-id="b39ac-131">用户主体名称包含 Active Directory 中使用的用户对象名称，后跟符号 (\@) 然后通常是域名系统父域。</span><span class="sxs-lookup"><span data-stu-id="b39ac-131">The user principal name consists of the user object name used in Active Directory, followed by the at symbol (\@) and then, typically, the Domain Name System parent domain.</span></span> <span data-ttu-id="b39ac-132">例如，Fabrikam.com 域树中的 Jeff 可能具有用户主体名称 [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com) 。</span><span class="sxs-lookup"><span data-stu-id="b39ac-132">For example, Jeff in the Fabrikam.com domain tree might have the user principal name [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com).</span></span>  <span data-ttu-id="b39ac-133">此元素包含一个 `value` 属性，该属性是一个字符串，其中包含实际的主体名称。</span><span class="sxs-lookup"><span data-stu-id="b39ac-133">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="b39ac-134">此元素的类型为 <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>。</span><span class="sxs-lookup"><span data-stu-id="b39ac-134">This element is of type <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b39ac-135">父元素</span><span class="sxs-lookup"><span data-stu-id="b39ac-135">Parent Elements</span></span>  
  
|<span data-ttu-id="b39ac-136">元素</span><span class="sxs-lookup"><span data-stu-id="b39ac-136">Element</span></span>|<span data-ttu-id="b39ac-137">描述</span><span class="sxs-lookup"><span data-stu-id="b39ac-137">Description</span></span>|  
|-------------|-----------------|  
|[\<custom>](custom.md)|<span data-ttu-id="b39ac-138">指定 netPeerTcpBinding 的自定义对等解析程序。</span><span class="sxs-lookup"><span data-stu-id="b39ac-138">Specifies a custom peer resolver for a netPeerTcpBinding.</span></span>|  
|[\<endpoint>](endpoint-element.md)|<span data-ttu-id="b39ac-139">配置服务终结点。</span><span class="sxs-lookup"><span data-stu-id="b39ac-139">Configures service endpoints.</span></span>|  
|[<span data-ttu-id="b39ac-140">\<client> 的 \<endpoint></span><span class="sxs-lookup"><span data-stu-id="b39ac-140">\<endpoint> of \<client></span></span>](endpoint-of-client.md)|<span data-ttu-id="b39ac-141">配置通道终结点。</span><span class="sxs-lookup"><span data-stu-id="b39ac-141">Configures channel endpoints.</span></span>|  
|[\<issuer>](issuer.md)|<span data-ttu-id="b39ac-142">指定联合服务的安全令牌服务 (STS)。</span><span class="sxs-lookup"><span data-stu-id="b39ac-142">Specifies the Security Token Service (STS) for the federated service.</span></span>|  
|[\<issuerMetadata>](issuermetadata.md)|<span data-ttu-id="b39ac-143">指定联合服务的安全令牌服务 (STS) 的元数据终结点。</span><span class="sxs-lookup"><span data-stu-id="b39ac-143">Specifies the metadata endpoint for the Security Token Service (STS) of a federated service.</span></span>|  
|[\<issuedTokenParameters>](issuedtokenparameters.md)|<span data-ttu-id="b39ac-144">定义自定义绑定中的已颁发令牌的参数。</span><span class="sxs-lookup"><span data-stu-id="b39ac-144">Defines parameters for an issued token in a custom binding.</span></span>|  
|[\<localIssuer>](localissuer.md)|<span data-ttu-id="b39ac-145">指定本地安全令牌服务 (STS)。</span><span class="sxs-lookup"><span data-stu-id="b39ac-145">Specifies a local Security Token Service (STS).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b39ac-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="b39ac-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- [<span data-ttu-id="b39ac-147">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="b39ac-147">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="b39ac-148">终结点：地址、绑定和协定</span><span class="sxs-lookup"><span data-stu-id="b39ac-148">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
