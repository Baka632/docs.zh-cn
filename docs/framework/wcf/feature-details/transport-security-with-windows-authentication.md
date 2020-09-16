---
title: 通过 Windows 身份验证确保的传输安全
description: 查看此方案，其中显示了由 Windows 安全保护的 WCF 客户端/服务。 在此示例中，intranet 服务显示人力资源信息。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 96dd26e2-46e7-4de0-9a29-4fcb05bf187b
ms.openlocfilehash: 9b81f2f2fb6352af254146951ed35ad4fdca8caa
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "90545202"
---
# <a name="transport-security-with-windows-authentication"></a><span data-ttu-id="becd3-104">通过 Windows 身份验证确保的传输安全</span><span class="sxs-lookup"><span data-stu-id="becd3-104">Transport Security with Windows Authentication</span></span>
<span data-ttu-id="becd3-105">下面的方案演示了 Windows 安全性所保护的 Windows Communication Foundation (WCF) 客户端和服务。</span><span class="sxs-lookup"><span data-stu-id="becd3-105">The following scenario shows a Windows Communication Foundation (WCF) client and service secured by Windows security.</span></span> <span data-ttu-id="becd3-106">有关编程的详细信息，请参阅 [如何：使用 Windows 凭据保护服务](../how-to-secure-a-service-with-windows-credentials.md)。</span><span class="sxs-lookup"><span data-stu-id="becd3-106">For more information about programming, see [How to: Secure a Service with Windows Credentials](../how-to-secure-a-service-with-windows-credentials.md).</span></span>  
  
 <span data-ttu-id="becd3-107">Intranet Web 服务显示了人力资源信息。</span><span class="sxs-lookup"><span data-stu-id="becd3-107">An intranet Web service displays human resources information.</span></span> <span data-ttu-id="becd3-108">客户端是 Windows 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="becd3-108">The client is a Windows Form application.</span></span> <span data-ttu-id="becd3-109">该应用程序部署在具有 Kerberos 控制器保护的域中。</span><span class="sxs-lookup"><span data-stu-id="becd3-109">The application is deployed in a domain with a Kerberos controller securing the domain.</span></span>  
  
 ![使用 Windows 身份验证的传输安全性](./media/transport-security-with-windows-authentication/secured-windows-authentication.gif)  
  
|<span data-ttu-id="becd3-111">特征</span><span class="sxs-lookup"><span data-stu-id="becd3-111">Characteristic</span></span>|<span data-ttu-id="becd3-112">说明</span><span class="sxs-lookup"><span data-stu-id="becd3-112">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="becd3-113">安全模式</span><span class="sxs-lookup"><span data-stu-id="becd3-113">Security Mode</span></span>|<span data-ttu-id="becd3-114">Transport</span><span class="sxs-lookup"><span data-stu-id="becd3-114">Transport</span></span>|  
|<span data-ttu-id="becd3-115">互操作性</span><span class="sxs-lookup"><span data-stu-id="becd3-115">Interoperability</span></span>|<span data-ttu-id="becd3-116">仅 WCF</span><span class="sxs-lookup"><span data-stu-id="becd3-116">WCF only</span></span>|  
|<span data-ttu-id="becd3-117">身份验证（服务器）</span><span class="sxs-lookup"><span data-stu-id="becd3-117">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="becd3-118">身份验证（客户端）</span><span class="sxs-lookup"><span data-stu-id="becd3-118">Authentication (Client)</span></span>|<span data-ttu-id="becd3-119">是（使用 Windows 集成身份验证）</span><span class="sxs-lookup"><span data-stu-id="becd3-119">Yes (using Windows integrated authentication)</span></span><br /><br /> <span data-ttu-id="becd3-120">是（使用 Windows 集成身份验证）</span><span class="sxs-lookup"><span data-stu-id="becd3-120">Yes (using Windows integrated authentication)</span></span>|  
|<span data-ttu-id="becd3-121">完整性</span><span class="sxs-lookup"><span data-stu-id="becd3-121">Integrity</span></span>|<span data-ttu-id="becd3-122">是</span><span class="sxs-lookup"><span data-stu-id="becd3-122">Yes</span></span>|  
|<span data-ttu-id="becd3-123">保密性</span><span class="sxs-lookup"><span data-stu-id="becd3-123">Confidentiality</span></span>|<span data-ttu-id="becd3-124">是</span><span class="sxs-lookup"><span data-stu-id="becd3-124">Yes</span></span>|  
|<span data-ttu-id="becd3-125">Transport</span><span class="sxs-lookup"><span data-stu-id="becd3-125">Transport</span></span>|<span data-ttu-id="becd3-126">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="becd3-126">NET.TCP</span></span>|  
|<span data-ttu-id="becd3-127">绑定</span><span class="sxs-lookup"><span data-stu-id="becd3-127">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
  
