---
title: 使用 .NET Core 创建 REST 客户端
description: 此教程将介绍 .NET Core 和 C# 语言的许多功能。
ms.date: 01/09/2020
ms.assetid: 51033ce2-7a53-4cdd-966d-9da15c8204d2
ms.openlocfilehash: b537108bd77b3ed2248ca9e459044e09fa854ba9
ms.sourcegitcommit: 88fbb019b84c2d044d11fb4f6004aec07f2b25b1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2021
ms.locfileid: "97899647"
---
# <a name="rest-client"></a><span data-ttu-id="661e8-103">REST 客户端</span><span class="sxs-lookup"><span data-stu-id="661e8-103">REST client</span></span>

<span data-ttu-id="661e8-104">此教程将介绍 .NET Core 和 C# 语言的许多功能。</span><span class="sxs-lookup"><span data-stu-id="661e8-104">This tutorial teaches you a number of features in .NET Core and the C# language.</span></span> <span data-ttu-id="661e8-105">你将了解：</span><span class="sxs-lookup"><span data-stu-id="661e8-105">You’ll learn:</span></span>

* <span data-ttu-id="661e8-106">.NET Core CLI 的基础知识。</span><span class="sxs-lookup"><span data-stu-id="661e8-106">The basics of the .NET Core CLI.</span></span>
* <span data-ttu-id="661e8-107">C# 语言功能概述。</span><span class="sxs-lookup"><span data-stu-id="661e8-107">An overview of C# Language features.</span></span>
* <span data-ttu-id="661e8-108">如何使用 NuGet 管理依赖项</span><span class="sxs-lookup"><span data-stu-id="661e8-108">Managing dependencies with NuGet</span></span>
* <span data-ttu-id="661e8-109">HTTP 通信</span><span class="sxs-lookup"><span data-stu-id="661e8-109">HTTP Communications</span></span>
* <span data-ttu-id="661e8-110">如何处理 JSON 信息</span><span class="sxs-lookup"><span data-stu-id="661e8-110">Processing JSON information</span></span>
* <span data-ttu-id="661e8-111">如何管理含特性的配置。</span><span class="sxs-lookup"><span data-stu-id="661e8-111">Managing configuration with Attributes.</span></span>

<span data-ttu-id="661e8-112">将生成一个应用程序，向 GitHub 上的 REST 服务发出 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="661e8-112">You’ll build an application that issues HTTP Requests to a REST service on GitHub.</span></span> <span data-ttu-id="661e8-113">需要读取 JSON 格式的信息，并将相应的 JSON 数据包转换成 C# 对象。</span><span class="sxs-lookup"><span data-stu-id="661e8-113">You'll read information in JSON format, and convert that JSON packet into C# objects.</span></span> <span data-ttu-id="661e8-114">最后将了解如何使用 C# 对象。</span><span class="sxs-lookup"><span data-stu-id="661e8-114">Finally, you'll see how to work with C# objects.</span></span>

<span data-ttu-id="661e8-115">此教程中介绍了多项功能。</span><span class="sxs-lookup"><span data-stu-id="661e8-115">There are many features in this tutorial.</span></span> <span data-ttu-id="661e8-116">我们将逐个生成这些功能。</span><span class="sxs-lookup"><span data-stu-id="661e8-116">Let’s build them one by one.</span></span>

