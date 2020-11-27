---
title: 部署 WCF 库项目
ms.date: 03/30/2017
ms.assetid: 9f9222fe-d358-443c-9a49-12c5498e35e7
ms.openlocfilehash: e3a90f03639a888b4528a1962a24b7adc5d43c58
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96260885"
---
# <a name="deploying-a-wcf-library-project"></a><span data-ttu-id="38973-102">部署 WCF 库项目</span><span class="sxs-lookup"><span data-stu-id="38973-102">Deploying a WCF Library Project</span></span>

<span data-ttu-id="38973-103">本主题介绍如何部署 Windows Communication Foundation (WCF) 服务库项目。</span><span class="sxs-lookup"><span data-stu-id="38973-103">This topic describes how you can deploy a Windows Communication Foundation (WCF) Service Library Project.</span></span>  
  
## <a name="deploying-a-wcf-service-library"></a><span data-ttu-id="38973-104">部署 WCF 服务库</span><span class="sxs-lookup"><span data-stu-id="38973-104">Deploying a WCF Service Library</span></span>  

 <span data-ttu-id="38973-105">WCF 服务库是 (DLL) 的动态链接库。</span><span class="sxs-lookup"><span data-stu-id="38973-105">A WCF service library is a dynamic-link library (DLL).</span></span> <span data-ttu-id="38973-106">因此，它不能自己运行。</span><span class="sxs-lookup"><span data-stu-id="38973-106">As such, it cannot be executed on its own.</span></span> <span data-ttu-id="38973-107">必须将其部署到宿主环境中。</span><span class="sxs-lookup"><span data-stu-id="38973-107">It needs to be deployed into a hosting environment.</span></span> <span data-ttu-id="38973-108">有关此过程的详细信息，请参阅 [托管和使用 WCF 服务](/previous-versions/dotnet/articles/bb332338(v=msdn.10))。</span><span class="sxs-lookup"><span data-stu-id="38973-108">For more information about this process, see [Hosting and Consuming WCF Services](/previous-versions/dotnet/articles/bb332338(v=msdn.10)).</span></span>  
  
 <span data-ttu-id="38973-109">WCF 服务库可以像任何其他 WCF 服务一样部署。</span><span class="sxs-lookup"><span data-stu-id="38973-109">A WCF service library can be deployed like any other WCF service.</span></span> <span data-ttu-id="38973-110">但请注意，.NET Framework 不支持 Dll 的配置。</span><span class="sxs-lookup"><span data-stu-id="38973-110">However, be aware that .NET Framework does not support configuration for DLLs.</span></span> <span data-ttu-id="38973-111"><xref:System.Configuration> 支持每个应用程序域一个配置文件。</span><span class="sxs-lookup"><span data-stu-id="38973-111"><xref:System.Configuration> supports one configuration file per app-domain.</span></span> <span data-ttu-id="38973-112">WCF 服务库项目在开发期间为库提供了一个 App.config 文件，从而减轻了这一限制。</span><span class="sxs-lookup"><span data-stu-id="38973-112">The WCF service library project alleviates this limitation by providing an App.config file for the library during development.</span></span> <span data-ttu-id="38973-113">但在部署之后不能识别 App.config 文件。</span><span class="sxs-lookup"><span data-stu-id="38973-113">However, the App.config file is not recognized after deployment.</span></span>  
  
 <span data-ttu-id="38973-114">必须将配置代码移动到主机环境所识别的配置文件中。</span><span class="sxs-lookup"><span data-stu-id="38973-114">You have to move your configuration code into the configuration file recognized by your hosting environment.</span></span> <span data-ttu-id="38973-115">对于自承载，您应将 App.config 文件的内容复制到宿主可执行文件的 App.config 文件中。</span><span class="sxs-lookup"><span data-stu-id="38973-115">For self-hosting, you should copy the contents of the App.config file into the App.config file of the hosting executable.</span></span> <span data-ttu-id="38973-116">如果使用 IIS 承载服务，则应将 App.config 文件的内容复制到虚拟目录的 Web.config 文件中。</span><span class="sxs-lookup"><span data-stu-id="38973-116">If you use IIS to host your service, you should copy the contents of the App.config file into the Web.config file of the virtual directory.</span></span>
