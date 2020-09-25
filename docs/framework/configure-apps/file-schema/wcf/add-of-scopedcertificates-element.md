---
title: <add> of <scopedCertificates> 元素
ms.date: 03/30/2017
ms.assetid: e21c1ef8-d6d6-4bca-ac5a-6fbf4bd77412
ms.openlocfilehash: 28777ecac130295a8ba82a8e4d67cc519d088d8a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195137"
---
# <a name="add-of-scopedcertificates-element"></a><span data-ttu-id="14ec8-102">\<add> of \<scopedCertificates> 元素</span><span class="sxs-lookup"><span data-stu-id="14ec8-102">\<add> of \<scopedCertificates> Element</span></span>

<span data-ttu-id="14ec8-103">向作用域证书集合添加 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="14ec8-103">Adds an X.509 certificate to the collection of scoped certificates.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<scopedCertificates>**](scopedcertificates-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="14ec8-104">语法</span><span class="sxs-lookup"><span data-stu-id="14ec8-104">Syntax</span></span>  
  
```xml  
<add findValue="String"
     storeLocation="CurrentUser/LocalMachine"
     storeName=" CurrentUser/LocalMachine"
     targetUri="string"
     x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14ec8-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="14ec8-105">Attributes and Elements</span></span>  

 <span data-ttu-id="14ec8-106">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="14ec8-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14ec8-107">特性</span><span class="sxs-lookup"><span data-stu-id="14ec8-107">Attributes</span></span>  
  
|<span data-ttu-id="14ec8-108">属性</span><span class="sxs-lookup"><span data-stu-id="14ec8-108">Attribute</span></span>|<span data-ttu-id="14ec8-109">描述</span><span class="sxs-lookup"><span data-stu-id="14ec8-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="14ec8-110">targetUri</span><span class="sxs-lookup"><span data-stu-id="14ec8-110">targetUri</span></span>|<span data-ttu-id="14ec8-111">字符串。</span><span class="sxs-lookup"><span data-stu-id="14ec8-111">String.</span></span> <span data-ttu-id="14ec8-112">指定与证书相关的服务的 URI。</span><span class="sxs-lookup"><span data-stu-id="14ec8-112">Specifies the URI of the service associated with the certificate.</span></span>|  
|<span data-ttu-id="14ec8-113">findValue</span><span class="sxs-lookup"><span data-stu-id="14ec8-113">findValue</span></span>|<span data-ttu-id="14ec8-114">字符串。</span><span class="sxs-lookup"><span data-stu-id="14ec8-114">String.</span></span> <span data-ttu-id="14ec8-115">要搜索的值。</span><span class="sxs-lookup"><span data-stu-id="14ec8-115">The value to search for.</span></span>|  
|<span data-ttu-id="14ec8-116">x509FindType</span><span class="sxs-lookup"><span data-stu-id="14ec8-116">x509FindType</span></span>|<span data-ttu-id="14ec8-117">枚举。</span><span class="sxs-lookup"><span data-stu-id="14ec8-117">Enumeration.</span></span> <span data-ttu-id="14ec8-118">要搜索的证书字段之一。</span><span class="sxs-lookup"><span data-stu-id="14ec8-118">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="14ec8-119">storeLocation</span><span class="sxs-lookup"><span data-stu-id="14ec8-119">storeLocation</span></span>|<span data-ttu-id="14ec8-120">枚举。</span><span class="sxs-lookup"><span data-stu-id="14ec8-120">Enumeration.</span></span> <span data-ttu-id="14ec8-121">要搜索的两个存储位置之一。</span><span class="sxs-lookup"><span data-stu-id="14ec8-121">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="14ec8-122">storeName</span><span class="sxs-lookup"><span data-stu-id="14ec8-122">storeName</span></span>|<span data-ttu-id="14ec8-123">枚举。</span><span class="sxs-lookup"><span data-stu-id="14ec8-123">Enumeration.</span></span> <span data-ttu-id="14ec8-124">要搜索的系统存储之一。</span><span class="sxs-lookup"><span data-stu-id="14ec8-124">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="14ec8-125">findValue 属性</span><span class="sxs-lookup"><span data-stu-id="14ec8-125">findValue Attribute</span></span>  
  
|<span data-ttu-id="14ec8-126">值</span><span class="sxs-lookup"><span data-stu-id="14ec8-126">Value</span></span>|<span data-ttu-id="14ec8-127">说明</span><span class="sxs-lookup"><span data-stu-id="14ec8-127">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="14ec8-128">字符串</span><span class="sxs-lookup"><span data-stu-id="14ec8-128">String</span></span>|<span data-ttu-id="14ec8-129">值取决于搜索的字段（由 X509FindType 属性指定）。</span><span class="sxs-lookup"><span data-stu-id="14ec8-129">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="14ec8-130">例如，如果搜索指纹，则此值必须为十六进制数字字符串。</span><span class="sxs-lookup"><span data-stu-id="14ec8-130">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="14ec8-131">x509FindType 属性</span><span class="sxs-lookup"><span data-stu-id="14ec8-131">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="14ec8-132">值</span><span class="sxs-lookup"><span data-stu-id="14ec8-132">Value</span></span>|<span data-ttu-id="14ec8-133">描述</span><span class="sxs-lookup"><span data-stu-id="14ec8-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="14ec8-134">枚举</span><span class="sxs-lookup"><span data-stu-id="14ec8-134">Enumeration</span></span>|<span data-ttu-id="14ec8-135">值包括：FindByThumbprint、FindBySubjectName、FindBySubjectDistinguishedName、FindByIssuerName、FindByIssuerDistinguishedName、FindBySerialNumber、FindByTimeValid、FindByTimeNotYetValid、FindBySerialNumber、FindByTimeExpired、FindByTemplateName、FindByApplicationPolicy、FindByCertificatePolicy、FindByExtension、FindByKeyUsage 和 FindBySubjectKeyIdentifier。</span><span class="sxs-lookup"><span data-stu-id="14ec8-135">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="14ec8-136">storeLocation 属性</span><span class="sxs-lookup"><span data-stu-id="14ec8-136">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="14ec8-137">值</span><span class="sxs-lookup"><span data-stu-id="14ec8-137">Value</span></span>|<span data-ttu-id="14ec8-138">描述</span><span class="sxs-lookup"><span data-stu-id="14ec8-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="14ec8-139">枚举</span><span class="sxs-lookup"><span data-stu-id="14ec8-139">Enumeration</span></span>|<span data-ttu-id="14ec8-140">CurrentUser 或 LocalMachine。</span><span class="sxs-lookup"><span data-stu-id="14ec8-140">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="14ec8-141">storeName 属性</span><span class="sxs-lookup"><span data-stu-id="14ec8-141">storeName Attribute</span></span>  
  
|<span data-ttu-id="14ec8-142">值</span><span class="sxs-lookup"><span data-stu-id="14ec8-142">Value</span></span>|<span data-ttu-id="14ec8-143">描述</span><span class="sxs-lookup"><span data-stu-id="14ec8-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="14ec8-144">枚举</span><span class="sxs-lookup"><span data-stu-id="14ec8-144">Enumeration</span></span>|<span data-ttu-id="14ec8-145">值包括：AddressBook、AuthRoot、CertificateAuthority、Disallowed、My、Root、TrustedPeople 和 TrustedPublisher。</span><span class="sxs-lookup"><span data-stu-id="14ec8-145">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="14ec8-146">子元素</span><span class="sxs-lookup"><span data-stu-id="14ec8-146">Child Elements</span></span>  

 <span data-ttu-id="14ec8-147">无。</span><span class="sxs-lookup"><span data-stu-id="14ec8-147">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="14ec8-148">父元素</span><span class="sxs-lookup"><span data-stu-id="14ec8-148">Parent Elements</span></span>  
  
|<span data-ttu-id="14ec8-149">元素</span><span class="sxs-lookup"><span data-stu-id="14ec8-149">Element</span></span>|<span data-ttu-id="14ec8-150">描述</span><span class="sxs-lookup"><span data-stu-id="14ec8-150">Description</span></span>|  
|-------------|-----------------|  
|[\<scopedCertificates>](scopedcertificates-element.md)|<span data-ttu-id="14ec8-151">表示特定服务为身份验证提供的 X.509（作用域）证书的集合。</span><span class="sxs-lookup"><span data-stu-id="14ec8-151">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14ec8-152">备注</span><span class="sxs-lookup"><span data-stu-id="14ec8-152">Remarks</span></span>  

 <span data-ttu-id="14ec8-153">此元素使客户端能够根据与它通信的服务的 URL 来配置要使用的服务证书。</span><span class="sxs-lookup"><span data-stu-id="14ec8-153">This element enables the client to configure a service certificate to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="14ec8-154">这在已颁发令牌的方案中尤其有用，在这些方案中，客户端可与多个服务（终端服务以及中间的安全令牌服务）进行通信。</span><span class="sxs-lookup"><span data-stu-id="14ec8-154">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="14ec8-155">对于使用基于证书的消息安全的绑定，此证书用于加密发送给服务的消息，并期望服务用它来对客户端的应答进行签名。</span><span class="sxs-lookup"><span data-stu-id="14ec8-155">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="14ec8-156">如果绑定需要服务的证书，但在 ScopedCertificates 中未找到服务 URL 的特定证书，则使用默认证书。</span><span class="sxs-lookup"><span data-stu-id="14ec8-156">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="14ec8-157">有关详细信息，请参阅 [如何：创建联合客户端](../../../wcf/feature-details/how-to-create-a-federated-client.md)中的 "范围内的证书" 一节。</span><span class="sxs-lookup"><span data-stu-id="14ec8-157">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="14ec8-158">示例</span><span class="sxs-lookup"><span data-stu-id="14ec8-158">Example</span></span>  

 <span data-ttu-id="14ec8-159">下面的示例向集合中添加一个 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="14ec8-159">The following example adds an X.509 certificate the collection.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <serviceCertificate>
          <scopedCertificates>
            <add targetUri="http://www.contoso.com"
                 findValue="www.Contoso.com"
                 storeLocation="LocalMachine"
                 storeName="Root"
                 x509FindType="FindByIssuerName" />
          </scopedCertificates>
        </serviceCertificate>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="14ec8-160">请参阅</span><span class="sxs-lookup"><span data-stu-id="14ec8-160">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="14ec8-161">如何：创建联合客户端</span><span class="sxs-lookup"><span data-stu-id="14ec8-161">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="14ec8-162">使用证书</span><span class="sxs-lookup"><span data-stu-id="14ec8-162">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="14ec8-163">保证客户端的安全</span><span class="sxs-lookup"><span data-stu-id="14ec8-163">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="14ec8-164">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="14ec8-164">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
