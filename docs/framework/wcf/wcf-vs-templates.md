---
title: WCF Visual Studio 模板
ms.date: 03/30/2017
ms.assetid: 6a608575-3535-4190-89da-911e24c8374f
ms.openlocfilehash: a3aa7e3ee57759ef54ddaa898fe036c4e3caa33e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279696"
---
# <a name="wcf-visual-studio-templates"></a><span data-ttu-id="5c239-102">WCF Visual Studio 模板</span><span class="sxs-lookup"><span data-stu-id="5c239-102">WCF Visual Studio Templates</span></span>

<span data-ttu-id="5c239-103">Windows Communication Foundation (WCF) Visual Studio 模板是预定义的项目和项模板，你可以在 Visual Studio 中使用这些模板快速生成 WCF 服务和应用程序。</span><span class="sxs-lookup"><span data-stu-id="5c239-103">Windows Communication Foundation (WCF) Visual Studio templates are predefined project and item templates you can use in Visual Studio to quickly build WCF services and surrounding applications.</span></span>  
  
## <a name="using-the-wcf-templates"></a><span data-ttu-id="5c239-104">使用 WCF 模板</span><span class="sxs-lookup"><span data-stu-id="5c239-104">Using the WCF Templates</span></span>  

 <span data-ttu-id="5c239-105">WCF Visual Studio 模板为服务开发提供基本的类结构。</span><span class="sxs-lookup"><span data-stu-id="5c239-105">WCF Visual Studio templates provide a basic class structure for service development.</span></span> <span data-ttu-id="5c239-106">具体地说，这些模板提供服务协定、数据协定、服务实现和配置的基本定义。</span><span class="sxs-lookup"><span data-stu-id="5c239-106">Specifically, these templates provide the basic definitions for service contract, data contract, service implementation, and configuration.</span></span> <span data-ttu-id="5c239-107">可以使用这些模板创建代码交互最少的简单服务以及更高级的服务的构造块。</span><span class="sxs-lookup"><span data-stu-id="5c239-107">You can use these templates to create a simple service with minimal code interaction, as well as a building block for more advanced services.</span></span>  
  
### <a name="wcf-service-library-project-template"></a><span data-ttu-id="5c239-108">WCF 服务库项目模板</span><span class="sxs-lookup"><span data-stu-id="5c239-108">WCF Service Library Project Template</span></span>  

 <span data-ttu-id="5c239-109">"WCF 服务库" 项目模板在 "新项目" 对话框中的 " **Visual c # \WCF** " 和 " **visual Basic\WCF**" 下提供。</span><span class="sxs-lookup"><span data-stu-id="5c239-109">The WCF Service Library project template is available in the new project dialog box under **Visual C#\WCF** and **Visual Basic\WCF**.</span></span>  
  
 <span data-ttu-id="5c239-110">当你使用 **WCF 服务** 模板创建新项目时，新项目将自动包含以下三个文件：</span><span class="sxs-lookup"><span data-stu-id="5c239-110">When you create a new project using the **WCF Service** template, the new project automatically includes the following three files:</span></span>  
  
- <span data-ttu-id="5c239-111">服务协定文件（IService1.cs 或 IService1.vb）。</span><span class="sxs-lookup"><span data-stu-id="5c239-111">Service contract file (IService1.cs or IService1.vb).</span></span> <span data-ttu-id="5c239-112">服务协定文件是一个应用了 WCF 服务特性的接口。</span><span class="sxs-lookup"><span data-stu-id="5c239-112">The service contract file is an interface that has WCF service attributes applied.</span></span> <span data-ttu-id="5c239-113">此文件提供简单服务的定义以表明如何定义服务，并且包括基于参数的操作和简单的数据协定示例。</span><span class="sxs-lookup"><span data-stu-id="5c239-113">This file provides a definition of a simple service to show you how to define your services, and includes parameter-based operations and a simple data contract sample.</span></span> <span data-ttu-id="5c239-114">这是创建 WCF 服务项目后在代码编辑器中显示的默认文件。</span><span class="sxs-lookup"><span data-stu-id="5c239-114">This is the default file displayed in the code editor after creating a WCF service project.</span></span>  
  
