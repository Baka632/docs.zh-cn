---
title: 用户名客户端的消息安全
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 36335cb9-76b8-4443-92c7-44f081eabb21
ms.openlocfilehash: 7168b393bde626c8c413cda3c7422e0eee4ce267
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96292865"
---
# <a name="message-security-with-a-user-name-client"></a><span data-ttu-id="5b356-102">用户名客户端的消息安全</span><span class="sxs-lookup"><span data-stu-id="5b356-102">Message Security with a User Name Client</span></span>

<span data-ttu-id="5b356-103">下图显示了使用消息级安全性来保护 Windows Communication Foundation (WCF) 服务和客户端。</span><span class="sxs-lookup"><span data-stu-id="5b356-103">The following illustration shows an Windows Communication Foundation (WCF) service and client secured using message-level security.</span></span> <span data-ttu-id="5b356-104">服务使用 X.509 证书进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="5b356-104">The service is authenticated with an X.509 certificate.</span></span> <span data-ttu-id="5b356-105">客户端使用用户名和密码进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="5b356-105">The client authenticates using a user name and password.</span></span>  
  
 <span data-ttu-id="5b356-106">有关示例应用程序，请参阅 [消息安全用户名](../samples/message-security-user-name.md)。</span><span class="sxs-lookup"><span data-stu-id="5b356-106">For a sample application, see [Message Security User Name](../samples/message-security-user-name.md).</span></span>  
  
 <span data-ttu-id="5b356-107">![使用用户名身份验证的消息安全](media/1fb10a61-7e1d-42f5-b1af-195bfee5b3c6.gif "1fb10a61-7e1d-42f5-b1af-195bfee5b3c6")</span><span class="sxs-lookup"><span data-stu-id="5b356-107">![Message security using username authentication](media/1fb10a61-7e1d-42f5-b1af-195bfee5b3c6.gif "1fb10a61-7e1d-42f5-b1af-195bfee5b3c6")</span></span>  
  
|<span data-ttu-id="5b356-108">特征</span><span class="sxs-lookup"><span data-stu-id="5b356-108">Characteristic</span></span>|<span data-ttu-id="5b356-109">说明</span><span class="sxs-lookup"><span data-stu-id="5b356-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="5b356-110">安全模式</span><span class="sxs-lookup"><span data-stu-id="5b356-110">Security Mode</span></span>|<span data-ttu-id="5b356-111">消息</span><span class="sxs-lookup"><span data-stu-id="5b356-111">Message</span></span>|  
|<span data-ttu-id="5b356-112">互操作性</span><span class="sxs-lookup"><span data-stu-id="5b356-112">Interoperability</span></span>|<span data-ttu-id="5b356-113">仅 Windows Communication Foundation (WCF) </span><span class="sxs-lookup"><span data-stu-id="5b356-113">Windows Communication Foundation (WCF) only</span></span>|  
|<span data-ttu-id="5b356-114">身份验证（服务器）</span><span class="sxs-lookup"><span data-stu-id="5b356-114">Authentication (Server)</span></span>|<span data-ttu-id="5b356-115">初始协商需要服务器身份验证</span><span class="sxs-lookup"><span data-stu-id="5b356-115">Initial negotiation requires server authentication</span></span>|  
|<span data-ttu-id="5b356-116">身份验证（客户端）</span><span class="sxs-lookup"><span data-stu-id="5b356-116">Authentication (Client)</span></span>|<span data-ttu-id="5b356-117">用户名/密码</span><span class="sxs-lookup"><span data-stu-id="5b356-117">User name/password</span></span>|  
|<span data-ttu-id="5b356-118">完整性</span><span class="sxs-lookup"><span data-stu-id="5b356-118">Integrity</span></span>|<span data-ttu-id="5b356-119">是，使用共享安全上下文</span><span class="sxs-lookup"><span data-stu-id="5b356-119">Yes, using shared security context</span></span>|  
|<span data-ttu-id="5b356-120">机密性</span><span class="sxs-lookup"><span data-stu-id="5b356-120">Confidentiality</span></span>|<span data-ttu-id="5b356-121">是，使用共享安全上下文</span><span class="sxs-lookup"><span data-stu-id="5b356-121">Yes, using shared security context</span></span>|  
|<span data-ttu-id="5b356-122">Transport</span><span class="sxs-lookup"><span data-stu-id="5b356-122">Transport</span></span>|<span data-ttu-id="5b356-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="5b356-123">HTTP</span></span>|  
|<span data-ttu-id="5b356-124">绑定</span><span class="sxs-lookup"><span data-stu-id="5b356-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="5b356-125">服务</span><span class="sxs-lookup"><span data-stu-id="5b356-125">Service</span></span>  

 <span data-ttu-id="5b356-126">下面的代码和配置应独立运行。</span><span class="sxs-lookup"><span data-stu-id="5b356-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="5b356-127">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="5b356-127">Do one of the following:</span></span>  
  
