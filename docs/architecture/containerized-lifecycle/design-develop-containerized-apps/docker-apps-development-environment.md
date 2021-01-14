---
title: Docker 应用的开发环境
description: 了解支持 Docker 开发生命周期的最重要的开发工具选项。
ms.date: 01/06/2021
ms.openlocfilehash: c6c4a1fda41131c00ba87808ed408f1d3250cabf
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970520"
---
# <a name="development-environment-for-docker-apps"></a><span data-ttu-id="49b6c-103">Docker 应用的开发环境</span><span class="sxs-lookup"><span data-stu-id="49b6c-103">Development environment for Docker apps</span></span>

## <a name="development-tools-choices-ide-or-editor"></a><span data-ttu-id="49b6c-104">开发工具选择：IDE 或编辑器</span><span class="sxs-lookup"><span data-stu-id="49b6c-104">Development tools choices: IDE or editor</span></span>

<span data-ttu-id="49b6c-105">无论你更青睐内容丰富、功能强大的 IDE 还是灵活轻量的编辑器，Microsoft 在开发 Docker 应用程序时都能满足你的需求。</span><span class="sxs-lookup"><span data-stu-id="49b6c-105">No matter if you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has you covered when it comes to developing Docker applications.</span></span>

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a><span data-ttu-id="49b6c-106">Visual Studio Code 和 Docker CLI（适用于 Mac、Linux 和 Windows 的跨平台工具）</span><span class="sxs-lookup"><span data-stu-id="49b6c-106">Visual Studio Code and Docker CLI (cross-platform tools for Mac, Linux, and Windows)</span></span>

<span data-ttu-id="49b6c-107">如果更青睐支持任何开发语言的轻量级跨平台编辑器，可以使用 Visual Studio Code 和 Docker CLI。</span><span class="sxs-lookup"><span data-stu-id="49b6c-107">If you prefer a lightweight, cross-platform editor supporting any development language, you can use Visual Studio Code and Docker CLI.</span></span> <span data-ttu-id="49b6c-108">这些产品提供简单而可靠的体验，这对简化开发人员工作流至关重要。</span><span class="sxs-lookup"><span data-stu-id="49b6c-108">These products provide a simple yet robust experience, which is critical for streamlining the developer workflow.</span></span> <span data-ttu-id="49b6c-109">安装“用于 Mac 的 Docker”或“用于 Windows 的 Docker”（开发环境），Docker 开发人员即可使用单个 Docker CLI 为 Windows 或 Linux（运行时环境）构建应用。</span><span class="sxs-lookup"><span data-stu-id="49b6c-109">By installing "Docker for Mac" or "Docker for Windows" (development environment), Docker developers can use a single Docker CLI to build apps for both Windows or Linux (runtime environment).</span></span> <span data-ttu-id="49b6c-110">此外，Visual Studio Code 还支持 Docker 扩展（例如适用于 Dockerfile 的 IntelliSense）和在编辑器中运行 Docker 命令的快捷任务。</span><span class="sxs-lookup"><span data-stu-id="49b6c-110">Plus, Visual Studio Code supports extensions for Docker with IntelliSense for Dockerfiles and shortcut-tasks to run Docker commands from the editor.</span></span>

> [!NOTE]
> <span data-ttu-id="49b6c-111">要下载 Visual Studio Code，请转到 <https://code.visualstudio.com/download>。</span><span class="sxs-lookup"><span data-stu-id="49b6c-111">To download Visual Studio Code, go to <https://code.visualstudio.com/download>.</span></span>
>
> <span data-ttu-id="49b6c-112">要下载用于 Mac 和 Windows 的 Docker，请转到 <https://www.docker.com/products/docker>。</span><span class="sxs-lookup"><span data-stu-id="49b6c-112">To download Docker for Mac and Windows, go to <https://www.docker.com/products/docker>.</span></span>

### <a name="visual-studio-with-docker-tools-windows-development-machine"></a><span data-ttu-id="49b6c-113">附带 Docker 工具的 Visual Studio（Windows 开发计算机）</span><span class="sxs-lookup"><span data-stu-id="49b6c-113">Visual Studio with Docker Tools (Windows development machine)</span></span>