- <span data-ttu-id="5c239-115">服务实现文件（Service1.cs 或 Service1.vb）。</span><span class="sxs-lookup"><span data-stu-id="5c239-115">Service implementation file (Service1.cs or Service1.vb).</span></span> <span data-ttu-id="5c239-116">服务实现文件实现服务协定文件中定义的协定。</span><span class="sxs-lookup"><span data-stu-id="5c239-116">The service implementation file implements the contract defined in the service contract file.</span></span>  
  
- <span data-ttu-id="5c239-117">应用程序配置文件 (App.config)。</span><span class="sxs-lookup"><span data-stu-id="5c239-117">Application configuration file (App.config).</span></span> <span data-ttu-id="5c239-118">配置文件使用安全 HTTP 绑定提供 WCF 服务模型的基本元素。</span><span class="sxs-lookup"><span data-stu-id="5c239-118">The configuration file provides the basic elements of a WCF service model with a secure HTTP binding.</span></span> <span data-ttu-id="5c239-119">它还包括一个服务终结点，并启用了元数据交换。</span><span class="sxs-lookup"><span data-stu-id="5c239-119">It also includes an endpoint for the service and enables metadata exchange.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5c239-120">当使用 WCF 服务主机（默认配置） [ ( # A1) ](wcf-service-host-wcfsvchost-exe.md)运行时，Visual Studio 将配置为将 App.config 文件识别为项目的配置文件。</span><span class="sxs-lookup"><span data-stu-id="5c239-120">Visual Studio is configured to recognize the App.config file as the configuration file for the project when it is run using the [WCF Service Host (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md), which is the default configuration.</span></span> <span data-ttu-id="5c239-121">如果在可执行文件中承载服务库，则由于 DLL 的配置文件无效，必须将配置代码移动到可执行文件的配置文件。</span><span class="sxs-lookup"><span data-stu-id="5c239-121">If you host the service library in an executable, you have to move the configuration code to the configuration file of the executable, as configuration files for DLLs are not valid.</span></span>  
  
### <a name="wcf-service-application-template"></a><span data-ttu-id="5c239-122">WCF 服务应用程序模板</span><span class="sxs-lookup"><span data-stu-id="5c239-122">WCF Service Application Template</span></span>  

 <span data-ttu-id="5c239-123">"WCF 服务应用程序" 模板在 "新建项目" 对话框中的 " **Visual c # \WCF** " 和 " **visual Basic\WCF**" 下提供。</span><span class="sxs-lookup"><span data-stu-id="5c239-123">The WCF Service Application template is available in the New Project dialog box under **Visual C#\WCF** and **Visual Basic\WCF**.</span></span>  
  
 <span data-ttu-id="5c239-124">当你使用 **WCF Web 应用程序服务** 模板创建新项目时，该项目包括以下四个文件：</span><span class="sxs-lookup"><span data-stu-id="5c239-124">When you create a new project using the **WCF Web Application Service** template, the project includes the following four files:</span></span>  
  
- <span data-ttu-id="5c239-125">服务主机文件 (service1.svc)。</span><span class="sxs-lookup"><span data-stu-id="5c239-125">Service host file (service1.svc).</span></span>  
  
- <span data-ttu-id="5c239-126">服务协定文件（IService1.cs 或 IService1.vb）。</span><span class="sxs-lookup"><span data-stu-id="5c239-126">Service contract file (IService1.cs or IService1.vb).</span></span>  
  
- <span data-ttu-id="5c239-127">服务实现文件（Service1.svc.cs 或 Service1.svc.vb）。</span><span class="sxs-lookup"><span data-stu-id="5c239-127">Service implementation file (Service1.svc.cs or Service1.svc.vb).</span></span>  
  
- <span data-ttu-id="5c239-128">Web 配置文件 (Web.config)。</span><span class="sxs-lookup"><span data-stu-id="5c239-128">Web configuration file (Web.config).</span></span>  
  
 <span data-ttu-id="5c239-129">此模板将自动创建一个网站（该网站将要部署到虚拟目录），并在该网站中承载服务。</span><span class="sxs-lookup"><span data-stu-id="5c239-129">The template automatically creates a Web site (to be deployed to a virtual directory) and hosts a service in it.</span></span>  
  