- <span data-ttu-id="5b356-128">使用代码（而不使用配置）创建独立服务。</span><span class="sxs-lookup"><span data-stu-id="5b356-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="5b356-129">使用提供的配置创建服务，但不定义任何终结点。</span><span class="sxs-lookup"><span data-stu-id="5b356-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="5b356-130">代码</span><span class="sxs-lookup"><span data-stu-id="5b356-130">Code</span></span>  

 <span data-ttu-id="5b356-131">下面的代码演示如何创建使用消息安全的服务终结点。</span><span class="sxs-lookup"><span data-stu-id="5b356-131">The following code shows how to create a service endpoint that uses message security.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#9)]
 [!code-vb[C_SecurityScenarios#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#9)]  
  
### <a name="configuration"></a><span data-ttu-id="5b356-132">Configuration</span><span class="sxs-lookup"><span data-stu-id="5b356-132">Configuration</span></span>  

 <span data-ttu-id="5b356-133">以下配置可代替代码使用：</span><span class="sxs-lookup"><span data-stu-id="5b356-133">The following configuration can be used instead of the code:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ServiceCredentialsBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"
                                storeLocation="LocalMachine"  
                                storeName="My"
                                x509FindType="FindBySubjectName" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service behaviorConfiguration="ServiceCredentialsBehavior"  
               name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"  
                  binding="wsHttpBinding"  
                  bindingConfiguration="MessageAndUserName"  
                  name="SecuredByTransportEndpoint"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="MessageAndUserName">  
          <security mode="Message">
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="5b356-134">客户端</span><span class="sxs-lookup"><span data-stu-id="5b356-134">Client</span></span>  
  
### <a name="code"></a><span data-ttu-id="5b356-135">代码</span><span class="sxs-lookup"><span data-stu-id="5b356-135">Code</span></span>  

 <span data-ttu-id="5b356-136">下面的代码创建客户端。</span><span class="sxs-lookup"><span data-stu-id="5b356-136">The following code creates the client.</span></span> <span data-ttu-id="5b356-137">绑定设置为消息模式安全，客户端凭据类型设置为 `UserName`。</span><span class="sxs-lookup"><span data-stu-id="5b356-137">The binding is to message mode security, and the client credential type is set to `UserName`.</span></span> <span data-ttu-id="5b356-138">用户名和密码只能使用代码指定（不可配置）。</span><span class="sxs-lookup"><span data-stu-id="5b356-138">The user name and password can only be specified using code (it is not configurable).</span></span> <span data-ttu-id="5b356-139">返回用户名和密码的代码未在此处显示，因为这必须在应用程序级完成。</span><span class="sxs-lookup"><span data-stu-id="5b356-139">The code to return the user name and password is not shown here because it must be done at the application level.</span></span> <span data-ttu-id="5b356-140">例如，使用 Windows 窗体对话框查询用户以获得这些数据。</span><span class="sxs-lookup"><span data-stu-id="5b356-140">For example, use a Windows Forms dialog box to query the user for the data.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#16](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#16)]
 [!code-vb[C_SecurityScenarios#16](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#16)]  
  
### <a name="configuration"></a><span data-ttu-id="5b356-141">Configuration</span><span class="sxs-lookup"><span data-stu-id="5b356-141">Configuration</span></span>  

 <span data-ttu-id="5b356-142">下面的代码将配置客户端。</span><span class="sxs-lookup"><span data-stu-id="5b356-142">The following code configures the client.</span></span> <span data-ttu-id="5b356-143">绑定设置为消息模式安全，客户端凭据类型设置为 `UserName`。</span><span class="sxs-lookup"><span data-stu-id="5b356-143">The binding is to message mode security, and the client credential type is set to `UserName`.</span></span> <span data-ttu-id="5b356-144">用户名和密码只能使用代码指定（不可配置）。</span><span class="sxs-lookup"><span data-stu-id="5b356-144">The user name and password can only be specified using code (it is not configurable).</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <dns value ="Contoso.com" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5b356-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b356-145">See also</span></span>

- [<span data-ttu-id="5b356-146">安全性概述</span><span class="sxs-lookup"><span data-stu-id="5b356-146">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="5b356-147">用户名消息安全</span><span class="sxs-lookup"><span data-stu-id="5b356-147">Message Security User Name</span></span>](../samples/message-security-user-name.md)
- [<span data-ttu-id="5b356-148">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="5b356-148">Service Identity and Authentication</span></span>](service-identity-and-authentication.md)
- [\<identity>](../../configure-apps/file-schema/wcf/identity.md)
- <span data-ttu-id="5b356-149">[Windows Server App Fabric 的安全模型](/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="5b356-149">[Security Model for Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
