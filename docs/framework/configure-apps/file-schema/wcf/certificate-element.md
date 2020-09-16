---
title: <certificate> 元素
ms.date: 03/30/2017
ms.assetid: 9b3d9233-ef35-477a-bf5d-efd1e80a52f4
ms.openlocfilehash: c5fd156904ed30035991a8391c8f975da2a97ea7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554366"
---
# <a name="certificate-element"></a><span data-ttu-id="1f3bb-102">\<certificate> 元素</span><span class="sxs-lookup"><span data-stu-id="1f3bb-102">\<certificate> Element</span></span>
<span data-ttu-id="1f3bb-103">指定要用于为对等客户端的消息进行签名和加密的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="1f3bb-103">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**  
  
## <a name="syntax"></a><span data-ttu-id="1f3bb-104">语法</span><span class="sxs-lookup"><span data-stu-id="1f3bb-104">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation="LocalMachine/CurrentUser"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1f3bb-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1f3bb-105">Attributes and Elements</span></span>  
 <span data-ttu-id="1f3bb-106">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1f3bb-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1f3bb-107">特性</span><span class="sxs-lookup"><span data-stu-id="1f3bb-107">Attributes</span></span>  
  
|<span data-ttu-id="1f3bb-108">属性</span><span class="sxs-lookup"><span data-stu-id="1f3bb-108">Attribute</span></span>|<span data-ttu-id="1f3bb-109">说明</span><span class="sxs-lookup"><span data-stu-id="1f3bb-109">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="1f3bb-110">一个字符串，包含要在 X.509 证书存储中搜索的值。</span><span class="sxs-lookup"><span data-stu-id="1f3bb-110">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="1f3bb-111">此属性中包含的类型必须满足指定 `x509FindType` 的要求。</span><span class="sxs-lookup"><span data-stu-id="1f3bb-111">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="1f3bb-112">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="1f3bb-112">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="1f3bb-113">指定客户端可用于验证对等方的证书的 X.509 证书存储的位置。</span><span class="sxs-lookup"><span data-stu-id="1f3bb-113">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="1f3bb-114">有效值包括以下值：</span><span class="sxs-lookup"><span data-stu-id="1f3bb-114">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="1f3bb-115">-LocalMachine：分配给本地计算机的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="1f3bb-115">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="1f3bb-116">-CurrentUser：分配给当前用户的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="1f3bb-116">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="1f3bb-117">默认值为 LocalMachine。</span><span class="sxs-lookup"><span data-stu-id="1f3bb-117">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="1f3bb-118">指定要打开的 X.509 证书存储区的名称。</span><span class="sxs-lookup"><span data-stu-id="1f3bb-118">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="1f3bb-119">有效值包括以下值：</span><span class="sxs-lookup"><span data-stu-id="1f3bb-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="1f3bb-120">-通讯簿：其他用户的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="1f3bb-120">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="1f3bb-121">-AuthRoot：第三方证书颁发机构的证书存储 (Ca) 。</span><span class="sxs-lookup"><span data-stu-id="1f3bb-121">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="1f3bb-122">-CertificateAuthority：用于中间证书颁发机构的证书存储 (Ca) 。</span><span class="sxs-lookup"><span data-stu-id="1f3bb-122">-   CertificateAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="1f3bb-123">-不允许：吊销的证书的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="1f3bb-123">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="1f3bb-124">-My：个人证书的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="1f3bb-124">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="1f3bb-125">-Root：受信任的根证书颁发机构的证书存储 (Ca) 。</span><span class="sxs-lookup"><span data-stu-id="1f3bb-125">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="1f3bb-126">-TrustedPeople：直接受信任的人和资源的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="1f3bb-126">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="1f3bb-127">-TrustedPublisher：直接受信任的发布者的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="1f3bb-127">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="1f3bb-128">默认值为 My。</span><span class="sxs-lookup"><span data-stu-id="1f3bb-128">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="1f3bb-129">定义要执行的 X.509 搜索的类型。</span><span class="sxs-lookup"><span data-stu-id="1f3bb-129">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="1f3bb-130">有效值包括以下值：</span><span class="sxs-lookup"><span data-stu-id="1f3bb-130">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="1f3bb-131">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="1f3bb-131">-   FindByThumbPrint</span></span><br /><span data-ttu-id="1f3bb-132">-Findbysubjectname) </span><span class="sxs-lookup"><span data-stu-id="1f3bb-132">-   FindBySubjectName</span></span><br /><span data-ttu-id="1f3bb-133">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="1f3bb-133">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="1f3bb-134">- FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="1f3bb-134">-   FindByIssuerName</span></span><br /><span data-ttu-id="1f3bb-135">- FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="1f3bb-135">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="1f3bb-136">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="1f3bb-136">-   FindBySerialNumber</span></span><br /><span data-ttu-id="1f3bb-137">- FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="1f3bb-137">-   FindByTimeValid</span></span><br /><span data-ttu-id="1f3bb-138">- FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="1f3bb-138">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="1f3bb-139">- FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="1f3bb-139">-   FindByTemplateName</span></span><br /><span data-ttu-id="1f3bb-140">- FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="1f3bb-140">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="1f3bb-141">- FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="1f3bb-141">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="1f3bb-142">- FindByExtension</span><span class="sxs-lookup"><span data-stu-id="1f3bb-142">-   FindByExtension</span></span><br /><span data-ttu-id="1f3bb-143">- FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="1f3bb-143">-   FindByKeyUsage</span></span><br /><span data-ttu-id="1f3bb-144">- FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="1f3bb-144">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="1f3bb-145">`findValue` 属性中包含的类型必须满足指定 `X509FindType` 的要求。</span><span class="sxs-lookup"><span data-stu-id="1f3bb-145">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="1f3bb-146">默认值为 FindBySubjectDistinguishedName。</span><span class="sxs-lookup"><span data-stu-id="1f3bb-146">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1f3bb-147">子元素</span><span class="sxs-lookup"><span data-stu-id="1f3bb-147">Child Elements</span></span>  
 <span data-ttu-id="1f3bb-148">无。</span><span class="sxs-lookup"><span data-stu-id="1f3bb-148">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1f3bb-149">父元素</span><span class="sxs-lookup"><span data-stu-id="1f3bb-149">Parent Elements</span></span>  
  