## <a name="service"></a><span data-ttu-id="becd3-128">服务</span><span class="sxs-lookup"><span data-stu-id="becd3-128">Service</span></span>  
 <span data-ttu-id="becd3-129">下面的代码和配置应独立运行。</span><span class="sxs-lookup"><span data-stu-id="becd3-129">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="becd3-130">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="becd3-130">Do one of the following:</span></span>  
  
- <span data-ttu-id="becd3-131">使用代码（而不使用配置）创建独立服务。</span><span class="sxs-lookup"><span data-stu-id="becd3-131">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="becd3-132">使用提供的配置创建服务，但不定义任何终结点。</span><span class="sxs-lookup"><span data-stu-id="becd3-132">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="becd3-133">代码</span><span class="sxs-lookup"><span data-stu-id="becd3-133">Code</span></span>  
 <span data-ttu-id="becd3-134">下面的代码演示如何创建使用 Windows 安全的服务终结点。</span><span class="sxs-lookup"><span data-stu-id="becd3-134">The following code shows how to create a service endpoint that uses a Windows security.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#3)]
 [!code-vb[C_SecurityScenarios#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#3)]  
  
### <a name="configuration"></a><span data-ttu-id="becd3-135">Configuration</span><span class="sxs-lookup"><span data-stu-id="becd3-135">Configuration</span></span>  
 <span data-ttu-id="becd3-136">可以使用下面的配置代替代码来设置服务终结点：</span><span class="sxs-lookup"><span data-stu-id="becd3-136">The following configuration can be used instead of the code to set up the service endpoint:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration="" name="ServiceModel.Calculator">  
        <endpoint address="net.tcp://localhost:8008/Calculator"
                  binding="netTcpBinding"  
          bindingConfiguration="WindowsClientOverTcp"
                  name="WindowsClientOverTcp"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <netTcpBinding>  
        <binding name="WindowsClientOverTcp">  
          <security mode="Transport">  
            <transport clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="becd3-137">客户端</span><span class="sxs-lookup"><span data-stu-id="becd3-137">Client</span></span>  
 <span data-ttu-id="becd3-138">下面的代码和配置应独立运行。</span><span class="sxs-lookup"><span data-stu-id="becd3-138">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="becd3-139">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="becd3-139">Do one of the following:</span></span>  
  
- <span data-ttu-id="becd3-140">使用代码（和客户端代码）创建独立客户端。</span><span class="sxs-lookup"><span data-stu-id="becd3-140">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="becd3-141">创建不定义任何终结点地址的客户端。</span><span class="sxs-lookup"><span data-stu-id="becd3-141">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="becd3-142">而使用将配置名称作为自变量的客户端构造函数。</span><span class="sxs-lookup"><span data-stu-id="becd3-142">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="becd3-143">例如：</span><span class="sxs-lookup"><span data-stu-id="becd3-143">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="becd3-144">代码</span><span class="sxs-lookup"><span data-stu-id="becd3-144">Code</span></span>  
 <span data-ttu-id="becd3-145">下面的代码创建客户端。</span><span class="sxs-lookup"><span data-stu-id="becd3-145">The following code creates the client.</span></span> <span data-ttu-id="becd3-146">绑定配置为使用传输模式安全（采用 TCP 传输协议），并且客户端凭据类型设置为 Windows。</span><span class="sxs-lookup"><span data-stu-id="becd3-146">The binding is configured to use the Transport mode security, with the TCP transport, with the client credential type set to Windows.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#4)]
 [!code-vb[C_SecurityScenarios#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#4)]  
  
### <a name="configuration"></a><span data-ttu-id="becd3-147">Configuration</span><span class="sxs-lookup"><span data-stu-id="becd3-147">Configuration</span></span>  
 <span data-ttu-id="becd3-148">可以使用下面的配置代替代码来创建客户端。</span><span class="sxs-lookup"><span data-stu-id="becd3-148">The following configuration can be used instead of the code to create the client.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <netTcpBinding>  
        <binding name="NetTcpBinding_ICalculator" >  
          <security mode="Transport">  
            <transport clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client>  
      <endpoint address="net.tcp://localhost:8008/Calculator"
                binding="netTcpBinding"
                bindingConfiguration="NetTcpBinding_ICalculator"
                contract="ICalculator"  
                name="NetTcpBinding_ICalculator">  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="becd3-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="becd3-149">See also</span></span>

- [<span data-ttu-id="becd3-150">安全性概述</span><span class="sxs-lookup"><span data-stu-id="becd3-150">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="becd3-151">如何：使用 Windows 凭据保护服务的安全</span><span class="sxs-lookup"><span data-stu-id="becd3-151">How to: Secure a Service with Windows Credentials</span></span>](../how-to-secure-a-service-with-windows-credentials.md)
- <span data-ttu-id="becd3-152">[Windows Server App Fabric 的安全模型](/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="becd3-152">[Security Model for Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
