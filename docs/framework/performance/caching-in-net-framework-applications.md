---
title: .NET Framework 应用程序中的缓存
description: 在 .NET 应用程序中使用缓存。 了解如何缓存数据、在 ASP.NET 应用程序中缓存或 WCF REST 服务，以及如何在 .NET 中扩展缓存。
ms.date: 03/30/2017
helpviewer_keywords:
- ASP.NET caching
- caching [.NET Framework]
- caching [ASP.NET]
ms.assetid: c4b47ee0-4b82-4124-9bce-818088385e34
ms.openlocfilehash: 5518151c26c528095ec91116b53e82e22e23d25f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96235203"
---
# <a name="caching-in-net-framework-applications"></a><span data-ttu-id="deb21-104">.NET Framework 应用程序中的缓存</span><span class="sxs-lookup"><span data-stu-id="deb21-104">Caching in .NET Framework Applications</span></span>

<span data-ttu-id="deb21-105">缓存可以将数据存储在内存中以便快速访问。</span><span class="sxs-lookup"><span data-stu-id="deb21-105">Caching enables you to store data in memory for rapid access.</span></span> <span data-ttu-id="deb21-106">再次访问数据时，应用程序可以从缓存获取数据，而不是从原始源检索数据。</span><span class="sxs-lookup"><span data-stu-id="deb21-106">When the data is accessed again, applications can get the data from the cache instead of retrieving it from the original source.</span></span> <span data-ttu-id="deb21-107">这可改善性能和可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="deb21-107">This can improve performance and scalability.</span></span> <span data-ttu-id="deb21-108">此外，数据源暂时不可用时，缓存可提供数据。</span><span class="sxs-lookup"><span data-stu-id="deb21-108">In addition, caching makes data available when the data source is temporarily unavailable.</span></span>

 <span data-ttu-id="deb21-109">.NET Framework 提供了缓存功能，可提高 Windows 客户端和服务器应用程序（包括 ASP.NET）的性能和可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="deb21-109">The .NET Framework provides caching functionality that you can use to improve the performance and scalability of both Windows client and server applications, including ASP.NET.</span></span>

> [!NOTE]
> <span data-ttu-id="deb21-110">在 .NET Framework 3.5 及更早版本中，ASP.NET 提供了命名空间中的内存中缓存实现 <xref:System.Web.Caching> 。</span><span class="sxs-lookup"><span data-stu-id="deb21-110">In the .NET Framework 3.5 and earlier versions, ASP.NET provided an in-memory cache implementation in the <xref:System.Web.Caching> namespace.</span></span> <span data-ttu-id="deb21-111">在 .NET Framework 的以前版本中，仅在命名空间中提供缓存， <xref:System.Web> 因此需要依赖 ASP.NET 类。</span><span class="sxs-lookup"><span data-stu-id="deb21-111">In previous versions of the .NET Framework, caching was available only in the <xref:System.Web> namespace and therefore required a dependency on ASP.NET classes.</span></span> <span data-ttu-id="deb21-112">在 .NET Framework 4 中，<xref:System.Runtime.Caching> 命名空间包含为 Web 和非 Web 应用程序设计的 API。</span><span class="sxs-lookup"><span data-stu-id="deb21-112">In the .NET Framework 4, the <xref:System.Runtime.Caching> namespace contains APIs that are designed for both Web and non-Web applications.</span></span>

## <a name="caching-data"></a><span data-ttu-id="deb21-113">缓存数据</span><span class="sxs-lookup"><span data-stu-id="deb21-113">Caching Data</span></span>

 <span data-ttu-id="deb21-114">可使用 <xref:System.Runtime.Caching> 命名空间中的类来缓存信息。</span><span class="sxs-lookup"><span data-stu-id="deb21-114">You can cache information by using classes in the <xref:System.Runtime.Caching> namespace.</span></span> <span data-ttu-id="deb21-115">此命名空间中的缓存类提供下列功能：</span><span class="sxs-lookup"><span data-stu-id="deb21-115">The caching classes in this namespace provide the following features:</span></span>