### <a name="wcf-web-site-template"></a><span data-ttu-id="5c239-130">WCF 网站模板</span><span class="sxs-lookup"><span data-stu-id="5c239-130">WCF Web Site Template</span></span>  

 <span data-ttu-id="5c239-131">在 "新建项目" 对话框中的 " **Visual c # \Web 网站 \wcf service** " 和 " **Visual Basic\Web 网站 \wcf service**" 下提供 WCF 网站模板。</span><span class="sxs-lookup"><span data-stu-id="5c239-131">The WCF Web Site template is available in the New Project dialog box under **Visual C#\Web Site\WCF Service** and **Visual Basic\Web Site\WCF Service**.</span></span> <span data-ttu-id="5c239-132">这将创建与 WCF 服务应用程序模板相同的文件，但按照它是 ASP.NET 网站来进行组织。</span><span class="sxs-lookup"><span data-stu-id="5c239-132">This creates the same files as the WCF Service Application template but organizes it as if it were a ASP.NET web site.</span></span> <span data-ttu-id="5c239-133">创建 App_Code 和 App_Data 文件夹。</span><span class="sxs-lookup"><span data-stu-id="5c239-133">App_Code and App_Data folders are created.</span></span>  
  
### <a name="wcf-service-item-template"></a><span data-ttu-id="5c239-134">WCF 服务项模板</span><span class="sxs-lookup"><span data-stu-id="5c239-134">WCF Service Item Template</span></span>  

 <span data-ttu-id="5c239-135">WCF 服务项模板是一个自定义模板，它提供了一种将 WCF 服务添加到现有 Visual Studio 项目的快速方法。</span><span class="sxs-lookup"><span data-stu-id="5c239-135">The WCF Service Item template is a custom template that provides a quick way to add WCF services to your existing Visual Studio projects.</span></span>  
  
 <span data-ttu-id="5c239-136">若要使用此模板，请在 " **解决方案资源管理器** " 窗格中，右键单击项目名称，指向 " **添加**"，然后单击 " **新建项** " 以启动 " **添加新项** " 对话框。</span><span class="sxs-lookup"><span data-stu-id="5c239-136">To use this template, go to the **Solution Explorer** pane, right-click your project name, point to **Add**, and then click **New Item** to launch the **Add New Item** dialog box.</span></span>  
  
 <span data-ttu-id="5c239-137">服务接口和实现文件放在根项目文件夹中。</span><span class="sxs-lookup"><span data-stu-id="5c239-137">The service interface and implementation files are placed in the root project folder.</span></span>  
  
 <span data-ttu-id="5c239-138">该模板尝试将新服务的配置节合并到兼容类型的现有配置文件中。</span><span class="sxs-lookup"><span data-stu-id="5c239-138">The template attempts to merge the configuration section of the new service to the existing configuration file, if they are compatible types.</span></span>  
  
 <span data-ttu-id="5c239-139">如果现有项目是 Web 项目，则也会创建服务主机文件 (service1.svc)。</span><span class="sxs-lookup"><span data-stu-id="5c239-139">A service host file (service1.svc) is also created if the existing project is a Web project.</span></span>  
  
