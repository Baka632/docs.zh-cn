---
title: UriTemplate 表调度程序示例
ms.date: 03/30/2017
ms.assetid: 3b32975d-ba90-4c5c-83bc-2fbb48f11c0c
ms.openlocfilehash: 57489264de62b6adbca1c98230a0f90735b3918a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294945"
---
# <a name="uritemplate-table-dispatcher-sample"></a><span data-ttu-id="0e409-102">UriTemplate 表调度程序示例</span><span class="sxs-lookup"><span data-stu-id="0e409-102">UriTemplate Table Dispatcher Sample</span></span>

<span data-ttu-id="0e409-103"><xref:System.UriTemplateTable> 类提供了一个类似字典的关联表结构，该结构可用来处理一组 <xref:System.UriTemplate> 实例。</span><span class="sxs-lookup"><span data-stu-id="0e409-103">The <xref:System.UriTemplateTable> class provides a dictionary-like associative table structure for working with a set of <xref:System.UriTemplate> instances.</span></span> <span data-ttu-id="0e409-104">此示例演示使用 `UriTemplateTable` 生成的基本调度引擎，这是 `UriTemplateTable` 类的常见使用方案。</span><span class="sxs-lookup"><span data-stu-id="0e409-104">This sample demonstrates a basic dispatching engine built using `UriTemplateTable`, a common usage scenario for the `UriTemplateTable` class.</span></span>  
  
 <span data-ttu-id="0e409-105">此示例演示 `UriTemplateTable` 类的以下关键概念：</span><span class="sxs-lookup"><span data-stu-id="0e409-105">This sample demonstrates the following key concepts for the `UriTemplateTable` class:</span></span>  
  
- <span data-ttu-id="0e409-106">将委托与 `UriTemplates` 中的 `UriTemplateTable` 关联。</span><span class="sxs-lookup"><span data-stu-id="0e409-106">Associating delegates with `UriTemplates` in a `UriTemplateTable`.</span></span>  
  
- <span data-ttu-id="0e409-107">使用 <xref:System.UriTemplateTable.MatchSingle%2A> 获取特定 URI 的正确处理程序委托。</span><span class="sxs-lookup"><span data-stu-id="0e409-107">Using <xref:System.UriTemplateTable.MatchSingle%2A> to obtain the correct handler delegate for a particular URI.</span></span>  
  
- <span data-ttu-id="0e409-108">调用处理程序委托以处理请求。</span><span class="sxs-lookup"><span data-stu-id="0e409-108">Invoking the handler delegate to process the request.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0e409-109">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="0e409-109">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="0e409-110">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="0e409-110">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="0e409-111">若要以单机配置或跨计算机配置来运行示例，请按照 [运行 Windows Communication Foundation 示例](running-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="0e409-111">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="0e409-112">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="0e409-112">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0e409-113">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="0e409-113">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="0e409-114">如果此目录不存在，请参阅[Windows Communication Foundation (wcf) ，并 Windows Workflow Foundation (的 WF](https://www.microsoft.com/download/details.aspx?id=21459)) .NET Framework Windows Communication Foundation ([!INCLUDE[wf1](../../../../includes/wf1-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e409-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0e409-115">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="0e409-115">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplateDispatcher`  
  
## <a name="see-also"></a><span data-ttu-id="0e409-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0e409-116">See also</span></span>

- [<span data-ttu-id="0e409-117">UriTemplate 表</span><span class="sxs-lookup"><span data-stu-id="0e409-117">UriTemplate Table</span></span>](uritemplate-table-sample.md)
- [<span data-ttu-id="0e409-118">UriTemplate</span><span class="sxs-lookup"><span data-stu-id="0e409-118">UriTemplate</span></span>](uritemplate-sample.md)
