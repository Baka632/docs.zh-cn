---
title: <servicePrincipalName>
ms.date: 03/30/2017
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
ms.openlocfilehash: 0d03844a58de5b4af93f276de75c88af6efed3f8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153789"
---
# \<servicePrincipalName>

<span data-ttu-id="42376-101">利用对应的服务主体名称 (SPN) 指定服务的标识。</span><span class="sxs-lookup"><span data-stu-id="42376-101">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
<span data-ttu-id="42376-102">有关设置 SPN 的详细信息，请参阅 [服务标识和身份验证](../../../wcf/feature-details/service-identity-and-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="42376-102">For more information about setting the SPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<servicePrincipalName>**  
  
## <a name="syntax"></a><span data-ttu-id="42376-103">语法</span><span class="sxs-lookup"><span data-stu-id="42376-103">Syntax</span></span>  
  
```xml  
<servicePrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42376-104">特性和元素</span><span class="sxs-lookup"><span data-stu-id="42376-104">Attributes and Elements</span></span>  

 <span data-ttu-id="42376-105">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="42376-105">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="42376-106">特性</span><span class="sxs-lookup"><span data-stu-id="42376-106">Attributes</span></span>  
  
|<span data-ttu-id="42376-107">属性</span><span class="sxs-lookup"><span data-stu-id="42376-107">Attribute</span></span>|<span data-ttu-id="42376-108">说明</span><span class="sxs-lookup"><span data-stu-id="42376-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="42376-109">值</span><span class="sxs-lookup"><span data-stu-id="42376-109">value</span></span>|<span data-ttu-id="42376-110">客户端用于唯一标识服务实例的名称。</span><span class="sxs-lookup"><span data-stu-id="42376-110">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="42376-111">如果在计算机的整个目录林上安装多个服务实例，那么每个实例都必须有自己的 SPN。</span><span class="sxs-lookup"><span data-stu-id="42376-111">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="42376-112">如果客户端有多个名称可用于身份验证，则给定的服务实例可以有多个 SPN。</span><span class="sxs-lookup"><span data-stu-id="42376-112">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="42376-113">子元素</span><span class="sxs-lookup"><span data-stu-id="42376-113">Child Elements</span></span>  

 <span data-ttu-id="42376-114">无。</span><span class="sxs-lookup"><span data-stu-id="42376-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="42376-115">父元素</span><span class="sxs-lookup"><span data-stu-id="42376-115">Parent Elements</span></span>  
  
|<span data-ttu-id="42376-116">元素</span><span class="sxs-lookup"><span data-stu-id="42376-116">Element</span></span>|<span data-ttu-id="42376-117">描述</span><span class="sxs-lookup"><span data-stu-id="42376-117">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="42376-118">指定要由客户端进行身份验证的服务的标识。</span><span class="sxs-lookup"><span data-stu-id="42376-118">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42376-119">备注</span><span class="sxs-lookup"><span data-stu-id="42376-119">Remarks</span></span>  

 <span data-ttu-id="42376-120">使用此标识连接到终结点的安全 Windows Communication Foundation (WCF) 客户端在使用终结点进行 SSPI 身份验证时使用 SPN。</span><span class="sxs-lookup"><span data-stu-id="42376-120">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42376-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="42376-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.SpnEndpointIdentity>
- [<span data-ttu-id="42376-122">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="42376-122">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
