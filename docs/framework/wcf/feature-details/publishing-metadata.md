---
title: 发布元数据
description: 了解 WCF 服务如何通过发布一个或多个元数据终结点来发布元数据，从而使元数据可通过标准协议使用。
ms.date: 03/30/2017
helpviewer_keywords:
- metadata [WCF], publishing
ms.assetid: 3a56831a-cabc-45c0-bd02-12e2e9bd7313
ms.openlocfilehash: 3ea2377870a37e7dee6f4253503d70167d021a0d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244725"
---
# <a name="publishing-metadata"></a><span data-ttu-id="8f6b1-103">发布元数据</span><span class="sxs-lookup"><span data-stu-id="8f6b1-103">Publishing Metadata</span></span>

<span data-ttu-id="8f6b1-104">Windows Communication Foundation (WCF) 服务通过发布一个或多个元数据终结点来发布元数据。</span><span class="sxs-lookup"><span data-stu-id="8f6b1-104">Windows Communication Foundation (WCF) services publish metadata by publishing one or more metadata endpoints.</span></span> <span data-ttu-id="8f6b1-105">发布服务元数据之后，可以通过标准协议（如 WS-MetadataExchange (MEX) 和 HTTP/GET 请求）来使用该元数据。</span><span class="sxs-lookup"><span data-stu-id="8f6b1-105">Publishing service metadata makes the metadata available using standardized protocols, such as WS-MetadataExchange (MEX) and HTTP/GET requests.</span></span> <span data-ttu-id="8f6b1-106">元数据终结点类似于其他服务终结点，因为它们都有一个地址、一个绑定和一个协定，并且它们都可通过配置或命令代码添加到服务主机。</span><span class="sxs-lookup"><span data-stu-id="8f6b1-106">Metadata endpoints are similar to other service endpoints in that they have an address, a binding, and a contract, and they can be added to a service host through configuration or imperative code.</span></span>  
  
## <a name="publishing-metadata-endpoints"></a><span data-ttu-id="8f6b1-107">发布元数据终结点</span><span class="sxs-lookup"><span data-stu-id="8f6b1-107">Publishing Metadata Endpoints</span></span>  

 <span data-ttu-id="8f6b1-108">若要发布 WCF 服务的元数据终结点，你必须首先将 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 服务行为添加到服务。</span><span class="sxs-lookup"><span data-stu-id="8f6b1-108">To publish metadata endpoints for a WCF service, you first must add the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> service behavior to the service.</span></span> <span data-ttu-id="8f6b1-109">添加一个 <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> 实例将允许服务公开元数据终结点。</span><span class="sxs-lookup"><span data-stu-id="8f6b1-109">Adding a <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> instance allows your service to expose metadata endpoints.</span></span> <span data-ttu-id="8f6b1-110">添加 <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> 服务行为之后，就可以公开支持 MEX 协议或响应 HTTP/GET 请求的元数据终结点。</span><span class="sxs-lookup"><span data-stu-id="8f6b1-110">Once you add the <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> service behavior, you can then expose metadata endpoints that support the MEX protocol or that respond to HTTP/GET requests.</span></span>  
  
 <span data-ttu-id="8f6b1-111"><xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> 使用 <xref:System.ServiceModel.Description.WsdlExporter> 来导出服务中所有服务终结点的元数据。</span><span class="sxs-lookup"><span data-stu-id="8f6b1-111">The <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> uses a <xref:System.ServiceModel.Description.WsdlExporter> to export metadata for all service endpoints in your service.</span></span> <span data-ttu-id="8f6b1-112">有关从服务中导出元数据的详细信息，请参阅 [导出和导入元数据](exporting-and-importing-metadata.md)。</span><span class="sxs-lookup"><span data-stu-id="8f6b1-112">For more information about exporting metadata from a service, see [Exporting and Importing Metadata](exporting-and-importing-metadata.md).</span></span>  
  
 <span data-ttu-id="8f6b1-113"><xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> 添加一个 <xref:System.ServiceModel.Description.ServiceMetadataExtension> 实例作为服务主机的扩展。</span><span class="sxs-lookup"><span data-stu-id="8f6b1-113">The <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> adds a <xref:System.ServiceModel.Description.ServiceMetadataExtension> instance as an extension to your service host.</span></span> <span data-ttu-id="8f6b1-114"><xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> 提供了元数据发布协议的实现。</span><span class="sxs-lookup"><span data-stu-id="8f6b1-114">The <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> provides the implementation for the metadata publishing protocols.</span></span> <span data-ttu-id="8f6b1-115">还可以使用 <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> 通过访问 <xref:System.ServiceModel.Description.ServiceMetadataExtension.Metadata%2A?displayProperty=nameWithType> 属性来在运行时获取服务的元数据。</span><span class="sxs-lookup"><span data-stu-id="8f6b1-115">You can also use the <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> to get the service's metadata at runtime by accessing the <xref:System.ServiceModel.Description.ServiceMetadataExtension.Metadata%2A?displayProperty=nameWithType> property.</span></span>  
  