|<span data-ttu-id="1f3bb-150">元素</span><span class="sxs-lookup"><span data-stu-id="1f3bb-150">Element</span></span>|<span data-ttu-id="1f3bb-151">说明</span><span class="sxs-lookup"><span data-stu-id="1f3bb-151">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-clientcredentials-element.md)|<span data-ttu-id="1f3bb-152">指定在向对等客户端进行身份验证时使用的凭据。</span><span class="sxs-lookup"><span data-stu-id="1f3bb-152">Specifies credentials used when authenticating peer-to-peer clients.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f3bb-153">备注</span><span class="sxs-lookup"><span data-stu-id="1f3bb-153">Remarks</span></span>  
 <span data-ttu-id="1f3bb-154">此配置元素包含对对等网格中的邻居进行身份验证时使用的 X509Certificate2 实例。</span><span class="sxs-lookup"><span data-stu-id="1f3bb-154">This configuration element contains a X509Certificate2 instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="1f3bb-155">有关对等编程的详细信息，请参阅对等 [网络](../../../wcf/feature-details/peer-to-peer-networking.md)。</span><span class="sxs-lookup"><span data-stu-id="1f3bb-155">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f3bb-156">示例</span><span class="sxs-lookup"><span data-stu-id="1f3bb-156">Example</span></span>  
 <span data-ttu-id="1f3bb-157">下面的代码指定如何查找在对等方案中使用的证书。</span><span class="sxs-lookup"><span data-stu-id="1f3bb-157">The following code specifies how to find the certificate used in a peer-to-peer scenario.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="1f3bb-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="1f3bb-158">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>
- <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>
- [<span data-ttu-id="1f3bb-159">使用证书</span><span class="sxs-lookup"><span data-stu-id="1f3bb-159">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="1f3bb-160">对等网络</span><span class="sxs-lookup"><span data-stu-id="1f3bb-160">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="1f3bb-161">[对等通道消息身份验证](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="1f3bb-161">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="1f3bb-162">[对等通道自定义身份验证](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="1f3bb-162">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="1f3bb-163">保护对等通道应用程序</span><span class="sxs-lookup"><span data-stu-id="1f3bb-163">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
