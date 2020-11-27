---
title: 安全协议版本 1.0
ms.date: 03/30/2017
ms.assetid: ee3402d2-1076-410b-a3cb-fae0372bd7af
ms.openlocfilehash: d98a05bbcb8413c33672a17580c6d16b57c63b83
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254020"
---
# <a name="security-protocols-version-10"></a><span data-ttu-id="74e76-102">安全协议版本 1.0</span><span class="sxs-lookup"><span data-stu-id="74e76-102">Security Protocols version 1.0</span></span>

<span data-ttu-id="74e76-103">Web 服务安全协议提供 Web 服务安全机制，这些机制可满足所有现有企业的消息传递安全要求。</span><span class="sxs-lookup"><span data-stu-id="74e76-103">The Web Services Security Protocols provide Web services security mechanisms that cover all existing enterprise messaging security requirements.</span></span> <span data-ttu-id="74e76-104">本部分介绍 (WCF) 版本1.0 详细信息 (在 <xref:System.ServiceModel.Channels.SecurityBindingElement>) 中为以下 Web 服务安全协议实现的 Windows Communication Foundation。</span><span class="sxs-lookup"><span data-stu-id="74e76-104">This section describes the Windows Communication Foundation (WCF) version 1.0 details (implemented in the <xref:System.ServiceModel.Channels.SecurityBindingElement>) for the following Web services security protocols.</span></span>  
  
|<span data-ttu-id="74e76-105">规范/文档</span><span class="sxs-lookup"><span data-stu-id="74e76-105">Specification/Document</span></span>|<span data-ttu-id="74e76-106">链接</span><span class="sxs-lookup"><span data-stu-id="74e76-106">Link</span></span>|  
|-|-|  
|<span data-ttu-id="74e76-107">WSS：SOAP 消息安全 1.0</span><span class="sxs-lookup"><span data-stu-id="74e76-107">WSS: SOAP Message Security 1.0</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf>|
|<span data-ttu-id="74e76-108">WSS：用户名令牌配置文件 1.0</span><span class="sxs-lookup"><span data-stu-id="74e76-108">WSS: Username Token Profile 1.0</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf>|
|<span data-ttu-id="74e76-109">WSS：X509 令牌配置文件 1.0</span><span class="sxs-lookup"><span data-stu-id="74e76-109">WSS: X509 Token Profile 1.0</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0.pdf>|
|<span data-ttu-id="74e76-110">WSS：SAML 1.1 令牌配置文件 1.0</span><span class="sxs-lookup"><span data-stu-id="74e76-110">WSS: SAML 1.1 Token Profile 1.0</span></span>|<https://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.0.pdf>|
|<span data-ttu-id="74e76-111">WSS：SOAP 消息安全 1.1</span><span class="sxs-lookup"><span data-stu-id="74e76-111">WSS: SOAP Message Security 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16790/wss-v1.1-spec-os-SOAPMessageSecurity.pdf>|
|<span data-ttu-id="74e76-112">WSS 用户名令牌配置文件 1.1</span><span class="sxs-lookup"><span data-stu-id="74e76-112">WSS Username Token Profile 1.1</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf>|
|<span data-ttu-id="74e76-113">WSS：X.509 令牌配置文件 1.1</span><span class="sxs-lookup"><span data-stu-id="74e76-113">WSS: X.509 Token Profile 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16785/wss-v1.1-spec-os-x509TokenProfile.pdf>|
|<span data-ttu-id="74e76-114">WSS：Kerberos 令牌配置文件 1.1</span><span class="sxs-lookup"><span data-stu-id="74e76-114">WSS: Kerberos Token Profile 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16788/wss-v1.1-spec-os-KerberosTokenProfile.pdf>|
|<span data-ttu-id="74e76-115">WSS：SAML 1.1 令牌配置文件 1.1</span><span class="sxs-lookup"><span data-stu-id="74e76-115">WSS: SAML 1.1 Token Profile 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16768/wss-v1.1-spec-os-SAMLTokenProfile.pdf>|
|<span data-ttu-id="74e76-116">WS-Secure 对话</span><span class="sxs-lookup"><span data-stu-id="74e76-116">WS-Secure Conversation</span></span>|<http://specs.xmlsoap.org/ws/2005/02/sc/WS-SecureConversation.pdf>|
|<span data-ttu-id="74e76-117">WS-Trust</span><span class="sxs-lookup"><span data-stu-id="74e76-117">WS-Trust</span></span>|<http://specs.xmlsoap.org/ws/2005/02/trust/ws-trust.pdf>|
|<span data-ttu-id="74e76-118">应用说明：</span><span class="sxs-lookup"><span data-stu-id="74e76-118">Application Note:</span></span><br /><br /> <span data-ttu-id="74e76-119">将 WS-Trust 用于 TLS 握手</span><span class="sxs-lookup"><span data-stu-id="74e76-119">Using WS-Trust for TLS Handshake</span></span>|<span data-ttu-id="74e76-120">即将发布</span><span class="sxs-lookup"><span data-stu-id="74e76-120">To be published</span></span>|  
|<span data-ttu-id="74e76-121">应用说明：</span><span class="sxs-lookup"><span data-stu-id="74e76-121">Application Note:</span></span><br /><br /> <span data-ttu-id="74e76-122">将 WS-Trust 用于 SPNEGO</span><span class="sxs-lookup"><span data-stu-id="74e76-122">Using WS-Trust for SPNEGO</span></span>|<span data-ttu-id="74e76-123">即将发布</span><span class="sxs-lookup"><span data-stu-id="74e76-123">To be published</span></span>|  
|<span data-ttu-id="74e76-124">应用说明：</span><span class="sxs-lookup"><span data-stu-id="74e76-124">Application Note:</span></span><br /><br /> <span data-ttu-id="74e76-125">Web 服务寻址终结点引用和标识</span><span class="sxs-lookup"><span data-stu-id="74e76-125">Web Services Addressing Endpoint References And Identity</span></span>|<span data-ttu-id="74e76-126">即将发布</span><span class="sxs-lookup"><span data-stu-id="74e76-126">To be published</span></span>|  
|<span data-ttu-id="74e76-127">WS-SecurityPolicy 1.1</span><span class="sxs-lookup"><span data-stu-id="74e76-127">WS-SecurityPolicy 1.1</span></span><br /><br /> <span data-ttu-id="74e76-128">(2005/07)</span><span class="sxs-lookup"><span data-stu-id="74e76-128">(2005/07)</span></span>|<http://specs.xmlsoap.org/ws/2005/07/securitypolicy/ws-securitypolicy.pdf><br /><br /> <span data-ttu-id="74e76-129">正如提交给 OASIS WS-I 技术委员会的 [勘误表](https://lists.oasis-open.org/archives/ws-sx/200512/msg00017.html) 所修改</span><span class="sxs-lookup"><span data-stu-id="74e76-129">as amended by [errata](https://lists.oasis-open.org/archives/ws-sx/200512/msg00017.html) submitted to OASIS WS-SX Technical Committee</span></span> |  
  
 <span data-ttu-id="74e76-130">WCF，版本1提供17个身份验证模式，可用作 Web 服务安全配置的基础。</span><span class="sxs-lookup"><span data-stu-id="74e76-130">WCF, version 1, provides 17 authentication modes that can be used as the basis for Web services security configuration.</span></span> <span data-ttu-id="74e76-131">每一种模式都针对一组常用部署需求进行了优化，如：</span><span class="sxs-lookup"><span data-stu-id="74e76-131">Each mode is optimized for a common set of deployment requirements, such as:</span></span>  
  
- <span data-ttu-id="74e76-132">用于对客户端和服务进行身份验证的凭据。</span><span class="sxs-lookup"><span data-stu-id="74e76-132">Credentials used to authenticate client and service.</span></span>  
  
- <span data-ttu-id="74e76-133">消息或传输安全保护机制。</span><span class="sxs-lookup"><span data-stu-id="74e76-133">Message or transport security protection mechanisms.</span></span>  
  
- <span data-ttu-id="74e76-134">消息交换模式。</span><span class="sxs-lookup"><span data-stu-id="74e76-134">Message exchange patterns.</span></span>  
  