<span data-ttu-id="661e8-117">如果想要按照针对本主题的[最终示例](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient)操作，可以下载它。</span><span class="sxs-lookup"><span data-stu-id="661e8-117">If you prefer to follow along with the [final sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient) for this topic, you can download it.</span></span> <span data-ttu-id="661e8-118">有关下载说明，请参阅[示例和教程](../../samples-and-tutorials/index.md#view-and-download-samples)。</span><span class="sxs-lookup"><span data-stu-id="661e8-118">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#view-and-download-samples).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="661e8-119">先决条件</span><span class="sxs-lookup"><span data-stu-id="661e8-119">Prerequisites</span></span>

<span data-ttu-id="661e8-120">必须将计算机设置为运行 .Net Core。</span><span class="sxs-lookup"><span data-stu-id="661e8-120">You’ll need to set up your machine to run .NET core.</span></span> <span data-ttu-id="661e8-121">有关安装说明，请访问 [.NET Core 下载](https://dotnet.microsoft.com/download)页。</span><span class="sxs-lookup"><span data-stu-id="661e8-121">You can find the installation instructions on the [.NET Core Downloads](https://dotnet.microsoft.com/download) page.</span></span> <span data-ttu-id="661e8-122">可以在 Windows、Linux、macOS 或 Docker 容器中运行此应用程序。</span><span class="sxs-lookup"><span data-stu-id="661e8-122">You can run this application on Windows, Linux, macOS or in a Docker container.</span></span>
<span data-ttu-id="661e8-123">必须安装常用的代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="661e8-123">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="661e8-124">在以下说明中，我们使用的是开放源代码跨平台编辑器 [Visual Studio Code](https://code.visualstudio.com/)。</span><span class="sxs-lookup"><span data-stu-id="661e8-124">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/), which is an open source, cross platform editor.</span></span> <span data-ttu-id="661e8-125">不过，你可以使用习惯使用的任意工具。</span><span class="sxs-lookup"><span data-stu-id="661e8-125">However, you can use whatever tools you are comfortable with.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="661e8-126">创建应用程序</span><span class="sxs-lookup"><span data-stu-id="661e8-126">Create the Application</span></span>

<span data-ttu-id="661e8-127">第一步是新建应用程序。</span><span class="sxs-lookup"><span data-stu-id="661e8-127">The first step is to create a new application.</span></span> <span data-ttu-id="661e8-128">打开命令提示符，然后新建应用程序的目录。</span><span class="sxs-lookup"><span data-stu-id="661e8-128">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="661e8-129">将新建的目录设为当前目录。</span><span class="sxs-lookup"><span data-stu-id="661e8-129">Make that the current directory.</span></span> <span data-ttu-id="661e8-130">在控制台窗口中输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="661e8-130">Enter the following command in a console window:</span></span>

```dotnetcli
dotnet new console --name WebAPIClient
```

<span data-ttu-id="661e8-131">这将为基本的“Hello World”应用程序创建起始文件。</span><span class="sxs-lookup"><span data-stu-id="661e8-131">This creates the starter files for a basic "Hello World" application.</span></span> <span data-ttu-id="661e8-132">项目名称为“WebAPIClient”。</span><span class="sxs-lookup"><span data-stu-id="661e8-132">The project name is "WebAPIClient".</span></span> <span data-ttu-id="661e8-133">这是一个新项目，因此没有部署任何依赖项。</span><span class="sxs-lookup"><span data-stu-id="661e8-133">As this is a new project, none of the dependencies are in place.</span></span> <span data-ttu-id="661e8-134">第一次运行时将下载 .NET Core 框架、安装开发证书并运行 NuGet 包管理器来还原缺少的依赖项。</span><span class="sxs-lookup"><span data-stu-id="661e8-134">The first run will download the .NET Core framework, install a development certificate, and run the NuGet package manager to restore missing dependencies.</span></span>

<span data-ttu-id="661e8-135">开始修改之前，使用 `cd` 转到“WebAPIClient”目录，然后在命令提示符下键入 `dotnet run`（[参见注释](#dotnet-restore-note)）以运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="661e8-135">Before you start making modifications, `cd` into the "WebAPIClient" directory and type `dotnet run` ([see note](#dotnet-restore-note)) at the command prompt to run your application.</span></span> <span data-ttu-id="661e8-136">如果环境缺少依赖项，则 `dotnet run` 会自动执行 `dotnet restore`。</span><span class="sxs-lookup"><span data-stu-id="661e8-136">`dotnet run` automatically performs `dotnet restore` if your environment is missing dependencies.</span></span> <span data-ttu-id="661e8-137">如果需要重新生成应用程序，它还会执行 `dotnet build`。</span><span class="sxs-lookup"><span data-stu-id="661e8-137">It also performs `dotnet build` if your application needs to be rebuilt.</span></span>
<span data-ttu-id="661e8-138">初始设置完成后，只需在对项目有意义的情况下运行 `dotnet restore` 或 `dotnet build`。</span><span class="sxs-lookup"><span data-stu-id="661e8-138">After your initial setup, you will only need to run `dotnet restore` or `dotnet build` when it makes sense for your project.</span></span>

## <a name="adding-new-dependencies"></a><span data-ttu-id="661e8-139">添加新的依赖项</span><span class="sxs-lookup"><span data-stu-id="661e8-139">Adding New Dependencies</span></span>

<span data-ttu-id="661e8-140">.NET Core 的主要设计目标之一是最小化 .NET 安装的大小。</span><span class="sxs-lookup"><span data-stu-id="661e8-140">One of the key design goals for .NET Core is to minimize the size of the .NET installation.</span></span> <span data-ttu-id="661e8-141">如果应用程序需要使用其他库来生成某些功能，请将这些依赖项添加到 C# 项目 (\*.csproj) 文件中。</span><span class="sxs-lookup"><span data-stu-id="661e8-141">If an application needs additional libraries for some of its features, you add those dependencies into your C# project (\*.csproj) file.</span></span> <span data-ttu-id="661e8-142">对于我们的示例，将需要添加 `System.Runtime.Serialization.Json` 包，以便应用程序可以处理 JSON 响应。</span><span class="sxs-lookup"><span data-stu-id="661e8-142">For our example, you'll need to add the `System.Runtime.Serialization.Json` package, so your application can process JSON responses.</span></span>

<span data-ttu-id="661e8-143">你将需要此应用程序的 `System.Runtime.Serialization.Json` 包。</span><span class="sxs-lookup"><span data-stu-id="661e8-143">You'll need the `System.Runtime.Serialization.Json` package for this application.</span></span> <span data-ttu-id="661e8-144">通过运行以下 [.NET CLI](../../core/tools/dotnet-add-package.md) 命令，将其添加到项目：</span><span class="sxs-lookup"><span data-stu-id="661e8-144">Add it to your project by running the following [.NET CLI](../../core/tools/dotnet-add-package.md) command:</span></span>

```dotnetcli
dotnet add package System.Text.Json
```

## <a name="making-web-requests"></a><span data-ttu-id="661e8-145">发出 Web 请求</span><span class="sxs-lookup"><span data-stu-id="661e8-145">Making Web Requests</span></span>

<span data-ttu-id="661e8-146">现在，可以开始检索 Web 数据了。</span><span class="sxs-lookup"><span data-stu-id="661e8-146">Now you're ready to start retrieving data from the web.</span></span> <span data-ttu-id="661e8-147">在此应用程序中，需要读取 [GitHub API](https://developer.github.com/v3/) 返回的信息。</span><span class="sxs-lookup"><span data-stu-id="661e8-147">In this application, you'll read information from the [GitHub API](https://developer.github.com/v3/).</span></span> <span data-ttu-id="661e8-148">让我们在 [.NET Foundation](https://www.dotnetfoundation.org/) 的保护下读取项目信息。</span><span class="sxs-lookup"><span data-stu-id="661e8-148">Let's read information about the projects under the [.NET Foundation](https://www.dotnetfoundation.org/) umbrella.</span></span> <span data-ttu-id="661e8-149">先向 GitHub API 发出请求，以检索项目信息。</span><span class="sxs-lookup"><span data-stu-id="661e8-149">You'll start by making the request to the GitHub API to retrieve information on the projects.</span></span> <span data-ttu-id="661e8-150">将使用终结点 <https://api.github.com/orgs/dotnet/repos>。</span><span class="sxs-lookup"><span data-stu-id="661e8-150">The endpoint you'll use is: <https://api.github.com/orgs/dotnet/repos>.</span></span> <span data-ttu-id="661e8-151">由于要检索这些项目的所有信息，因此将发出 HTTP GET 请求。</span><span class="sxs-lookup"><span data-stu-id="661e8-151">You want to retrieve all the information about these projects, so you'll use an HTTP GET request.</span></span>
<span data-ttu-id="661e8-152">此外，浏览器也使用 HTTP GET 请求，以便你可以将相应的 URL 粘贴到浏览器，查看将要收到并处理的信息。</span><span class="sxs-lookup"><span data-stu-id="661e8-152">Your browser also uses HTTP GET requests, so you can paste that URL into your browser to see what information you'll be receiving and processing.</span></span>

<span data-ttu-id="661e8-153">使用 <xref:System.Net.Http.HttpClient> 类发出 Web 请求。</span><span class="sxs-lookup"><span data-stu-id="661e8-153">You use the <xref:System.Net.Http.HttpClient> class to make web requests.</span></span> <span data-ttu-id="661e8-154">与所有新式 .NET API 一样，<xref:System.Net.Http.HttpClient> 只支持长时间运行 API 的异步方法。</span><span class="sxs-lookup"><span data-stu-id="661e8-154">Like all modern .NET APIs, <xref:System.Net.Http.HttpClient> supports only async methods for its long-running APIs.</span></span>
<span data-ttu-id="661e8-155">从异步方法入手。</span><span class="sxs-lookup"><span data-stu-id="661e8-155">Start by making an async method.</span></span> <span data-ttu-id="661e8-156">将一边填充实现代码，一边生成应用程序功能。</span><span class="sxs-lookup"><span data-stu-id="661e8-156">You'll fill in the implementation as you build the functionality of the application.</span></span> <span data-ttu-id="661e8-157">首先，打开项目目录中的 `program.cs` 文件，然后向 `Program` 类添加以下方法：</span><span class="sxs-lookup"><span data-stu-id="661e8-157">Start by opening the `program.cs` file in your project directory and adding the following method to the `Program` class:</span></span>

```csharp
private static async Task ProcessRepositories()
{
}
```

<span data-ttu-id="661e8-158">需要在 `Main` 方法的最上面添加 `using` 指令，以便 C# 编译器能够识别 <xref:System.Threading.Tasks.Task> 类型：</span><span class="sxs-lookup"><span data-stu-id="661e8-158">You'll need to add a `using` directive at the top of your `Main` method so that the C# compiler recognizes the <xref:System.Threading.Tasks.Task> type:</span></span>

```csharp
using System.Threading.Tasks;
```

<span data-ttu-id="661e8-159">如果此时生成项目，将会看到系统针对此方法生成的警告，因为其中不含任何 `await` 运算符，将以同步方式运行。</span><span class="sxs-lookup"><span data-stu-id="661e8-159">If you build your project at this point, you'll get a warning generated for this method, because it does not contain any `await` operators and will run synchronously.</span></span> <span data-ttu-id="661e8-160">暂且忽略此警告；将在填充方法时添加 `await` 运算符。</span><span class="sxs-lookup"><span data-stu-id="661e8-160">Ignore that for now; you'll add `await` operators as you fill in the method.</span></span>

<span data-ttu-id="661e8-161">接下来，更新 `Main` 方法以调用 `ProcessRepositories` 方法。</span><span class="sxs-lookup"><span data-stu-id="661e8-161">Next, update the `Main` method to call the `ProcessRepositories` method.</span></span> <span data-ttu-id="661e8-162">`ProcessRepositories` 方法会返回一个任务，不应在此任务完成前退出程序。</span><span class="sxs-lookup"><span data-stu-id="661e8-162">The `ProcessRepositories` method returns a task, and you shouldn't exit the program before that task finishes.</span></span> <span data-ttu-id="661e8-163">因此，必须更改 `Main` 的签名。</span><span class="sxs-lookup"><span data-stu-id="661e8-163">Therefore, you must change the signature of `Main`.</span></span> <span data-ttu-id="661e8-164">添加 `async` 修饰符，并将返回类型更改为 `Task`。</span><span class="sxs-lookup"><span data-stu-id="661e8-164">Add the `async` modifier, and change the return type to `Task`.</span></span> <span data-ttu-id="661e8-165">然后，在方法的主体中，添加对 `ProcessRepositories` 的调用。</span><span class="sxs-lookup"><span data-stu-id="661e8-165">Then, in the body of the method, add a call to `ProcessRepositories`.</span></span> <span data-ttu-id="661e8-166">向该方法调用添加 `await` 关键字：</span><span class="sxs-lookup"><span data-stu-id="661e8-166">Add the `await` keyword to that method call:</span></span>

```csharp
static async Task Main(string[] args)
{
    await ProcessRepositories();
}
```

<span data-ttu-id="661e8-167">现在，生成了一个不执行任何操作但具备异步功能的程序。</span><span class="sxs-lookup"><span data-stu-id="661e8-167">Now, you have a program that does nothing, but does it asynchronously.</span></span> <span data-ttu-id="661e8-168">现在进行改进。</span><span class="sxs-lookup"><span data-stu-id="661e8-168">Let's improve it.</span></span>

<span data-ttu-id="661e8-169">首先需要一个能从 Web 检索数据的对象；可使用 <xref:System.Net.Http.HttpClient> 执行此操作。</span><span class="sxs-lookup"><span data-stu-id="661e8-169">First you need an object that is capable to retrieve data from the web; you can use a <xref:System.Net.Http.HttpClient> to do that.</span></span> <span data-ttu-id="661e8-170">此对象负责处理请求和响应。</span><span class="sxs-lookup"><span data-stu-id="661e8-170">This object handles the request and the responses.</span></span> <span data-ttu-id="661e8-171">在 Program.cs 文件内的 `Program` 类中初始化该类型的一个实例。</span><span class="sxs-lookup"><span data-stu-id="661e8-171">Instantiate a single instance of that type in the `Program` class inside the *Program.cs* file.</span></span>

```csharp
namespace WebAPIClient
{
    class Program
    {
        private static readonly HttpClient client = new HttpClient();

        static async Task Main(string[] args)
        {
            //...
        }
    }
}
```

<span data-ttu-id="661e8-172">让我们回到 `ProcessRepositories` 方法，并填充它的第一个版本：</span><span class="sxs-lookup"><span data-stu-id="661e8-172">Let's go back to the `ProcessRepositories` method and fill in a first version of it:</span></span>

```csharp
private static async Task ProcessRepositories()
{
    client.DefaultRequestHeaders.Accept.Clear();
    client.DefaultRequestHeaders.Accept.Add(
        new MediaTypeWithQualityHeaderValue("application/vnd.github.v3+json"));
    client.DefaultRequestHeaders.Add("User-Agent", ".NET Foundation Repository Reporter");

    var stringTask = client.GetStringAsync("https://api.github.com/orgs/dotnet/repos");

    var msg = await stringTask;
    Console.Write(msg);
}
```

<span data-ttu-id="661e8-173">此外，为了让编译能够顺利进行，还需要在文件的最上面添加两个新的 `using` 指令：</span><span class="sxs-lookup"><span data-stu-id="661e8-173">You'll need to also add two new `using` directives at the top of the file for this to compile:</span></span>

```csharp
using System.Net.Http;
using System.Net.Http.Headers;
```

<span data-ttu-id="661e8-174">第一个版本发出 Web 请求来读取 .NET Foundation 组织下的所有存储库列表。</span><span class="sxs-lookup"><span data-stu-id="661e8-174">This first version makes a web request to read the list of all repositories under the dotnet foundation organization.</span></span> <span data-ttu-id="661e8-175">（.NET Foundation 的 gitHub ID 为“dotnet”）。</span><span class="sxs-lookup"><span data-stu-id="661e8-175">(The gitHub ID for the .NET Foundation is 'dotnet').</span></span> <span data-ttu-id="661e8-176">前几行代码针对该请求设置 <xref:System.Net.Http.HttpClient>。</span><span class="sxs-lookup"><span data-stu-id="661e8-176">The first few lines set up the <xref:System.Net.Http.HttpClient> for this request.</span></span> <span data-ttu-id="661e8-177">在第一行中，它被配置为接受 GitHub JSON 响应。</span><span class="sxs-lookup"><span data-stu-id="661e8-177">First, it is configured to accept the GitHub JSON responses.</span></span>
<span data-ttu-id="661e8-178">此格式仅为 JSON。</span><span class="sxs-lookup"><span data-stu-id="661e8-178">This format is simply JSON.</span></span> <span data-ttu-id="661e8-179">下一代码行将用户代理标头添加到此对象发出的所有请求中。</span><span class="sxs-lookup"><span data-stu-id="661e8-179">The next line adds a User Agent header to all requests from this object.</span></span> <span data-ttu-id="661e8-180">这两个标头均由 GitHub 服务器代码进行检查，必须使用它们，才能检索 GitHub 中的信息。</span><span class="sxs-lookup"><span data-stu-id="661e8-180">These two headers are checked by the GitHub server code, and are necessary to retrieve information from GitHub.</span></span>

<span data-ttu-id="661e8-181">配置 <xref:System.Net.Http.HttpClient> 后，发出 Web 请求并检索响应。</span><span class="sxs-lookup"><span data-stu-id="661e8-181">After you've configured the <xref:System.Net.Http.HttpClient>, you make a web request and retrieve the response.</span></span> <span data-ttu-id="661e8-182">在此第一个版本中，将使用 <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType> 便捷方法。</span><span class="sxs-lookup"><span data-stu-id="661e8-182">In this first version, you use the <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType> convenience method.</span></span> <span data-ttu-id="661e8-183">此便捷方法先执行发出 Web 请求的任务，然后当返回请求时读取响应流，并从流中提取内容。</span><span class="sxs-lookup"><span data-stu-id="661e8-183">This convenience method starts a task that makes the web request, and then when the request returns, it reads the response stream and extracts the content from the stream.</span></span> <span data-ttu-id="661e8-184">响应正文以 <xref:System.String> 的形式返回。</span><span class="sxs-lookup"><span data-stu-id="661e8-184">The body of the response is returned as a <xref:System.String>.</span></span> <span data-ttu-id="661e8-185">此字符串在任务完成时可用。</span><span class="sxs-lookup"><span data-stu-id="661e8-185">The string is available when the task completes.</span></span>

<span data-ttu-id="661e8-186">此方法的最后两行代码用于等待任务完成，然后在控制台中打印输出响应。</span><span class="sxs-lookup"><span data-stu-id="661e8-186">The final two lines of this method await that task, and then print the response to the console.</span></span>
<span data-ttu-id="661e8-187">生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="661e8-187">Build the app, and run it.</span></span> <span data-ttu-id="661e8-188">此时，生成警告不再显示，因为 `ProcessRepositories` 现在的确包含 `await` 运算符。</span><span class="sxs-lookup"><span data-stu-id="661e8-188">The build warning is gone now, because the `ProcessRepositories` now does contain an `await` operator.</span></span> <span data-ttu-id="661e8-189">将看到很长的 JSON 格式文本。</span><span class="sxs-lookup"><span data-stu-id="661e8-189">You'll see a long display of JSON formatted text.</span></span>

## <a name="processing-the-json-result"></a><span data-ttu-id="661e8-190">处理 JSON 结果</span><span class="sxs-lookup"><span data-stu-id="661e8-190">Processing the JSON Result</span></span>

<span data-ttu-id="661e8-191">此时，你已编写用于检索来自 Web 服务器的响应，并显示响应文本的代码。</span><span class="sxs-lookup"><span data-stu-id="661e8-191">At this point, you've written the code to retrieve a response from a web server, and display the text that is contained in that response.</span></span> <span data-ttu-id="661e8-192">接下来，让我们将相应的 JSON 响应转换成 C# 对象。</span><span class="sxs-lookup"><span data-stu-id="661e8-192">Next, let's convert that JSON response into C# objects.</span></span>

<span data-ttu-id="661e8-193"><xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType> 类将对象序列化为 JSON，并将 JSON 反序列化为对象。</span><span class="sxs-lookup"><span data-stu-id="661e8-193">The <xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType> class serializes objects to JSON and deserializes JSON into objects.</span></span> <span data-ttu-id="661e8-194">首先定义一个类，用于表示从 GitHub API 返回的 `repo` JSON 对象：</span><span class="sxs-lookup"><span data-stu-id="661e8-194">Start by defining a class to represent the `repo` JSON object returned from the GitHub API:</span></span>

```csharp
using System;

namespace WebAPIClient
{
    public class Repository
    {
        public string name { get; set; }
    }
}
```

<span data-ttu-id="661e8-195">将以上代码添加到“repo.cs”新文件中。</span><span class="sxs-lookup"><span data-stu-id="661e8-195">Put the above code in a new file called 'repo.cs'.</span></span> <span data-ttu-id="661e8-196">此版本的类表示处理 JSON 数据的最简单路径。</span><span class="sxs-lookup"><span data-stu-id="661e8-196">This version of the class represents the simplest path to process JSON data.</span></span> <span data-ttu-id="661e8-197">类名和成员名称与 JSON 数据包中使用的名称一致，而不是遵循以下 C# 约定。</span><span class="sxs-lookup"><span data-stu-id="661e8-197">The class name and the member name match the names used in the JSON packet, instead of following C# conventions.</span></span> <span data-ttu-id="661e8-198">稍后将通过提供某些配置特性进行修复。</span><span class="sxs-lookup"><span data-stu-id="661e8-198">You'll fix that by providing some configuration attributes later.</span></span> <span data-ttu-id="661e8-199">此类展示了 JSON 序列化和反序列化的另一个重要功能：并非 JSON 数据包中的所有字段都属于此类。</span><span class="sxs-lookup"><span data-stu-id="661e8-199">This class demonstrates another important feature of JSON serialization and deserialization: Not all the fields in the JSON packet are part of this class.</span></span>
<span data-ttu-id="661e8-200">JSON 序列化程序将忽略所使用的类类型未包含的信息。</span><span class="sxs-lookup"><span data-stu-id="661e8-200">The JSON serializer will ignore information that is not included in the class type being used.</span></span>
<span data-ttu-id="661e8-201">借助此功能，可更轻松地创建仅处理一部分 JSON 数据包字段的类型。</span><span class="sxs-lookup"><span data-stu-id="661e8-201">This feature makes it easier to create types that work with only a subset of the fields in the JSON packet.</span></span>

<span data-ttu-id="661e8-202">至此，你已创建类型，让我们来进行反序列化吧。</span><span class="sxs-lookup"><span data-stu-id="661e8-202">Now that you've created the type, let's deserialize it.</span></span>

<span data-ttu-id="661e8-203">接下来，使用序列化程序将 JSON 转换成 C# 对象。</span><span class="sxs-lookup"><span data-stu-id="661e8-203">Next, you'll use the serializer to convert JSON into C# objects.</span></span> <span data-ttu-id="661e8-204">使用以下行替换 `ProcessRepositories` 方法中对 <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> 的调用：</span><span class="sxs-lookup"><span data-stu-id="661e8-204">Replace the call to <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> in your `ProcessRepositories` method with the following lines:</span></span>

```csharp
var streamTask = client.GetStreamAsync("https://api.github.com/orgs/dotnet/repos");
var repositories = await JsonSerializer.DeserializeAsync<List<Repository>>(await streamTask);
```

<span data-ttu-id="661e8-205">你使用的是新命名空间，因此，还需要将其添加到文件顶部：</span><span class="sxs-lookup"><span data-stu-id="661e8-205">You're using new namespaces, so you'll need to add it at the top of the file as well:</span></span>

```csharp
using System.Collections.Generic;
using System.Text.Json;
```

<span data-ttu-id="661e8-206">请注意，现使用 <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)>，而不是 <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)>。</span><span class="sxs-lookup"><span data-stu-id="661e8-206">Notice that you're now using <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> instead of <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)>.</span></span> <span data-ttu-id="661e8-207">序列化程序使用流（而不是字符串）作为其源。</span><span class="sxs-lookup"><span data-stu-id="661e8-207">The serializer uses a stream instead of a string as its source.</span></span> <span data-ttu-id="661e8-208">让我们来看看前面第二行代码段中所使用的多项 C# 语言功能。</span><span class="sxs-lookup"><span data-stu-id="661e8-208">Let's explain a couple features of the C# language that are being used in the second line of the preceding code snippet.</span></span> <span data-ttu-id="661e8-209"><xref:System.Text.Json.JsonSerializer.DeserializeAsync%60%601(System.IO.Stream,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType> 的第一个自变量是 `await` 表达式。</span><span class="sxs-lookup"><span data-stu-id="661e8-209">The first argument to <xref:System.Text.Json.JsonSerializer.DeserializeAsync%60%601(System.IO.Stream,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType> is an `await` expression.</span></span> <span data-ttu-id="661e8-210">（其他两个参数为可选，并在代码段中省略。）Await 表达式可以出现在代码中的几乎任何位置，尽管到目前为止，你只在赋值语句中看到过它们。</span><span class="sxs-lookup"><span data-stu-id="661e8-210">(The other two parameters are optional and are omitted in the code snippet.) Await expressions can appear almost anywhere in your code, even though up to now, you've only seen them as part of an assignment statement.</span></span> <span data-ttu-id="661e8-211">`Deserialize` 方法为泛型，这意味着必须为应从 JSON 文本创建的对象的类型提供类型参数。</span><span class="sxs-lookup"><span data-stu-id="661e8-211">The `Deserialize` method is *generic*, which means you must supply type arguments for what kind of objects should be created from the JSON text.</span></span> <span data-ttu-id="661e8-212">在此示例中，你要反序列化到 `List<Repository>`，这是另一个泛型对象，即 <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="661e8-212">In this example, you're deserializing to a `List<Repository>`, which is another generic object, the <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="661e8-213">`List<>` 类存储对象的集合。</span><span class="sxs-lookup"><span data-stu-id="661e8-213">The `List<>` class stores a collection of objects.</span></span> <span data-ttu-id="661e8-214">类型参数声明存储在 `List<>` 中的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="661e8-214">The type argument declares the type of objects stored in the `List<>`.</span></span> <span data-ttu-id="661e8-215">JSON 文本表示存储库对象的集合，因此类型参数为 `Repository`。</span><span class="sxs-lookup"><span data-stu-id="661e8-215">The JSON text represents a collection of repo objects, so the type argument is `Repository`.</span></span>

<span data-ttu-id="661e8-216">即将完成此部分的操作。</span><span class="sxs-lookup"><span data-stu-id="661e8-216">You're almost done with this section.</span></span> <span data-ttu-id="661e8-217">至此，你已将 JSON 数据转换成 C# 对象，让我们来显示每个存储库的名称。</span><span class="sxs-lookup"><span data-stu-id="661e8-217">Now that you've converted the JSON to C# objects, let's display the name of each repository.</span></span> <span data-ttu-id="661e8-218">将以下代码行：</span><span class="sxs-lookup"><span data-stu-id="661e8-218">Replace the lines that read:</span></span>

```csharp
var msg = await stringTask;   //**Deleted this
Console.Write(msg);
```

<span data-ttu-id="661e8-219">替换为：</span><span class="sxs-lookup"><span data-stu-id="661e8-219">with the following:</span></span>

```csharp
foreach (var repo in repositories)
    Console.WriteLine(repo.name);
```

<span data-ttu-id="661e8-220">编译并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="661e8-220">Compile and run the application.</span></span> <span data-ttu-id="661e8-221">将打印输出属于 .NET Foundation 的存储库的名称。</span><span class="sxs-lookup"><span data-stu-id="661e8-221">It will print out the names of the repositories that are part of the .NET Foundation.</span></span>

## <a name="controlling-serialization"></a><span data-ttu-id="661e8-222">控制序列化</span><span class="sxs-lookup"><span data-stu-id="661e8-222">Controlling Serialization</span></span>

<span data-ttu-id="661e8-223">在添加更多功能之前，让我们通过使用 `[JsonPropertyName]` 特性来处理 `name` 属性。</span><span class="sxs-lookup"><span data-stu-id="661e8-223">Before you add more features, let's address the `name` property by using the `[JsonPropertyName]` attribute.</span></span> <span data-ttu-id="661e8-224">对 repo.cs 中的 `name` 字段声明执行以下更改：</span><span class="sxs-lookup"><span data-stu-id="661e8-224">Make the following changes to the declaration of the `name` field in repo.cs:</span></span>

```csharp
[JsonPropertyName("name")]
public string Name { get; set; }
```

<span data-ttu-id="661e8-225">若要使用 `[JsonPropertyName]` 属性，需要将 <xref:System.Text.Json.Serialization> 命名空间添加到 `using` 指令：</span><span class="sxs-lookup"><span data-stu-id="661e8-225">To use `[JsonPropertyName]` attribute, you will need to add the <xref:System.Text.Json.Serialization> namespace to the `using` directives:</span></span>

```csharp
using System.Text.Json.Serialization;
```

<span data-ttu-id="661e8-226">此更改意味着需要更改用于在 program.cs 中写入每个存储库名称的代码：</span><span class="sxs-lookup"><span data-stu-id="661e8-226">This change means you need to change the code that writes the name of each repository in program.cs:</span></span>

```csharp
Console.WriteLine(repo.Name);
```

<span data-ttu-id="661e8-227">执行 `dotnet run`，以确保生成正确映射。</span><span class="sxs-lookup"><span data-stu-id="661e8-227">Execute `dotnet run` to make sure you've got the mappings correct.</span></span> <span data-ttu-id="661e8-228">应能看到与之前一样的输出。</span><span class="sxs-lookup"><span data-stu-id="661e8-228">You should see the same output as before.</span></span>

<span data-ttu-id="661e8-229">让我们在添加新功能前执行另一项更改。</span><span class="sxs-lookup"><span data-stu-id="661e8-229">Let's make one more change before adding new features.</span></span> <span data-ttu-id="661e8-230">`ProcessRepositories` 方法可以执行异步工作，并返回一组存储库。</span><span class="sxs-lookup"><span data-stu-id="661e8-230">The `ProcessRepositories` method can do the async work and return a collection of the repositories.</span></span> <span data-ttu-id="661e8-231">我们将使用此方法返回 `List<Repository>`，并将用于写入信息的代码移到 `Main` 方法中。</span><span class="sxs-lookup"><span data-stu-id="661e8-231">Let's return the `List<Repository>` from that method, and move the code that writes the information into the `Main` method.</span></span>

<span data-ttu-id="661e8-232">更改 `ProcessRepositories` 的签名，以返回可生成 `Repository` 对象列表的任务：</span><span class="sxs-lookup"><span data-stu-id="661e8-232">Change the signature of `ProcessRepositories` to return a task whose result is a list of `Repository` objects:</span></span>

```csharp
private static async Task<List<Repository>> ProcessRepositories()
```

<span data-ttu-id="661e8-233">然后，在处理 JSON 响应后仅返回存储库：</span><span class="sxs-lookup"><span data-stu-id="661e8-233">Then, just return the repositories after processing the JSON response:</span></span>

```csharp
var streamTask = client.GetStreamAsync("https://api.github.com/orgs/dotnet/repos");
var repositories = await JsonSerializer.DeserializeAsync<List<Repository>>(await streamTask);
return repositories;
```

<span data-ttu-id="661e8-234">编译器将生成返回内容的 `Task<T>` 对象，因为你已将此方法标记为 `async`。</span><span class="sxs-lookup"><span data-stu-id="661e8-234">The compiler generates the `Task<T>` object for the return because you've marked this method as `async`.</span></span>
<span data-ttu-id="661e8-235">然后，我们将把 `Main` 方法修改为，捕获这些结果并将每个存储库名称写入控制台。</span><span class="sxs-lookup"><span data-stu-id="661e8-235">Then, let's modify the `Main` method so that it captures those results and writes each repository name to the console.</span></span> <span data-ttu-id="661e8-236">现在，`Main` 方法如下所示：</span><span class="sxs-lookup"><span data-stu-id="661e8-236">Your `Main` method now looks like this:</span></span>

```csharp
public static async Task Main(string[] args)
{
    var repositories = await ProcessRepositories();

    foreach (var repo in repositories)
        Console.WriteLine(repo.Name);
}
```

## <a name="reading-more-information"></a><span data-ttu-id="661e8-237">读取详细信息</span><span class="sxs-lookup"><span data-stu-id="661e8-237">Reading More Information</span></span>

<span data-ttu-id="661e8-238">最后，让我们来处理 GitHub API 发送的 JSON 数据包中的其他一些属性。</span><span class="sxs-lookup"><span data-stu-id="661e8-238">Let's finish this by processing a few more of the properties in the JSON packet that gets sent from the GitHub API.</span></span> <span data-ttu-id="661e8-239">虽然你不想面面俱到，但添加其他一些属性将展示更多的 C# 语言功能。</span><span class="sxs-lookup"><span data-stu-id="661e8-239">You won't want to grab everything, but adding a few properties will demonstrate a few more features of the C# language.</span></span>

<span data-ttu-id="661e8-240">首先，将其他一些简单类型添加到 `Repository` 类定义中。</span><span class="sxs-lookup"><span data-stu-id="661e8-240">Let's start by adding a few more simple types to the `Repository` class definition.</span></span> <span data-ttu-id="661e8-241">将这些属性添加到此类：</span><span class="sxs-lookup"><span data-stu-id="661e8-241">Add these properties to that class:</span></span>

```csharp
[JsonPropertyName("description")]
public string Description { get; set; }

[JsonPropertyName("html_url")]
public Uri GitHubHomeUrl { get; set; }

[JsonPropertyName("homepage")]
public Uri Homepage { get; set; }

[JsonPropertyName("watchers")]
public int Watchers { get; set; }
```

<span data-ttu-id="661e8-242">这些属性内置转换功能，可从字符串类型（即 JSON 数据包所含）转换成目标类型。</span><span class="sxs-lookup"><span data-stu-id="661e8-242">These properties have built-in conversions from the string type (which is what the JSON packets contain) to the target type.</span></span> <span data-ttu-id="661e8-243">你可能是刚开始接触 <xref:System.Uri> 类型。</span><span class="sxs-lookup"><span data-stu-id="661e8-243">The <xref:System.Uri> type may be new to you.</span></span> <span data-ttu-id="661e8-244">它代表 URI（或在此示例中，代表 URL）。</span><span class="sxs-lookup"><span data-stu-id="661e8-244">It represents a URI, or in this case, a URL.</span></span> <span data-ttu-id="661e8-245">在有 `Uri` 和 `int` 类型的情况下，如果 JSON 数据包内的数据未转换成目标类型，那么序列化操作将会抛出异常。</span><span class="sxs-lookup"><span data-stu-id="661e8-245">In the case of the `Uri` and `int` types, if the JSON packet contains data that does not convert to the target type, the serialization action will throw an exception.</span></span>

<span data-ttu-id="661e8-246">添加这些元素后，将 `Main` 方法更新为显示它们：</span><span class="sxs-lookup"><span data-stu-id="661e8-246">Once you've added these, update the `Main` method to display those elements:</span></span>

```csharp
foreach (var repo in repositories)
{
    Console.WriteLine(repo.Name);
    Console.WriteLine(repo.Description);
    Console.WriteLine(repo.GitHubHomeUrl);
    Console.WriteLine(repo.Homepage);
    Console.WriteLine(repo.Watchers);
    Console.WriteLine();
}
```

<span data-ttu-id="661e8-247">最后一步，让我们添加最后一次推送操作的信息。</span><span class="sxs-lookup"><span data-stu-id="661e8-247">As a final step, let's add the information for the last push operation.</span></span> <span data-ttu-id="661e8-248">此信息按如下方式在 JSON 响应中进行格式化：</span><span class="sxs-lookup"><span data-stu-id="661e8-248">This information is formatted in this fashion in the JSON response:</span></span>

```json
2016-02-08T21:27:00Z
```

<span data-ttu-id="661e8-249">该格式为协调世界时 (UTC)，因此，你将获得一个 <xref:System.DateTime> 值，该值的 <xref:System.DateTime.Kind%2A> 属性为 <xref:System.DateTimeKind.Utc>。</span><span class="sxs-lookup"><span data-stu-id="661e8-249">That format is in Coordinated Universal Time (UTC) so you'll get a <xref:System.DateTime> value whose <xref:System.DateTime.Kind%2A> property is <xref:System.DateTimeKind.Utc>.</span></span> <span data-ttu-id="661e8-250">如果你倾向于以时区表示的日期，则需要编写自定义转换方法。</span><span class="sxs-lookup"><span data-stu-id="661e8-250">If you prefer a date represented in your time zone, you'll need to write a custom conversion method.</span></span> <span data-ttu-id="661e8-251">首先，定义一个 `public` 属性，该属性将保存 `Repository` 类中日期和时间的 UTC 表示形式，并定义一个 `LastPush` `readonly` 属性，该属性返回转换为本地时间的日期：</span><span class="sxs-lookup"><span data-stu-id="661e8-251">First, define a `public` property that will hold the UTC representation of the date and time in your `Repository` class and a `LastPush` `readonly` property that returns the date converted to local time:</span></span>

```csharp
[JsonPropertyName("pushed_at")]
public DateTime LastPushUtc { get; set; }

public DateTime LastPush => LastPushUtc.ToLocalTime();
```

<span data-ttu-id="661e8-252">让我们来看一下刚定义的新构造。</span><span class="sxs-lookup"><span data-stu-id="661e8-252">Let's go over the new constructs we just defined.</span></span> <span data-ttu-id="661e8-253">`LastPush` 属性使用 `get` 访问器的 expression-bodied member 进行定义。</span><span class="sxs-lookup"><span data-stu-id="661e8-253">The `LastPush` property is defined using an *expression-bodied member* for the `get` accessor.</span></span> <span data-ttu-id="661e8-254">不存在 `set` 访问器。</span><span class="sxs-lookup"><span data-stu-id="661e8-254">There is no `set` accessor.</span></span> <span data-ttu-id="661e8-255">省略 `set` 访问器就是在 C# 中定义只读属性的方式。</span><span class="sxs-lookup"><span data-stu-id="661e8-255">Omitting the `set` accessor is how you define a *read-only* property in C#.</span></span> <span data-ttu-id="661e8-256">（是的，可以在 C# 中创建 *只写* 属性，但属性值受限。）</span><span class="sxs-lookup"><span data-stu-id="661e8-256">(Yes, you can create *write-only* properties in C#, but their value is limited.)</span></span>

<span data-ttu-id="661e8-257">最后，在控制台中再添加一个输出语句，然后就可以再次生成并运行此应用程序：</span><span class="sxs-lookup"><span data-stu-id="661e8-257">Finally, add one more output statement in the console, and you're ready to build and run this app again:</span></span>

```csharp
Console.WriteLine(repo.LastPush);
```

<span data-ttu-id="661e8-258">你的版本现在应与[已完成的示例](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient)匹配。</span><span class="sxs-lookup"><span data-stu-id="661e8-258">Your version should now match the [finished sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient).</span></span>

## <a name="conclusion"></a><span data-ttu-id="661e8-259">结束语</span><span class="sxs-lookup"><span data-stu-id="661e8-259">Conclusion</span></span>

<span data-ttu-id="661e8-260">此教程介绍了如何发出 Web 请求、分析结果，以及如何显示这些结果的属性。</span><span class="sxs-lookup"><span data-stu-id="661e8-260">This tutorial showed you how to make web requests, parse the result, and display properties of those results.</span></span> <span data-ttu-id="661e8-261">你也已经在项目中将新的包添加为依赖项，</span><span class="sxs-lookup"><span data-stu-id="661e8-261">You've also added new packages as dependencies in your project.</span></span> <span data-ttu-id="661e8-262">并已了解一些支持面向对象的技术的 C# 语言功能。</span><span class="sxs-lookup"><span data-stu-id="661e8-262">You've seen some of the features of the C# language that support object-oriented techniques.</span></span>

<a name="dotnet-restore-note"></a>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
