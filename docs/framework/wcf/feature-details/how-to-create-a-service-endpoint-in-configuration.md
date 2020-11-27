---
title: 如何：在配置中创建服务终结点
description: 了解如何使用同时包含相对和绝对地址的配置文件为 WCF 服务添加终结点。
ms.date: 06/16/2016
ms.assetid: f474e25d-2a27-4f31-84c5-395c442b8e70
ms.openlocfilehash: aa8dce18a39b44c2c56d072a81699d1bc1e7d7da
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286417"
---
# <a name="how-to-create-a-service-endpoint-in-configuration"></a><span data-ttu-id="c894e-103">如何：在配置中创建服务终结点</span><span class="sxs-lookup"><span data-stu-id="c894e-103">How to: Create a Service Endpoint in Configuration</span></span>

<span data-ttu-id="c894e-104">终结点使客户端能够访问 Windows Communication Foundation (WCF) 服务所提供的功能。</span><span class="sxs-lookup"><span data-stu-id="c894e-104">Endpoints provide clients with access to the functionality a Windows Communication Foundation (WCF) service offers.</span></span> <span data-ttu-id="c894e-105">您可以通过使用相对和绝对终结点地址的组合来定义一个或多个终结点，或者如果您未定义任何服务终结点，则默认情况下运行时为您提供一些终结点。</span><span class="sxs-lookup"><span data-stu-id="c894e-105">You can define one or more endpoints for a service by using a combination of relative and absolute endpoint addresses, or if you do not define any service endpoints, the runtime provides some by default for you.</span></span> <span data-ttu-id="c894e-106">本主题演示如何使用同时包含相对和绝对地址的配置文件来添加终结点。</span><span class="sxs-lookup"><span data-stu-id="c894e-106">This topic shows how to add endpoints using a configuration file that contain both relative and absolute addresses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c894e-107">示例</span><span class="sxs-lookup"><span data-stu-id="c894e-107">Example</span></span>  

 <span data-ttu-id="c894e-108">下列服务配置指定一个基址和五个终结点。</span><span class="sxs-lookup"><span data-stu-id="c894e-108">The following service configuration specifies a base address and five endpoints.</span></span>  
  
```xml  
<configuration>  
  
  <appSettings>  
    <!-- use appSetting to configure base address provided by host -->  
    <add key="baseAddress" value="http://localhost:8000/servicemodelsamples/service" />  
  </appSettings>  
  
  <system.serviceModel>  
    <services>  
    <!-- This section is optional with the default configuration introduced in .NET Framework 4. -->  
      <service name="Microsoft.ServiceModel.Samples.CalculatorService">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
          </baseAddresses>  
        </host>  
        <endpoint address=""  
                  binding="wsHttpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <endpoint address="/test"  
                  binding="wsHttpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <endpoint address="http://localhost:8001/hello/servicemodelsamples"  
                  binding="wsHttpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <endpoint address="net.tcp://localhost:9000/servicemodelsamples/service"  
                  binding="netTcpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <!-- the mex endpoint is another relative address exposed at   
             http://localhost:8000/ServiceModelSamples/service/mex -->  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
  </system.serviceModel>  
  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="c894e-109">示例</span><span class="sxs-lookup"><span data-stu-id="c894e-109">Example</span></span>  

 <span data-ttu-id="c894e-110">基址是使用 `add` 元素在 service/host/baseAddresses 下指定的，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="c894e-110">The base address is specified using the `add` element, under service/host/baseAddresses, as shown in the following sample.</span></span>  
  
```xml  
<service
    name="Microsoft.ServiceModel.Samples.CalculatorService">  
  <host>  
    <baseAddresses>  
      <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
    </baseAddresses>  
  </host>  
```  
  
## <a name="example"></a><span data-ttu-id="c894e-111">示例</span><span class="sxs-lookup"><span data-stu-id="c894e-111">Example</span></span>  

 <span data-ttu-id="c894e-112">在以下示例中显示的第一个终结点指定一个相对地址，这意味着该终结点地址是遵循统一资源标识符 (URI) 构成规则的基址和相对地址的结合。</span><span class="sxs-lookup"><span data-stu-id="c894e-112">The first endpoint definition shown in the following sample specifies a relative address, which means the endpoint address is a combination of the base address and the relative address following the rules of Uniform Resource Identifier (URI) composition.</span></span> <span data-ttu-id="c894e-113">相对地址为空 ("")，因此终结点地址与基址相同。</span><span class="sxs-lookup"><span data-stu-id="c894e-113">The relative address is empty (""), so the endpoint address is the same as the base address.</span></span> <span data-ttu-id="c894e-114">实际终结点地址为 `http://localhost:8000/servicemodelsamples/service` 。</span><span class="sxs-lookup"><span data-stu-id="c894e-114">The actual endpoint address is `http://localhost:8000/servicemodelsamples/service`.</span></span>  
  
