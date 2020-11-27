---
title: 如何：实现向发现代理注册的可发现的服务
ms.date: 03/30/2017
ms.assetid: eb275bc1-535b-44c8-b9f3-0b75e9aa473b
ms.openlocfilehash: 1e6b57193d25da7e5c9a865525dd5e9ea21110b0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254254"
---
# <a name="how-to-implement-a-discoverable-service-that-registers-with-the-discovery-proxy"></a><span data-ttu-id="da1e6-102">如何：实现向发现代理注册的可发现的服务</span><span class="sxs-lookup"><span data-stu-id="da1e6-102">How to: Implement a Discoverable Service that Registers with the Discovery Proxy</span></span>

<span data-ttu-id="da1e6-103">本主题是讨论如何实现发现代理的四个主题中的第二个主题。</span><span class="sxs-lookup"><span data-stu-id="da1e6-103">This topic is the second of four topics that discusses how to implement a discovery proxy.</span></span> <span data-ttu-id="da1e6-104">在上一个主题中， [如何：实现发现代理](how-to-implement-a-discovery-proxy.md)，你已实现了发现代理。</span><span class="sxs-lookup"><span data-stu-id="da1e6-104">In the previous topic, [How to: Implement a Discovery Proxy](how-to-implement-a-discovery-proxy.md), you implemented a discovery proxy.</span></span> <span data-ttu-id="da1e6-105">在本主题中，你将创建一个 WCF 服务，该服务将公告消息 (`Hello` 和 `Bye`) 发送到发现代理，从而使该服务向发现代理注册并向其注销。</span><span class="sxs-lookup"><span data-stu-id="da1e6-105">In this topic, you create a WCF service that sends announcement messages (`Hello` and `Bye`) to the discovery proxy, causing it to register and unregister itself with the discovery proxy.</span></span>

### <a name="to-define-the-service-contract"></a><span data-ttu-id="da1e6-106">定义服务协定</span><span class="sxs-lookup"><span data-stu-id="da1e6-106">To define the service contract</span></span>

1. <span data-ttu-id="da1e6-107">将一个新控制台应用程序项目添加到名为 `DiscoveryProxyExample` 的 `Service` 解决方案。</span><span class="sxs-lookup"><span data-stu-id="da1e6-107">Add a new console application project to the `DiscoveryProxyExample` solution called `Service`.</span></span>

2. <span data-ttu-id="da1e6-108">添加对下列程序集的引用：</span><span class="sxs-lookup"><span data-stu-id="da1e6-108">Add references to the following assemblies:</span></span>

    1. <span data-ttu-id="da1e6-109">System.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="da1e6-109">System.ServiceModel</span></span>

    2. <span data-ttu-id="da1e6-110">System.ServiceModel.Discovery</span><span class="sxs-lookup"><span data-stu-id="da1e6-110">System.ServiceModel.Discovery</span></span>

3. <span data-ttu-id="da1e6-111">将新类添加到名为 `CalculatorService` 的项目中。</span><span class="sxs-lookup"><span data-stu-id="da1e6-111">Add a new class to the project called `CalculatorService`.</span></span>

4. <span data-ttu-id="da1e6-112">添加下面的 using 语句。</span><span class="sxs-lookup"><span data-stu-id="da1e6-112">Add the following using statements.</span></span>

    ```csharp
    using System;
    using System.ServiceModel;
    ```

5. <span data-ttu-id="da1e6-113">在 CalculatorService.cs 中，定义服务协定。</span><span class="sxs-lookup"><span data-stu-id="da1e6-113">Within CalculatorService.cs, define the service contract.</span></span>

    ```csharp
    // Define a service contract.
    [ServiceContract(Namespace = "http://Microsoft.Samples.Discovery")]
    public interface ICalculatorService
    {
        [OperationContract]
        double Add(double n1, double n2);
        [OperationContract]
        double Subtract(double n1, double n2);
        [OperationContract]
        double Multiply(double n1, double n2);
        [OperationContract]
        double Divide(double n1, double n2);
    }
    ```

