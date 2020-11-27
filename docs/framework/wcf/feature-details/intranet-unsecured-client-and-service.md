---
title: 不安全的 Intranet 客户端和服务
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f450f5d4-3547-47ec-9320-2809e6a12634
ms.openlocfilehash: f9cd297b479a07f2330eabbaaf81605a3874ec25
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96257216"
---
# <a name="intranet-unsecured-client-and-service"></a><span data-ttu-id="38f90-102">不安全的 Intranet 客户端和服务</span><span class="sxs-lookup"><span data-stu-id="38f90-102">Intranet Unsecured Client and Service</span></span>

<span data-ttu-id="38f90-103">下图描绘了一个简单的 Windows Communication Foundation (WCF) 服务，该服务开发用于向 WCF 应用程序提供安全的专用网络的信息。</span><span class="sxs-lookup"><span data-stu-id="38f90-103">The following illustration depicts a simple Windows Communication Foundation (WCF) service developed to provide information on a secure private network to a WCF application.</span></span> <span data-ttu-id="38f90-104">安全不是必需的，因为数据重要性较低，网络本来就是安全的，或者是由 WCF 基础结构下面的层提供的。</span><span class="sxs-lookup"><span data-stu-id="38f90-104">Security is not required because the data is of low importance, the network is expected to be inherently secure, or security is provided by a layer below the WCF infrastructure.</span></span>  
  
 ![Intranet 不安全的客户端和服务方案。](./media/intranet-unsecured-client-and-service/unsecured-web-client-service.gif)  
  
|<span data-ttu-id="38f90-106">特征</span><span class="sxs-lookup"><span data-stu-id="38f90-106">Characteristic</span></span>|<span data-ttu-id="38f90-107">说明</span><span class="sxs-lookup"><span data-stu-id="38f90-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="38f90-108">安全模式</span><span class="sxs-lookup"><span data-stu-id="38f90-108">Security Mode</span></span>|<span data-ttu-id="38f90-109">无</span><span class="sxs-lookup"><span data-stu-id="38f90-109">None</span></span>|  
|<span data-ttu-id="38f90-110">Transport</span><span class="sxs-lookup"><span data-stu-id="38f90-110">Transport</span></span>|<span data-ttu-id="38f90-111">TCP</span><span class="sxs-lookup"><span data-stu-id="38f90-111">TCP</span></span>|  
|<span data-ttu-id="38f90-112">绑定</span><span class="sxs-lookup"><span data-stu-id="38f90-112">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
|<span data-ttu-id="38f90-113">互操作性</span><span class="sxs-lookup"><span data-stu-id="38f90-113">Interoperability</span></span>|<span data-ttu-id="38f90-114">仅 WCF</span><span class="sxs-lookup"><span data-stu-id="38f90-114">WCF only</span></span>|  
|<span data-ttu-id="38f90-115">身份验证</span><span class="sxs-lookup"><span data-stu-id="38f90-115">Authentication</span></span>|<span data-ttu-id="38f90-116">无</span><span class="sxs-lookup"><span data-stu-id="38f90-116">None</span></span>|  
|<span data-ttu-id="38f90-117">完整性</span><span class="sxs-lookup"><span data-stu-id="38f90-117">Integrity</span></span>|<span data-ttu-id="38f90-118">无</span><span class="sxs-lookup"><span data-stu-id="38f90-118">None</span></span>|  
|<span data-ttu-id="38f90-119">机密性</span><span class="sxs-lookup"><span data-stu-id="38f90-119">Confidentiality</span></span>|<span data-ttu-id="38f90-120">无</span><span class="sxs-lookup"><span data-stu-id="38f90-120">None</span></span>|  
  
## <a name="service"></a><span data-ttu-id="38f90-121">服务</span><span class="sxs-lookup"><span data-stu-id="38f90-121">Service</span></span>  

 <span data-ttu-id="38f90-122">下面的代码和配置应独立运行。</span><span class="sxs-lookup"><span data-stu-id="38f90-122">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="38f90-123">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="38f90-123">Do one of the following:</span></span>  
  
