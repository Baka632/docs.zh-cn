---
title: 从 WebResponse 派生
ms.date: 03/30/2017
helpviewer_keywords:
- Deriving from WebResponse
ms.assetid: f11d4866-a199-4087-9306-a5a4c18b13db
ms.openlocfilehash: 793533b632952df3f0866bb6377efd0e313cd007
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96287522"
---
# <a name="deriving-from-webresponse"></a><span data-ttu-id="45d2c-102">从 WebResponse 派生</span><span class="sxs-lookup"><span data-stu-id="45d2c-102">Deriving from WebResponse</span></span>

<span data-ttu-id="45d2c-103"><xref:System.Net.WebResponse> 类是一个抽象基类，可为创建适合 .NET Framework 可插入协议模型的协议特定的响应提供基本方法和属性。</span><span class="sxs-lookup"><span data-stu-id="45d2c-103">The <xref:System.Net.WebResponse> class is an abstract base class that provides the basic methods and properties for creating a protocol-specific response that fits the .NET Framework pluggable protocol model.</span></span> <span data-ttu-id="45d2c-104">使用 <xref:System.Net.WebRequest> 类从资源请求数据的应用程序会在 WebResponse 中接收响应  。</span><span class="sxs-lookup"><span data-stu-id="45d2c-104">Applications that use the <xref:System.Net.WebRequest> class to request data from resources receive the responses in a **WebResponse**.</span></span> <span data-ttu-id="45d2c-105">协议特定的 WebResponse 后代必须实现 WebResponse 类的抽象成员   。</span><span class="sxs-lookup"><span data-stu-id="45d2c-105">Protocol-specific **WebResponse** descendants must implement the abstract members of the **WebResponse** class.</span></span>  
  
 <span data-ttu-id="45d2c-106">关联的 WebRequest 类必须创建 WebResponse 后代   。</span><span class="sxs-lookup"><span data-stu-id="45d2c-106">The associated **WebRequest** class must create **WebResponse** descendants.</span></span> <span data-ttu-id="45d2c-107">例如，<xref:System.Net.HttpWebResponse> 实例仅作为调用 <xref:System.Net.HttpWebRequest.GetResponse%2A?displayProperty=nameWithType> 或 <xref:System.Net.HttpWebRequest.EndGetResponse%2A?displayProperty=nameWithType> 的结果而创建。</span><span class="sxs-lookup"><span data-stu-id="45d2c-107">For example, <xref:System.Net.HttpWebResponse> instances are created only as the result of calling <xref:System.Net.HttpWebRequest.GetResponse%2A?displayProperty=nameWithType> or <xref:System.Net.HttpWebRequest.EndGetResponse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="45d2c-108">每个 WebResponse 都包含对资源的请求结果，不可重复使用  。</span><span class="sxs-lookup"><span data-stu-id="45d2c-108">Each **WebResponse** contains the result of a request to a resource and is not intended to be reused.</span></span>  
  
## <a name="contentlength-property"></a><span data-ttu-id="45d2c-109">ContentLength 属性</span><span class="sxs-lookup"><span data-stu-id="45d2c-109">ContentLength Property</span></span>  

 <span data-ttu-id="45d2c-110"><xref:System.Net.WebResponse.ContentLength%2A> 属性表示从 <xref:System.Net.WebResponse.GetResponseStream%2A> 方法返回的流中可用的数据字节数。</span><span class="sxs-lookup"><span data-stu-id="45d2c-110">The <xref:System.Net.WebResponse.ContentLength%2A> property indicates the number of bytes of data that are available from the stream returned by the <xref:System.Net.WebResponse.GetResponseStream%2A> method.</span></span> <span data-ttu-id="45d2c-111">ContentLength 属性不表示服务器返回的标头或元数据信息的字节数，仅表示所请求资源本身的数据字节数  。</span><span class="sxs-lookup"><span data-stu-id="45d2c-111">The **ContentLength** property does not indicate the number of bytes of header or metadata information returned by the server; it indicates only the number of bytes of data in the requested resource itself.</span></span>  
  
## <a name="contenttype-property"></a><span data-ttu-id="45d2c-112">ContentType 属性</span><span class="sxs-lookup"><span data-stu-id="45d2c-112">ContentType Property</span></span>  

 <span data-ttu-id="45d2c-113"><xref:System.Net.WebResponse.ContentType%2A> 属性提供协议要求用户发送至客户端的所有特殊信息，以确定服务器发送的内容的类型。</span><span class="sxs-lookup"><span data-stu-id="45d2c-113">The <xref:System.Net.WebResponse.ContentType%2A> property provides any special information that your protocol requires you to send to the client to identify the type of content being sent by the server.</span></span> <span data-ttu-id="45d2c-114">这通常是所有返回数据的 MIME 内容类型。</span><span class="sxs-lookup"><span data-stu-id="45d2c-114">Typically this is the MIME content type of any data returned.</span></span>  
  