6. <span data-ttu-id="da1e6-114">同样，在 CalculatorService.cs 中，实现服务协定。</span><span class="sxs-lookup"><span data-stu-id="da1e6-114">Also within CalculatorService.cs, implement the service contract.</span></span>

    ```csharp
    // Service class which implements the service contract.
    public class CalculatorService : ICalculatorService
    {
        public double Add(double n1, double n2)
        {
            double result = n1 + n2;
            Console.WriteLine("Received Add({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Subtract(double n1, double n2)
        {
            double result = n1 - n2;
            Console.WriteLine("Received Subtract({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Multiply(double n1, double n2)
        {
            double result = n1 * n2;
            Console.WriteLine("Received Multiply({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Divide(double n1, double n2)
        {
            double result = n1 / n2;
            Console.WriteLine("Received Divide({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }
    }
    ```

### <a name="to-host-the-service"></a><span data-ttu-id="da1e6-115">承载服务</span><span class="sxs-lookup"><span data-stu-id="da1e6-115">To host the service</span></span>

1. <span data-ttu-id="da1e6-116">打开在创建项目时生成的 Program.cs 文件。</span><span class="sxs-lookup"><span data-stu-id="da1e6-116">Open the Program.cs file that was generated when you created the project.</span></span>

2. <span data-ttu-id="da1e6-117">添加下面的 using 语句。</span><span class="sxs-lookup"><span data-stu-id="da1e6-117">Add the following using statements.</span></span>

    ```csharp
    using System;
    using System.ServiceModel;
    using System.ServiceModel.Description;
    using System.ServiceModel.Discovery;
    ```

3. <span data-ttu-id="da1e6-118">在 `Main()` 方法中，添加下面的代码：</span><span class="sxs-lookup"><span data-stu-id="da1e6-118">Within the `Main()` method, add the following code:</span></span>

    ```csharp
    // Define the base address of the service
    Uri baseAddress = new Uri("net.tcp://localhost:9002/CalculatorService/" + Guid.NewGuid().ToString());
    // Define the endpoint address where announcement messages will be sent
    Uri announcementEndpointAddress = new Uri("net.tcp://localhost:9021/Announcement");

    // Create the service host
    ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress);
    try
    {
        // Add a service endpoint
        ServiceEndpoint netTcpEndpoint = serviceHost.AddServiceEndpoint(typeof(ICalculatorService),
            new NetTcpBinding(), string.Empty);

        // Create an announcement endpoint, which points to the Announcement Endpoint hosted by the proxy service.
        AnnouncementEndpoint announcementEndpoint = new AnnouncementEndpoint(new NetTcpBinding(),
            new EndpointAddress(announcementEndpointAddress));

        // Create a ServiceDiscoveryBehavior and add the announcement endpoint
        ServiceDiscoveryBehavior serviceDiscoveryBehavior = new ServiceDiscoveryBehavior();
        serviceDiscoveryBehavior.AnnouncementEndpoints.Add(announcementEndpoint);

        // Add the ServiceDiscoveryBehavior to the service host to make the service discoverable
        serviceHost.Description.Behaviors.Add(serviceDiscoveryBehavior);

        // Start listening for messages
        serviceHost.Open();

        Console.WriteLine("Calculator Service started at {0}", baseAddress);
        Console.WriteLine();
        Console.WriteLine("Press <ENTER> to terminate the service.");
        Console.WriteLine();
        Console.ReadLine();

        serviceHost.Close();
    }
    catch (CommunicationException e)
    {
        Console.WriteLine(e.Message);
    }
    catch (TimeoutException e)
    {
        Console.WriteLine(e.Message);
    }

    if (serviceHost.State != CommunicationState.Closed)
    {
        Console.WriteLine("Aborting the service...");
        serviceHost.Abort();
    }
    ```

<span data-ttu-id="da1e6-119">至此您已完成可检测到的服务的实现过程。</span><span class="sxs-lookup"><span data-stu-id="da1e6-119">You have completed implementing a discoverable service.</span></span> <span data-ttu-id="da1e6-120">继续 [操作如何：实现使用发现代理查找服务的客户端应用程序](client-app-discovery-proxy-to-find-a-service.md)。</span><span class="sxs-lookup"><span data-stu-id="da1e6-120">Continue on to [How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service](client-app-discovery-proxy-to-find-a-service.md).</span></span>

