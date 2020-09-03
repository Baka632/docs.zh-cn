---
title: 使用 Visual Studio for Mac 发布 .NET Core 控制台应用程序
description: 发布应用程序会创建运行 .NET Core 应用程序所需的一组文件。
ms.date: 06/08/2020
ms.openlocfilehash: ec6b867f145ffdea491187de3745149f2cebd8dd
ms.sourcegitcommit: b9122d1af21898eaba81e990c70fef46fef74a8d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2020
ms.locfileid: "88867537"
---
# <a name="tutorial-publish-a-net-core-console-application-using-visual-studio-for-mac"></a>教程：使用 Visual Studio for Mac 发布 .NET Core 控制台应用程序

本教程演示如何发布控制台应用，以便其他用户可以运行它。 发布应用程序会创建运行应用程序所需的一组文件。 若要部署文件，请将文件复制到目标计算机。

## <a name="prerequisites"></a>先决条件

- 本教程适用于在[使用 Visual Studio for Mac 创建 .NET Core 控制台应用程序](with-visual-studio-mac.md)中创建的控制台应用。

## <a name="publish-the-app"></a>发布应用

1. 启动 Visual Studio for Mac。

1. 打开在[使用 Visual Studio for Mac 创建 .NET Core 控制台应用程序](with-visual-studio-mac.md)中创建的 HelloWorld 项目。

1. 请确保 Visual Studio 生成的是应用程序的发布版本。 必要时，将工具栏上的生成配置设置从“调试”更改为“发布”。

   :::image type="content" source="media/publishing-with-visual-studio-mac/toolbar-release.png" alt-text="选定发布版本的 Visual Studio 工具栏":::

1. 从主菜单中，选择“生成” > “发布到文件夹...”。

   :::image type="content" source="media/publishing-with-visual-studio-mac/publish-context-menu.png" alt-text="Visual Studio 发布上下文菜单":::

1. 在“发布到文件夹”对话框中，选择“发布” 。

   :::image type="content" source="media/publishing-with-visual-studio-mac/publish-to-folder-dialog.png" alt-text="Visual Studio“发布到文件夹”对话框":::

   此时会打开发布文件夹，其中显示已创建的文件。

   :::image type="content" source="media/publishing-with-visual-studio-mac/publish-folder.png" alt-text="发布文件夹":::

1. 选择齿轮图标，并从上下文菜单中选择“将“发布”复制为路径名称”。

   :::image type="content" source="media/publishing-with-visual-studio-mac/copy-path.png" alt-text="将路径复制到发布文件夹":::

## <a name="inspect-the-files"></a>检查文件

发布过程中会创建依赖于框架的部署，在此类部署中，已发布的应用程序在已安装 .NET Core 运行时的计算机上运行。 用户可以通过从命令提示符运行 `dotnet HelloWorld.dll` 命令来运行发布的应用。

如上图所示，已发布的输出包括以下文件：

* HelloWorld.deps.json

  这是应用程序的运行时依赖项文件。 它定义了运行应用程序所需的 .NET Core 组件和库（包括包含该应用程序的动态链接库）。 有关详细信息，请参阅[运行时配置文件](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md)。

* HelloWorld.dll

   这是应用程序的[依赖于框架的部署](../deploying/deploy-with-cli.md#framework-dependent-deployment)版本。 若要执行此动态链接库，请在命令提示符处输入 `dotnet HelloWorld.dll`。 这种运行应用的方法适用于安装了 .NET Core 运行时的任何平台。

* HelloWorld.pdb（对于部署是可选的）

   这是调试符号文件。 尽管应在需要调试应用程序的已发布版本时保存此文件，但无需将此文件与应用程序一起部署。

* HelloWorld.runtimeconfig.json

   这是应用程序的运行时配置文件。 它标识用于运行应用程序的 .NET Core 版本。 还可向其添加配置选项。 有关详细信息，请参阅 [.NET Core 运行时配置设置](../run-time-config/index.md#runtimeconfigjson)。

## <a name="run-the-published-app"></a>运行已发布的应用

1. 打开终端并导航到发布文件夹。 为此，请输入 `cd`，然后粘贴前面复制的路径。 例如：

   ```console
   cd ~/Projects/HelloWorld/HelloWorld/bin/Release/netcoreapp3.1/publish/
   ```

1. 使用 `dotnet` 命令运行应用：

   1. 输入 `dotnet HelloWorld.dll`，然后按 <kbd>Enter</kbd>。

   1. 输入一个名字以响应提示，并按任意键退出。

## <a name="additional-resources"></a>其他资源

- [.NET Core 应用程序部署](../deploying/index.md)

## <a name="next-steps"></a>后续步骤

在本教程中，你发布了一个控制台应用。 在下一教程中，你将创建类库。

> [!div class="nextstepaction"]
> [使用 Visual Studio for Mac 创建 .NET Standard 库](library-with-visual-studio-mac.md)