- <span data-ttu-id="deb21-116">为创建自定义缓存实现提供基础的抽象类型。</span><span class="sxs-lookup"><span data-stu-id="deb21-116">Abstract types that provide the foundation for creating custom cache implementations.</span></span>

- <span data-ttu-id="deb21-117">具体的内存中对象缓存实现。</span><span class="sxs-lookup"><span data-stu-id="deb21-117">A concrete in-memory object cache implementation.</span></span>

 <span data-ttu-id="deb21-118">抽象基缓存类 (<xref:System.Runtime.Caching.ObjectCache>) 定义以下缓存任务：</span><span class="sxs-lookup"><span data-stu-id="deb21-118">The abstract base caching class (<xref:System.Runtime.Caching.ObjectCache>) defines the following caching tasks:</span></span>

- <span data-ttu-id="deb21-119">创建和管理缓存项。</span><span class="sxs-lookup"><span data-stu-id="deb21-119">Creating and managing cache entries.</span></span>

- <span data-ttu-id="deb21-120">指定过期和逐出信息。</span><span class="sxs-lookup"><span data-stu-id="deb21-120">Specifying expiration and eviction information.</span></span>

- <span data-ttu-id="deb21-121">触发响应缓存项更改而引发的事件。</span><span class="sxs-lookup"><span data-stu-id="deb21-121">Triggering events that are raised in response to changes in cache entries.</span></span>

 <span data-ttu-id="deb21-122"><xref:System.Runtime.Caching.MemoryCache> 类是 <xref:System.Runtime.Caching.ObjectCache> 类的内存中对象缓存实现。</span><span class="sxs-lookup"><span data-stu-id="deb21-122">The <xref:System.Runtime.Caching.MemoryCache> class is an in-memory object cache implementation of the <xref:System.Runtime.Caching.ObjectCache> class.</span></span> <span data-ttu-id="deb21-123"><xref:System.Runtime.Caching.MemoryCache> 类可用于大多数缓存任务。</span><span class="sxs-lookup"><span data-stu-id="deb21-123">You can use the <xref:System.Runtime.Caching.MemoryCache> class for most caching tasks.</span></span>

> [!NOTE]
> <span data-ttu-id="deb21-124"><xref:System.Runtime.Caching.MemoryCache> 类在 <xref:System.Web.Caching> 命名空间中定义的 ASP.NET 缓存对象中建模。</span><span class="sxs-lookup"><span data-stu-id="deb21-124">The <xref:System.Runtime.Caching.MemoryCache> class is modeled on the ASP.NET cache object that is defined in the <xref:System.Web.Caching> namespace.</span></span> <span data-ttu-id="deb21-125">因此，内部缓存逻辑与 ASP.NET 早期版本所提供的逻辑相似。</span><span class="sxs-lookup"><span data-stu-id="deb21-125">Therefore, the internal caching logic similar to the logic that was provided in earlier versions of ASP.NET.</span></span>

 <span data-ttu-id="deb21-126">有关如何在 WPF 应用程序中使用缓存的示例，请参阅[演练：在 WPF 应用程序中缓存应用程序数据](/dotnet/desktop/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application)。</span><span class="sxs-lookup"><span data-stu-id="deb21-126">For an example of how to use to caching in a WPF application, see [Walkthrough: Caching Application Data in a WPF Application](/dotnet/desktop/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application).</span></span>

## <a name="caching-in-aspnet-applications"></a><span data-ttu-id="deb21-127">在 ASP.NET 应用程序中进行缓存</span><span class="sxs-lookup"><span data-stu-id="deb21-127">Caching in ASP.NET Applications</span></span>

 <span data-ttu-id="deb21-128"><xref:System.Runtime.Caching> 命名空间中的缓存类提供在 ASP.NET 中缓存数据的功能。</span><span class="sxs-lookup"><span data-stu-id="deb21-128">The caching classes in the <xref:System.Runtime.Caching> namespace provide functionality for caching data in ASP.NET.</span></span>