## <a name="example"></a><span data-ttu-id="da1e6-121">示例</span><span class="sxs-lookup"><span data-stu-id="da1e6-121">Example</span></span>

 <span data-ttu-id="da1e6-122">下面是本主题中使用的代码的完整清单。</span><span class="sxs-lookup"><span data-stu-id="da1e6-122">This is the full listing of the code used in this topic.</span></span>

```csharp
// CalculatorService.cs
//----------------------------------------------------------------
// Copyright (c) Microsoft Corporation.  All rights reserved.
//----------------------------------------------------------------

using System;
using System.ServiceModel;

namespace Microsoft.Samples.Discovery
{
    // Define a service contract.
    [ServiceContract(Namespace = "http://Microsoft.Samples.Discovery")]
    public interface ICalculatorService
    {
        [OperationContract]
        double Add(double n1, double n2);
        [OperationContract]
        double Subtract(double n1, double n2);
        [OperationContract]
        double Multiply(double n1, double n2);
        [OperationContract]
        double Divide(double n1, double n2);
    }

    // Service class which implements the service contract.
    public class CalculatorService : ICalculatorService
    {
        public double Add(double n1, double n2)
        {
            double result = n1 + n2;
            Console.WriteLine("Received Add({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }
  
        public double Subtract(double n1, double n2)
        {
            double result = n1 - n2;
            Console.WriteLine("Received Subtract({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Multiply(double n1, double n2)
        {
            double result = n1 * n2;
            Console.WriteLine("Received Multiply({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Divide(double n1, double n2)
        {
            double result = n1 / n2;
            Console.WriteLine("Received Divide({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }
    }
}
```

```csharp
// Program.cs
//----------------------------------------------------------------
// Copyright (c) Microsoft Corporation.  All rights reserved.
//----------------------------------------------------------------

using System;
using System.ServiceModel;
using System.ServiceModel.Description;
using System.ServiceModel.Discovery;

namespace Microsoft.Samples.Discovery
{
    class Program
    {
        public static void Main()
        {
            Uri baseAddress = new Uri("net.tcp://localhost:9002/CalculatorService/" + Guid.NewGuid().ToString());
            Uri announcementEndpointAddress = new Uri("net.tcp://localhost:9021/Announcement");

            ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress);
            try
            {
                ServiceEndpoint netTcpEndpoint = serviceHost.AddServiceEndpoint(typeof(ICalculatorService),
                    new NetTcpBinding(), string.Empty);

                // Create an announcement endpoint, which points to the Announcement Endpoint hosted by the proxy service.
                AnnouncementEndpoint announcementEndpoint = new AnnouncementEndpoint(new NetTcpBinding(),
                    new EndpointAddress(announcementEndpointAddress));

                ServiceDiscoveryBehavior serviceDiscoveryBehavior = new ServiceDiscoveryBehavior();
                serviceDiscoveryBehavior.AnnouncementEndpoints.Add(announcementEndpoint);

                // Make the service discoverable
                serviceHost.Description.Behaviors.Add(serviceDiscoveryBehavior);

                serviceHost.Open();

                Console.WriteLine("Calculator Service started at {0}", baseAddress);
                Console.WriteLine();
                Console.WriteLine("Press <ENTER> to terminate the service.");
                Console.WriteLine();
                Console.ReadLine();

                serviceHost.Close();
            }
            catch (CommunicationException e)
            {
                Console.WriteLine(e.Message);
            }
            catch (TimeoutException e)
            {
                Console.WriteLine(e.Message);
            }

            if (serviceHost.State != CommunicationState.Closed)
            {
                Console.WriteLine("Aborting the service...");
                serviceHost.Abort();
            }
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="da1e6-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="da1e6-123">See also</span></span>

- [<span data-ttu-id="da1e6-124">WCF Discovery</span><span class="sxs-lookup"><span data-stu-id="da1e6-124">WCF Discovery</span></span>](wcf-discovery.md)
- [<span data-ttu-id="da1e6-125">如何：实现发现代理</span><span class="sxs-lookup"><span data-stu-id="da1e6-125">How to: Implement a Discovery Proxy</span></span>](how-to-implement-a-discovery-proxy.md)
- [<span data-ttu-id="da1e6-126">如何：实现使用发现代理查找服务的客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="da1e6-126">How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service</span></span>](client-app-discovery-proxy-to-find-a-service.md)
