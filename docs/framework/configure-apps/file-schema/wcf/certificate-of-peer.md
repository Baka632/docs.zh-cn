---
title: <certificate> 的 <peer>
ms.date: 03/30/2017
ms.assetid: 48b69142-c957-4305-a042-c9d0c9a55c0e
ms.openlocfilehash: ed24e9061f57798197ad41c1f556ce612a357e9e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555310"
---
# <a name="certificate-of-peer"></a><span data-ttu-id="4aea8-102">\<certificate> 的 \<peer></span><span class="sxs-lookup"><span data-stu-id="4aea8-102">\<certificate> of \<peer></span></span>
<span data-ttu-id="4aea8-103">指定对等方使用的证书。</span><span class="sxs-lookup"><span data-stu-id="4aea8-103">Specifies a certificate used by a peer.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**  
  
## <a name="syntax"></a><span data-ttu-id="4aea8-104">语法</span><span class="sxs-lookup"><span data-stu-id="4aea8-104">Syntax</span></span>  
  
```xml  
<certificate findValue = "String"
             storeLocation = "CurrentUser/LocalMachine"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4aea8-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4aea8-105">Attributes and Elements</span></span>  
 <span data-ttu-id="4aea8-106">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4aea8-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4aea8-107">特性</span><span class="sxs-lookup"><span data-stu-id="4aea8-107">Attributes</span></span>  
  
|<span data-ttu-id="4aea8-108">属性</span><span class="sxs-lookup"><span data-stu-id="4aea8-108">Attribute</span></span>|<span data-ttu-id="4aea8-109">说明</span><span class="sxs-lookup"><span data-stu-id="4aea8-109">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="4aea8-110">一个字符串，包含要在 X.509 证书存储中搜索的值。</span><span class="sxs-lookup"><span data-stu-id="4aea8-110">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="4aea8-111">此属性中包含的类型必须满足指定 `x509FindType` 的要求。</span><span class="sxs-lookup"><span data-stu-id="4aea8-111">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="4aea8-112">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="4aea8-112">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="4aea8-113">指定客户端可用于验证对等方的证书的 X.509 证书存储的位置。</span><span class="sxs-lookup"><span data-stu-id="4aea8-113">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="4aea8-114">有效值包括以下值：</span><span class="sxs-lookup"><span data-stu-id="4aea8-114">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="4aea8-115">-LocalMachine：分配给本地计算机的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="4aea8-115">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="4aea8-116">-CurrentUser：分配给当前用户的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="4aea8-116">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="4aea8-117">默认值为 LocalMachine。</span><span class="sxs-lookup"><span data-stu-id="4aea8-117">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="4aea8-118">指定要打开的 X.509 证书存储区的名称。</span><span class="sxs-lookup"><span data-stu-id="4aea8-118">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="4aea8-119">有效值包括以下值：</span><span class="sxs-lookup"><span data-stu-id="4aea8-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="4aea8-120">-通讯簿：其他用户的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="4aea8-120">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="4aea8-121">-AuthRoot：第三方证书颁发机构的证书存储 (Ca) 。</span><span class="sxs-lookup"><span data-stu-id="4aea8-121">-   AuthRoot: Certificate store for third-party certificate authorities (CAs).</span></span><br /><span data-ttu-id="4aea8-122">-CertificateAuthority：用于中间证书颁发机构的证书存储 (Ca) 。</span><span class="sxs-lookup"><span data-stu-id="4aea8-122">-   CertificateAuthority: Certificate store for intermediate certificate authorities (CAs).</span></span><br /><span data-ttu-id="4aea8-123">-不允许：吊销的证书的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="4aea8-123">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="4aea8-124">-My：个人证书的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="4aea8-124">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="4aea8-125">-Root：受信任的根证书颁发机构的证书存储 (Ca) 。</span><span class="sxs-lookup"><span data-stu-id="4aea8-125">-   Root: Certificate store for trusted root certificate authorities (CAs).</span></span><br /><span data-ttu-id="4aea8-126">-TrustedPeople：直接受信任的人和资源的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="4aea8-126">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="4aea8-127">-TrustedPublisher：直接受信任的发布者的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="4aea8-127">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="4aea8-128">默认值为 My。</span><span class="sxs-lookup"><span data-stu-id="4aea8-128">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="4aea8-129">定义要执行的 X.509 搜索的类型。</span><span class="sxs-lookup"><span data-stu-id="4aea8-129">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="4aea8-130">有效值包括以下值：</span><span class="sxs-lookup"><span data-stu-id="4aea8-130">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="4aea8-131">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="4aea8-131">-   FindByThumbPrint</span></span><br /><span data-ttu-id="4aea8-132">-Findbysubjectname) </span><span class="sxs-lookup"><span data-stu-id="4aea8-132">-   FindBySubjectName</span></span><br /><span data-ttu-id="4aea8-133">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="4aea8-133">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="4aea8-134">- FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="4aea8-134">-   FindByIssuerName</span></span><br /><span data-ttu-id="4aea8-135">- FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="4aea8-135">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="4aea8-136">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="4aea8-136">-   FindBySerialNumber</span></span><br /><span data-ttu-id="4aea8-137">- FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="4aea8-137">-   FindByTimeValid</span></span><br /><span data-ttu-id="4aea8-138">- FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="4aea8-138">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="4aea8-139">- FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="4aea8-139">-   FindByTemplateName</span></span><br /><span data-ttu-id="4aea8-140">- FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="4aea8-140">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="4aea8-141">- FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="4aea8-141">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="4aea8-142">- FindByExtension</span><span class="sxs-lookup"><span data-stu-id="4aea8-142">-   FindByExtension</span></span><br /><span data-ttu-id="4aea8-143">- FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="4aea8-143">-   FindByKeyUsage</span></span><br /><span data-ttu-id="4aea8-144">- FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="4aea8-144">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="4aea8-145">`findValue` 属性中包含的类型必须满足指定 `X509FindType` 的要求。</span><span class="sxs-lookup"><span data-stu-id="4aea8-145">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="4aea8-146">默认值为 FindBySubjectDistinguishedName。</span><span class="sxs-lookup"><span data-stu-id="4aea8-146">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4aea8-147">子元素</span><span class="sxs-lookup"><span data-stu-id="4aea8-147">Child Elements</span></span>  
 <span data-ttu-id="4aea8-148">无。</span><span class="sxs-lookup"><span data-stu-id="4aea8-148">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4aea8-149">父元素</span><span class="sxs-lookup"><span data-stu-id="4aea8-149">Parent Elements</span></span>  
  
|<span data-ttu-id="4aea8-150">元素</span><span class="sxs-lookup"><span data-stu-id="4aea8-150">Element</span></span>|<span data-ttu-id="4aea8-151">说明</span><span class="sxs-lookup"><span data-stu-id="4aea8-151">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-servicecredentials.md)|<span data-ttu-id="4aea8-152">指定对等节点的当前凭据。</span><span class="sxs-lookup"><span data-stu-id="4aea8-152">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4aea8-153">备注</span><span class="sxs-lookup"><span data-stu-id="4aea8-153">Remarks</span></span>  
 <span data-ttu-id="4aea8-154">此配置元素包含对对等网格中的邻居进行身份验证时使用的 `X509Certificate2` 实例。</span><span class="sxs-lookup"><span data-stu-id="4aea8-154">This configuration element contains an `X509Certificate2` instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="4aea8-155">有关对等编程的详细信息，请参阅对等 [网络](../../../wcf/feature-details/peer-to-peer-networking.md)。</span><span class="sxs-lookup"><span data-stu-id="4aea8-155">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4aea8-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="4aea8-156">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>
- <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="4aea8-157">使用证书</span><span class="sxs-lookup"><span data-stu-id="4aea8-157">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="4aea8-158">对等网络</span><span class="sxs-lookup"><span data-stu-id="4aea8-158">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="4aea8-159">[对等通道消息身份验证](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="4aea8-159">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="4aea8-160">[对等通道自定义身份验证](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="4aea8-160">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="4aea8-161">保护对等通道应用程序</span><span class="sxs-lookup"><span data-stu-id="4aea8-161">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="4aea8-162">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="4aea8-162">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
