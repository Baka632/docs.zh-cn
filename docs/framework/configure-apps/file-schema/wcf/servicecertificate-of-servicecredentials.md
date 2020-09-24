---
title: <serviceCertificate> 的 <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 597ae6d5-4938-4950-9f5e-b2280e816182
ms.openlocfilehash: 936661595813d7b8f3e894efb7bf6cf3aab7e89e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167090"
---
# <a name="servicecertificate-of-servicecredentials"></a><span data-ttu-id="a3a65-102">\<serviceCertificate> 的 \<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="a3a65-102">\<serviceCertificate> of \<serviceCredentials></span></span>

<span data-ttu-id="a3a65-103">指定一个 X.509 证书，以供服务用来向使用 Message 安全模式的客户端证明自己的身份。</span><span class="sxs-lookup"><span data-stu-id="a3a65-103">Specify an X.509 certificate that will be used to authenticate the service to clients using Message security mode.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="a3a65-104">语法</span><span class="sxs-lookup"><span data-stu-id="a3a65-104">Syntax</span></span>  
  
```xml  
<serviceCertificate findValue="String"
                    storeLocation="LocalMachine/CurrentUser"
                    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                    x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a3a65-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a3a65-105">Attributes and Elements</span></span>  

 <span data-ttu-id="a3a65-106">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a3a65-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a3a65-107">特性</span><span class="sxs-lookup"><span data-stu-id="a3a65-107">Attributes</span></span>  
  
|<span data-ttu-id="a3a65-108">属性</span><span class="sxs-lookup"><span data-stu-id="a3a65-108">Attribute</span></span>|<span data-ttu-id="a3a65-109">描述</span><span class="sxs-lookup"><span data-stu-id="a3a65-109">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="a3a65-110">一个字符串，包含要在 X.509 证书存储中搜索的值。</span><span class="sxs-lookup"><span data-stu-id="a3a65-110">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="a3a65-111">此属性中包含的类型必须满足指定 X509FindType 的需求。</span><span class="sxs-lookup"><span data-stu-id="a3a65-111">The type contained in the attribute must satisfy the requirements of the specified X509FindType.</span></span> <span data-ttu-id="a3a65-112">默认值为空字符串。</span><span class="sxs-lookup"><span data-stu-id="a3a65-112">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="a3a65-113">指定客户端可用于验证服务器证书的 X.509 证书存储的位置。</span><span class="sxs-lookup"><span data-stu-id="a3a65-113">Specifies the location of the X.509 certificate store that the client uses to validate the server’s certificate against.</span></span> <span data-ttu-id="a3a65-114">有效值包括以下值：</span><span class="sxs-lookup"><span data-stu-id="a3a65-114">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a3a65-115">-LocalMachine：分配给本地计算机的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="a3a65-115">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="a3a65-116">-CurrentUser：分配给当前用户的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="a3a65-116">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="a3a65-117">默认值为 LocalMachine。</span><span class="sxs-lookup"><span data-stu-id="a3a65-117">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="a3a65-118">指定要打开的 X.509 证书存储区的名称。</span><span class="sxs-lookup"><span data-stu-id="a3a65-118">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="a3a65-119">有效值包括以下值：</span><span class="sxs-lookup"><span data-stu-id="a3a65-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a3a65-120">-通讯簿：其他用户的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="a3a65-120">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="a3a65-121">-AuthRoot：第三方证书颁发机构的证书存储 (Ca) 。</span><span class="sxs-lookup"><span data-stu-id="a3a65-121">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="a3a65-122">-CertificatAuthority：用于中间证书颁发机构的证书存储 (Ca) 。</span><span class="sxs-lookup"><span data-stu-id="a3a65-122">-   CertificatAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="a3a65-123">-不允许：吊销的证书的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="a3a65-123">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="a3a65-124">-My：个人证书的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="a3a65-124">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="a3a65-125">-Root：受信任的根证书颁发机构的证书存储 (Ca) 。</span><span class="sxs-lookup"><span data-stu-id="a3a65-125">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="a3a65-126">-TrustedPeople：直接受信任的人和资源的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="a3a65-126">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="a3a65-127">-TrustedPublisher：直接受信任的发布者的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="a3a65-127">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="a3a65-128">默认值为 My。</span><span class="sxs-lookup"><span data-stu-id="a3a65-128">The default is My.</span></span>|  
|`x509FindType`|<span data-ttu-id="a3a65-129">定义要执行的 X.509 搜索的类型。</span><span class="sxs-lookup"><span data-stu-id="a3a65-129">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="a3a65-130">有效值包括以下值：</span><span class="sxs-lookup"><span data-stu-id="a3a65-130">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a3a65-131">-FindByThumbprint</span><span class="sxs-lookup"><span data-stu-id="a3a65-131">-   FindByThumbprint</span></span><br /><span data-ttu-id="a3a65-132">-Findbysubjectname) </span><span class="sxs-lookup"><span data-stu-id="a3a65-132">-   FindBySubjectName</span></span><br /><span data-ttu-id="a3a65-133">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="a3a65-133">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="a3a65-134">- FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="a3a65-134">-   FindByIssuerName</span></span><br /><span data-ttu-id="a3a65-135">- FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="a3a65-135">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="a3a65-136">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="a3a65-136">-   FindBySerialNumber</span></span><br /><span data-ttu-id="a3a65-137">- FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="a3a65-137">-   FindByTimeValid</span></span><br /><span data-ttu-id="a3a65-138">- FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="a3a65-138">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="a3a65-139">- FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="a3a65-139">-   FindByTemplateName</span></span><br /><span data-ttu-id="a3a65-140">- FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="a3a65-140">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="a3a65-141">- FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="a3a65-141">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="a3a65-142">- FindByExtension</span><span class="sxs-lookup"><span data-stu-id="a3a65-142">-   FindByExtension</span></span><br /><span data-ttu-id="a3a65-143">- FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="a3a65-143">-   FindByKeyUsage</span></span><br /><span data-ttu-id="a3a65-144">- FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="a3a65-144">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="a3a65-145">`findValue` 属性中包含的类型必须满足指定 X509FindType 的要求。</span><span class="sxs-lookup"><span data-stu-id="a3a65-145">The type contained in the `findValue` attribute must satisfy the requirements of the specified X509FindType.</span></span><br /><br /> <span data-ttu-id="a3a65-146">默认值为 FindBySubjectDistinguishedName。</span><span class="sxs-lookup"><span data-stu-id="a3a65-146">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a3a65-147">子元素</span><span class="sxs-lookup"><span data-stu-id="a3a65-147">Child Elements</span></span>  

 <span data-ttu-id="a3a65-148">无</span><span class="sxs-lookup"><span data-stu-id="a3a65-148">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a3a65-149">父元素</span><span class="sxs-lookup"><span data-stu-id="a3a65-149">Parent Elements</span></span>  
  
|<span data-ttu-id="a3a65-150">元素</span><span class="sxs-lookup"><span data-stu-id="a3a65-150">Element</span></span>|<span data-ttu-id="a3a65-151">描述</span><span class="sxs-lookup"><span data-stu-id="a3a65-151">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="a3a65-152">指定要用于对服务进行身份验证的凭据以及与客户端凭据验证相关的设置。</span><span class="sxs-lookup"><span data-stu-id="a3a65-152">Specifies the credential to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3a65-153">备注</span><span class="sxs-lookup"><span data-stu-id="a3a65-153">Remarks</span></span>  

 <span data-ttu-id="a3a65-154">使用此元素可指定一个 X.509 证书，以供服务用来向使用 Message 安全模式的客户端证明自己的身份。</span><span class="sxs-lookup"><span data-stu-id="a3a65-154">Use this element to specify an X.509 certificate that will be used to authenticate the service to clients using Message security mode.</span></span> <span data-ttu-id="a3a65-155">如果您使用的是将会定期续订的证书，则证书的指纹将会变更。</span><span class="sxs-lookup"><span data-stu-id="a3a65-155">If you are using a certificate that will be periodically renewed, then its thumbprint will change.</span></span> <span data-ttu-id="a3a65-156">在此情况下，请使用主题名称作为 `x509FindType`，因为可以使用同一主题名称来重新颁发该证书。</span><span class="sxs-lookup"><span data-stu-id="a3a65-156">In that case, use the subject name as the `x509FindType` because the certificate can be reissued with the same subject name.</span></span>  
  
 <span data-ttu-id="a3a65-157">有关使用元素的详细信息，请参阅 [如何：指定客户端凭据值](../../../wcf/how-to-specify-client-credential-values.md)。</span><span class="sxs-lookup"><span data-stu-id="a3a65-157">For more information about using the element, see [How to: Specify Client Credential Values](../../../wcf/how-to-specify-client-credential-values.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3a65-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="a3a65-158">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ServiceCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>
- <xref:System.ServiceModel.Description.ServiceCredentials.ServiceCertificate%2A>
- [<span data-ttu-id="a3a65-159">如何：指定客户端凭据值</span><span class="sxs-lookup"><span data-stu-id="a3a65-159">How to: Specify Client Credential Values</span></span>](../../../wcf/how-to-specify-client-credential-values.md)
- [<span data-ttu-id="a3a65-160">安全行为</span><span class="sxs-lookup"><span data-stu-id="a3a65-160">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