- <span data-ttu-id="38f90-124">使用代码（而不使用配置）创建独立服务。</span><span class="sxs-lookup"><span data-stu-id="38f90-124">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="38f90-125">使用提供的配置创建服务，但不定义任何终结点。</span><span class="sxs-lookup"><span data-stu-id="38f90-125">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="38f90-126">代码</span><span class="sxs-lookup"><span data-stu-id="38f90-126">Code</span></span>  

 <span data-ttu-id="38f90-127">下面的代码演示如何创建不安全的终结点：</span><span class="sxs-lookup"><span data-stu-id="38f90-127">The following code shows how to create an endpoint with no security:</span></span>  
  
 [!code-csharp[C_UnsecuredService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredservice/cs/source.cs#2)]
 [!code-vb[C_UnsecuredService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredservice/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="38f90-128">Configuration</span><span class="sxs-lookup"><span data-stu-id="38f90-128">Configuration</span></span>  

 <span data-ttu-id="38f90-129">下面的代码使用配置设置相同的终结点：</span><span class="sxs-lookup"><span data-stu-id="38f90-129">The following code sets up the same endpoint using configuration:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration=""
               name="ServiceModel.Calculator">  
        <endpoint address="net.tcp://localhost:8008/Calculator"
                  binding="netTcpBinding"  
                  bindingConfiguration="tcp_Unsecured"
                  name="netTcp_ICalculator"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <netTcpBinding>  
        <binding name="tcp_Unsecured">  
          <security mode="None" />  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="38f90-130">客户端</span><span class="sxs-lookup"><span data-stu-id="38f90-130">Client</span></span>  

 <span data-ttu-id="38f90-131">下面的代码和配置应独立运行。</span><span class="sxs-lookup"><span data-stu-id="38f90-131">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="38f90-132">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="38f90-132">Do one of the following:</span></span>  
  
- <span data-ttu-id="38f90-133">使用代码（和客户端代码）创建独立客户端。</span><span class="sxs-lookup"><span data-stu-id="38f90-133">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="38f90-134">创建不定义任何终结点地址的客户端。</span><span class="sxs-lookup"><span data-stu-id="38f90-134">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="38f90-135">而使用将配置名称作为自变量的客户端构造函数。</span><span class="sxs-lookup"><span data-stu-id="38f90-135">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="38f90-136">例如：</span><span class="sxs-lookup"><span data-stu-id="38f90-136">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="38f90-137">代码</span><span class="sxs-lookup"><span data-stu-id="38f90-137">Code</span></span>  

 <span data-ttu-id="38f90-138">下面的代码演示一个基本 WCF 客户端，它使用 TCP 协议访问不安全的终结点。</span><span class="sxs-lookup"><span data-stu-id="38f90-138">The following code shows a basic WCF client that accesses an unsecured endpoint using the TCP protocol.</span></span>  
  
 [!code-csharp[C_UnsecuredClient#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredclient/cs/source.cs#2)]
 [!code-vb[C_UnsecuredClient#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredclient/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="38f90-139">Configuration</span><span class="sxs-lookup"><span data-stu-id="38f90-139">Configuration</span></span>  

 <span data-ttu-id="38f90-140">下面的配置代码应用于客户端：</span><span class="sxs-lookup"><span data-stu-id="38f90-140">The following configuration code applies to the client:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <netTcpBinding>  
        <binding name="NetTcpBinding_ICalculator" >  
          <security mode="None">  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client>  
      <endpoint address="net.tcp://machineName:8008/Calculator "  
                binding="netTcpBinding"
                bindingConfiguration="NetTcpBinding_ICalculator"  
                contract="ICalculator"
                name="NetTcpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="38f90-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38f90-141">See also</span></span>

- <xref:System.ServiceModel.NetTcpBinding>
- [<span data-ttu-id="38f90-142">安全性概述</span><span class="sxs-lookup"><span data-stu-id="38f90-142">Security Overview</span></span>](security-overview.md)
- <span data-ttu-id="38f90-143">[Windows Server App Fabric 的安全模型](/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="38f90-143">[Security Model for Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