## <a name="headers-property"></a><span data-ttu-id="45d2c-115">Headers 属性</span><span class="sxs-lookup"><span data-stu-id="45d2c-115">Headers Property</span></span>  

 <span data-ttu-id="45d2c-116"><xref:System.Net.WebResponse.Headers%2A> 属性包含与响应相关联的元数据名称/值对的任意集合。</span><span class="sxs-lookup"><span data-stu-id="45d2c-116">The <xref:System.Net.WebResponse.Headers%2A> property contains an arbitrary collection of name/value pairs of metadata associated with the response.</span></span> <span data-ttu-id="45d2c-117">协议所需的任何可表示为名称/值对的元数据都可以包含在 Headers 属性中  。</span><span class="sxs-lookup"><span data-stu-id="45d2c-117">Any metadata needed by the protocol that can be expressed as a name/value pair can be included in the **Headers** property.</span></span>  
  
 <span data-ttu-id="45d2c-118">用户无需使用 Headers 属性即可使用标头元数据  。</span><span class="sxs-lookup"><span data-stu-id="45d2c-118">You are not required to use the **Headers** property to use header metadata.</span></span> <span data-ttu-id="45d2c-119">协议特定的元数据可作为属性公开，例如，<xref:System.Net.HttpWebResponse.LastModified%2A?displayProperty=nameWithType> 属性公开了 Last-Modified HTTP 标头  。</span><span class="sxs-lookup"><span data-stu-id="45d2c-119">Protocol-specific metadata can be exposed as properties; for example, the <xref:System.Net.HttpWebResponse.LastModified%2A?displayProperty=nameWithType> property exposes the **Last-Modified** HTTP header.</span></span> <span data-ttu-id="45d2c-120">将标头元数据作为属性公开时，应禁止使用 Headers 属性设置相同的属性  。</span><span class="sxs-lookup"><span data-stu-id="45d2c-120">When you expose header metadata as a property, you should not allow the same property to be set using the **Headers** property.</span></span>  
  
## <a name="responseuri-property"></a><span data-ttu-id="45d2c-121">ResponseUri 属性</span><span class="sxs-lookup"><span data-stu-id="45d2c-121">ResponseUri Property</span></span>  

 <span data-ttu-id="45d2c-122"><xref:System.Net.WebResponse.ResponseUri%2A> 属性包含实际提供响应的资源的 URI。</span><span class="sxs-lookup"><span data-stu-id="45d2c-122">The <xref:System.Net.WebResponse.ResponseUri%2A> property contains the URI of the resource that actually provided the response.</span></span> <span data-ttu-id="45d2c-123">对于不支持重定向的协议，ResponseUri 与创建响应的 WebRequest 的 <xref:System.Net.WebRequest.RequestUri%2A> 属性相同。</span><span class="sxs-lookup"><span data-stu-id="45d2c-123">For protocols that do not support redirection, **ResponseUri** will be the same as the <xref:System.Net.WebRequest.RequestUri%2A> property of the **WebRequest** that created the response.</span></span> <span data-ttu-id="45d2c-124">如果协议支持重定向请求，则 ResponseUri 将包含响应的 URI  。</span><span class="sxs-lookup"><span data-stu-id="45d2c-124">If the protocol supports redirecting the request, **ResponseUri** will contain the URI of the response.</span></span>  
  
## <a name="close-method"></a><span data-ttu-id="45d2c-125">Close 方法</span><span class="sxs-lookup"><span data-stu-id="45d2c-125">Close Method</span></span>  

 <span data-ttu-id="45d2c-126"><xref:System.Net.WebResponse.Close%2A> 方法关闭请求和响应进行的任何连接，并清除响应使用的资源。</span><span class="sxs-lookup"><span data-stu-id="45d2c-126">The <xref:System.Net.WebResponse.Close%2A> method closes any connections made by the request and response and cleans up resources used by the response.</span></span> <span data-ttu-id="45d2c-127">Close 方法关闭响应使用的所有流实例，但如果之前通过调用 <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> 方法关闭了响应流，也不会引发异常。</span><span class="sxs-lookup"><span data-stu-id="45d2c-127">The **Close** method closes any stream instances used by the response, but it does not throw an exception if the response stream was previously closed by a call to the <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="getresponsestream-method"></a><span data-ttu-id="45d2c-128">GetResponseStream 方法</span><span class="sxs-lookup"><span data-stu-id="45d2c-128">GetResponseStream Method</span></span>  

 <span data-ttu-id="45d2c-129"><xref:System.Net.WebResponse.GetResponseStream%2A> 方法返回的流中包含所请求资源的响应。</span><span class="sxs-lookup"><span data-stu-id="45d2c-129">The <xref:System.Net.WebResponse.GetResponseStream%2A> method returns a stream containing the response from the requested resource.</span></span> <span data-ttu-id="45d2c-130">响应流仅包含资源返回的数据，响应中包含的任何标头或元数据应从响应中删除，并通过协议特定的属性或 Headers 属性公开给应用程序  。</span><span class="sxs-lookup"><span data-stu-id="45d2c-130">The response stream contains only the data returned by the resource; any header or metadata included in the response should be stripped from the response and exposed to the application through protocol-specific properties or the **Headers** property.</span></span>  
  
 <span data-ttu-id="45d2c-131">GetResponseStream 方法返回的流实例为应用程序所有，无需关闭 WebResponse 即可将其关闭   。</span><span class="sxs-lookup"><span data-stu-id="45d2c-131">The stream instance returned by the **GetResponseStream** method is owned by the application and can be closed without closing the **WebResponse**.</span></span> <span data-ttu-id="45d2c-132">按照惯例，调用 WebResponse.Close 方法也会关闭 GetResponse 返回的流   。</span><span class="sxs-lookup"><span data-stu-id="45d2c-132">By convention, calling the **WebResponse.Close** method also closes the stream returned by **GetResponse**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45d2c-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="45d2c-133">See also</span></span>

- <xref:System.Net.WebResponse>
- <xref:System.Net.HttpWebResponse>
- <xref:System.Net.FileWebResponse>
- [<span data-ttu-id="45d2c-134">对可插入协议进行编程</span><span class="sxs-lookup"><span data-stu-id="45d2c-134">Programming Pluggable Protocols</span></span>](programming-pluggable-protocols.md)
- [<span data-ttu-id="45d2c-135">从 WebRequest 派生</span><span class="sxs-lookup"><span data-stu-id="45d2c-135">Deriving from WebRequest</span></span>](deriving-from-webrequest.md)
