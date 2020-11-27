---
title: UriTemplate 表示例
ms.date: 03/30/2017
ms.assetid: 5dd1d38f-1989-4c64-820d-821f5a02216a
ms.openlocfilehash: caa8e2aab82283b8ca41dd650cd299485d922305
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294932"
---
# <a name="uritemplate-table-sample"></a><span data-ttu-id="8ca26-102">UriTemplate 表示例</span><span class="sxs-lookup"><span data-stu-id="8ca26-102">UriTemplate Table Sample</span></span>

<span data-ttu-id="8ca26-103"><xref:System.UriTemplateTable> 类提供了一个类似字典的关联表结构，该结构可用来处理一组 `UriTemplate` 实例。</span><span class="sxs-lookup"><span data-stu-id="8ca26-103">The <xref:System.UriTemplateTable> class provides a dictionary-like associative table structure for working with a set of `UriTemplate` instances.</span></span> <span data-ttu-id="8ca26-104">可以按照该表中的所有模板来高效地匹配特定统一资源标识符 (URI)，并可以检索与匹配的模板相关联的数据。</span><span class="sxs-lookup"><span data-stu-id="8ca26-104">Specific Uniform Resource Identifiers (URIs) can be matched efficiently against all templates in the table, and data associated with the matched template can be retrieved.</span></span>  
  
 <span data-ttu-id="8ca26-105">此示例演示与 `UriTemplateTable` 类相关的以下关键概念：</span><span class="sxs-lookup"><span data-stu-id="8ca26-105">This sample demonstrates the following key concepts related to the `UriTemplateTable` class:</span></span>  
  
- <span data-ttu-id="8ca26-106">用来实例化 `UriTemplateTable` 的语法。</span><span class="sxs-lookup"><span data-stu-id="8ca26-106">Syntax for instantiating a `UriTemplateTable`.</span></span>  
  
- <span data-ttu-id="8ca26-107">用一组键/值对填充 `UriTemplateTable`。</span><span class="sxs-lookup"><span data-stu-id="8ca26-107">Populating a `UriTemplateTable` with a set of key/value pairs.</span></span>  
  
- <span data-ttu-id="8ca26-108">按照该表使用 <xref:System.UriTemplateTable.MatchSingle%2A> 来匹配候选 URI。</span><span class="sxs-lookup"><span data-stu-id="8ca26-108">Matching a candidate URI against the table using <xref:System.UriTemplateTable.MatchSingle%2A>.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8ca26-109">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="8ca26-109">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="8ca26-110">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="8ca26-110">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="8ca26-111">若要以单机配置或跨计算机配置来运行示例，请按照 [运行 Windows Communication Foundation 示例](running-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="8ca26-111">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="8ca26-112">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="8ca26-112">The samples may already be installed on your computer.</span></span> <span data-ttu-id="8ca26-113">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="8ca26-113">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="8ca26-114">如果此目录不存在，请参阅[Windows Communication Foundation (wcf) ，并 Windows Workflow Foundation (的 WF](https://www.microsoft.com/download/details.aspx?id=21459)) .NET Framework Windows Communication Foundation ([!INCLUDE[wf1](../../../../includes/wf1-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ca26-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8ca26-115">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="8ca26-115">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplateTable`  
  
## <a name="see-also"></a><span data-ttu-id="8ca26-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8ca26-116">See also</span></span>

- [<span data-ttu-id="8ca26-117">UriTemplate 表调度程序</span><span class="sxs-lookup"><span data-stu-id="8ca26-117">UriTemplate Table Dispatcher</span></span>](uritemplate-table-dispatcher-sample.md)
- [<span data-ttu-id="8ca26-118">UriTemplate</span><span class="sxs-lookup"><span data-stu-id="8ca26-118">UriTemplate</span></span>](uritemplate-sample.md)