|<span data-ttu-id="74e76-135">身份验证模式</span><span class="sxs-lookup"><span data-stu-id="74e76-135">Authentication Mode</span></span>|<span data-ttu-id="74e76-136">客户端身份验证</span><span class="sxs-lookup"><span data-stu-id="74e76-136">Client Authentication</span></span>|<span data-ttu-id="74e76-137">服务器身份验证</span><span class="sxs-lookup"><span data-stu-id="74e76-137">Server Authentication</span></span>|<span data-ttu-id="74e76-138">“模式”</span><span class="sxs-lookup"><span data-stu-id="74e76-138">Mode</span></span>|  
|-------------------------|---------------------------|---------------------------|----------|  
|<span data-ttu-id="74e76-139">UserNameOverTransport</span><span class="sxs-lookup"><span data-stu-id="74e76-139">UserNameOverTransport</span></span>|<span data-ttu-id="74e76-140">用户名/密码</span><span class="sxs-lookup"><span data-stu-id="74e76-140">User name/password</span></span>|<span data-ttu-id="74e76-141">X509</span><span class="sxs-lookup"><span data-stu-id="74e76-141">X509</span></span>|<span data-ttu-id="74e76-142">Transport</span><span class="sxs-lookup"><span data-stu-id="74e76-142">Transport</span></span>|  
|<span data-ttu-id="74e76-143">CertificateOverTransport</span><span class="sxs-lookup"><span data-stu-id="74e76-143">CertificateOverTransport</span></span>|<span data-ttu-id="74e76-144">X509</span><span class="sxs-lookup"><span data-stu-id="74e76-144">X509</span></span>|<span data-ttu-id="74e76-145">X509</span><span class="sxs-lookup"><span data-stu-id="74e76-145">X509</span></span>|<span data-ttu-id="74e76-146">Transport</span><span class="sxs-lookup"><span data-stu-id="74e76-146">Transport</span></span>|  
|<span data-ttu-id="74e76-147">KerberosOverTransport</span><span class="sxs-lookup"><span data-stu-id="74e76-147">KerberosOverTransport</span></span>|<span data-ttu-id="74e76-148">Windows</span><span class="sxs-lookup"><span data-stu-id="74e76-148">Windows</span></span>|<span data-ttu-id="74e76-149">X509</span><span class="sxs-lookup"><span data-stu-id="74e76-149">X509</span></span>|<span data-ttu-id="74e76-150">Transport</span><span class="sxs-lookup"><span data-stu-id="74e76-150">Transport</span></span>|  
|<span data-ttu-id="74e76-151">IssuedTokenOverTransport</span><span class="sxs-lookup"><span data-stu-id="74e76-151">IssuedTokenOverTransport</span></span>|<span data-ttu-id="74e76-152">联合</span><span class="sxs-lookup"><span data-stu-id="74e76-152">Federated</span></span>|<span data-ttu-id="74e76-153">X509</span><span class="sxs-lookup"><span data-stu-id="74e76-153">X509</span></span>|<span data-ttu-id="74e76-154">Transport</span><span class="sxs-lookup"><span data-stu-id="74e76-154">Transport</span></span>|  
|<span data-ttu-id="74e76-155">SspiNegotiatedOverTransport</span><span class="sxs-lookup"><span data-stu-id="74e76-155">SspiNegotiatedOverTransport</span></span>|<span data-ttu-id="74e76-156">协商的 Windows Sspi</span><span class="sxs-lookup"><span data-stu-id="74e76-156">Windows Sspi Negotiated</span></span>|<span data-ttu-id="74e76-157">协商的 Windows Sspi</span><span class="sxs-lookup"><span data-stu-id="74e76-157">Windows Sspi Negotiated</span></span>|<span data-ttu-id="74e76-158">Transport</span><span class="sxs-lookup"><span data-stu-id="74e76-158">Transport</span></span>|  
|<span data-ttu-id="74e76-159">AnonymousForCertificate</span><span class="sxs-lookup"><span data-stu-id="74e76-159">AnonymousForCertificate</span></span>|<span data-ttu-id="74e76-160">无</span><span class="sxs-lookup"><span data-stu-id="74e76-160">None</span></span>|<span data-ttu-id="74e76-161">X509</span><span class="sxs-lookup"><span data-stu-id="74e76-161">X509</span></span>|<span data-ttu-id="74e76-162">消息</span><span class="sxs-lookup"><span data-stu-id="74e76-162">Message</span></span>|  
|<span data-ttu-id="74e76-163">UserNameForCertificate</span><span class="sxs-lookup"><span data-stu-id="74e76-163">UserNameForCertificate</span></span>|<span data-ttu-id="74e76-164">用户名/密码</span><span class="sxs-lookup"><span data-stu-id="74e76-164">User name/password</span></span>|<span data-ttu-id="74e76-165">X509</span><span class="sxs-lookup"><span data-stu-id="74e76-165">X509</span></span>|<span data-ttu-id="74e76-166">消息</span><span class="sxs-lookup"><span data-stu-id="74e76-166">Message</span></span>|  
|<span data-ttu-id="74e76-167">MutualCertificate</span><span class="sxs-lookup"><span data-stu-id="74e76-167">MutualCertificate</span></span>|<span data-ttu-id="74e76-168">X509</span><span class="sxs-lookup"><span data-stu-id="74e76-168">X509</span></span>|<span data-ttu-id="74e76-169">X509</span><span class="sxs-lookup"><span data-stu-id="74e76-169">X509</span></span>|<span data-ttu-id="74e76-170">消息</span><span class="sxs-lookup"><span data-stu-id="74e76-170">Message</span></span>|  
|<span data-ttu-id="74e76-171">MutualCertificateDuplex</span><span class="sxs-lookup"><span data-stu-id="74e76-171">MutualCertificateDuplex</span></span>|<span data-ttu-id="74e76-172">X509</span><span class="sxs-lookup"><span data-stu-id="74e76-172">X509</span></span>|<span data-ttu-id="74e76-173">X509</span><span class="sxs-lookup"><span data-stu-id="74e76-173">X509</span></span>|<span data-ttu-id="74e76-174">消息</span><span class="sxs-lookup"><span data-stu-id="74e76-174">Message</span></span>|  
|<span data-ttu-id="74e76-175">IssuedTokenForCertificate</span><span class="sxs-lookup"><span data-stu-id="74e76-175">IssuedTokenForCertificate</span></span>|<span data-ttu-id="74e76-176">联合</span><span class="sxs-lookup"><span data-stu-id="74e76-176">Federated</span></span>|<span data-ttu-id="74e76-177">X509</span><span class="sxs-lookup"><span data-stu-id="74e76-177">X509</span></span>|<span data-ttu-id="74e76-178">消息</span><span class="sxs-lookup"><span data-stu-id="74e76-178">Message</span></span>|  
|<span data-ttu-id="74e76-179">Kerberos</span><span class="sxs-lookup"><span data-stu-id="74e76-179">Kerberos</span></span>|<span data-ttu-id="74e76-180">Windows</span><span class="sxs-lookup"><span data-stu-id="74e76-180">Windows</span></span>|<span data-ttu-id="74e76-181">Windows</span><span class="sxs-lookup"><span data-stu-id="74e76-181">Windows</span></span>|<span data-ttu-id="74e76-182">消息</span><span class="sxs-lookup"><span data-stu-id="74e76-182">Message</span></span>|  
|<span data-ttu-id="74e76-183">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="74e76-183">IssuedToken</span></span>|<span data-ttu-id="74e76-184">联合</span><span class="sxs-lookup"><span data-stu-id="74e76-184">Federated</span></span>|<span data-ttu-id="74e76-185">联合</span><span class="sxs-lookup"><span data-stu-id="74e76-185">Federated</span></span>|<span data-ttu-id="74e76-186">消息</span><span class="sxs-lookup"><span data-stu-id="74e76-186">Message</span></span>|  
|<span data-ttu-id="74e76-187">SspiNegotiated</span><span class="sxs-lookup"><span data-stu-id="74e76-187">SspiNegotiated</span></span>|<span data-ttu-id="74e76-188">协商的 Windows Sspi</span><span class="sxs-lookup"><span data-stu-id="74e76-188">Windows Sspi Negotiated</span></span>|<span data-ttu-id="74e76-189">协商的 Windows Sspi</span><span class="sxs-lookup"><span data-stu-id="74e76-189">Windows Sspi Negotiated</span></span>|<span data-ttu-id="74e76-190">消息</span><span class="sxs-lookup"><span data-stu-id="74e76-190">Message</span></span>|  
|<span data-ttu-id="74e76-191">AnonymousForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="74e76-191">AnonymousForSslNegotiated</span></span>|<span data-ttu-id="74e76-192">无</span><span class="sxs-lookup"><span data-stu-id="74e76-192">None</span></span>|<span data-ttu-id="74e76-193">X509、TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="74e76-193">X509, TLS-Nego</span></span>|<span data-ttu-id="74e76-194">消息</span><span class="sxs-lookup"><span data-stu-id="74e76-194">Message</span></span>|  
|<span data-ttu-id="74e76-195">UserNameForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="74e76-195">UserNameForSslNegotiated</span></span>|<span data-ttu-id="74e76-196">用户名/密码</span><span class="sxs-lookup"><span data-stu-id="74e76-196">User name/password</span></span>|<span data-ttu-id="74e76-197">X509、TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="74e76-197">X509, TLS-Nego</span></span>|<span data-ttu-id="74e76-198">消息</span><span class="sxs-lookup"><span data-stu-id="74e76-198">Message</span></span>|  
|<span data-ttu-id="74e76-199">MutualSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="74e76-199">MutualSslNegotiated</span></span>|<span data-ttu-id="74e76-200">X509</span><span class="sxs-lookup"><span data-stu-id="74e76-200">X509</span></span>|<span data-ttu-id="74e76-201">X509、TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="74e76-201">X509, TLS-Nego</span></span>|<span data-ttu-id="74e76-202">消息</span><span class="sxs-lookup"><span data-stu-id="74e76-202">Message</span></span>|  
|<span data-ttu-id="74e76-203">IssuedTokenForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="74e76-203">IssuedTokenForSslNegotiated</span></span>|<span data-ttu-id="74e76-204">联合</span><span class="sxs-lookup"><span data-stu-id="74e76-204">Federated</span></span>|<span data-ttu-id="74e76-205">X509、TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="74e76-205">X509, TLS-Nego</span></span>|<span data-ttu-id="74e76-206">消息</span><span class="sxs-lookup"><span data-stu-id="74e76-206">Message</span></span>|  
  
 <span data-ttu-id="74e76-207">使用此类身份验证模式的终结点可以使用 WS-SecurityPolicy (WS-SP) 表示其安全要求。</span><span class="sxs-lookup"><span data-stu-id="74e76-207">Endpoints using such authentication modes can express their security requirements using WS-SecurityPolicy (WS-SP).</span></span> <span data-ttu-id="74e76-208">本文档介绍每种身份验证模式的安全标头和基础结构消息的结构，并提供策略和消息的示例。</span><span class="sxs-lookup"><span data-stu-id="74e76-208">This document describes the structure of security header and infrastructure messages for each authentication mode and provides examples of policies and messages.</span></span>  
  
 <span data-ttu-id="74e76-209">WCF 利用 WS-SecureConversation 提供安全会话支持来保护应用程序之间的多消息交换。</span><span class="sxs-lookup"><span data-stu-id="74e76-209">WCF leverages WS-SecureConversation to provide secure sessions support to protect multi-message exchanges between applications.</span></span>  <span data-ttu-id="74e76-210">请参见下面的“安全会话”了解实现细节。</span><span class="sxs-lookup"><span data-stu-id="74e76-210">See "Secure Sessions" below for implementation details.</span></span>  
  
 <span data-ttu-id="74e76-211">除了身份验证模式之外，WCF 还提供一些设置，用于控制适用于大多数基于消息安全的身份验证模式的常见保护机制，例如：签名和加密操作的顺序、算法套件、密钥派生和签名确认。</span><span class="sxs-lookup"><span data-stu-id="74e76-211">In addition to authentication modes, WCF provides settings to control common protection mechanisms that apply to most message security-based authentication modes, for example: order of signature versus encryption operations, algorithm suites, key derivation, and signature confirmation.</span></span>  
  
 <span data-ttu-id="74e76-212">本文档使用以下前缀和命名空间。</span><span class="sxs-lookup"><span data-stu-id="74e76-212">The following prefixes and namespaces are used in this document.</span></span>  
  
|<span data-ttu-id="74e76-213">前缀</span><span class="sxs-lookup"><span data-stu-id="74e76-213">Prefix</span></span>|<span data-ttu-id="74e76-214">命名空间</span><span class="sxs-lookup"><span data-stu-id="74e76-214">Namespace</span></span>|  
|------------|---------------|  
|<span data-ttu-id="74e76-215">s</span><span class="sxs-lookup"><span data-stu-id="74e76-215">s</span></span>|<http://www.w3.org/2003/05/soap-envelope/>|
|<span data-ttu-id="74e76-216">sp</span><span class="sxs-lookup"><span data-stu-id="74e76-216">sp</span></span>|<http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/>|
|<span data-ttu-id="74e76-217">a</span><span class="sxs-lookup"><span data-stu-id="74e76-217">a</span></span>|<http://www.w3.org/2005/08/addressing>|  
|<span data-ttu-id="74e76-218">wsse</span><span class="sxs-lookup"><span data-stu-id="74e76-218">wsse</span></span>|<span data-ttu-id="74e76-219">TBD – OASIS WSS 1.0 URI</span><span class="sxs-lookup"><span data-stu-id="74e76-219">TBD – OASIS WSS 1.0 URI</span></span>|  
|<span data-ttu-id="74e76-220">wsse11</span><span class="sxs-lookup"><span data-stu-id="74e76-220">wsse11</span></span>|<span data-ttu-id="74e76-221">TBD – OASIS WSS 1.1 URI</span><span class="sxs-lookup"><span data-stu-id="74e76-221">TBD – OASIS WSS 1.1 URI</span></span>|  
|<span data-ttu-id="74e76-222">wsu</span><span class="sxs-lookup"><span data-stu-id="74e76-222">wsu</span></span>|<span data-ttu-id="74e76-223">TBD – OASIS WSS 1.0 Utility URI</span><span class="sxs-lookup"><span data-stu-id="74e76-223">TBD – OASIS WSS 1.0 Utility URI</span></span>|  
|<span data-ttu-id="74e76-224">ds</span><span class="sxs-lookup"><span data-stu-id="74e76-224">ds</span></span>|<span data-ttu-id="74e76-225">TBD – W3C XMLDSig URI</span><span class="sxs-lookup"><span data-stu-id="74e76-225">TBD – W3C XMLDSig URI</span></span>|  
|<span data-ttu-id="74e76-226">wst</span><span class="sxs-lookup"><span data-stu-id="74e76-226">wst</span></span>|<span data-ttu-id="74e76-227">TBD – WS-Trust 2005/02 URI</span><span class="sxs-lookup"><span data-stu-id="74e76-227">TBD – WS-Trust 2005/02 URI</span></span>|  
|<span data-ttu-id="74e76-228">wssc</span><span class="sxs-lookup"><span data-stu-id="74e76-228">wssc</span></span>|<span data-ttu-id="74e76-229">TBD – WS-SecureConversation 2005/02 URI</span><span class="sxs-lookup"><span data-stu-id="74e76-229">TBD – WS-SecureConversation 2005/02 URI</span></span>|  
|<span data-ttu-id="74e76-230">wsaw</span><span class="sxs-lookup"><span data-stu-id="74e76-230">wsaw</span></span>|<span data-ttu-id="74e76-231">TBD - WS-Addressing 策略命名空间</span><span class="sxs-lookup"><span data-stu-id="74e76-231">TBD - WS-Addressing policy namespace</span></span>|  
|<span data-ttu-id="74e76-232">wsp</span><span class="sxs-lookup"><span data-stu-id="74e76-232">wsp</span></span>|<http://schemas.xmlsoap.org/ws/2004/09/policy>|  
|<span data-ttu-id="74e76-233">mssp</span><span class="sxs-lookup"><span data-stu-id="74e76-233">mssp</span></span>|<http://schemas.xmlsoap.org/ws/2005/07/securitypolicy>|
  
## <a name="1-token-profiles"></a><span data-ttu-id="74e76-234">1. 令牌配置文件</span><span class="sxs-lookup"><span data-stu-id="74e76-234">1. Token Profiles</span></span>  

 <span data-ttu-id="74e76-235">Web 服务安全规范将凭据表示为安全令牌。</span><span class="sxs-lookup"><span data-stu-id="74e76-235">Web Services Security specifications represent credential as security tokens.</span></span> <span data-ttu-id="74e76-236">WCF 支持以下令牌类型：</span><span class="sxs-lookup"><span data-stu-id="74e76-236">WCF supports the following token types:</span></span>  
  