> [!NOTE]
> <span data-ttu-id="deb21-129">如果你的应用程序以 .NET Framework 3.5 或更早版本为目标，则必须使用命名空间中定义的缓存类 <xref:System.Web.Caching> 。</span><span class="sxs-lookup"><span data-stu-id="deb21-129">If your application targets the .NET Framework 3.5 or earlier, you must use the caching classes that are defined in the <xref:System.Web.Caching> namespace.</span></span> <span data-ttu-id="deb21-130">有关详细信息，请参阅 [ASP.NET 缓存概述](/previous-versions/aspnet/ms178597(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="deb21-130">For more information, see [ASP.NET Caching Overview](/previous-versions/aspnet/ms178597(v=vs.100)).</span></span>

> [!NOTE]
> <span data-ttu-id="deb21-131">开发新应用程序时，建议使用 <xref:System.Runtime.Caching.MemoryCache> 类。</span><span class="sxs-lookup"><span data-stu-id="deb21-131">When you develop new applications, we recommend that you use the <xref:System.Runtime.Caching.MemoryCache> class.</span></span> <span data-ttu-id="deb21-132"><xref:System.Runtime.Caching> 命名空间中提供的 API 与 <xref:System.Web.Caching.Cache> 命名空间中提供的 API 类似。</span><span class="sxs-lookup"><span data-stu-id="deb21-132">The API that is provided in the <xref:System.Runtime.Caching> namespace is like the API that is provided in the <xref:System.Web.Caching.Cache> namespace.</span></span> <span data-ttu-id="deb21-133">因此，如果你已在 ASP.NET 早期版本中使用过缓存，那么将会对 API 感到熟悉。</span><span class="sxs-lookup"><span data-stu-id="deb21-133">Therefore, the API will be familiar if you used caching in earlier versions of ASP.NET.</span></span> <span data-ttu-id="deb21-134">有关如何在 ASP.NET 应用程序中使用缓存的示例，请参阅[演练：在 ASP.NET 中缓存应用程序数据](/previous-versions/ff477235(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="deb21-134">For an example of how to use caching in ASP.NET applications, see [Walkthrough: Caching Application Data in ASP.NET](/previous-versions/ff477235(v=vs.100)).</span></span>

### <a name="output-caching"></a><span data-ttu-id="deb21-135">输出缓存</span><span class="sxs-lookup"><span data-stu-id="deb21-135">Output Caching</span></span>

 <span data-ttu-id="deb21-136">若要手动缓存应用程序数据，可使用 ASP.NET 中的 <xref:System.Runtime.Caching.MemoryCache> 类。</span><span class="sxs-lookup"><span data-stu-id="deb21-136">To manually cache application data, you can use the <xref:System.Runtime.Caching.MemoryCache> class in ASP.NET.</span></span> <span data-ttu-id="deb21-137">ASP.NET 还支持输出缓存，在内存中存储生成的页面输出、控件和 HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="deb21-137">ASP.NET also supports output caching, which stores the generated output of pages, controls, and HTTP responses in memory.</span></span> <span data-ttu-id="deb21-138">可在 ASP.NET Web 页中通过声明方式或使用 Web.config 文件中的设置，配置输出缓存。</span><span class="sxs-lookup"><span data-stu-id="deb21-138">You can configure output caching declaratively in an ASP.NET Web page or by using settings in the Web.config file.</span></span> <span data-ttu-id="deb21-139">有关详细信息，请参阅[用于缓存的 outputCache 元素（ASP.NET 设置架构）](/previous-versions/dotnet/netframework-4.0/ms228124(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="deb21-139">For more information, see [outputCache Element for caching (ASP.NET Settings Schema)](/previous-versions/dotnet/netframework-4.0/ms228124(v=vs.100)).</span></span>

 <span data-ttu-id="deb21-140">借助 ASP.NET，可通过创建自定义输出缓存提供程序扩展输出缓存。</span><span class="sxs-lookup"><span data-stu-id="deb21-140">ASP.NET lets you extend output caching by creating custom output-cache providers.</span></span> <span data-ttu-id="deb21-141">通过自定义提供程序，可使用磁盘、云存储和分布式缓存引擎等其他存储设备，存储缓存内容。</span><span class="sxs-lookup"><span data-stu-id="deb21-141">By using custom providers, you can store cached content using other storage devices such as disks, cloud storage, and distributed cache engines.</span></span> <span data-ttu-id="deb21-142">若要创建自定义输出缓存提供程序，可创建 <xref:System.Web.Caching.OutputCacheProvider> 类的派生类，并将应用程序配置为使用自定义输出缓存提供程序。</span><span class="sxs-lookup"><span data-stu-id="deb21-142">To create a custom output cache provider, you create a class that derives from the <xref:System.Web.Caching.OutputCacheProvider> class and configure the application to use the custom output cache provider.</span></span>

## <a name="caching-in-wcf-rest-services"></a><span data-ttu-id="deb21-143">在 WCF REST 服务中进行缓存</span><span class="sxs-lookup"><span data-stu-id="deb21-143">Caching in WCF REST Services</span></span>

 <span data-ttu-id="deb21-144">对于 WCF REST 服务，.NET Framework 可充分利用 ASP.NET 中提供的声明性输出缓存。</span><span class="sxs-lookup"><span data-stu-id="deb21-144">For WCF REST services, the .NET Framework enables you to take advantage of the declarative output caching that is available in ASP.NET.</span></span> <span data-ttu-id="deb21-145">这便可以缓存来自 WCF REST 服务操作的响应。</span><span class="sxs-lookup"><span data-stu-id="deb21-145">This enables you to cache responses from your WCF REST service operations.</span></span> <span data-ttu-id="deb21-146">如果用户向配置为进行缓存的服务发送了 HTTP GET 请求，那么 ASP.NET 将返回已缓存响应，且不会调用服务方法。</span><span class="sxs-lookup"><span data-stu-id="deb21-146">When a user sends an HTTP GET request to a service that is configured for caching, ASP.NET sends back the cached response, and the service method is not called.</span></span> <span data-ttu-id="deb21-147">缓存过期后，下次用户发送 HTTP GET 请求时，将会调用服务方法且再次缓存响应。</span><span class="sxs-lookup"><span data-stu-id="deb21-147">After the cache expires, the next time that a user sends an HTTP GET request, your service method is called and the response is again cached.</span></span>

 <span data-ttu-id="deb21-148">.NET Framework 还可实现条件 HTTP GET 缓存。</span><span class="sxs-lookup"><span data-stu-id="deb21-148">The .NET Framework also enables you to implement conditional HTTP GET caching.</span></span> <span data-ttu-id="deb21-149">在 REST 方案中，条件 HTTP GET 请求通常由服务用来实现智能 HTTP 缓存，如 [HTTP 规范](https://www.w3.org/Protocols/rfc2616/rfc2616.html)中所述。</span><span class="sxs-lookup"><span data-stu-id="deb21-149">In REST scenarios, a conditional HTTP GET request is often used by services to implement intelligent HTTP caching as described in the [HTTP Specification](https://www.w3.org/Protocols/rfc2616/rfc2616.html).</span></span> <span data-ttu-id="deb21-150">有关详细信息，请参阅 [Caching Support for WCF Web HTTP Services](../wcf/feature-details/caching-support-for-wcf-web-http-services.md)（对 WCF Web HTTP 服务的缓存支持）。</span><span class="sxs-lookup"><span data-stu-id="deb21-150">For more information, see [Caching Support for WCF Web HTTP Services](../wcf/feature-details/caching-support-for-wcf-web-http-services.md).</span></span>

## <a name="extending-caching-in-the-net-framework"></a><span data-ttu-id="deb21-151">在 .NET Framework 中扩展缓存</span><span class="sxs-lookup"><span data-stu-id="deb21-151">Extending Caching in the .NET Framework</span></span>

 <span data-ttu-id="deb21-152">.NET Framework 中的缓存设计为可扩展。</span><span class="sxs-lookup"><span data-stu-id="deb21-152">Caching in the .NET Framework is designed to be extensible.</span></span> <span data-ttu-id="deb21-153"><xref:System.Runtime.Caching.ObjectCache> 类能够创建自定义缓存实现。</span><span class="sxs-lookup"><span data-stu-id="deb21-153">The <xref:System.Runtime.Caching.ObjectCache> class enables you to create a custom cache implementation.</span></span> <span data-ttu-id="deb21-154">此类提供可用于所有托管应用程序（包括 Windows 窗体、Windows Presentation Foundation (WPF) 和 Windows Communications Foundation (WCF)）的成员。</span><span class="sxs-lookup"><span data-stu-id="deb21-154">This class provides members that are available to all managed applications, including Windows Forms, Windows Presentation Foundation (WPF), and Windows Communications Foundation (WCF).</span></span> <span data-ttu-id="deb21-155">若要创建使用不同存储机制的缓存类或希望精确地控制缓存操作，可能需要执行此操作。</span><span class="sxs-lookup"><span data-stu-id="deb21-155">You might do this in order to create a cache class that uses a different storage mechanism, or if you want granular control over cache operations.</span></span>

 <span data-ttu-id="deb21-156">要扩展缓存可执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="deb21-156">To extend caching you can do the following:</span></span>

- <span data-ttu-id="deb21-157">创建一个派生自 <xref:System.Runtime.Caching.ObjectCache> 类的自定义类，然后在此派生类中提供自定义缓存实现。</span><span class="sxs-lookup"><span data-stu-id="deb21-157">Create a custom class that derives from the <xref:System.Runtime.Caching.ObjectCache> class and then provide a custom cache implementation in the derived class.</span></span>

- <span data-ttu-id="deb21-158">创建一个派生自 <xref:System.Runtime.Caching.MemoryCache> 类的类，并自定义或扩展此派生类。</span><span class="sxs-lookup"><span data-stu-id="deb21-158">Create a class that derives from <xref:System.Runtime.Caching.MemoryCache> class and customize or extend the derived class.</span></span> <span data-ttu-id="deb21-159">有关如何执行此操作的示例，请参阅[在 ASP.NET 应用程序中使用多个缓存对象来缓存应用程序数据](/archive/blogs/aspnetue/caching-application-data-by-using-multiple-cache-objects-in-an-asp-net-application)。</span><span class="sxs-lookup"><span data-stu-id="deb21-159">For an example of how to do this, see [Caching Application Data by Using Multiple Cache Objects in an ASP.NET Application](/archive/blogs/aspnetue/caching-application-data-by-using-multiple-cache-objects-in-an-asp-net-application).</span></span>

- <span data-ttu-id="deb21-160">创建 <xref:System.Web.Caching.OutputCacheProvider> 类的派生类，并配置应用程序以使用自定义输出缓存提供程序。</span><span class="sxs-lookup"><span data-stu-id="deb21-160">Create a class that derives from the <xref:System.Web.Caching.OutputCacheProvider> class and configure the application to use the custom output cache provider.</span></span>

 <span data-ttu-id="deb21-161">有关详细信息，请参阅 Scott Guthrie 的博客上的进入 [可扩展输出缓存，其中包含 ASP.NET 4 (VS 2010 和 .NET Framework 4.0 系列) ](https://weblogs.asp.net/scottgu/extensible-output-caching-with-asp-net-4-vs-2010-and-net-4-0-series) 。</span><span class="sxs-lookup"><span data-stu-id="deb21-161">For more information, see the entry [Extensible Output Caching with ASP.NET 4 (VS 2010 and .NET Framework 4.0 Series)](https://weblogs.asp.net/scottgu/extensible-output-caching-with-asp-net-4-vs-2010-and-net-4-0-series) on Scott Guthrie's blog.</span></span>

## <a name="see-also"></a><span data-ttu-id="deb21-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="deb21-162">See also</span></span>

- <xref:System.Runtime.Caching.ObjectCache>
- <xref:System.Runtime.Caching.MemoryCache>
- [<span data-ttu-id="deb21-163">演练：在 WPF 应用程序中缓存应用程序数据</span><span class="sxs-lookup"><span data-stu-id="deb21-163">Walkthrough: Caching Application Data in a WPF Application</span></span>](/dotnet/desktop/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application)
- <span data-ttu-id="deb21-164">[演练：在 ASP.NET 中缓存应用程序数据](/previous-versions/ff477235(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="deb21-164">[Walkthrough: Caching Application Data in ASP.NET](/previous-versions/ff477235(v=vs.100))</span></span>