### <a name="wcf-wf-service-project-and-item-template"></a><span data-ttu-id="5c239-140">WCF WF 服务项目和项模板。</span><span class="sxs-lookup"><span data-stu-id="5c239-140">WCF WF Service Project and Item Template.</span></span>  

 <span data-ttu-id="5c239-141">这些模板可创建托管工作流服务的 WCF 服务，该服务是一个可像 web 服务一样访问的工作流。</span><span class="sxs-lookup"><span data-stu-id="5c239-141">These templates create WCF services that host a Workflow Service, which is a workflow that can be accessed like a web service.</span></span> <span data-ttu-id="5c239-142">XAML 或命令式编程模型具有单独的模板。</span><span class="sxs-lookup"><span data-stu-id="5c239-142">Separate templates exist for XAML or imperative programming models.</span></span> <span data-ttu-id="5c239-143">通过使用模板，可以创建顺序工作流或状态机工作流。</span><span class="sxs-lookup"><span data-stu-id="5c239-143">Using the templates, you can create sequential or state machine workflow.</span></span> <span data-ttu-id="5c239-144">有关这些类型的工作流的详细信息，请参阅 [如何：创建工作流](../windows-workflow-foundation/how-to-create-a-workflow.md)。</span><span class="sxs-lookup"><span data-stu-id="5c239-144">For more information on these types of workflow, see [How to: Create a Workflow](../windows-workflow-foundation/how-to-create-a-workflow.md).</span></span> <span data-ttu-id="5c239-145">有关创建工作流项目的详细信息，请参阅 [创建旧工作流项目](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)。</span><span class="sxs-lookup"><span data-stu-id="5c239-145">For more information about creating workflow projects, see [Creating Legacy Workflow Projects](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer).</span></span>  
  
 <span data-ttu-id="5c239-146">当使用 XOML 类型的工作流而不是基于代码的工作流时，Visual Studio 设计器会更快地响应。</span><span class="sxs-lookup"><span data-stu-id="5c239-146">Visual Studio designer is more responsive when XOML type workflows are used instead of code based ones.</span></span> <span data-ttu-id="5c239-147">XOML 工作流是要创建的默认工作流类型。</span><span class="sxs-lookup"><span data-stu-id="5c239-147">XOML workflow is the default workflow type to be created.</span></span>  
  
### <a name="wcf-syndication-service-library-template"></a><span data-ttu-id="5c239-148">WCF 联合服务库模板</span><span class="sxs-lookup"><span data-stu-id="5c239-148">WCF Syndication Service Library Template</span></span>  

 <span data-ttu-id="5c239-149">使用此模板，可以将 RSS 或 ATOM 格式的源作为 WCF 服务公开。</span><span class="sxs-lookup"><span data-stu-id="5c239-149">This template enables you to expose your feed in the RSS or ATOM format as a WCF service.</span></span> <span data-ttu-id="5c239-150">有关详细信息，请参阅 [WCF 联合](./feature-details/wcf-syndication.md)。</span><span class="sxs-lookup"><span data-stu-id="5c239-150">For more information, see [WCF Syndication](./feature-details/wcf-syndication.md).</span></span>  
  
#### <a name="changing-the-address-of-the-feed"></a><span data-ttu-id="5c239-151">更改源的地址</span><span class="sxs-lookup"><span data-stu-id="5c239-151">Changing the Address of the Feed</span></span>  

 <span data-ttu-id="5c239-152">在执行期间，联合模板使用 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="5c239-152">The syndication template uses Internet Explorer during execution.</span></span> <span data-ttu-id="5c239-153">在 Visual Studio 的 **解决方案资源管理器** 中右键单击项目时，选择 " **属性**"，然后选择 " **调试** " 选项卡，可以看到模板的默认地址。</span><span class="sxs-lookup"><span data-stu-id="5c239-153">When you right-click your project in **Solutions Explorer** in Visual Studio, select **Properties**, then select the **Debug** tab and you can see the default address of the template.</span></span> <span data-ttu-id="5c239-154">Internet Explorer 尝试在此地址打开源。</span><span class="sxs-lookup"><span data-stu-id="5c239-154">Internet Explorer attempts to open the feed at this address.</span></span>  
  
 <span data-ttu-id="5c239-155">如果更改源的地址，则还必须更改 " **调试** " 选项卡中的地址。如果不这样做，Internet Explorer 将尝试在默认地址打开源，并失败。</span><span class="sxs-lookup"><span data-stu-id="5c239-155">If you change the address of your feed, you must also change the address in the **Debug** tab. If you do not do this, Internet Explorer attempts to open the feed at the default address and fail.</span></span>  
  
