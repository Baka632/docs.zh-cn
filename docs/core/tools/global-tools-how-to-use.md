---
title: 教程：安装和使用 .NET 全局工具
description: 了解如何安装和使用 .NET 工具作为全局工具。
ms.topic: tutorial
ms.date: 02/12/2020
ms.openlocfilehash: 01b773516da92fb16fb0f67fc6617e0c70d17c9d
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2020
ms.locfileid: "94633889"
---
# <a name="tutorial-install-and-use-a-net-global-tool-using-the-net-cli"></a><span data-ttu-id="8fb8c-103">教程：使用 .NET CLI 安装和使用 .NET 全局工具</span><span class="sxs-lookup"><span data-stu-id="8fb8c-103">Tutorial: Install and use a .NET global tool using the .NET CLI</span></span>

<span data-ttu-id="8fb8c-104"> 本文适用于： ✔️ .NET Core 2.1 SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="8fb8c-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="8fb8c-105">本教程介绍如何安装和使用全局工具。</span><span class="sxs-lookup"><span data-stu-id="8fb8c-105">This tutorial teaches you how to install and use a global tool.</span></span> <span data-ttu-id="8fb8c-106">使用在[本系列的第一个教程](global-tools-how-to-create.md)中创建的工具。</span><span class="sxs-lookup"><span data-stu-id="8fb8c-106">You use a tool that you create in the [first tutorial of this series](global-tools-how-to-create.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8fb8c-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="8fb8c-107">Prerequisites</span></span>

* <span data-ttu-id="8fb8c-108">完成[本系列的第一个教程](global-tools-how-to-create.md)。</span><span class="sxs-lookup"><span data-stu-id="8fb8c-108">Complete the [first tutorial of this series](global-tools-how-to-create.md).</span></span>

## <a name="use-the-tool-as-a-global-tool"></a><span data-ttu-id="8fb8c-109">使用该工具作为全局工具</span><span class="sxs-lookup"><span data-stu-id="8fb8c-109">Use the tool as a global tool</span></span>

1. <span data-ttu-id="8fb8c-110">通过运行 microsoft.botsay 项目文件夹中的 [dotnet tool install](dotnet-tool-install.md) 命令，从包中安装该工具  ：</span><span class="sxs-lookup"><span data-stu-id="8fb8c-110">Install the tool from the package by running the [dotnet tool install](dotnet-tool-install.md) command in the *microsoft.botsay* project folder:</span></span>

   ```dotnetcli
   dotnet tool install --global --add-source ./nupkg microsoft.botsay
   ```

   <span data-ttu-id="8fb8c-111">`--global` 参数指示 .NET CLI 将工具二进制文件安装在自动添加到 PATH 环境变量的默认位置中。</span><span class="sxs-lookup"><span data-stu-id="8fb8c-111">The `--global` parameter tells the .NET CLI to install the tool binaries in a default location that is automatically added to the PATH environment variable.</span></span>

   <span data-ttu-id="8fb8c-112">`--add-source` 参数指示 .NET CLI 临时使用 ./nupkg 目录作为 NuGet 包的附加源数据源。</span><span class="sxs-lookup"><span data-stu-id="8fb8c-112">The `--add-source` parameter tells the .NET CLI to temporarily use the *./nupkg* directory as an additional source feed for NuGet packages.</span></span> <span data-ttu-id="8fb8c-113">为包提供了唯一名称，以确保它仅位于 ./nupkg  目录中，而不是在 Nuget.org 站点上。</span><span class="sxs-lookup"><span data-stu-id="8fb8c-113">You gave your package a unique name to make sure that it will only be found in the *./nupkg* directory, not on the Nuget.org site.</span></span>

   <span data-ttu-id="8fb8c-114">输出显示用于调用该工具和已安装的版本的命令：</span><span class="sxs-lookup"><span data-stu-id="8fb8c-114">The output shows the command used to call the tool and the version installed:</span></span>

   ```console
   You can invoke the tool using the following command: botsay
   Tool 'microsoft.botsay' (version '1.0.0') was successfully installed.
   ```

1. <span data-ttu-id="8fb8c-115">调用该工具：</span><span class="sxs-lookup"><span data-stu-id="8fb8c-115">Invoke the tool:</span></span>

   ```console
   botsay hello from the bot
   ```

   > [!NOTE]
   > <span data-ttu-id="8fb8c-116">如果此命令失败，则可能需要打开新终端来刷新 PATH。</span><span class="sxs-lookup"><span data-stu-id="8fb8c-116">If this command fails, you may need to open a new terminal to refresh the PATH.</span></span>

1. <span data-ttu-id="8fb8c-117">通过运行 [dotnet tool uninstall](dotnet-tool-uninstall.md) 命令来删除该工具：</span><span class="sxs-lookup"><span data-stu-id="8fb8c-117">Remove the tool by running the [dotnet tool uninstall](dotnet-tool-uninstall.md) command:</span></span>

   ```dotnetcli
   dotnet tool uninstall -g microsoft.botsay
   ```

