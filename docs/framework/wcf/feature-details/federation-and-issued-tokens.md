---
title: 联合令牌与颁发的令牌
ms.date: 03/30/2017
helpviewer_keywords:
- WCF, federation
- issued tokens [WCF]
- federation [WCF], issued tokens
ms.assetid: 4c31ee7d-a820-4067-8b84-a83049021bb6
ms.openlocfilehash: 0ab3d6bad717e71901b4d94c99f1c48f99d8675e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255515"
---
# <a name="federation-and-issued-tokens"></a><span data-ttu-id="77f97-102">联合令牌与颁发的令牌</span><span class="sxs-lookup"><span data-stu-id="77f97-102">Federation and Issued Tokens</span></span>

<span data-ttu-id="77f97-103">利用 Windows Communication Foundation (WCF) ，可以创建与实现 WS-Federation 和 WS-Trust 规范的服务安全通信的客户端。</span><span class="sxs-lookup"><span data-stu-id="77f97-103">With Windows Communication Foundation (WCF), you can create clients that communicate securely with services that implement the WS-Federation and WS-Trust specifications.</span></span> <span data-ttu-id="77f97-104">这些规范使用 XML、SOAP 和 Web 服务描述语言 (WSDL) 来提供用来跨不同的信任领域进行身份验证和授权的机制。</span><span class="sxs-lookup"><span data-stu-id="77f97-104">The specifications use XML, SOAP, and Web Services Description Language (WSDL) to provide mechanisms that enable authentication and authorization across different trust realms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="77f97-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="77f97-105">In This Section</span></span>  

 [<span data-ttu-id="77f97-106">联合</span><span class="sxs-lookup"><span data-stu-id="77f97-106">Federation</span></span>](federation.md)  
 <span data-ttu-id="77f97-107">提供对联合的概述。</span><span class="sxs-lookup"><span data-stu-id="77f97-107">Provides an overview of federation.</span></span>  
  
 [<span data-ttu-id="77f97-108">联合与信任</span><span class="sxs-lookup"><span data-stu-id="77f97-108">Federation and Trust</span></span>](federation-and-trust.md)  
 <span data-ttu-id="77f97-109">列出在创建联合服务或客户端时应注意的设计问题。</span><span class="sxs-lookup"><span data-stu-id="77f97-109">Lists the design issues to be aware of when creating federated services or clients.</span></span>  
  
 [<span data-ttu-id="77f97-110">如何：创建联合客户端</span><span class="sxs-lookup"><span data-stu-id="77f97-110">How to: Create a Federated Client</span></span>](how-to-create-a-federated-client.md)  
 <span data-ttu-id="77f97-111">介绍使用 WCF 创建联合客户端的基础知识。</span><span class="sxs-lookup"><span data-stu-id="77f97-111">Describes the basics of creating a federated client with WCF.</span></span>  
  
 [<span data-ttu-id="77f97-112">如何：在联合身份验证服务上配置凭据</span><span class="sxs-lookup"><span data-stu-id="77f97-112">How to: Configure Credentials on a Federation Service</span></span>](how-to-configure-credentials-on-a-federation-service.md)  
 <span data-ttu-id="77f97-113">描述创建联合服务的步骤。</span><span class="sxs-lookup"><span data-stu-id="77f97-113">Describes the steps of creating a federated service.</span></span>  
  
 [<span data-ttu-id="77f97-114">如何：创建 WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="77f97-114">How to: Create a WSFederationHttpBinding</span></span>](how-to-create-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="77f97-115">描述如何配置使用 `WSFederationHttpBinding` 的客户端和服务。</span><span class="sxs-lookup"><span data-stu-id="77f97-115">Describes how to configure clients and services that use the `WSFederationHttpBinding`.</span></span>  
  
 [<span data-ttu-id="77f97-116">如何：创建安全令牌服务</span><span class="sxs-lookup"><span data-stu-id="77f97-116">How to: Create a Security Token Service</span></span>](how-to-create-a-security-token-service.md)  
 <span data-ttu-id="77f97-117">描述创建安全令牌服务的步骤。</span><span class="sxs-lookup"><span data-stu-id="77f97-117">Describes the steps of creating a security token service.</span></span>  
  
 [<span data-ttu-id="77f97-118">安全断言标记语言 (SAML) 令牌和声明</span><span class="sxs-lookup"><span data-stu-id="77f97-118">Security Assertions Markup Language (SAML) Tokens and Claims</span></span>](saml-tokens-and-claims.md)  
 <span data-ttu-id="77f97-119">描述可扩展并能够用来创建丰富的声明类型的安全断言标记语言 (SAML) 令牌。</span><span class="sxs-lookup"><span data-stu-id="77f97-119">Describes Security Assertions Markup Language (SAML) tokens, which are extensible and enable you to create rich claim types.</span></span>  
  
 [<span data-ttu-id="77f97-120">如何：配置本地颁发者</span><span class="sxs-lookup"><span data-stu-id="77f97-120">How to: Configure a Local Issuer</span></span>](how-to-configure-a-local-issuer.md)  
 <span data-ttu-id="77f97-121">描述如何创建安全令牌的本地颁发机构。</span><span class="sxs-lookup"><span data-stu-id="77f97-121">Describes how to create a local issuer of security tokens.</span></span>  
  
 [<span data-ttu-id="77f97-122">如何：在 WSFederationHttpBinding 上禁用安全会话</span><span class="sxs-lookup"><span data-stu-id="77f97-122">How to: Disable Secure Sessions on a WSFederationHttpBinding</span></span>](how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="77f97-123">描述如何在 `WSFederationHttpBinding` 上禁用安全会话。</span><span class="sxs-lookup"><span data-stu-id="77f97-123">Describes how to disable secure sessions on a `WSFederationHttpBinding`.</span></span> <span data-ttu-id="77f97-124">在创建要求每个客户端都有一个会话的网络场时，有必要禁用安全会话。</span><span class="sxs-lookup"><span data-stu-id="77f97-124">Disabling secure sessions is necessary when creating a Web farm that requires a session for each client.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="77f97-125">参考</span><span class="sxs-lookup"><span data-stu-id="77f97-125">Reference</span></span>  

 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.IdentityModel.Tokens.SamlSecurityToken>  
  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenProvider>  
  
 <xref:System.ServiceModel.WSFederationHttpBinding>  
  
## <a name="see-also"></a><span data-ttu-id="77f97-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="77f97-126">See also</span></span>

- [<span data-ttu-id="77f97-127">授权</span><span class="sxs-lookup"><span data-stu-id="77f97-127">Authorization</span></span>](authorization-in-wcf.md)
- [<span data-ttu-id="77f97-128">自定义令牌</span><span class="sxs-lookup"><span data-stu-id="77f97-128">Custom Tokens</span></span>](../extending/custom-tokens.md)
- <span data-ttu-id="77f97-129">[Windows Server App Fabric 的安全模型](/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="77f97-129">[Security Model for Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