### <a name="ajax-enabled-wcf-service-item-template"></a><span data-ttu-id="5c239-156">支持 AJAX 的 WCF 服务项模板</span><span class="sxs-lookup"><span data-stu-id="5c239-156">AJAX enabled WCF Service Item Template</span></span>  

 <span data-ttu-id="5c239-157">此模板将 AJAX 控件作为 WCF 服务公开。</span><span class="sxs-lookup"><span data-stu-id="5c239-157">This template exposes an AJAX control as a WCF service.</span></span> <span data-ttu-id="5c239-158">有关 AJAX 控件的详细信息，请参阅 [ajax 控件文档](/aspnet/ajax/)。</span><span class="sxs-lookup"><span data-stu-id="5c239-158">For more information on AJAX controls, see the [AJAX control documentation](/aspnet/ajax/).</span></span>  
  
### <a name="silverlight-enabled-wcf-service-item-template"></a><span data-ttu-id="5c239-159">启用了 Silverlight 的 WCF 服务项模板</span><span class="sxs-lookup"><span data-stu-id="5c239-159">Silverlight-enabled WCF Service Item Template</span></span>  

 <span data-ttu-id="5c239-160">该模板创建提供数据给 Silverlight 客户端或前端的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="5c239-160">This template creates a Web service that provides data to a Silverlight client or front-end.</span></span> <span data-ttu-id="5c239-161">可以将模板添加到网站或 Web 应用程序项目中，以创建 WCF 服务，其中包括支持与 Silverlight 客户端进行通信的服务代码和配置。</span><span class="sxs-lookup"><span data-stu-id="5c239-161">The template can be added to a Web site or Web application project to create a WCF service, which includes service code and configuration that support communicating with a Silverlight client.</span></span> <span data-ttu-id="5c239-162">然后，你可以使用 **添加服务引用** 向客户端添加服务的客户端代理，以及在 silverlight 客户端与启用了 SILVERLIGHT 的 WCF 服务之间交换数据。</span><span class="sxs-lookup"><span data-stu-id="5c239-162">You can then use **Add Service Reference** to add a client proxy of the service to the client, and exchange data between the Silverlight client and the Silverlight-enabled WCF service.</span></span>  
  
 <span data-ttu-id="5c239-163">若要访问此模板，请在 **解决方案资源管理器** 中右键单击网站或 web 应用程序项目，单击 " **添加新项**"，然后单击 " **支持 Silverlight 的 WCF 服务**"。</span><span class="sxs-lookup"><span data-stu-id="5c239-163">To access this template, right-click a Web site or Web application project in **Solution Explorer**, click **Add a new item**, and click **Silverlight-enabled WCF Service**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5c239-164">启用了 Silverlight 的 WCF 服务公开 `basicHttpBinding` 终结点，不启用任何安全设置。</span><span class="sxs-lookup"><span data-stu-id="5c239-164">The Silverlight-enabled WCF Service exposes a `basicHttpBinding` endpoint without enabling any security settings.</span></span> <span data-ttu-id="5c239-165">因此，连接到此服务的任何客户端都可以获取有关此服务的信息。</span><span class="sxs-lookup"><span data-stu-id="5c239-165">Therefore, information about the service can be obtained by all clients that connect to this service.</span></span> <span data-ttu-id="5c239-166">此外，在该服务与客户端之间交换的消息也未经过签名和加密处理。</span><span class="sxs-lookup"><span data-stu-id="5c239-166">Messages exchanged between the service and the client are also not signed or encrypted.</span></span> <span data-ttu-id="5c239-167">若要正确保护该终结点，应使用 ASP.NET 身份验证、HTTPS 或其他机制。</span><span class="sxs-lookup"><span data-stu-id="5c239-167">To secure the endpoint properly, you should use ASP.NET authentication, HTTPS or other mechanisms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c239-168">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5c239-168">See also</span></span>

- [<span data-ttu-id="5c239-169">WCF 服务主机 (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="5c239-169">WCF Service Host (WcfSvcHost.exe)</span></span>](wcf-service-host-wcfsvchost-exe.md)
- [<span data-ttu-id="5c239-170">WCF 测试客户端 (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="5c239-170">WCF Test Client (WcfTestClient.exe)</span></span>](wcf-test-client-wcftestclient-exe.md)