```xml  
<endpoint address=""
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a><span data-ttu-id="c894e-115">示例</span><span class="sxs-lookup"><span data-stu-id="c894e-115">Example</span></span>  

 <span data-ttu-id="c894e-116">第二个终结点定义也指定一个相对地址，如下面的示例配置所示。</span><span class="sxs-lookup"><span data-stu-id="c894e-116">The second endpoint definition also specifies a relative address, as shown in the following sample configuration.</span></span> <span data-ttu-id="c894e-117">将相对地址“test”追加到基址。</span><span class="sxs-lookup"><span data-stu-id="c894e-117">The relative address, "test", is appended to the base address.</span></span> <span data-ttu-id="c894e-118">实际终结点地址为 `http://localhost:8000/servicemodelsamples/service/test` 。</span><span class="sxs-lookup"><span data-stu-id="c894e-118">The actual endpoint address is `http://localhost:8000/servicemodelsamples/service/test`.</span></span>  
  
```xml  
<endpoint address="/test"  
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a><span data-ttu-id="c894e-119">示例</span><span class="sxs-lookup"><span data-stu-id="c894e-119">Example</span></span>  

 <span data-ttu-id="c894e-120">第三个终结点定义指定一个绝对地址，如下面的示例配置所示。</span><span class="sxs-lookup"><span data-stu-id="c894e-120">The third endpoint definition specifies an absolute address, as shown in the following sample configuration.</span></span> <span data-ttu-id="c894e-121">基址在地址中不起作用。</span><span class="sxs-lookup"><span data-stu-id="c894e-121">The base address plays no role in the address.</span></span> <span data-ttu-id="c894e-122">实际终结点地址为 `http://localhost:8001/hello/servicemodelsamples` 。</span><span class="sxs-lookup"><span data-stu-id="c894e-122">The actual endpoint address is `http://localhost:8001/hello/servicemodelsamples`.</span></span>  
  
```xml  
<endpoint address="http://localhost:8001/hello/servicemodelsamples"  
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a><span data-ttu-id="c894e-123">示例</span><span class="sxs-lookup"><span data-stu-id="c894e-123">Example</span></span>  

 <span data-ttu-id="c894e-124">第四个终结点地址指定一个绝对地址和一个不同的传输协议 (TCP)。</span><span class="sxs-lookup"><span data-stu-id="c894e-124">The fourth endpoint address specifies an absolute address and a different transport—TCP.</span></span> <span data-ttu-id="c894e-125">基址在地址中不起作用。</span><span class="sxs-lookup"><span data-stu-id="c894e-125">The base address plays no role in the address.</span></span> <span data-ttu-id="c894e-126">实际终结点地址为 net.tcp://localhost:9000/servicemodelsamples/service。</span><span class="sxs-lookup"><span data-stu-id="c894e-126">The actual endpoint address is net.tcp://localhost:9000/servicemodelsamples/service.</span></span>  
  
```xml  
<endpoint address="net.tcp://localhost:9000/servicemodelsamples/service"  
    binding="netTcpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a><span data-ttu-id="c894e-127">示例</span><span class="sxs-lookup"><span data-stu-id="c894e-127">Example</span></span>  

 <span data-ttu-id="c894e-128">若要使用运行时提供的默认终结点，请不要在代码或配置文件中指定任何服务终结点。</span><span class="sxs-lookup"><span data-stu-id="c894e-128">To use the default endpoints provided by the runtime, do not specify any service endpoints in either the code or the configuration file.</span></span> <span data-ttu-id="c894e-129">在此示例中，运行时在打开服务时创建默认终结点。</span><span class="sxs-lookup"><span data-stu-id="c894e-129">In this example, the runtime creates the default endpoints when the service is opened.</span></span> <span data-ttu-id="c894e-130">有关默认终结点、绑定和行为的详细信息，请参阅[简化配置](../simplified-configuration.md)和 [WCF 服务的简化配置](../samples/simplified-configuration-for-wcf-services.md)。</span><span class="sxs-lookup"><span data-stu-id="c894e-130">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](../simplified-configuration.md) and [Simplified Configuration for WCF Services](../samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
```xml  
<configuration>  
  
  <appSettings>  
    <!-- use appSetting to configure base address provided by host -->  
    <add key="baseAddress" value="http://localhost:8000/servicemodelsamples/service" />  
  </appSettings>  
  
  <system.serviceModel>  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
  </system.serviceModel>  
  
</configuration>  
```