### <a name="11-usernametoken"></a><span data-ttu-id="74e76-237">1.1 UsernameToken</span><span class="sxs-lookup"><span data-stu-id="74e76-237">1.1 UsernameToken</span></span>  

 <span data-ttu-id="74e76-238">WCF 遵循 UsernameToken10 和 UsernameToken11 配置文件，其约束如下：</span><span class="sxs-lookup"><span data-stu-id="74e76-238">WCF follows UsernameToken10 and UsernameToken11 profiles with the following constraints:</span></span>  
  
 <span data-ttu-id="74e76-239">R1101 UsernameToken\Password 元素的 PasswordType 属性必须省略或者值为 #PasswordText（默认值）。</span><span class="sxs-lookup"><span data-stu-id="74e76-239">R1101 PasswordType attribute on UsernameToken\Password element MUST be either omitted or have value #PasswordText (default).</span></span>  
  
 <span data-ttu-id="74e76-240">可以使用可扩展性实现 #PasswordDigest。</span><span class="sxs-lookup"><span data-stu-id="74e76-240">One can implement the #PasswordDigest using extensibility.</span></span> <span data-ttu-id="74e76-241">人们已经发现，#PasswordDigest 经常被误认为是足够安全的密码保护机制。</span><span class="sxs-lookup"><span data-stu-id="74e76-241">It has been observed that #PasswordDigest was often mistaken to be a secure enough password protection mechanism.</span></span> <span data-ttu-id="74e76-242">但实际上，#PasswordDigest 不可取代 UsernameToken 加密。</span><span class="sxs-lookup"><span data-stu-id="74e76-242">But #PasswordDigest cannot serve as a substitute for encryption of the UsernameToken.</span></span> <span data-ttu-id="74e76-243">#PasswordDigest 的主要目的是防止重放攻击。</span><span class="sxs-lookup"><span data-stu-id="74e76-243">The primary goal of #PasswordDigest is protection against replay attacks.</span></span> <span data-ttu-id="74e76-244">在 WCF 身份验证模式下，通过使用消息签名缓解重播攻击威胁。</span><span class="sxs-lookup"><span data-stu-id="74e76-244">In WCF authentication modes, replay attack threats are mitigated by using message signatures.</span></span>  
  
 <span data-ttu-id="74e76-245">B1102 WCF 从不发出 Nonce 并创建 UsernameToken 的子元素。</span><span class="sxs-lookup"><span data-stu-id="74e76-245">B1102 WCF never emits Nonce and Created sub-elements of the UsernameToken.</span></span>  
  
 <span data-ttu-id="74e76-246">这些子元素旨在帮助重放检测。</span><span class="sxs-lookup"><span data-stu-id="74e76-246">These sub-elements are intended to help replay detection.</span></span> <span data-ttu-id="74e76-247">WCF 使用消息签名。</span><span class="sxs-lookup"><span data-stu-id="74e76-247">WCF uses message signatures instead.</span></span>  
  
 <span data-ttu-id="74e76-248">OASIS WSS SOAP Message Security UsernameToken Profile 1.1 (UsernameToken11) 引入了从密码派生密钥的功能。</span><span class="sxs-lookup"><span data-stu-id="74e76-248">OASIS WSS SOAP Message Security UsernameToken Profile 1.1 (UsernameToken11) introduced key derivation from password feature.</span></span>  
  
 <span data-ttu-id="74e76-249">B1103 UsernameToken 密码不得用于密钥派生，因此也不得用于加密操作。</span><span class="sxs-lookup"><span data-stu-id="74e76-249">B1103 UsernameToken password MUST not be used for key derivation and therefore for cryptographic operations.</span></span>  
  
 <span data-ttu-id="74e76-250">根本原因：密码通常被视为过于脆弱，不适合用于加密操作。</span><span class="sxs-lookup"><span data-stu-id="74e76-250">Rationale: passwords are generally considered too weak to be used for cryptographic operations.</span></span>  
  
### <a name="12-x509-token"></a><span data-ttu-id="74e76-251">1.2 X509 令牌</span><span class="sxs-lookup"><span data-stu-id="74e76-251">1.2 X509 Token</span></span>  

 <span data-ttu-id="74e76-252">WCF 支持 X509v3 证书作为凭据类型，并遵循 X509tokenprofile1.1 1.0 和 X509tokenprofile1.1 1.1 的限制：</span><span class="sxs-lookup"><span data-stu-id="74e76-252">WCF supports X509v3 certificates as a credential type and follows X509TokenProfile1.0 and X509TokenProfile1.1 with the following constraints:</span></span>  
  
 <span data-ttu-id="74e76-253">R1201 在包含 X509v3 证书时，BinarySecurityToken 元素的 ValueType 属性必须值为 #X509v3。</span><span class="sxs-lookup"><span data-stu-id="74e76-253">R1201 The ValueType attribute on the BinarySecurityToken element must have value #X509v3 when it contains an X509v3 certificate.</span></span>  
  
 <span data-ttu-id="74e76-254">WSS X509 Token Profile 1.0 和 1.1 还定义了 #X509PKIPathv1 和 #PKCS7 作为值类型。</span><span class="sxs-lookup"><span data-stu-id="74e76-254">WSS X509 Token Profile 1.0 and 1.1 define also #X509PKIPathv1 and #PKCS7 as value types.</span></span> <span data-ttu-id="74e76-255">WCF 不支持这些类型。</span><span class="sxs-lookup"><span data-stu-id="74e76-255">WCF does not support these types.</span></span>  
  
 <span data-ttu-id="74e76-256">R1202 如果 SubjectKeyIdentifier (SKI) 扩展在 X509 证书中存在，wsse:KeyIdentifier 应该用于对该令牌的外部引用，并且 ValueType 属性为 #X509SubjectKeyIdentifier 且其内容为证书的 SKI 扩展的 base64 编码值。</span><span class="sxs-lookup"><span data-stu-id="74e76-256">R1202 If a SubjectKeyIdentifier (SKI) extension is present in an X509 certificate, wsse:KeyIdentifier should be used for external references to the token, with the ValueType attribute as #X509SubjectKeyIdentifier and its content the base64-encoded value of certificate's SKI extension.</span></span>  
  
 <span data-ttu-id="74e76-257">SKI 引用已广泛实现，已证明是高度可互操作的外部引用类型。</span><span class="sxs-lookup"><span data-stu-id="74e76-257">SKI references are widely implemented and proven to be a highly interoperable external reference type.</span></span>  
  
 <span data-ttu-id="74e76-258">R1203 对 X509 安全令牌的外部引用不应使用 ds:X509IssuerSerial。</span><span class="sxs-lookup"><span data-stu-id="74e76-258">R1203 An external Reference to X509 Security Token SHOULD NOT use ds:X509IssuerSerial.</span></span>  
  
 <span data-ttu-id="74e76-259">R1204 如果使用 X509TokenProfile1.1，则对 X509 安全令牌的外部引用应该使用 WS-Security 1.1 引入的指纹。</span><span class="sxs-lookup"><span data-stu-id="74e76-259">R1204 If X509TokenProfile1.1 is in use, an external reference to X509 Security Token SHOULD use the thumbprint introduced by WS-Security 1.1.</span></span>  
  
 <span data-ttu-id="74e76-260">WCF 支持 X509IssuerSerial。</span><span class="sxs-lookup"><span data-stu-id="74e76-260">WCF supports X509IssuerSerial.</span></span> <span data-ttu-id="74e76-261">但是，X509IssuerSerial 存在互操作性问题： WCF 使用字符串来比较 X509IssuerSerial 的两个值。</span><span class="sxs-lookup"><span data-stu-id="74e76-261">However There are interoperability issues with X509IssuerSerial: WCF uses a string to compare two values of X509IssuerSerial.</span></span> <span data-ttu-id="74e76-262">因此，如果一次重命名使用者名称的组件并将其发送到 WCF 服务，则可能找不到该证书。</span><span class="sxs-lookup"><span data-stu-id="74e76-262">Therefore if one reorders components of the Subject Name and sends to an WCF service a reference to a certificate, it may not be found.</span></span>  
  
### <a name="13-kerberos-token"></a><span data-ttu-id="74e76-263">1.3 Kerberos 令牌</span><span class="sxs-lookup"><span data-stu-id="74e76-263">1.3 Kerberos Token</span></span>  

 <span data-ttu-id="74e76-264">为了实现 Windows 身份验证，WCF 支持 KerberosTokenProfile 1.1，但具有以下限制：</span><span class="sxs-lookup"><span data-stu-id="74e76-264">WCF supports KerberosTokenProfile1.1 for the purpose of Windows authentication with the following constraints:</span></span>  
  
 <span data-ttu-id="74e76-265">R1301 Kerberos 令牌必须携带 GSS_API 和 Kerberos 规范中定义的 GSS 包装的 Kerberos v4 AP_REQ 的值，并且必须有值为 #GSS_Kerberosv5_AP_REQ 的 ValueType 属性。</span><span class="sxs-lookup"><span data-stu-id="74e76-265">R1301 A Kerberos Token must carry the value of a GSS wrapped Kerberos v4 AP_REQ as defined in GSS_API and the Kerberos specification, and must have the ValueType attribute with the value #GSS_Kerberosv5_AP_REQ.</span></span>  
  
 <span data-ttu-id="74e76-266">WCF 使用 GSS 包装的 Kerberos AP 要求，而不是要求空的 AP 要求。</span><span class="sxs-lookup"><span data-stu-id="74e76-266">WCF uses GSS wrapped Kerberos AP-REQ, not a bare AP-REQ.</span></span> <span data-ttu-id="74e76-267">这是一种安全最佳做法。</span><span class="sxs-lookup"><span data-stu-id="74e76-267">This is a security best practice.</span></span>  
  
### <a name="14-saml-v11-token"></a><span data-ttu-id="74e76-268">1.4 SAML v1.1 令牌</span><span class="sxs-lookup"><span data-stu-id="74e76-268">1.4 SAML v1.1 Token</span></span>  

 <span data-ttu-id="74e76-269">对于 SAML v1.1 令牌，WCF 支持 WSS SAML 令牌配置文件1.0 和1.1。</span><span class="sxs-lookup"><span data-stu-id="74e76-269">WCF supports WSS SAML Token profiles 1.0 and 1.1 for SAML v1.1 tokens.</span></span> <span data-ttu-id="74e76-270">可以实现其他版本的 SAML 令牌格式。</span><span class="sxs-lookup"><span data-stu-id="74e76-270">It is possible to implement other versions of SAML token formats.</span></span>  
  
### <a name="15-security-context-token"></a><span data-ttu-id="74e76-271">1.5 安全上下文令牌</span><span class="sxs-lookup"><span data-stu-id="74e76-271">1.5 Security Context Token</span></span>  

 <span data-ttu-id="74e76-272">WCF 支持 Ws-secureconversation 中引入 (SCT) 安全上下文令牌。</span><span class="sxs-lookup"><span data-stu-id="74e76-272">WCF supports the Security Context Token (SCT) introduced in WS-SecureConversation.</span></span> <span data-ttu-id="74e76-273">SCT 用于表示在 SecureConversation 中建立的安全上下文以及下面所述的二进制协商协议 TLS 和 SSPI。</span><span class="sxs-lookup"><span data-stu-id="74e76-273">SCT is used to represent a security context established in SecureConversation as well as the binary negotiation protocols TLS and SSPI, described below.</span></span>  
  
## <a name="2-common-message-security-parameters"></a><span data-ttu-id="74e76-274">2. 公用消息安全参数</span><span class="sxs-lookup"><span data-stu-id="74e76-274">2. Common Message Security Parameters</span></span>  
  
### <a name="21-timestamp"></a><span data-ttu-id="74e76-275">2.1 时间戳</span><span class="sxs-lookup"><span data-stu-id="74e76-275">2.1 TimeStamp</span></span>  

 <span data-ttu-id="74e76-276">时间戳存在与否是使用 <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> 类的 <xref:System.ServiceModel.Channels.SecurityBindingElement> 属性控制的。</span><span class="sxs-lookup"><span data-stu-id="74e76-276">Timestamp presence is controlled using the <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> property of the <xref:System.ServiceModel.Channels.SecurityBindingElement> class.</span></span> <span data-ttu-id="74e76-277">WCF 始终序列化 wsse： TimeStamp with wsse：已创建和 wsse： Expires 字段。</span><span class="sxs-lookup"><span data-stu-id="74e76-277">WCF always serializes wsse:TimeStamp with wsse:Created and wsse:Expires fields.</span></span> <span data-ttu-id="74e76-278">使用签名时，总会对 wsse:TimeStamp 进行签名。</span><span class="sxs-lookup"><span data-stu-id="74e76-278">The wsse:TimeStamp is always signed when signing is used.</span></span>  
  
### <a name="22-protection-order"></a><span data-ttu-id="74e76-279">2.2 保护顺序</span><span class="sxs-lookup"><span data-stu-id="74e76-279">2.2 Protection Order</span></span>  

 <span data-ttu-id="74e76-280">WCF 支持消息保护顺序 "加密前签名" 和 "签名前加密" (安全策略 1.1) 。</span><span class="sxs-lookup"><span data-stu-id="74e76-280">WCF supports the message protection order "Sign Before Encrypt" and "Encrypt Before Sign" (Security Policy 1.1).</span></span> <span data-ttu-id="74e76-281">建议使用“加密前签名”，其原因包括：除非使用 WS-Security 1.1 SignatureConfirmation 机制，否则使用“签名前加密”进行保护的消息易受签名替换攻击，并且对加密内容进行签名使得审核更加困难。</span><span class="sxs-lookup"><span data-stu-id="74e76-281">"Sign Before Encrypt" is recommended for reasons including: messages protected with Encrypt Before Sign are open to signature substitution attacks unless the WS-Security 1.1 SignatureConfirmation mechanism is used, and a signature over encrypted content makes auditing harder.</span></span>  
  