## <a name="use-the-tool-as-a-global-tool-installed-in-a-custom-location"></a><span data-ttu-id="8fb8c-118">使用该工具作为自定义位置中安装的全局工具</span><span class="sxs-lookup"><span data-stu-id="8fb8c-118">Use the tool as a global tool installed in a custom location</span></span>

1. <span data-ttu-id="8fb8c-119">从包中安装该工具。</span><span class="sxs-lookup"><span data-stu-id="8fb8c-119">Install the tool from the package.</span></span>

   <span data-ttu-id="8fb8c-120">在 Windows 上：</span><span class="sxs-lookup"><span data-stu-id="8fb8c-120">On Windows:</span></span>

   ```dotnetcli
   dotnet tool install --tool-path c:\dotnet-tools --add-source ./nupkg microsoft.botsay
   ```

   <span data-ttu-id="8fb8c-121">在 Linux 或 macOS 上：</span><span class="sxs-lookup"><span data-stu-id="8fb8c-121">On Linux or macOS:</span></span>

   ```dotnetcli
   dotnet tool install --tool-path ~/bin --add-source ./nupkg microsoft.botsay
   ```

   <span data-ttu-id="8fb8c-122">`--tool-path` 参数指示 .NET CLI 将工具二进制文件安装在指定位置中。</span><span class="sxs-lookup"><span data-stu-id="8fb8c-122">The `--tool-path` parameter tells the .NET CLI to install the tool binaries in the specified location.</span></span> <span data-ttu-id="8fb8c-123">如果目录不存在，则会创建该目录。</span><span class="sxs-lookup"><span data-stu-id="8fb8c-123">If the directory doesn't exist, it is created.</span></span> <span data-ttu-id="8fb8c-124">此目录不会自动添加到 PATH 环境变量中。</span><span class="sxs-lookup"><span data-stu-id="8fb8c-124">This directory is not automatically added to the PATH environment variable.</span></span>

   <span data-ttu-id="8fb8c-125">输出显示用于调用该工具和已安装的版本的命令：</span><span class="sxs-lookup"><span data-stu-id="8fb8c-125">The output shows the command used to call the tool and the version installed:</span></span>

   ```console
   You can invoke the tool using the following command: botsay
   Tool 'microsoft.botsay' (version '1.0.0') was successfully installed.
   ```

1. <span data-ttu-id="8fb8c-126">调用该工具：</span><span class="sxs-lookup"><span data-stu-id="8fb8c-126">Invoke the tool:</span></span>

   <span data-ttu-id="8fb8c-127">在 Windows 上：</span><span class="sxs-lookup"><span data-stu-id="8fb8c-127">On Windows:</span></span>

   ```console
   c:\dotnet-tools\botsay hello from the bot
   ```

   <span data-ttu-id="8fb8c-128">在 Linux 或 macOS 上：</span><span class="sxs-lookup"><span data-stu-id="8fb8c-128">On Linux or macOS:</span></span>

   ```console
   ~/bin/botsay hello from the bot
   ```

1. <span data-ttu-id="8fb8c-129">通过运行 [dotnet tool uninstall](dotnet-tool-uninstall.md) 命令来删除该工具：</span><span class="sxs-lookup"><span data-stu-id="8fb8c-129">Remove the tool by running the [dotnet tool uninstall](dotnet-tool-uninstall.md) command:</span></span>

   <span data-ttu-id="8fb8c-130">在 Windows 上：</span><span class="sxs-lookup"><span data-stu-id="8fb8c-130">On Windows:</span></span>

   ```dotnetcli
   dotnet tool uninstall --tool-path c:\dotnet-tools microsoft.botsay
   ```

   <span data-ttu-id="8fb8c-131">在 Linux 或 macOS 上：</span><span class="sxs-lookup"><span data-stu-id="8fb8c-131">On Linux or macOS:</span></span>

   ```dotnetcli
   dotnet tool uninstall --tool-path ~/bin microsoft.botsay
   ```

## <a name="troubleshoot"></a><span data-ttu-id="8fb8c-132">疑难解答</span><span class="sxs-lookup"><span data-stu-id="8fb8c-132">Troubleshoot</span></span>

<span data-ttu-id="8fb8c-133">如果在学习本教程时收到错误消息，请参阅[排查 .NET 工具使用问题](troubleshoot-usage-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="8fb8c-133">If you get an error message while following the tutorial, see [Troubleshoot .NET tool usage issues](troubleshoot-usage-issues.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="8fb8c-134">后续步骤</span><span class="sxs-lookup"><span data-stu-id="8fb8c-134">Next steps</span></span>

<span data-ttu-id="8fb8c-135">在本教程中，已将工具作为全局工具安装和使用。</span><span class="sxs-lookup"><span data-stu-id="8fb8c-135">In this tutorial, you installed and used a tool as a global tool.</span></span> <span data-ttu-id="8fb8c-136">若要安装和使用与本地工具相同的工具，请转到下一教程。</span><span class="sxs-lookup"><span data-stu-id="8fb8c-136">To install and use the same tool as a local tool, advance to the next tutorial.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="8fb8c-137">安装和使用本地工具</span><span class="sxs-lookup"><span data-stu-id="8fb8c-137">Install and use local tools</span></span>](local-tools-how-to-use.md)
