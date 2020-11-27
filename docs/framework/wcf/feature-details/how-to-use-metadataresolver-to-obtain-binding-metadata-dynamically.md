---
title: 如何：使用 MetadataResolver 动态获取绑定元数据
ms.date: 03/30/2017
ms.assetid: 56ffcb99-fff0-4479-aca0-e3909009f605
ms.openlocfilehash: fc64e11271c6901a8d4598c0efa563a06a92decf
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280710"
---
# <a name="how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically"></a><span data-ttu-id="bdeb8-102">如何：使用 MetadataResolver 动态获取绑定元数据</span><span class="sxs-lookup"><span data-stu-id="bdeb8-102">How to: Use MetadataResolver to Obtain Binding Metadata Dynamically</span></span>

<span data-ttu-id="bdeb8-103">本主题演示如何使用 <xref:System.ServiceModel.Description.MetadataResolver> 类来动态获取绑定元数据。</span><span class="sxs-lookup"><span data-stu-id="bdeb8-103">This topic shows you how to use the <xref:System.ServiceModel.Description.MetadataResolver> class to dynamically obtain binding metadata.</span></span>  
  
### <a name="to-dynamically-obtain-binding-metadata"></a><span data-ttu-id="bdeb8-104">动态获取绑定元数据</span><span class="sxs-lookup"><span data-stu-id="bdeb8-104">To dynamically obtain binding metadata</span></span>  
  
1. <span data-ttu-id="bdeb8-105">使用元数据终结点的地址创建一个 <xref:System.ServiceModel.EndpointAddress> 对象。</span><span class="sxs-lookup"><span data-stu-id="bdeb8-105">Create an <xref:System.ServiceModel.EndpointAddress> object with the address of the metadata endpoint.</span></span>  
  
    ```csharp
    EndpointAddress metaAddress  
      = new EndpointAddress(new Uri("http://localhost:8080/SampleService/mex"));  
    ```  
  
2. <span data-ttu-id="bdeb8-106">调用 <xref:System.ServiceModel.Description.MetadataResolver.Resolve%28System.Type%2CSystem.ServiceModel.EndpointAddress%29>，它传入服务类型和元数据终结点地址。</span><span class="sxs-lookup"><span data-stu-id="bdeb8-106">Call <xref:System.ServiceModel.Description.MetadataResolver.Resolve%28System.Type%2CSystem.ServiceModel.EndpointAddress%29>, which passes in the service type and the metadata endpoint address.</span></span> <span data-ttu-id="bdeb8-107">这将返回实现了指定协定的终结点的集合。</span><span class="sxs-lookup"><span data-stu-id="bdeb8-107">This returns a collection of endpoints that implement the specified contract.</span></span> <span data-ttu-id="bdeb8-108">仅从元数据导入绑定信息；不导入协定信息。</span><span class="sxs-lookup"><span data-stu-id="bdeb8-108">Only binding information is imported from the metadata; contract information is not imported.</span></span> <span data-ttu-id="bdeb8-109">改用所提供的协定。</span><span class="sxs-lookup"><span data-stu-id="bdeb8-109">The supplied contract is used instead.</span></span>  
  
    ```csharp  
    ServiceEndpointCollection endpoints = MetadataResolver.Resolve(typeof(SampleServiceClient),metaAddress);  
    ```  
  
3. <span data-ttu-id="bdeb8-110">然后，可以遍历该服务终结点集合，以提取所需的绑定信息。</span><span class="sxs-lookup"><span data-stu-id="bdeb8-110">You can then iterate through the collection of service endpoints to extract the binding information you need.</span></span> <span data-ttu-id="bdeb8-111">下面的代码遍历终结点，创建一个服务客户端对象（该对象传入与当前终结点关联的绑定和地址），然后调用该服务上的一个方法。</span><span class="sxs-lookup"><span data-stu-id="bdeb8-111">The following code iterates through the endpoints, creates a service client object that passes in the binding and address associated with the current endpoint, and then calls a method on the service.</span></span>  
  
    ```csharp  
    foreach (ServiceEndpoint point in endpoints)  
    {  
       if (point != null)  
       {  
          // Create a new wcfClient using retrieved endpoints.  
          using (wcfClient = new SampleServiceClient(point.Binding, point.Address))  
          {  
             Console.WriteLine(  
               wcfClient.SampleMethod("Client used the "  
               + point.Address.ToString() + " address."));  
          }  
      }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="bdeb8-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bdeb8-112">See also</span></span>

- <span data-ttu-id="bdeb8-113">Metadata </span><span class="sxs-lookup"><span data-stu-id="bdeb8-113">[Metadata](metadata.md)</span></span>