### <a name="23-signature-protection"></a><span data-ttu-id="74e76-282">2.3 签名保护</span><span class="sxs-lookup"><span data-stu-id="74e76-282">2.3 Signature Protection</span></span>  

 <span data-ttu-id="74e76-283">在使用“签名前加密”时，建议保护签名以防止对加密内容或签名密钥进行猜测的蛮力攻击（尤其是在自定义令牌与弱密钥材料一起使用时）。</span><span class="sxs-lookup"><span data-stu-id="74e76-283">When Encrypt Before Sign is used, it is recommended to protect the signature to prevent brute force attacks for guessing the encrypted content or the signing key (especially when a custom token is used with weak key material).</span></span>  
  
### <a name="24-algorithm-suite"></a><span data-ttu-id="74e76-284">2.4 算法组</span><span class="sxs-lookup"><span data-stu-id="74e76-284">2.4 Algorithm Suite</span></span>  

 <span data-ttu-id="74e76-285">WCF 支持安全策略1.1 中列出的所有算法套件。</span><span class="sxs-lookup"><span data-stu-id="74e76-285">WCF supports all algorithm suites listed in Security Policy 1.1.</span></span>  
  
### <a name="25-key-derivation"></a><span data-ttu-id="74e76-286">2.5 密钥派生</span><span class="sxs-lookup"><span data-stu-id="74e76-286">2.5 Key Derivation</span></span>  

 <span data-ttu-id="74e76-287">WCF 使用 "对称密钥的密钥派生"，如 Ws-secureconversation 中所述。</span><span class="sxs-lookup"><span data-stu-id="74e76-287">WCF uses "Key Derivation for symmetric keys" as described in WS-SecureConversation.</span></span>  
  
### <a name="26-signature-confirmation"></a><span data-ttu-id="74e76-288">2.6 签名确认</span><span class="sxs-lookup"><span data-stu-id="74e76-288">2.6 Signature Confirmation</span></span>  

 <span data-ttu-id="74e76-289">签名确认可用于防止中间人攻击以保护签名集。</span><span class="sxs-lookup"><span data-stu-id="74e76-289">Signature confirmation can be as protection from middle man attacks to protect the set of signatures.</span></span>  
  
### <a name="27-security-header-layout"></a><span data-ttu-id="74e76-290">2.7 安全标头布局</span><span class="sxs-lookup"><span data-stu-id="74e76-290">2.7 Security Header Layout</span></span>  

 <span data-ttu-id="74e76-291">每种身份验证模式都描述一种特定的安全标头布局。</span><span class="sxs-lookup"><span data-stu-id="74e76-291">Each authentication mode describes a certain layout for the security header.</span></span> <span data-ttu-id="74e76-292">安全标头内的元素为半有序。</span><span class="sxs-lookup"><span data-stu-id="74e76-292">Elements within the security header are semi-ordered.</span></span> <span data-ttu-id="74e76-293">为了定义安全标头子元素的顺序，WS-Security Policy 定义了以下安全标头布局模式：</span><span class="sxs-lookup"><span data-stu-id="74e76-293">To define the order of security header child elements, WS-Security Policy defines the following security header layout modes:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="74e76-294">严格</span><span class="sxs-lookup"><span data-stu-id="74e76-294">Strict</span></span>|<span data-ttu-id="74e76-295">根据“使用前先声明”的一般原则，各项按照 Security Policy 第 7.7.1 节中所述的编号布局规则添加到安全标头中。</span><span class="sxs-lookup"><span data-stu-id="74e76-295">Items are added to the security header following the numbered layout rules described in Security Policy section 7.7.1 according to a general principle of "declare before use".</span></span>|  
|<span data-ttu-id="74e76-296">Lax</span><span class="sxs-lookup"><span data-stu-id="74e76-296">Lax</span></span>|<span data-ttu-id="74e76-297">各项以任何符合“WSS: SOAP 消息安全”的顺序添加到安全标头中。</span><span class="sxs-lookup"><span data-stu-id="74e76-297">Items are added to the security header in any order that conforms to WSS: SOAP Message Security.</span></span>|  
|<span data-ttu-id="74e76-298">LaxTimestampFirst</span><span class="sxs-lookup"><span data-stu-id="74e76-298">LaxTimestampFirst</span></span>|<span data-ttu-id="74e76-299">与 Lax 相同，只是安全标头中的第一项必须为 wsse:Timestamp</span><span class="sxs-lookup"><span data-stu-id="74e76-299">Same as Lax except that the first item in the security header must be a wsse:Timestamp</span></span>|  
|<span data-ttu-id="74e76-300">LaxTimestampLast</span><span class="sxs-lookup"><span data-stu-id="74e76-300">LaxTimestampLast</span></span>|<span data-ttu-id="74e76-301">与 lax 相同，只是安全标头中的最后一项必须为 wsse:Timestamp</span><span class="sxs-lookup"><span data-stu-id="74e76-301">Same as lax except that the last item in the security header must be a wsse:Timestamp</span></span>|  
  
 <span data-ttu-id="74e76-302">WCF 支持安全标头布局的所有四种模式。</span><span class="sxs-lookup"><span data-stu-id="74e76-302">WCF supports all four modes for security header layout.</span></span> <span data-ttu-id="74e76-303">以下针对身份验证模式的安全标头结构和消息示例遵循“Strict”模式。</span><span class="sxs-lookup"><span data-stu-id="74e76-303">Security header structure and message examples for authentication modes below follow the "Strict" mode.</span></span>  
  
## <a name="2-common-message-security-parameters"></a><span data-ttu-id="74e76-304">2. 公用消息安全参数</span><span class="sxs-lookup"><span data-stu-id="74e76-304">2. Common Message Security Parameters</span></span>  

 <span data-ttu-id="74e76-305">本节介绍每种身份验证模式的示例策略以及演示客户端和服务所交换的消息中的安全标头结构的示例。</span><span class="sxs-lookup"><span data-stu-id="74e76-305">This section provides example policies for each authentication mode along with examples showing security header structure in messages exchanged by client and service.</span></span>  
  
### <a name="61-transport-protection"></a><span data-ttu-id="74e76-306">6.1 传输保护</span><span class="sxs-lookup"><span data-stu-id="74e76-306">6.1 Transport Protection</span></span>  

 <span data-ttu-id="74e76-307">WCF 提供五种使用安全传输来保护消息的身份验证模式。UserNameOverTransport、CertificateOverTransport、KerberosOverTransport、IssuedTokenOverTransport 和 SspiNegotiatedOverTransport。</span><span class="sxs-lookup"><span data-stu-id="74e76-307">WCF provides five authentication modes that use secure transport to protect messages; UserNameOverTransport, CertificateOverTransport, KerberosOverTransport, IssuedTokenOverTransport and SspiNegotiatedOverTransport.</span></span>  
  
 <span data-ttu-id="74e76-308">这些身份验证模式是使用 SecurityPolicy 中描述的传输绑定构造的。</span><span class="sxs-lookup"><span data-stu-id="74e76-308">These authentication modes are constructed using the transport binding described in SecurityPolicy.</span></span> <span data-ttu-id="74e76-309">对于 UserNameOverTransport 身份验证模式，UsernameToken 是签名支持令牌。</span><span class="sxs-lookup"><span data-stu-id="74e76-309">For the UserNameOverTransport authentication mode the UsernameToken is a signed supporting token.</span></span> <span data-ttu-id="74e76-310">对于其他身份验证模式，令牌作为签名认可令牌出现。</span><span class="sxs-lookup"><span data-stu-id="74e76-310">For the other authentication modes the token appears as a signed endorsing token.</span></span> <span data-ttu-id="74e76-311">SecurityPolicy 的附录 C.1.2 和 C.1.3 详细介绍了安全标头布局。</span><span class="sxs-lookup"><span data-stu-id="74e76-311">Appendix C.1.2 and C.1.3 of SecurityPolicy describe the security header layout in detail.</span></span> <span data-ttu-id="74e76-312">下面的示例安全标头演示给定身份验证模式的 Strict 布局。</span><span class="sxs-lookup"><span data-stu-id="74e76-312">The following example security headers show the Strict layout for a given authentication mode.</span></span>  
  
 <span data-ttu-id="74e76-313">任何情况下，令牌的“Derived Keys”属性的值总是为“false”。</span><span class="sxs-lookup"><span data-stu-id="74e76-313">The value of the "Derived Keys" property for the tokens in all cases is "false".</span></span>  
  
 <span data-ttu-id="74e76-314">传输绑定的各个属性的值如下：</span><span class="sxs-lookup"><span data-stu-id="74e76-314">The values of the various properties of the transport binding are as follows:</span></span>  
  
 <span data-ttu-id="74e76-315">时间戳：true</span><span class="sxs-lookup"><span data-stu-id="74e76-315">Timestamp: true</span></span>  
  
 <span data-ttu-id="74e76-316">安全标头布局：Strict</span><span class="sxs-lookup"><span data-stu-id="74e76-316">Security Header Layout: Strict</span></span>  
  
 <span data-ttu-id="74e76-317">算法组：Basic256</span><span class="sxs-lookup"><span data-stu-id="74e76-317">Algorithm Suite: Basic256</span></span>  
  
#### <a name="611-usernameovertransport"></a><span data-ttu-id="74e76-318">6.1.1 UsernameOverTransport</span><span class="sxs-lookup"><span data-stu-id="74e76-318">6.1.1 UsernameOverTransport</span></span>  

 <span data-ttu-id="74e76-319">在此身份验证模式下，客户端使用“用户名令牌”进行身份验证，该令牌作为签名支持令牌（总是从发起方发送到接收方）出现在 SOAP 层上。</span><span class="sxs-lookup"><span data-stu-id="74e76-319">With this authentication mode, the client authenticates with a Username Token which appears at the SOAP layer as a signed supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="74e76-320">在传输层，服务是用 X.509 证书进行身份验证的。</span><span class="sxs-lookup"><span data-stu-id="74e76-320">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="74e76-321">所用绑定为传输绑定。</span><span class="sxs-lookup"><span data-stu-id="74e76-321">The binding used is a transport binding.</span></span>  
  
 <span data-ttu-id="74e76-322">策略</span><span class="sxs-lookup"><span data-stu-id="74e76-322">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='UsernameOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding >  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:SignedSupportingTokens >  
        <wsp:Policy>  
          <sp:UsernameToken
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <wsp:Policy>  
              <sp:WssUsernameToken10 />
            </wsp:Policy>  
          </sp:UsernameToken>  
        </wsp:Policy>  
      </sp:SignedSupportingTokens>  
      <sp:Wss11 >  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10 >  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="74e76-323">安全标头布局</span><span class="sxs-lookup"><span data-stu-id="74e76-323">Security Header Layout</span></span>  
  
 <span data-ttu-id="74e76-324">请求</span><span class="sxs-lookup"><span data-stu-id="74e76-324">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:UsernameToken>  
  ...  
  </wsse:UsernameToken>  
</wsse:Security>  
```  
  
 <span data-ttu-id="74e76-325">响应</span><span class="sxs-lookup"><span data-stu-id="74e76-325">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="612-certificateovertransport"></a><span data-ttu-id="74e76-326">6.1.2 CertificateOverTransport</span><span class="sxs-lookup"><span data-stu-id="74e76-326">6.1.2 CertificateOverTransport</span></span>  

 <span data-ttu-id="74e76-327">在此身份验证模式下，客户端使用 X.509 证书进行身份验证，该证书作为认可支持令牌（总是从发起方发送到接收方）出现在 SOAP 层上。</span><span class="sxs-lookup"><span data-stu-id="74e76-327">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as an endorsing supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="74e76-328">在传输层，服务是用 X.509 证书进行身份验证的。</span><span class="sxs-lookup"><span data-stu-id="74e76-328">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="74e76-329">所用绑定为传输绑定。</span><span class="sxs-lookup"><span data-stu-id="74e76-329">The binding used is a transport binding.</span></span>  
  
 <span data-ttu-id="74e76-330">策略</span><span class="sxs-lookup"><span data-stu-id="74e76-330">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='CertificateOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding xmlns:sp='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy' >  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
             <sp:HttpsToken RequireClientCertificate='false' />
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:X509Token
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <wsp:Policy>  
              <sp:RequireThumbprintReference />
              <sp:WssX509V3Token10 />
            </wsp:Policy>  
          </sp:X509Token>  
          <sp:SignedParts>  
            <sp:Header Name='To'
Namespace='http://www.w3.org/2005/08/addressing' />
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="74e76-331">安全标头布局</span><span class="sxs-lookup"><span data-stu-id="74e76-331">Security Header Layout</span></span>  
  
 <span data-ttu-id="74e76-332">请求</span><span class="sxs-lookup"><span data-stu-id="74e76-332">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wse:Timestamp u:Id="_0">  
  ...  
  </wse:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="74e76-333">响应</span><span class="sxs-lookup"><span data-stu-id="74e76-333">Response</span></span>  
  
```xml  
<o:Security>  
  <u:Timestamp u:Id="_0">  
  ...  
  </u:Timestamp>  
