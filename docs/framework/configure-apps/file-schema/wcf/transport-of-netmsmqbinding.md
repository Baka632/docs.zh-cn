---
title: <transport> 的 <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
ms.openlocfilehash: 84a5437de851ecdb96d0463ec574186ba5f91d9e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203873"
---
# <a name="transport-of-netmsmqbinding"></a><span data-ttu-id="79533-102">\<transport> 的 \<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="79533-102">\<transport> of \<netMsmqBinding></span></span>

<span data-ttu-id="79533-103">定义传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="79533-103">Defines the transport security settings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="79533-104">语法</span><span class="sxs-lookup"><span data-stu-id="79533-104">Syntax</span></span>  
  
```xml  
<netMsmqBinding>
  <binding>
    <security>
      <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
                 msmqEncryptionAlgorithm="RC4Stream/AES"
                 msmqProtectionLevel="None/Sign/EncryptAndSign"
                 msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
    </security>
  </binding>
</netMsmqBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="79533-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="79533-105">Attributes and Elements</span></span>  

 <span data-ttu-id="79533-106">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="79533-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="79533-107">特性</span><span class="sxs-lookup"><span data-stu-id="79533-107">Attributes</span></span>  
  
|<span data-ttu-id="79533-108">属性</span><span class="sxs-lookup"><span data-stu-id="79533-108">Attribute</span></span>|<span data-ttu-id="79533-109">描述</span><span class="sxs-lookup"><span data-stu-id="79533-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="79533-110">msmqAuthenticationMode</span><span class="sxs-lookup"><span data-stu-id="79533-110">msmqAuthenticationMode</span></span>|<span data-ttu-id="79533-111">指定 MSMQ 传输必须采用什么方式对消息进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="79533-111">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="79533-112">有效值包括以下值：</span><span class="sxs-lookup"><span data-stu-id="79533-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="79533-113">-None：无身份验证。</span><span class="sxs-lookup"><span data-stu-id="79533-113">-   None: No authentication.</span></span><br /><span data-ttu-id="79533-114">-WindowsDomain：身份验证机制使用 Active Directory 检索与消息关联的安全标识符的 x.509 证书。</span><span class="sxs-lookup"><span data-stu-id="79533-114">-   WindowsDomain: The authentication mechanism uses Active Directory to retrieve the X.509 certificate for the security identifier associated with the message.</span></span> <span data-ttu-id="79533-115">然后使用它来检查队列的 ACL 以确保用户具有队列写权限。</span><span class="sxs-lookup"><span data-stu-id="79533-115">This is then used to check the ACL of the queue to ensure the user has write permission for the queue.</span></span><br /><span data-ttu-id="79533-116">-Certificate：通道从证书存储中检索证书。</span><span class="sxs-lookup"><span data-stu-id="79533-116">-   Certificate: The channel retrieves the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="79533-117">默认为 `WindowsDomain`。</span><span class="sxs-lookup"><span data-stu-id="79533-117">The default is `WindowsDomain`.</span></span><br /><br /> <span data-ttu-id="79533-118">如果将此属性设置为 `None`，则 `msmqProtectionLevel` 属性也必须设置为 `None`。</span><span class="sxs-lookup"><span data-stu-id="79533-118">If this attribute is set to `None`, the `msmqProtectionLevel` attribute must also be set to `None`.</span></span> <span data-ttu-id="79533-119">此特性的类型为 <xref:System.ServiceModel.MsmqAuthenticationMode></span><span class="sxs-lookup"><span data-stu-id="79533-119">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode></span></span>|  
|<span data-ttu-id="79533-120">msmqEncryptionAlgorithm</span><span class="sxs-lookup"><span data-stu-id="79533-120">msmqEncryptionAlgorithm</span></span>|<span data-ttu-id="79533-121">指定在消息队列管理器之间传输消息时用于在网络上对消息进行加密的算法。</span><span class="sxs-lookup"><span data-stu-id="79533-121">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="79533-122">有效值包括以下值：</span><span class="sxs-lookup"><span data-stu-id="79533-122">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="79533-123">-RC4Stream</span><span class="sxs-lookup"><span data-stu-id="79533-123">-   RC4Stream</span></span><br /><span data-ttu-id="79533-124">-AES</span><span class="sxs-lookup"><span data-stu-id="79533-124">-   AES</span></span><br /><span data-ttu-id="79533-125">-默认值为 `RC4Stream` 。</span><span class="sxs-lookup"><span data-stu-id="79533-125">-   The default value is `RC4Stream`.</span></span> <span data-ttu-id="79533-126">此属性的类型为 <xref:System.ServiceModel.MsmqEncryptionAlgorithm>。</span><span class="sxs-lookup"><span data-stu-id="79533-126">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|<span data-ttu-id="79533-127">msmqProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="79533-127">msmqProtectionLevel</span></span>|<span data-ttu-id="79533-128">指定在 MSMQ 传输级别采用什么方式来保护消息。</span><span class="sxs-lookup"><span data-stu-id="79533-128">Specifies the way messages are secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="79533-129">加密可确保消息的完整性，而签名和加密不仅可以确保消息的完整性，还可以确保消息的不可否认性。</span><span class="sxs-lookup"><span data-stu-id="79533-129">Encryption ensures message integrity, while sign and encrypt ensures both message integrity and non-repudiation.</span></span> <span data-ttu-id="79533-130">也就是说，消息确实来自发件人，发件人是谁说。</span><span class="sxs-lookup"><span data-stu-id="79533-130">That is, the message indeed came from the sender and the sender is who they say they are.</span></span> <span data-ttu-id="79533-131">有效值包括以下值：</span><span class="sxs-lookup"><span data-stu-id="79533-131">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="79533-132">-None：无保护。</span><span class="sxs-lookup"><span data-stu-id="79533-132">-   None: No protection.</span></span><br /><span data-ttu-id="79533-133">-Sign：对消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="79533-133">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="79533-134">-EncryptAndSign：对消息进行加密和签名。</span><span class="sxs-lookup"><span data-stu-id="79533-134">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><span data-ttu-id="79533-135">-默认值为 `Sign` 。</span><span class="sxs-lookup"><span data-stu-id="79533-135">-   The default is `Sign`.</span></span>|  
|<span data-ttu-id="79533-136">msmqSecureHashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="79533-136">msmqSecureHashAlgorithm</span></span>|<span data-ttu-id="79533-137">指定用于计算消息摘要的哈希算法。</span><span class="sxs-lookup"><span data-stu-id="79533-137">Specifies the hash algorithm to be used for computing the message digest.</span></span> <span data-ttu-id="79533-138">有效值包括以下值：</span><span class="sxs-lookup"><span data-stu-id="79533-138">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="79533-139">-MD5</span><span class="sxs-lookup"><span data-stu-id="79533-139">-   MD5</span></span><br /><span data-ttu-id="79533-140">-SHA1</span><span class="sxs-lookup"><span data-stu-id="79533-140">-   SHA1</span></span><br /><span data-ttu-id="79533-141">-SHA256</span><span class="sxs-lookup"><span data-stu-id="79533-141">-   SHA256</span></span><br /><span data-ttu-id="79533-142">-SHA512</span><span class="sxs-lookup"><span data-stu-id="79533-142">-   SHA512</span></span><br /><br /> <span data-ttu-id="79533-143">默认为 `SHA1`。</span><span class="sxs-lookup"><span data-stu-id="79533-143">The default is `SHA1`.</span></span> <span data-ttu-id="79533-144">此属性的类型为 <xref:System.ServiceModel.MsmqSecureHashAlgorithm>。</span><span class="sxs-lookup"><span data-stu-id="79533-144">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span><br><span data-ttu-id="79533-145">由于 MD5 和 SHA1 出现冲突，Microsoft 建议 SHA256 或更好。</span><span class="sxs-lookup"><span data-stu-id="79533-145">Due to collision problems with MD5 and SHA1, Microsoft recommends SHA256 or better.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="79533-146">子元素</span><span class="sxs-lookup"><span data-stu-id="79533-146">Child Elements</span></span>  

 <span data-ttu-id="79533-147">无</span><span class="sxs-lookup"><span data-stu-id="79533-147">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="79533-148">父元素</span><span class="sxs-lookup"><span data-stu-id="79533-148">Parent Elements</span></span>  
  
|<span data-ttu-id="79533-149">元素</span><span class="sxs-lookup"><span data-stu-id="79533-149">Element</span></span>|<span data-ttu-id="79533-150">描述</span><span class="sxs-lookup"><span data-stu-id="79533-150">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-netmsmqbinding.md)|<span data-ttu-id="79533-151">定义排队传输的传输安全设置。</span><span class="sxs-lookup"><span data-stu-id="79533-151">Defines the transport security settings for queued transports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="79533-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="79533-152">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [<span data-ttu-id="79533-153">WCF 中的队列</span><span class="sxs-lookup"><span data-stu-id="79533-153">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="79533-154">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="79533-154">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="79533-155">绑定</span><span class="sxs-lookup"><span data-stu-id="79533-155">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="79533-156">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="79533-156">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="79533-157">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="79533-157">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