### <a name="mex-metadata-endpoints"></a><span data-ttu-id="8f6b1-116">MEX 元数据终结点</span><span class="sxs-lookup"><span data-stu-id="8f6b1-116">MEX Metadata Endpoints</span></span>  

 <span data-ttu-id="8f6b1-117">要添加使用 MEX 协议的元数据终结点，请将服务终结点添加到使用 `IMetadataExchange` 服务协定的服务主机。</span><span class="sxs-lookup"><span data-stu-id="8f6b1-117">To add metadata endpoints that use the MEX protocol, add service endpoints to your service host that use the `IMetadataExchange` service contract.</span></span> <span data-ttu-id="8f6b1-118">WCF 包含一个 <xref:System.ServiceModel.Description.IMetadataExchange> 接口，该接口具有此服务协定名称，你可以将其用作 WCF 编程模型的一部分。</span><span class="sxs-lookup"><span data-stu-id="8f6b1-118">WCF includes an <xref:System.ServiceModel.Description.IMetadataExchange> interface with this service contract name that you can use as part of the WCF programming model.</span></span> <span data-ttu-id="8f6b1-119">WS-MetadataExchange 终结点或 MEX 终结点，可以使用静态工厂方法在类上公开的四个默认绑定之一， <xref:System.ServiceModel.Description.MetadataExchangeBindings> 以匹配 WCF 工具（如 Svcutil.exe）所使用的默认绑定。</span><span class="sxs-lookup"><span data-stu-id="8f6b1-119">WS-MetadataExchange endpoints, or MEX endpoints, can use one of the four default bindings that the static factory methods expose on the <xref:System.ServiceModel.Description.MetadataExchangeBindings> class to match the default bindings used by WCF tools such as Svcutil.exe.</span></span> <span data-ttu-id="8f6b1-120">还可以使用自己的自定义绑定来配置 MEX 元数据终结点。</span><span class="sxs-lookup"><span data-stu-id="8f6b1-120">You can also configure MEX metadata endpoints using your own custom binding.</span></span>  
  
### <a name="http-get-metadata-endpoints"></a><span data-ttu-id="8f6b1-121">HTTP GET 元数据终结点</span><span class="sxs-lookup"><span data-stu-id="8f6b1-121">HTTP GET Metadata Endpoints</span></span>  

 <span data-ttu-id="8f6b1-122">若要将元数据终结点添加到响应 HTTP/GET 请求的服务，请将 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> 的 <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="8f6b1-122">To add a metadata endpoint to your service that responds to HTTP/GET requests, set the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> property on the <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> to `true`.</span></span> <span data-ttu-id="8f6b1-123">将 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> 的 <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> 属性设置为 `true` 还可以配置使用 HTTPS 的元数据终结点。</span><span class="sxs-lookup"><span data-stu-id="8f6b1-123">You can also configure a metadata endpoint that uses HTTPS by setting the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> property on the <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> to `true`.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8f6b1-124">本节内容</span><span class="sxs-lookup"><span data-stu-id="8f6b1-124">In This Section</span></span>  

 [<span data-ttu-id="8f6b1-125">如何：使用配置文件发布服务的元数据</span><span class="sxs-lookup"><span data-stu-id="8f6b1-125">How to: Publish Metadata for a Service Using a Configuration File</span></span>](how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 <span data-ttu-id="8f6b1-126">演示如何将 WCF 服务配置为发布元数据，以便客户端可以使用 WS-MetadataExchange 或使用查询字符串的 HTTP/GET 请求检索元数据 `?wsdl` 。</span><span class="sxs-lookup"><span data-stu-id="8f6b1-126">Demonstrates how to configure a WCF service to publish metadata so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
 [<span data-ttu-id="8f6b1-127">如何：使用代码发布服务的元数据</span><span class="sxs-lookup"><span data-stu-id="8f6b1-127">How to: Publish Metadata for a Service Using Code</span></span>](how-to-publish-metadata-for-a-service-using-code.md)  
 <span data-ttu-id="8f6b1-128">演示如何在代码中为 WCF 服务启用元数据发布，以便客户端可以使用 WS-MetadataExchange 或使用查询字符串的 HTTP/GET 请求来检索元数据 `?wsdl` 。</span><span class="sxs-lookup"><span data-stu-id="8f6b1-128">Demonstrates how to enable metadata publishing for a WCF service in code so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="8f6b1-129">参考</span><span class="sxs-lookup"><span data-stu-id="8f6b1-129">Reference</span></span>  

 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>  
  
 <xref:System.ServiceModel.Description.IMetadataExchange>  
  
 <xref:System.ServiceModel.Description.ServiceMetadataExtension>  
  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings>  
  
## <a name="see-also"></a><span data-ttu-id="8f6b1-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="8f6b1-130">See also</span></span>

- [<span data-ttu-id="8f6b1-131">导出和导入元数据</span><span class="sxs-lookup"><span data-stu-id="8f6b1-131">Exporting and Importing Metadata</span></span>](exporting-and-importing-metadata.md)