</o:Security>  
```  
  
#### <a name="613-issuedtokenovertransport"></a><span data-ttu-id="74e76-334">6.1.3 IssuedTokenOverTransport</span><span class="sxs-lookup"><span data-stu-id="74e76-334">6.1.3 IssuedTokenOverTransport</span></span>  

 <span data-ttu-id="74e76-335">在此身份验证模式下，客户端不向服务进行身份验证，而是出示一个由安全令牌服务 (STS) 颁发的令牌，并证明掌握了共享密钥。</span><span class="sxs-lookup"><span data-stu-id="74e76-335">With this authentication mode the client does not authenticate to the service, as such, but rather presents a token issued by a Security Token Service (STS) and proves knowledge of a shared key.</span></span> <span data-ttu-id="74e76-336">颁发的令牌作为认可支持令牌（总是从发起方发送到接收方）出现在 SOAP 层上。</span><span class="sxs-lookup"><span data-stu-id="74e76-336">The issued token appears at the SOAP layer as an endorsing supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="74e76-337">在传输层，服务是用 X.509 证书进行身份验证的。</span><span class="sxs-lookup"><span data-stu-id="74e76-337">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="74e76-338">绑定为传输绑定。</span><span class="sxs-lookup"><span data-stu-id="74e76-338">The binding is a transport binding.</span></span>  
  
 <span data-ttu-id="74e76-339">策略</span><span class="sxs-lookup"><span data-stu-id="74e76-339">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='IssuedTokenOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding >  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:IssuedToken
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <sp:RequestSecurityTokenTemplate>  
              <wst:KeyType>  
              http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
              </wst:KeyType>
            </sp:RequestSecurityTokenTemplate>  
            <wsp:Policy>  
              <sp:RequireInternalReference />
            </wsp:Policy>  
          </sp:IssuedToken>  
          <sp:SignedParts>  
            <sp:Header Name='To'
Namespace='http://www.w3.org/2005/08/addressing' />
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="74e76-340">安全标头布局</span><span class="sxs-lookup"><span data-stu-id="74e76-340">Security Header Layout</span></span>  
  
 <span data-ttu-id="74e76-341">请求</span><span class="sxs-lookup"><span data-stu-id="74e76-341">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1" >  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="74e76-342">响应</span><span class="sxs-lookup"><span data-stu-id="74e76-342">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="614-kerberosovertransport"></a><span data-ttu-id="74e76-343">6.1.4 KerberosOverTransport</span><span class="sxs-lookup"><span data-stu-id="74e76-343">6.1.4 KerberosOverTransport</span></span>  

 <span data-ttu-id="74e76-344">在此身份验证模式下，客户端使用 Kerberos 票证向服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="74e76-344">With this authentication mode the client authenticates to the service using a Kerberos ticket.</span></span> <span data-ttu-id="74e76-345">Kerberos 令牌作为认可支持令牌出现在 SOAP 层上。</span><span class="sxs-lookup"><span data-stu-id="74e76-345">The Kerberos token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="74e76-346">在传输层，服务是用 X.509 证书进行身份验证的。</span><span class="sxs-lookup"><span data-stu-id="74e76-346">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="74e76-347">绑定为传输绑定。</span><span class="sxs-lookup"><span data-stu-id="74e76-347">The binding is a transport binding.</span></span>  
  
 <span data-ttu-id="74e76-348">策略</span><span class="sxs-lookup"><span data-stu-id="74e76-348">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='KerberosOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding>  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic128 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:KerberosToken  
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Once' >  
            <wsp:Policy>  
              <sp:WssGssKerberosV5ApReqToken11 />
            </wsp:Policy>  
          </sp:KerberosToken>  
          <sp:SignedParts>  
            <sp:Header Name='To'
Namespace='http://www.w3.org/2005/08/addressing' />
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="74e76-349">安全标头布局</span><span class="sxs-lookup"><span data-stu-id="74e76-349">Security Header Layout</span></span>  
  
 <span data-ttu-id="74e76-350">请求</span><span class="sxs-lookup"><span data-stu-id="74e76-350">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1" >  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken ValueType="...#GSS_Kerberosv5_AP_REQ">  
  ...  
  </wsse:BinarySecurityToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="74e76-351">响应</span><span class="sxs-lookup"><span data-stu-id="74e76-351">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="615-sspinegotiatedovertransport"></a><span data-ttu-id="74e76-352">6.1.5 SspiNegotiatedOverTransport</span><span class="sxs-lookup"><span data-stu-id="74e76-352">6.1.5 SspiNegotiatedOverTransport</span></span>  

 <span data-ttu-id="74e76-353">在此模式下，将使用协商协议来执行客户端和服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="74e76-353">With this mode a negotiation protocol is used to perform client and server authentication.</span></span> <span data-ttu-id="74e76-354">如果可能，就使用 Kerberos，否则使用 NTLM。</span><span class="sxs-lookup"><span data-stu-id="74e76-354">Kerberos is used if possible, otherwise NTLM.</span></span> <span data-ttu-id="74e76-355">产生的 SCT 作为认可支持令牌（总是从发起方发送到接收方）出现在 SOAP 层上。</span><span class="sxs-lookup"><span data-stu-id="74e76-355">The resulting SCT appears at the SOAP layer as an endorsing supporting token that is always sent from initiator to recipient.</span></span> <span data-ttu-id="74e76-356">在传输层，服务还是由 X.509 证书另外进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="74e76-356">The service is additionally authenticated at the transport layer by an X.509 certificate.</span></span> <span data-ttu-id="74e76-357">所用绑定为传输绑定。</span><span class="sxs-lookup"><span data-stu-id="74e76-357">The binding used is a transport binding.</span></span> <span data-ttu-id="74e76-358">"SPNEGO" (协商) 介绍 WCF 如何将 SSPI 二进制协商协议用于 WS-TRUST。</span><span class="sxs-lookup"><span data-stu-id="74e76-358">"SPNEGO" (negotiation) describes how WCF uses SSPI binary negotiation protocol with WS-Trust.</span></span> <span data-ttu-id="74e76-359">在通过 SPNEGO 握手建立 SCT 之后，本节将介绍安全标头示例。</span><span class="sxs-lookup"><span data-stu-id="74e76-359">Security header examples in this section are after the SCT has been established through the SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="74e76-360">策略</span><span class="sxs-lookup"><span data-stu-id="74e76-360">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SspiNegotiatedOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding>  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:SpnegoContextToken
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <wsp:Policy />
          </sp:SpnegoContextToken>  
          <sp:SignedParts>  
            <sp:Header Name='To'
Namespace='http://www.w3.org/2005/08/addressing' />
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples"></a><span data-ttu-id="74e76-361">安全标头示例</span><span class="sxs-lookup"><span data-stu-id="74e76-361">Security Header Examples</span></span>  

 <span data-ttu-id="74e76-362">在使用 WS-Trust 二进制协商通过 SPNEGO 握手建立安全上下文令牌之后，应用程序消息将具有如下结构的安全标头。</span><span class="sxs-lookup"><span data-stu-id="74e76-362">Once the Security Context Token is established through SPNEGO handshake using WS-Trust Binary Negotiation, the application messages have security headers with the following structure.</span></span>  
  
 <span data-ttu-id="74e76-363">请求</span><span class="sxs-lookup"><span data-stu-id="74e76-363">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:SecurityContextToken u:Id="uuid-2202746a-7725-453d-8747-809cb718dab0-29" >  
  ...  
  </wssc:SecurityContextToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="74e76-364">响应</span><span class="sxs-lookup"><span data-stu-id="74e76-364">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
### <a name="62-using-x509-certificates-for-service-authentication"></a><span data-ttu-id="74e76-365">6.2 将 X.509 证书用于服务身份验证</span><span class="sxs-lookup"><span data-stu-id="74e76-365">6.2 Using X.509 Certificates for Service Authentication</span></span>  

 <span data-ttu-id="74e76-366">本节介绍以下身份验证模式：MutualCertificate WSS1.0、Mutual CertificateDuplex、MutualCertificate WSS1.1、AnonymousForCertificate、UserNameForCertificate 和 IssuedTokenForCertificate。</span><span class="sxs-lookup"><span data-stu-id="74e76-366">This section describes the following authentication modes: MutualCertificate WSS1.0, Mutual CertificateDuplex, MutualCertificate WSS1.1, AnonymousForCertificate, UserNameForCertificate and IssuedTokenForCertificate.</span></span>  
  
#### <a name="621-mutualcertificate-wss10"></a><span data-ttu-id="74e76-367">6.2.1 MutualCertificate WSS1.0</span><span class="sxs-lookup"><span data-stu-id="74e76-367">6.2.1 MutualCertificate WSS1.0</span></span>  

 <span data-ttu-id="74e76-368">在此身份验证模式下，客户端使用 X.509 证书进行身份验证，该证书作为发起方令牌出现在 SOAP 层上。</span><span class="sxs-lookup"><span data-stu-id="74e76-368">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as the initiator token.</span></span> <span data-ttu-id="74e76-369">同样使用 X.509 证书对服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="74e76-369">The service is also authenticated using an X.509 certificate.</span></span>  
  
 <span data-ttu-id="74e76-370">所用绑定为带有以下属性值的非对称绑定：</span><span class="sxs-lookup"><span data-stu-id="74e76-370">The binding used is an asymmetric binding with the following property values:</span></span>  
  
 <span data-ttu-id="74e76-371">发起方令牌：客户端的 X.509 证书，包含模式设置为 …/IncludeToken/AlwaysToRecipient</span><span class="sxs-lookup"><span data-stu-id="74e76-371">Initiator Token: the client’s X.509 certificate, with inclusion mode set to …/IncludeToken/AlwaysToRecipient</span></span>  
  
 <span data-ttu-id="74e76-372">接收方令牌：服务器的 X.509 证书，包含模式设置为 …/IncludeToken/Never</span><span class="sxs-lookup"><span data-stu-id="74e76-372">Recipient Token: Server’s X.509 Certificate, with inclusion mode is set …/IncludeToken/Never</span></span>  
  
 <span data-ttu-id="74e76-373">令牌保护：False</span><span class="sxs-lookup"><span data-stu-id="74e76-373">Token Protection: False</span></span>  
  
 <span data-ttu-id="74e76-374">整个标头和正文签名：True</span><span class="sxs-lookup"><span data-stu-id="74e76-374">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="74e76-375">保护顺序：SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="74e76-375">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="74e76-376">加密签名：True</span><span class="sxs-lookup"><span data-stu-id="74e76-376">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="74e76-377">策略</span><span class="sxs-lookup"><span data-stu-id="74e76-377">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='MutualCertificate_WSS10_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:AsymmetricBinding>  
        <wsp:Policy>  
          <sp:InitiatorToken>  
            <wsp:Policy>  
              <sp:X509Token
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:InitiatorToken>  
          <sp:RecipientToken>  
            <wsp:Policy>  
              <sp:X509Token
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Never' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:RecipientToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:AsymmetricBinding>  
      <sp:Wss10>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
        </wsp:Policy>  
      </sp:Wss10>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="74e76-378">安全标头示例：SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="74e76-378">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="74e76-379">请求</span><span class="sxs-lookup"><span data-stu-id="74e76-379">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
    <xenc:ReferenceList>  
    ...  
    </xenc:ReferenceList>  
  </xenc:EncryptedKey>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="74e76-380">响应</span><span class="sxs-lookup"><span data-stu-id="74e76-380">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
    <xenc:ReferenceList>  
    ...  
    </xenc:ReferenceList>  
  </xenc:EncryptedKey>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="74e76-381">安全标头示例：EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="74e76-381">Security Header Examples: EncryptBeforeSign</span></span>  
  
 <span data-ttu-id="74e76-382">请求</span><span class="sxs-lookup"><span data-stu-id="74e76-382">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="74e76-383">响应</span><span class="sxs-lookup"><span data-stu-id="74e76-383">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="622-mutualcertificateduplex"></a><span data-ttu-id="74e76-384">6.2.2 MutualCertificateDuplex</span><span class="sxs-lookup"><span data-stu-id="74e76-384">6.2.2 MutualCertificateDuplex</span></span>  

 <span data-ttu-id="74e76-385">在此身份验证模式下，客户端使用 X.509 证书进行身份验证，该证书作为发起方令牌出现在 SOAP 层上。</span><span class="sxs-lookup"><span data-stu-id="74e76-385">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as the initiator token.</span></span> <span data-ttu-id="74e76-386">同样使用 X.509 证书对服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="74e76-386">The service is also authenticated using an X.509 certificate.</span></span>  
  
 <span data-ttu-id="74e76-387">所用绑定为带有以下属性值的非对称绑定：</span><span class="sxs-lookup"><span data-stu-id="74e76-387">The binding used is an asymmetric binding with the following property values:</span></span>  
  
 <span data-ttu-id="74e76-388">发起方令牌：客户端的 X509 证书，包含模式设置为 …/IncludeToken/AlwaysToRecipient</span><span class="sxs-lookup"><span data-stu-id="74e76-388">Initiator Token: Client’s X509 Certificate, inclusion mode is set to …/IncludeToken/AlwaysToRecipient</span></span>  
  
 <span data-ttu-id="74e76-389">接收方令牌：服务器的 X509 证书，包含模式设置为 …/IncludeToken/AlwaysToInitiator</span><span class="sxs-lookup"><span data-stu-id="74e76-389">Recipient Token: Server’s X509 Certificate, inclusion mode is set to …/IncludeToken/AlwaysToInitiator</span></span>  
  
 <span data-ttu-id="74e76-390">令牌保护：False</span><span class="sxs-lookup"><span data-stu-id="74e76-390">Token Protection: False</span></span>  
  
 <span data-ttu-id="74e76-391">整个标头和正文签名：True</span><span class="sxs-lookup"><span data-stu-id="74e76-391">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="74e76-392">保护顺序：SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="74e76-392">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="74e76-393">加密签名：True</span><span class="sxs-lookup"><span data-stu-id="74e76-393">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="74e76-394">策略</span><span class="sxs-lookup"><span data-stu-id="74e76-394">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='MutualCertificateDuplex_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:AsymmetricBinding>  
        <wsp:Policy>  
          <sp:InitiatorToken>  
            <wsp:Policy>  
              <sp:X509Token
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:InitiatorToken>  
          <sp:RecipientToken>  
            <wsp:Policy>  
              <sp:X509Token
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToInitiator' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:RecipientToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:AsymmetricBinding>  
      <sp:Wss10>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
        </wsp:Policy>  
      </sp:Wss10>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="74e76-395">安全标头示例：SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="74e76-395">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="74e76-396">请求和响应</span><span class="sxs-lookup"><span data-stu-id="74e76-396">Request and Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
    <xenc:ReferenceList>  
    ...  
    </xenc:ReferenceList>  
  </xenc:EncryptedKey>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="74e76-397">安全标头示例：EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="74e76-397">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="74e76-398">请求和响应</span><span class="sxs-lookup"><span data-stu-id="74e76-398">Request and Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="623-using-symmetricbinding-with-x509-service-authentication"></a><span data-ttu-id="74e76-399">6.2.3 将 SymmetricBinding 用于 X.509 服务身份验证</span><span class="sxs-lookup"><span data-stu-id="74e76-399">6.2.3 Using SymmetricBinding with X.509 Service Authentication</span></span>  

 <span data-ttu-id="74e76-400">“WSS10”对 X509 令牌方案提供有限支持。</span><span class="sxs-lookup"><span data-stu-id="74e76-400">"WSS10" provided limited support for scenarios with X509 tokens.</span></span> <span data-ttu-id="74e76-401">例如，如果消息仅使用服务 X509 令牌，则无法为其提供签名和加密保护。</span><span class="sxs-lookup"><span data-stu-id="74e76-401">For example, there was no way to provide signature and encryption protection for messages using only service X509 token.</span></span> <span data-ttu-id="74e76-402">“WSS11”将 EncryptedKey 用作对称令牌。</span><span class="sxs-lookup"><span data-stu-id="74e76-402">"WSS11" introduced the usage of EncryptedKey as a symmetric token.</span></span> <span data-ttu-id="74e76-403">现在，为服务的 X.509 证书加密的临时密钥可同时用于请求和响应消息保护。</span><span class="sxs-lookup"><span data-stu-id="74e76-403">Now a temporary key encrypted for the service's X.509 certificate could be used for both request and response messages protection.</span></span> <span data-ttu-id="74e76-404">下面第 6.4 节中介绍的身份验证模式使用此模式。</span><span class="sxs-lookup"><span data-stu-id="74e76-404">The authentication modes described in the section 6.4 below use this pattern.</span></span>  
  
 <span data-ttu-id="74e76-405">WS-SecurityPolicy 描述了此模式，即将 SymmetricBinding 用于服务 X509 令牌作为保护令牌。</span><span class="sxs-lookup"><span data-stu-id="74e76-405">WS-SecurityPolicy describes this pattern using SymmetricBinding with Service X509 token as the protection token.</span></span>  
  
 <span data-ttu-id="74e76-406">身份验证模式 AnonymousForCertificate、UsernameForCertificate、MutualCertificate WSS11 和 IssuedTokenForCertificate 都使用具有以下属性值的类似的 sp:SymmetricBinding 实例：</span><span class="sxs-lookup"><span data-stu-id="74e76-406">Authentication modes AnonymousForCertificate, UsernameForCertificate, MutualCertificate WSS11 and IssuedTokenForCertificate all use a similar instance of sp:SymmetricBinding with the following property values:</span></span>  
  
 <span data-ttu-id="74e76-407">保护令牌：服务器的 X509 证书，包含模式设置为 …/IncludeToken/Never</span><span class="sxs-lookup"><span data-stu-id="74e76-407">Protection Token: Server’s X509 Certificate, inclusion mode is set to .../IncludeToken/Never</span></span>  
<span data-ttu-id="74e76-408">令牌保护：False</span><span class="sxs-lookup"><span data-stu-id="74e76-408">Token Protection: False</span></span>  
  
 <span data-ttu-id="74e76-409">整个标头和正文签名：True</span><span class="sxs-lookup"><span data-stu-id="74e76-409">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="74e76-410">保护顺序：SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="74e76-410">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="74e76-411">加密签名：True</span><span class="sxs-lookup"><span data-stu-id="74e76-411">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="74e76-412">上述身份验证模式的区别仅在于它们所使用的支持令牌。</span><span class="sxs-lookup"><span data-stu-id="74e76-412">The above authentication modes only differ by the supporting tokens they use.</span></span> <span data-ttu-id="74e76-413">AnonymousForCertificate 没有任何支持令牌，MutualCertificate WSS 1.1 将客户端的 X509 证书作为认可支持令牌，UserNameForCertificate 将“用户名令牌”作为签名支持令牌，而 IssuedTokenForCertificate 将颁发的令牌作为认可支持令牌。</span><span class="sxs-lookup"><span data-stu-id="74e76-413">AnonymousForCertificate does not have any supporting tokens, MutualCertificate WSS 1.1 has the client’s X509 certificate as an endorsing supporting tokens, UserNameForCertificate has a UserName Token as a signed supporting token and IssuedTokenForCertificate has the issued token as an endorsing supporting token.</span></span>  
  
 <span data-ttu-id="74e76-414">策略</span><span class="sxs-lookup"><span data-stu-id="74e76-414">Policy</span></span>  
  
 <span data-ttu-id="74e76-415">对称绑定</span><span class="sxs-lookup"><span data-stu-id="74e76-415">Symmetric Binding</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SymmetricCert_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:X509Token
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Never' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />
                  <sp:RequireThumbprintReference />
                  <sp:WssX509V3Token10 />
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />  
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <!-- Supporting Token Assertions appear here -->  
      ...  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
          <sp:RequireSignatureConfirmation />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
#### <a name="624-anonymousforcertificate"></a><span data-ttu-id="74e76-416">6.2.4 AnonymousForCertificate</span><span class="sxs-lookup"><span data-stu-id="74e76-416">6.2.4 AnonymousForCertificate</span></span>  

 <span data-ttu-id="74e76-417">在此身份验证模式下，客户端是匿名的，而使用 X.509 证书对服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="74e76-417">With this authentication mode the client is anonymous and the service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="74e76-418">所用绑定为 6.4.2 中所述的对称绑定的实例。</span><span class="sxs-lookup"><span data-stu-id="74e76-418">The binding used is an instance of symmetric binding as described in 6.4.2.</span></span>  
  
 <span data-ttu-id="74e76-419">策略</span><span class="sxs-lookup"><span data-stu-id="74e76-419">Policy</span></span>  
  
 <span data-ttu-id="74e76-420">请参见上面 6.2.3 中的“策略”以了解绑定详细信息</span><span class="sxs-lookup"><span data-stu-id="74e76-420">See "Policy" in 6.2.3 above for binding details</span></span>  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="74e76-421">安全标头示例：SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="74e76-421">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="74e76-422">请求</span><span class="sxs-lookup"><span data-stu-id="74e76-422">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="74e76-423">响应</span><span class="sxs-lookup"><span data-stu-id="74e76-423">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="74e76-424">安全标头示例：EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="74e76-424">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="74e76-425">请求</span><span class="sxs-lookup"><span data-stu-id="74e76-425">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="74e76-426">响应</span><span class="sxs-lookup"><span data-stu-id="74e76-426">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="625-usernameforcertificate"></a><span data-ttu-id="74e76-427">6.2.5 UserNameForCertificate</span><span class="sxs-lookup"><span data-stu-id="74e76-427">6.2.5 UserNameForCertificate</span></span>  

 <span data-ttu-id="74e76-428">在此身份验证模式下，客户端使用“用户名令牌”向服务进行身份验证，该令牌作为签名支持令牌出现在 SOAP 层上。</span><span class="sxs-lookup"><span data-stu-id="74e76-428">With this authentication mode the client authenticates to the service using a Username Token which appears at the SOAP layer as a signed supporting token.</span></span> <span data-ttu-id="74e76-429">服务使用 X.509 证书对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="74e76-429">The service authenticates to the client using an X.509 certificate.</span></span> <span data-ttu-id="74e76-430">所用绑定为对称绑定，其保护令牌是由客户端生成的密钥，用服务的公钥进行加密。</span><span class="sxs-lookup"><span data-stu-id="74e76-430">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="74e76-431">策略</span><span class="sxs-lookup"><span data-stu-id="74e76-431">Policy</span></span>  
  
 <span data-ttu-id="74e76-432">请参见上面 6.2.3 中的“策略”以了解绑定详细信息</span><span class="sxs-lookup"><span data-stu-id="74e76-432">See "Policy" in 6.2.3 above for binding details</span></span>  
  
 <span data-ttu-id="74e76-433">签名支持令牌</span><span class="sxs-lookup"><span data-stu-id="74e76-433">Signed Supporting Token</span></span>  
  
```xml  
<sp:SignedSupportingTokens>  
  <wsp:Policy>  
    <sp:UsernameToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:WssUsernameToken10 />
      </wsp:Policy>  
    </sp:UsernameToken>  
  </wsp:Policy>  