<span data-ttu-id="49b6c-114">建议使用 Visual Studio 2019 并启用内置 Docker 工具。</span><span class="sxs-lookup"><span data-stu-id="49b6c-114">It's recommend that you use Visual Studio 2019 with the built-in Docker Tools enabled.</span></span> <span data-ttu-id="49b6c-115">使用 Visual Studio，可以直接在所选的 Docker 环境中开发、运行和验证应用程序。</span><span class="sxs-lookup"><span data-stu-id="49b6c-115">With Visual Studio, you can develop, run, and validate your applications directly in the chosen Docker environment.</span></span> <span data-ttu-id="49b6c-116">按 F5，即可直接在 Docker 主机中调试应用程序（单个容器或多个容器）；也可以按 Ctrl+F5，无需重新生成容器，即可编辑并刷新应用。</span><span class="sxs-lookup"><span data-stu-id="49b6c-116">Press F5 to debug your application (single container or multiple containers) directly in a Docker host, or press Ctrl+F5 to edit and refresh your app without having to rebuild the container.</span></span> <span data-ttu-id="49b6c-117">对于创建用于 Linux 或 Windows 的 Docker 容器的 Windows 开发人员，这是最简单且功能最强大的选择。</span><span class="sxs-lookup"><span data-stu-id="49b6c-117">It's the simplest and most powerful choice for Windows developers to create Docker containers for Linux or Windows.</span></span>

### <a name="visual-studio-for-mac-mac-development-machine"></a><span data-ttu-id="49b6c-118">Visual Studio for Mac（Mac 开发计算机）</span><span class="sxs-lookup"><span data-stu-id="49b6c-118">Visual Studio for Mac (Mac development machine)</span></span>

<span data-ttu-id="49b6c-119">开发基于 Docker 的应用程序时，可以使用 [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)。</span><span class="sxs-lookup"><span data-stu-id="49b6c-119">You can use [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) when developing Docker-based applications.</span></span> <span data-ttu-id="49b6c-120">与 Visual Studio Code for Mac 相比，Visual Studio for Mac 提供了更丰富的 IDE。</span><span class="sxs-lookup"><span data-stu-id="49b6c-120">Visual Studio for Mac offers a richer IDE when compared to Visual Studio Code for Mac.</span></span>

## <a name="language-and-framework-choices"></a><span data-ttu-id="49b6c-121">选择语言和框架</span><span class="sxs-lookup"><span data-stu-id="49b6c-121">Language and framework choices</span></span>

<span data-ttu-id="49b6c-122">可以使用 Microsoft 工具和大多数现代语言开发 Docker 应用程序。</span><span class="sxs-lookup"><span data-stu-id="49b6c-122">You can develop Docker applications using Microsoft tools with most modern languages.</span></span> <span data-ttu-id="49b6c-123">以下是初始列表，但不局限于该表：</span><span class="sxs-lookup"><span data-stu-id="49b6c-123">The following is an initial list, but you're not limited to it:</span></span>

- <span data-ttu-id="49b6c-124">.NET 和 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="49b6c-124">.NET and ASP.NET Core</span></span>
- <span data-ttu-id="49b6c-125">Node.js</span><span class="sxs-lookup"><span data-stu-id="49b6c-125">Node.js</span></span>
- <span data-ttu-id="49b6c-126">Go</span><span class="sxs-lookup"><span data-stu-id="49b6c-126">Go</span></span>
- <span data-ttu-id="49b6c-127">Java</span><span class="sxs-lookup"><span data-stu-id="49b6c-127">Java</span></span>
- <span data-ttu-id="49b6c-128">Ruby</span><span class="sxs-lookup"><span data-stu-id="49b6c-128">Ruby</span></span>
- <span data-ttu-id="49b6c-129">Python</span><span class="sxs-lookup"><span data-stu-id="49b6c-129">Python</span></span>

<span data-ttu-id="49b6c-130">基本上可以使用由 Linux 或 Windows 中的 Docker 支持的任何现代语言。</span><span class="sxs-lookup"><span data-stu-id="49b6c-130">Basically, you can use any modern language supported by Docker in Linux or Windows.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="49b6c-131">[上一页](deploy-azure-kubernetes-service.md)
>[下一页](docker-apps-inner-loop-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="49b6c-131">[Previous](deploy-azure-kubernetes-service.md)
[Next](docker-apps-inner-loop-workflow.md)</span></span>
