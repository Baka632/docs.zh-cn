---
title: <serviceCertificate> of <clientCredentials> 元素
ms.date: 03/30/2017
ms.assetid: e50c0ac5-f0df-4c90-b54b-fc602c1f84ea
ms.openlocfilehash: 502452c664f2dcb0856f72e25ff8b1517f432919
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172887"
---
# <a name="servicecertificate-of-clientcredentials-element"></a><span data-ttu-id="af759-102">\<serviceCertificate> of \<clientCredentials> 元素</span><span class="sxs-lookup"><span data-stu-id="af759-102">\<serviceCertificate> of \<clientCredentials> Element</span></span>

<span data-ttu-id="af759-103">指定客户端对服务进行身份验证时使用的证书。</span><span class="sxs-lookup"><span data-stu-id="af759-103">Specifies a certificate to use when authenticating a service to the client.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="af759-104">语法</span><span class="sxs-lookup"><span data-stu-id="af759-104">Syntax</span></span>  
  
```xml  
<serviceCertificate />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af759-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="af759-105">Attributes and Elements</span></span>  

 <span data-ttu-id="af759-106">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="af759-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af759-107">特性</span><span class="sxs-lookup"><span data-stu-id="af759-107">Attributes</span></span>  

 <span data-ttu-id="af759-108">无。</span><span class="sxs-lookup"><span data-stu-id="af759-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="af759-109">子元素</span><span class="sxs-lookup"><span data-stu-id="af759-109">Child Elements</span></span>  
  
|<span data-ttu-id="af759-110">元素</span><span class="sxs-lookup"><span data-stu-id="af759-110">Element</span></span>|<span data-ttu-id="af759-111">描述</span><span class="sxs-lookup"><span data-stu-id="af759-111">Description</span></span>|  
|-------------|-----------------|  
|[\<defaultCertificate>](defaultcertificate-element.md)|<span data-ttu-id="af759-112">指定在服务或 STS 未通过协商协议提供证书时要使用的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="af759-112">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>|  
|[\<scopedCertificates>](scopedcertificates-element.md)|<span data-ttu-id="af759-113">表示特定服务为身份验证提供的 X.509（作用域）证书的集合。</span><span class="sxs-lookup"><span data-stu-id="af759-113">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="af759-114">此集合通常用于指定联合方案中安全令牌服务的服务证书。</span><span class="sxs-lookup"><span data-stu-id="af759-114">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>|  
|[\<authentication>](authentication-of-servicecertificate-element.md)|<span data-ttu-id="af759-115">指定客户端使用的服务证书的身份验证行为。</span><span class="sxs-lookup"><span data-stu-id="af759-115">Specifies authentication behaviors for service certificates used by a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="af759-116">父元素</span><span class="sxs-lookup"><span data-stu-id="af759-116">Parent Elements</span></span>  
  
|<span data-ttu-id="af759-117">元素</span><span class="sxs-lookup"><span data-stu-id="af759-117">Element</span></span>|<span data-ttu-id="af759-118">描述</span><span class="sxs-lookup"><span data-stu-id="af759-118">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="af759-119">指定客户端用于向服务证明自己的身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="af759-119">Specifies the credentials used by the client to authenticate itself to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af759-120">备注</span><span class="sxs-lookup"><span data-stu-id="af759-120">Remarks</span></span>  

 <span data-ttu-id="af759-121">此配置元素指定客户端在验证使用 SSL 身份验证的服务所出示的证书时使用的设置。</span><span class="sxs-lookup"><span data-stu-id="af759-121">This configuration element specifies the settings used by the client to validate the certificate presented by the service using SSL authentication.</span></span> <span data-ttu-id="af759-122">它还包含在客户端上显式配置为对发送给使用消息安全的服务的消息进行加密的服务的所有证书。</span><span class="sxs-lookup"><span data-stu-id="af759-122">It also contains any certificate for the service that is explicitly configured on the client to use for encrypting messages to the service using message security.</span></span>  
  
 <span data-ttu-id="af759-123">元素的特性与 `serviceCertificate` 的特性相同 [\<clientCertificate>](clientcertificate-of-clientcredentials-element.md) 。</span><span class="sxs-lookup"><span data-stu-id="af759-123">The attributes of the `serviceCertificate` element are identical to the attributes of the [\<clientCertificate>](clientcertificate-of-clientcredentials-element.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af759-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="af759-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ServiceCertificate%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- [<span data-ttu-id="af759-125">安全行为</span><span class="sxs-lookup"><span data-stu-id="af759-125">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="af759-126">保证客户端的安全</span><span class="sxs-lookup"><span data-stu-id="af759-126">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="af759-127">使用证书</span><span class="sxs-lookup"><span data-stu-id="af759-127">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="af759-128">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="af759-128">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