</sp:SignedSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="74e76-434">安全标头示例：SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="74e76-434">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="74e76-435">请求</span><span class="sxs-lookup"><span data-stu-id="74e76-435">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="74e76-436">响应</span><span class="sxs-lookup"><span data-stu-id="74e76-436">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="74e76-437">安全标头示例：EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="74e76-437">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="74e76-438">请求</span><span class="sxs-lookup"><span data-stu-id="74e76-438">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="74e76-439">响应</span><span class="sxs-lookup"><span data-stu-id="74e76-439">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="626-mutualcertificate-wss-11"></a><span data-ttu-id="74e76-440">6.2.6 MutualCertificate (WSS 1.1)</span><span class="sxs-lookup"><span data-stu-id="74e76-440">6.2.6 MutualCertificate (WSS 1.1)</span></span>  

 <span data-ttu-id="74e76-441">在此身份验证模式下，客户端使用 X.509 证书进行身份验证，该证书作为认可支持令牌出现在 SOAP 层上。</span><span class="sxs-lookup"><span data-stu-id="74e76-441">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="74e76-442">同样使用 X.509 证书对服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="74e76-442">The service is also authenticated using an X.509 certificate.</span></span> <span data-ttu-id="74e76-443">所用绑定为对称绑定，其保护令牌是由客户端生成的密钥，用服务的公钥进行加密。</span><span class="sxs-lookup"><span data-stu-id="74e76-443">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="74e76-444">策略</span><span class="sxs-lookup"><span data-stu-id="74e76-444">Policy</span></span>  
  
 <span data-ttu-id="74e76-445">请参见 6.2.3 中的“策略”以了解绑定详细信息</span><span class="sxs-lookup"><span data-stu-id="74e76-445">See Policy in 6.2.3 for binding details</span></span>  
  
 <span data-ttu-id="74e76-446">认可支持令牌</span><span class="sxs-lookup"><span data-stu-id="74e76-446">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:X509Token sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:RequireThumbprintReference />
        <sp:WssX509V3Token10 />
      </wsp:Policy>  
    </sp:X509Token>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="74e76-447">安全标头示例：SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="74e76-447">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="74e76-448">请求</span><span class="sxs-lookup"><span data-stu-id="74e76-448">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="74e76-449">响应</span><span class="sxs-lookup"><span data-stu-id="74e76-449">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="74e76-450">安全标头示例：EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="74e76-450">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="74e76-451">请求</span><span class="sxs-lookup"><span data-stu-id="74e76-451">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="74e76-452">响应</span><span class="sxs-lookup"><span data-stu-id="74e76-452">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="627-issuedtokenforcertificate"></a><span data-ttu-id="74e76-453">6.2.7 IssuedTokenForCertificate</span><span class="sxs-lookup"><span data-stu-id="74e76-453">6.2.7 IssuedTokenForCertificate</span></span>  

 <span data-ttu-id="74e76-454">在此身份验证模式下，客户端不向服务进行身份验证，而是出示一个由 STS 颁发的令牌，并证明掌握了共享密钥。</span><span class="sxs-lookup"><span data-stu-id="74e76-454">With this authentication mode the client does not authenticate to the service, as such, but instead presents a token issued by a STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="74e76-455">颁发的令牌作为认可支持令牌出现在 SOAP 层上。</span><span class="sxs-lookup"><span data-stu-id="74e76-455">The issued token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="74e76-456">服务使用 X.509 证书对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="74e76-456">The service authenticates to the client using an X.509 certificate.</span></span> <span data-ttu-id="74e76-457">所用绑定为对称绑定，其保护令牌是由客户端生成的密钥，用服务的公钥进行加密。</span><span class="sxs-lookup"><span data-stu-id="74e76-457">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="74e76-458">策略</span><span class="sxs-lookup"><span data-stu-id="74e76-458">Policy</span></span>  
  
 <span data-ttu-id="74e76-459">请参见上面的 6.2.3 以了解绑定详细信息。</span><span class="sxs-lookup"><span data-stu-id="74e76-459">See Policy in 6.2.3 above for binding details</span></span>  
  
 <span data-ttu-id="74e76-460">认可支持令牌</span><span class="sxs-lookup"><span data-stu-id="74e76-460">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:IssuedToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <sp:RequestSecurityTokenTemplate>  
        <wst:KeyType>  
http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
       </wst:KeyType>  
     </sp:RequestSecurityTokenTemplate>  
     <wsp:Policy>  
       <sp:RequireDerivedKeys />
       <sp:RequireInternalReference />
     </wsp:Policy>  
   </sp:IssuedToken>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="74e76-461">安全标头示例：SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="74e76-461">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="74e76-462">请求</span><span class="sxs-lookup"><span data-stu-id="74e76-462">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="74e76-463">响应</span><span class="sxs-lookup"><span data-stu-id="74e76-463">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="74e76-464">安全标头示例：EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="74e76-464">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="74e76-465">请求</span><span class="sxs-lookup"><span data-stu-id="74e76-465">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="74e76-466">响应</span><span class="sxs-lookup"><span data-stu-id="74e76-466">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
## <a name="63-kerberos"></a><span data-ttu-id="74e76-467">6.3 Kerberos</span><span class="sxs-lookup"><span data-stu-id="74e76-467">6.3 Kerberos</span></span>  

 <span data-ttu-id="74e76-468">在此身份验证模式下，客户端使用 Kerberos 票证向服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="74e76-468">With this authentication mode the client authenticates to the service using a Kerberos ticket.</span></span> <span data-ttu-id="74e76-469">该票证还提供服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="74e76-469">That same ticket also provides server authentication.</span></span> <span data-ttu-id="74e76-470">所用绑定为对称绑定，具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="74e76-470">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="74e76-471">保护令牌：Kerberos 票证，包含模式设置为 .../IncludeToken/Once</span><span class="sxs-lookup"><span data-stu-id="74e76-471">Protection Token: Kerberos Ticket, inclusion mode is set to .../IncludeToken/Once</span></span>  
<span data-ttu-id="74e76-472">令牌保护：False</span><span class="sxs-lookup"><span data-stu-id="74e76-472">Token Protection: False</span></span>  
  
 <span data-ttu-id="74e76-473">整个标头和正文签名：True</span><span class="sxs-lookup"><span data-stu-id="74e76-473">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="74e76-474">保护顺序：SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="74e76-474">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="74e76-475">加密签名：True</span><span class="sxs-lookup"><span data-stu-id="74e76-475">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="74e76-476">策略</span><span class="sxs-lookup"><span data-stu-id="74e76-476">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='Kerberos_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:KerberosToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Once' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />
                  <sp:WssGssKerberosV5ApReqToken11 />
                </wsp:Policy>  
              </sp:KerberosToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic128 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="74e76-477">安全标头示例：SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="74e76-477">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="74e76-478">请求</span><span class="sxs-lookup"><span data-stu-id="74e76-478">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="74e76-479">响应</span><span class="sxs-lookup"><span data-stu-id="74e76-479">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="74e76-480">安全标头示例：EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="74e76-480">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="74e76-481">请求</span><span class="sxs-lookup"><span data-stu-id="74e76-481">Request</span></span>  
  
```xml  
<wsse:Security>  
TBD  
</wsse:Security>  
```  
  
 <span data-ttu-id="74e76-482">响应</span><span class="sxs-lookup"><span data-stu-id="74e76-482">Response</span></span>  
  
```xml  
<wsse:Security>  
TBD  
</wsse:Security>  
```  
  
#### <a name="64-issuedtoken"></a><span data-ttu-id="74e76-483">6.4 IssuedToken</span><span class="sxs-lookup"><span data-stu-id="74e76-483">6.4 IssuedToken</span></span>  

 <span data-ttu-id="74e76-484">在此身份验证模式下，客户端不向服务进行身份验证，而是提供一个由 STS 颁发的令牌，并证明掌握了共享密钥。</span><span class="sxs-lookup"><span data-stu-id="74e76-484">With this authentication mode the client does not authenticate to the service, as such, rather the client presents a token issued by an STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="74e76-485">服务也不向客户端进行身份验证，而是由 STS 将共享密钥作为颁发的令牌的一部分进行加密，这样，只有服务才能解密该密钥。</span><span class="sxs-lookup"><span data-stu-id="74e76-485">The service is not authenticated to the client, as such, instead the STS encrypts the shared key as part of the issued token such that only the service can decrypt the key.</span></span> <span data-ttu-id="74e76-486">所用绑定为对称绑定，具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="74e76-486">The binding used is as symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="74e76-487">保护令牌：颁发的令牌，包含模式设置为 .../IncludeToken/AlwaysToRecipient</span><span class="sxs-lookup"><span data-stu-id="74e76-487">Protection Token: Issued Token, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
<span data-ttu-id="74e76-488">令牌保护：False</span><span class="sxs-lookup"><span data-stu-id="74e76-488">Token Protection: False</span></span>  
  
 <span data-ttu-id="74e76-489">整个标头和正文签名：True</span><span class="sxs-lookup"><span data-stu-id="74e76-489">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="74e76-490">保护顺序：SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="74e76-490">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="74e76-491">加密签名：True</span><span class="sxs-lookup"><span data-stu-id="74e76-491">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="74e76-492">策略</span><span class="sxs-lookup"><span data-stu-id="74e76-492">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='CustomBinding_ISimple3_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:IssuedToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <sp:RequestSecurityTokenTemplate>  
                  <wst:KeyType>  
http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
                  </wst:KeyType>
                </sp:RequestSecurityTokenTemplate>  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />
                  <sp:RequireInternalReference />
                </wsp:Policy>  
              </sp:IssuedToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="74e76-493">安全标头示例：SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="74e76-493">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="74e76-494">请求</span><span class="sxs-lookup"><span data-stu-id="74e76-494">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="74e76-495">响应</span><span class="sxs-lookup"><span data-stu-id="74e76-495">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="74e76-496">安全标头示例：EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="74e76-496">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="74e76-497">请求</span><span class="sxs-lookup"><span data-stu-id="74e76-497">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="74e76-498">响应</span><span class="sxs-lookup"><span data-stu-id="74e76-498">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
### <a name="65-using-sslnegotiated-for-service-authentication"></a><span data-ttu-id="74e76-499">6.5 将 SslNegotiated 用于服务身份验证</span><span class="sxs-lookup"><span data-stu-id="74e76-499">6.5 Using SslNegotiated for Service Authentication</span></span>  

 <span data-ttu-id="74e76-500">本节介绍的一组身份验证模式将对称绑定用于保护令牌，作为安全上下文令牌（符合 WS-SecureConversation (WS-SC)），其键值是通过对 WS-Trust (WS-T) RST/RSTR 消息执行 TLS 协议进行协商的。</span><span class="sxs-lookup"><span data-stu-id="74e76-500">This section describes a group of authentication modes that use a symmetric binding with the protection token being a Security Context Token per WS-SecureConversation (WS-SC) whose key value is negotiated by executing the TLS protocol over WS-Trust (WS-T) RST/RSTR messages.</span></span> <span data-ttu-id="74e76-501">有关使用 WS-Trust 实现 TLS 握手的详细信息，请参见 TLSNEGO 中的内容。</span><span class="sxs-lookup"><span data-stu-id="74e76-501">Details of the TLS handshake implementation using WS-Trust are described in TLSNEGO.</span></span> <span data-ttu-id="74e76-502">此处的消息示例中，我们假设已通过握手建立了带有关联安全上下文的 SCT。</span><span class="sxs-lookup"><span data-stu-id="74e76-502">Here in the message examples we will assume that SCT with an associated security context is already established through a handshake.</span></span>  
  
 <span data-ttu-id="74e76-503">所用绑定为对称绑定，具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="74e76-503">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="74e76-504">保护令牌：SslContextToken，包含模式设置为 .../IncludeToken/Never</span><span class="sxs-lookup"><span data-stu-id="74e76-504">Protection Token: SslContextToken, inclusion mode is set to .../IncludeToken/Never</span></span>  
<span data-ttu-id="74e76-505">令牌保护：False</span><span class="sxs-lookup"><span data-stu-id="74e76-505">Token Protection: False</span></span>  
  
 <span data-ttu-id="74e76-506">整个标头和正文签名：True</span><span class="sxs-lookup"><span data-stu-id="74e76-506">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="74e76-507">保护顺序：SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="74e76-507">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="74e76-508">加密签名：True</span><span class="sxs-lookup"><span data-stu-id="74e76-508">Encrypt Signature: True</span></span>  
  
#### <a name="651-policy-for-sslnegotiated-service-authentication"></a><span data-ttu-id="74e76-509">6.5.1 SslNegotiated 服务身份验证的策略</span><span class="sxs-lookup"><span data-stu-id="74e76-509">6.5.1 Policy for SslNegotiated service authentication</span></span>  

 <span data-ttu-id="74e76-510">本节介绍的所有身份验证模式的策略都相似，唯一的区别在于，所用的特定签名支持令牌或认可令牌不相同。</span><span class="sxs-lookup"><span data-stu-id="74e76-510">Policy for all authentication modes in this section are similar and differ only by specific signed supporting or endorsing tokens used.</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SslNegotiated_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <mssp:SslContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient'>  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />
                </wsp:Policy>  
              </mssp:SslContextToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <!-- Supporting token assertions go here -->  
      ..  
      <sp:Wss11>
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
#### <a name="652-anonymousforsslnegotiated"></a><span data-ttu-id="74e76-511">6.5.2 AnonymousForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="74e76-511">6.5.2 AnonymousForSslNegotiated</span></span>  

 <span data-ttu-id="74e76-512">在此身份验证模式下，客户端是匿名的，而使用 X.509 证书对服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="74e76-512">With this authentication mode the client is anonymous and the service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="74e76-513">所用绑定是对称绑定的一个实例，如上面 6.5.1 中所述。</span><span class="sxs-lookup"><span data-stu-id="74e76-513">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="74e76-514">策略</span><span class="sxs-lookup"><span data-stu-id="74e76-514">Policy</span></span>  
  
 <span data-ttu-id="74e76-515">请参见上面 6.5.1 中的“策略”以了解绑定详细信息。</span><span class="sxs-lookup"><span data-stu-id="74e76-515">See Policy in 6.5.1 above for binding details.</span></span>  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="74e76-516">安全标头示例：SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="74e76-516">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="74e76-517">请求</span><span class="sxs-lookup"><span data-stu-id="74e76-517">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="74e76-518">响应</span><span class="sxs-lookup"><span data-stu-id="74e76-518">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="74e76-519">安全标头示例：EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="74e76-519">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="74e76-520">请求</span><span class="sxs-lookup"><span data-stu-id="74e76-520">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="74e76-521">响应</span><span class="sxs-lookup"><span data-stu-id="74e76-521">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="653-usernameforsslnegotiated"></a><span data-ttu-id="74e76-522">6.5.3 UserNameForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="74e76-522">6.5.3 UserNameForSslNegotiated</span></span>  

 <span data-ttu-id="74e76-523">在此身份验证模式下，客户端使用“用户名令牌”进行身份验证，该令牌作为签名支持令牌出现在 SOAP 层上。</span><span class="sxs-lookup"><span data-stu-id="74e76-523">With this authentication mode the client is authenticates using a Username Token which appears at the SOAP layer as a signed supporting token.</span></span> <span data-ttu-id="74e76-524">使用 X.509 证书对服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="74e76-524">The service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="74e76-525">所用绑定是对称绑定的一个实例，如上面 6.5.1 中所述。</span><span class="sxs-lookup"><span data-stu-id="74e76-525">The binding used is an instance of symmetric binding as described in 6.5.1.</span></span>  
  
 <span data-ttu-id="74e76-526">策略</span><span class="sxs-lookup"><span data-stu-id="74e76-526">Policy</span></span>  
  
 <span data-ttu-id="74e76-527">请参见上面的第 6.5.1 节以了解绑定详细信息</span><span class="sxs-lookup"><span data-stu-id="74e76-527">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="74e76-528">签名支持令牌</span><span class="sxs-lookup"><span data-stu-id="74e76-528">Signed Supporting Token</span></span>  
  
```xml  
<sp:SignedSupportingTokens>  
  <wsp:Policy>  
    <sp:UsernameToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:WssUsernameToken10 />
      </wsp:Policy>  
    </sp:UsernameToken>  
  </wsp:Policy>  
</sp:SignedSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="74e76-529">安全标头示例：SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="74e76-529">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="74e76-530">请求</span><span class="sxs-lookup"><span data-stu-id="74e76-530">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="74e76-531">响应</span><span class="sxs-lookup"><span data-stu-id="74e76-531">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="74e76-532">安全标头示例：EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="74e76-532">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="74e76-533">请求</span><span class="sxs-lookup"><span data-stu-id="74e76-533">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="74e76-534">响应</span><span class="sxs-lookup"><span data-stu-id="74e76-534">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="654-issuedtokenforsslnegotiated"></a><span data-ttu-id="74e76-535">6.5.4 IssuedTokenForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="74e76-535">6.5.4 IssuedTokenForSslNegotiated</span></span>  

 <span data-ttu-id="74e76-536">在此身份验证模式下，客户端不向服务进行身份验证，而是出示一个由 STS 颁发的令牌，并证明掌握了共享密钥。</span><span class="sxs-lookup"><span data-stu-id="74e76-536">With this authentication mode the client does not authenticate to the service, as such, but instead presents a token issued by an STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="74e76-537">颁发的令牌作为认可支持令牌出现在 SOAP 层上。</span><span class="sxs-lookup"><span data-stu-id="74e76-537">The issued token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="74e76-538">使用 X.509 证书对服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="74e76-538">The service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="74e76-539">所用绑定是对称绑定的一个实例，如上面 6.5.1 中所述。</span><span class="sxs-lookup"><span data-stu-id="74e76-539">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="74e76-540">策略</span><span class="sxs-lookup"><span data-stu-id="74e76-540">Policy</span></span>  
  
 <span data-ttu-id="74e76-541">请参见上面的第 6.5.1 节以了解绑定详细信息</span><span class="sxs-lookup"><span data-stu-id="74e76-541">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="74e76-542">认可支持令牌</span><span class="sxs-lookup"><span data-stu-id="74e76-542">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:IssuedToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <sp:RequestSecurityTokenTemplate>  
        <wst:KeyType>  
http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
        </wst:KeyType>
      </sp:RequestSecurityTokenTemplate>  
      <wsp:Policy>  
        <sp:RequireDerivedKeys />
        <sp:RequireInternalReference />
      </wsp:Policy>  
    </sp:IssuedToken>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="74e76-543">安全标头示例：SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="74e76-543">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="74e76-544">请求</span><span class="sxs-lookup"><span data-stu-id="74e76-544">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="74e76-545">响应</span><span class="sxs-lookup"><span data-stu-id="74e76-545">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="74e76-546">安全标头示例：EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="74e76-546">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="74e76-547">请求</span><span class="sxs-lookup"><span data-stu-id="74e76-547">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="74e76-548">响应</span><span class="sxs-lookup"><span data-stu-id="74e76-548">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="655-mutualsslnegotiated"></a><span data-ttu-id="74e76-549">6.5.5 MutualSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="74e76-549">6.5.5 MutualSslNegotiated</span></span>  

 <span data-ttu-id="74e76-550">在此身份验证模式下，客户端和服务都使用 X.509 证书进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="74e76-550">With this authentication mode the client and the service authenticate using X.509 certificates.</span></span> <span data-ttu-id="74e76-551">所用绑定是对称绑定的一个实例，如上面 6.5.1 中所述。</span><span class="sxs-lookup"><span data-stu-id="74e76-551">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="74e76-552">策略</span><span class="sxs-lookup"><span data-stu-id="74e76-552">Policy</span></span>  
  
 <span data-ttu-id="74e76-553">请参见上面的第 6.5.1 节以了解绑定详细信息</span><span class="sxs-lookup"><span data-stu-id="74e76-553">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="74e76-554">认可支持令牌</span><span class="sxs-lookup"><span data-stu-id="74e76-554">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:X509Token sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:RequireThumbprintReference />
        <sp:WssX509V3Token10 />
      </wsp:Policy>  
    </sp:X509Token>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="74e76-555">安全标头示例：SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="74e76-555">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="74e76-556">请求</span><span class="sxs-lookup"><span data-stu-id="74e76-556">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="74e76-557">响应</span><span class="sxs-lookup"><span data-stu-id="74e76-557">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="74e76-558">安全标头示例：EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="74e76-558">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="74e76-559">请求</span><span class="sxs-lookup"><span data-stu-id="74e76-559">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="74e76-560">响应</span><span class="sxs-lookup"><span data-stu-id="74e76-560">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
### <a name="66-sspinegotiated"></a><span data-ttu-id="74e76-561">6.6 SspiNegotiated</span><span class="sxs-lookup"><span data-stu-id="74e76-561">6.6 SspiNegotiated</span></span>  

 <span data-ttu-id="74e76-562">在此身份验证模式下，将使用协商协议来执行客户端和服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="74e76-562">With this authentication mode a negotiation protocol is used to perform client and server authentication.</span></span> <span data-ttu-id="74e76-563">如果可能，就使用 Kerberos，否则使用 NTLM。</span><span class="sxs-lookup"><span data-stu-id="74e76-563">Kerberos is used if possible, otherwise NTLM.</span></span> <span data-ttu-id="74e76-564">所用绑定为对称绑定，具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="74e76-564">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="74e76-565">保护令牌：SpnegoContextToken，包含模式设置为 .../IncludeToken/AlwaysToRecipient</span><span class="sxs-lookup"><span data-stu-id="74e76-565">Protection Token: SpnegoContextToken, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
<span data-ttu-id="74e76-566">令牌保护：False</span><span class="sxs-lookup"><span data-stu-id="74e76-566">Token Protection: False</span></span>  
  
 <span data-ttu-id="74e76-567">整个标头和正文签名：True</span><span class="sxs-lookup"><span data-stu-id="74e76-567">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="74e76-568">保护顺序：SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="74e76-568">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="74e76-569">加密签名：True</span><span class="sxs-lookup"><span data-stu-id="74e76-569">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="74e76-570">策略</span><span class="sxs-lookup"><span data-stu-id="74e76-570">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='CustomBinding_ISimple13_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:SpnegoContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />
                </wsp:Policy>  
              </sp:SpnegoContextToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="74e76-571">安全标头示例：SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="74e76-571">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="74e76-572">请求</span><span class="sxs-lookup"><span data-stu-id="74e76-572">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="74e76-573">响应</span><span class="sxs-lookup"><span data-stu-id="74e76-573">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="74e76-574">安全标头示例：EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="74e76-574">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="74e76-575">请求</span><span class="sxs-lookup"><span data-stu-id="74e76-575">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="74e76-576">响应</span><span class="sxs-lookup"><span data-stu-id="74e76-576">Response</span></span>  
  
```xml  
<wsse:Security>  
<wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
### <a name="67-secureconversation"></a><span data-ttu-id="74e76-577">6.7 SecureConversation</span><span class="sxs-lookup"><span data-stu-id="74e76-577">6.7 SecureConversation</span></span>  

 <span data-ttu-id="74e76-578">所用绑定为对称绑定，保护令牌为符合 WS-SecureConversation (WS-SC) 的 SCT。</span><span class="sxs-lookup"><span data-stu-id="74e76-578">The binding used is a symmetric binding with the protection token being a SCT per WS-SecureConversation (WS-SC).</span></span> <span data-ttu-id="74e76-579">该 SCT 是根据嵌套的绑定使用 WS-Trust (WS-Trust) 或 WS-SecureConversation (WS-SC) 协商的，该嵌套绑定本身是使用协商协议的对称绑定。</span><span class="sxs-lookup"><span data-stu-id="74e76-579">The SCT is negotiated using WS-Trust (WS-Trust) or WS-SecureConversation (WS-SC) according to a nested binding, which is itself a symmetric binding that uses a negotiation protocol.</span></span> <span data-ttu-id="74e76-580">如果可能，协商协议将使用 Kerberos 来执行客户端和服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="74e76-580">The negotiation protocol will use Kerberos to perform client and server authentication if possible.</span></span> <span data-ttu-id="74e76-581">如果无法使用 Kerberos，则退而使用 NTLM。</span><span class="sxs-lookup"><span data-stu-id="74e76-581">If Kerberos cannot be used, it will fall back to NTLM.</span></span>  
  
 <span data-ttu-id="74e76-582">策略</span><span class="sxs-lookup"><span data-stu-id="74e76-582">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SecureConversation_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:SecureConversationToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />
                  <sp:BootstrapPolicy>  
                    <wsp:Policy>  
                      <sp:SignedParts>  
                        <sp:Body />
                        <sp:Header Name='To' Namespace='http://www.w3.org/2005/08/addressing' />
                        <sp:Header Name='From' Namespace='http://www.w3.org/2005/08/addressing' />
                        <sp:Header Name='FaultTo' Namespace='http://www.w3.org/2005/08/addressing' />
                        <sp:Header Name='ReplyTo' Namespace='http://www.w3.org/2005/08/addressing' />
                        <sp:Header Name='MessageID' Namespace='http://www.w3.org/2005/08/addressing' />
                        <sp:Header Name='RelatesTo' Namespace='http://www.w3.org/2005/08/addressing' />
                        <sp:Header Name='Action' Namespace='http://www.w3.org/2005/08/addressing' />
                      </sp:SignedParts>  
                      <sp:EncryptedParts>  
                        <sp:Body />
                      </sp:EncryptedParts>  
                      <sp:SymmetricBinding>  
                        <wsp:Policy>  
                          <sp:ProtectionToken>  
                            <wsp:Policy>  
                              <sp:SpnegoContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                                <wsp:Policy>  
                                  <sp:RequireDerivedKeys />
                                </wsp:Policy>  
                              </sp:SpnegoContextToken>  
                            </wsp:Policy>  
                          </sp:ProtectionToken>  
                          <sp:AlgorithmSuite>  
                            <wsp:Policy>  
                              <sp:Basic256 />
                            </wsp:Policy>  
                          </sp:AlgorithmSuite>  
                          <sp:Layout>  
                            <wsp:Policy>  
                              <sp:Strict />
                            </wsp:Policy>  
                          </sp:Layout>  
                          <sp:IncludeTimestamp />
                          <sp:EncryptSignature />
                          <sp:OnlySignEntireHeadersAndBody />
                        </wsp:Policy>  
                      </sp:SymmetricBinding>  
                      <sp:Wss11>  
                        <wsp:Policy>  
                          <sp:MustSupportRefKeyIdentifier />
                          <sp:MustSupportRefIssuerSerial />
                          <sp:MustSupportRefThumbprint />
                          <sp:MustSupportRefEncryptedKey />
                        </wsp:Policy>  
                      </sp:Wss11>  
                      <sp:Trust10>  
                        <wsp:Policy>  
                          <sp:MustSupportIssuedTokens />
                          <sp:RequireClientEntropy />
                          <sp:RequireServerEntropy />
                        </wsp:Policy>  
                      </sp:Trust10>  
                    </wsp:Policy>  
                  </sp:BootstrapPolicy>  
                </wsp:Policy>  
              </sp:SecureConversationToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="74e76-583">安全标头示例：SignBeforeEncrypt、EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="74e76-583">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="74e76-584">请求</span><span class="sxs-lookup"><span data-stu-id="74e76-584">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="74e76-585">响应</span><span class="sxs-lookup"><span data-stu-id="74e76-585">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="74e76-586">安全标头示例：EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="74e76-586">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="74e76-587">请求</span><span class="sxs-lookup"><span data-stu-id="74e76-587">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="74e76-588">响应</span><span class="sxs-lookup"><span data-stu-id="74e76-588">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```
