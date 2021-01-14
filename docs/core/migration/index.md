---
title: 从 project.json 迁移 .NET Core
description: 了解如何使用 project.json 迁移较旧的 .NET Core 项目
ms.date: 07/19/2017
ms.openlocfilehash: 28da1723ed91d169305c2865c5346b8ce6e0b3d1
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2021
ms.locfileid: "98189696"
---
# <a name="migrating-net-core-projects-from-projectjson"></a><span data-ttu-id="175ea-103">从 project.json 迁移 .NET Core 项目</span><span class="sxs-lookup"><span data-stu-id="175ea-103">Migrating .NET Core projects from project.json</span></span>

<span data-ttu-id="175ea-104">本文档介绍了以下三种适用于 .NET Core 项目的迁移方案：</span><span class="sxs-lookup"><span data-stu-id="175ea-104">This document covers the following three migration scenarios for .NET Core projects:</span></span>

1. [<span data-ttu-id="175ea-105">从 project.json 的一个最新有效架构迁移到 csproj</span><span class="sxs-lookup"><span data-stu-id="175ea-105">Migration from a valid latest schema of *project.json* to *csproj*</span></span>](#migration-from-projectjson-to-csproj)
2. [<span data-ttu-id="175ea-106">从 DNX 迁移到 csproj</span><span class="sxs-lookup"><span data-stu-id="175ea-106">Migration from DNX to csproj</span></span>](#migration-from-dnx-to-csproj)
3. [<span data-ttu-id="175ea-107">从 RC3 和以前的 .NET Core csproj 项目迁移到最终格式</span><span class="sxs-lookup"><span data-stu-id="175ea-107">Migration from RC3 and previous .NET Core csproj projects to the final format</span></span>](#migration-from-earlier-net-core-csproj-formats-to-rtm-csproj)

<span data-ttu-id="175ea-108">本文档仅适用于使用 project.json 的较旧的 .NET Core 项目。</span><span class="sxs-lookup"><span data-stu-id="175ea-108">This document is only applicable to older .NET Core projects that use project.json.</span></span> <span data-ttu-id="175ea-109">它不适用于从 .NET Framework 迁移到 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="175ea-109">It does not apply to migrating from .NET Framework to .NET Core.</span></span>

## <a name="migration-from-projectjson-to-csproj"></a><span data-ttu-id="175ea-110">从 project.json 迁移到 csproj</span><span class="sxs-lookup"><span data-stu-id="175ea-110">Migration from project.json to csproj</span></span>

<span data-ttu-id="175ea-111">可使用以下任一方法从 project.json 迁移到 .csproj：</span><span class="sxs-lookup"><span data-stu-id="175ea-111">Migration from *project.json* to *.csproj* can be done using one of the following methods:</span></span>

- [<span data-ttu-id="175ea-112">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="175ea-112">Visual Studio</span></span>](#visual-studio)
- [<span data-ttu-id="175ea-113">dotnet migrate 命令行工具</span><span class="sxs-lookup"><span data-stu-id="175ea-113">dotnet migrate command-line tool</span></span>](#dotnet-migrate)

<span data-ttu-id="175ea-114">这两种方法使用同一个基础引擎来迁移项目，因此，二者结果相同。</span><span class="sxs-lookup"><span data-stu-id="175ea-114">Both methods use the same underlying engine to migrate the projects, so the results will be the same for both.</span></span> <span data-ttu-id="175ea-115">在大多数情况下，只需使用这两种方法中的一种将 project.json 迁移到 csproj，而无需进一步对项目文件执行手动编辑。</span><span class="sxs-lookup"><span data-stu-id="175ea-115">In most cases, using one of these two ways to migrate the *project.json* to *csproj* is the only thing that is needed, and no further manual editing of the project file is necessary.</span></span> <span data-ttu-id="175ea-116">生成的 .csproj 文件的名称与包含目录名称相同。</span><span class="sxs-lookup"><span data-stu-id="175ea-116">The resulting *.csproj* file will be named the same as the containing directory name.</span></span>

### <a name="visual-studio"></a><span data-ttu-id="175ea-117">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="175ea-117">Visual Studio</span></span>

<span data-ttu-id="175ea-118">在 Visual Studio 2017 或 Visual Studio 2019 版本 16.2 及更早版本中打开 .xproj 文件或引用 .xproj 文件的解决方案文件时，将显示“单向升级”对话框。</span><span class="sxs-lookup"><span data-stu-id="175ea-118">When you open an *.xproj* file or a solution file that references *.xproj* files in Visual Studio 2017 or Visual Studio 2019 version 16.2 and earlier, the **One-way upgrade** dialog appears.</span></span> <span data-ttu-id="175ea-119">该对话框将显示要迁移的项目。</span><span class="sxs-lookup"><span data-stu-id="175ea-119">The dialog displays the projects to be migrated.</span></span> <span data-ttu-id="175ea-120">如果打开解决方案文件，则将列出解决方案文件中指定的所有项目。</span><span class="sxs-lookup"><span data-stu-id="175ea-120">If you open a solution file, all the projects specified in the solution file are listed.</span></span> <span data-ttu-id="175ea-121">查看要迁移的项目的列表，然后选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="175ea-121">Review the list of projects to be migrated and select **OK**.</span></span>

![单向升级对话框，其中显示要迁移的项目的列表](media/one-way-upgrade.jpg)

<span data-ttu-id="175ea-123">Visual Studio 自动迁移所选的项目。</span><span class="sxs-lookup"><span data-stu-id="175ea-123">Visual Studio migrates the selected projects automatically.</span></span> <span data-ttu-id="175ea-124">迁移解决方案时，如果不选择所有项目，则会显示相同的对话框，要求升级该解决方案的其余项目。</span><span class="sxs-lookup"><span data-stu-id="175ea-124">When migrating a solution, if you don't choose all projects, the same dialog appears asking you to upgrade the remaining projects from that solution.</span></span> <span data-ttu-id="175ea-125">迁移项目后，可通过在“解决方案资源管理器”窗口中右键单击该项目，并选择“编辑 \<project name>.csproj”来查看和修改其内容 。</span><span class="sxs-lookup"><span data-stu-id="175ea-125">After the project is migrated, you can see and modify its contents by right-clicking the project in the **Solution Explorer** window and selecting **Edit \<project name>.csproj**.</span></span>

<span data-ttu-id="175ea-126">已迁移的文件（project.json、global.json、.xproj 和解决方案文件）会移动到“备份”文件夹。</span><span class="sxs-lookup"><span data-stu-id="175ea-126">Files that were migrated (*project.json*, *global.json*, *.xproj*, and solution file) are moved to a *Backup* folder.</span></span> <span data-ttu-id="175ea-127">迁移的解决方案文件会升级到 Visual Studio 2017 或 Visual Studio 2019，并且将无法在 Visual Studio 2015 或更早版本中打开该解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="175ea-127">The migrated solution file is upgraded to Visual Studio 2017 or Visual Studio 2019 and you won't be able to open that solution file in Visual Studio 2015 or earlier versions.</span></span> <span data-ttu-id="175ea-128">还会保存并自动打开名为 UpgradeLog.htm 的文件，该文件包含迁移报告。</span><span class="sxs-lookup"><span data-stu-id="175ea-128">A file named *UpgradeLog.htm* that contains a migration report is also saved and opened automatically.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="175ea-129">在 Visual Studio 2019 版本 16.3 和更高版本中，无法加载或迁移 .xproj 文件。</span><span class="sxs-lookup"><span data-stu-id="175ea-129">In Visual Studio 2019 version 16.3 and later, you cannot load or migrate an *.xproj* file.</span></span> <span data-ttu-id="175ea-130">此外，Visual Studio 2015 也不提供 .xproj 文件迁移的功能。</span><span class="sxs-lookup"><span data-stu-id="175ea-130">Additionally, Visual Studio 2015 doesn't provide the ability to migrate an *.xproj* file.</span></span> <span data-ttu-id="175ea-131">如果使用以上任一 Visual Studio 版本，请安装适当版本的 Visual Studio，或使用下述命令行迁移工具。</span><span class="sxs-lookup"><span data-stu-id="175ea-131">If you're using one of these Visual Studio versions, either install a suitable version of Visual Studio, or use the command line migration tool that's described next.</span></span>

### <a name="dotnet-migrate"></a><span data-ttu-id="175ea-132">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="175ea-132">dotnet migrate</span></span>

<span data-ttu-id="175ea-133">在该命令行方案中，可以使用 [`dotnet migrate`](../tools/dotnet-migrate.md) 命令。</span><span class="sxs-lookup"><span data-stu-id="175ea-133">In the command-line scenario, you can use the [`dotnet migrate`](../tools/dotnet-migrate.md) command.</span></span> <span data-ttu-id="175ea-134">它会按顺序迁移项目、解决方案或一组文件夹，具体取决于所找到的项。</span><span class="sxs-lookup"><span data-stu-id="175ea-134">It migrates a project, a solution, or a set of folders in that order, depending on which ones were found.</span></span> <span data-ttu-id="175ea-135">迁移项目时，将迁移项目及其所有依赖项。</span><span class="sxs-lookup"><span data-stu-id="175ea-135">When you migrate a project, the project and all its dependencies are migrated.</span></span>

<span data-ttu-id="175ea-136">已迁移的文件（project.json、global.json 和 .xproj）会移动到“备份”文件夹。</span><span class="sxs-lookup"><span data-stu-id="175ea-136">Files that were migrated (*project.json*, *global.json*, and *.xproj*) are moved to a *backup* folder.</span></span>

> [!NOTE]
> <span data-ttu-id="175ea-137">如果使用 Visual Studio Code，则 `dotnet migrate` 命令不会修改 tasks.json 等 Visual Studio Code 专属文件。</span><span class="sxs-lookup"><span data-stu-id="175ea-137">If you are using Visual Studio Code, the `dotnet migrate` command does not modify Visual Studio Code-specific files such as *tasks.json*.</span></span> <span data-ttu-id="175ea-138">需要手动更改这些文件。</span><span class="sxs-lookup"><span data-stu-id="175ea-138">These files need to be changed manually.</span></span>
> <span data-ttu-id="175ea-139">如果使用 Visual Studio 以外的编辑器或集成开发环境 (IDE)，也是如此。</span><span class="sxs-lookup"><span data-stu-id="175ea-139">This is also true if you are using an editor or Integrated Development Environment (IDE) other than Visual Studio.</span></span>

<span data-ttu-id="175ea-140">请参阅 [project.json 和 csproj 属性之间的映射](../tools/project-json-to-csproj.md)，了解 project.json 和 csproj 格式的比较情况。 </span><span class="sxs-lookup"><span data-stu-id="175ea-140">See [A mapping between project.json and csproj properties](../tools/project-json-to-csproj.md) for a comparison of *project.json* and *.csproj* formats.</span></span>

<span data-ttu-id="175ea-141">如果看到错误消息：</span><span class="sxs-lookup"><span data-stu-id="175ea-141">If you get an error:</span></span>

> <span data-ttu-id="175ea-142">找不到匹配命令 dotnet-migrate 的可执行文件</span><span class="sxs-lookup"><span data-stu-id="175ea-142">No executable found matching command dotnet-migrate</span></span>

<span data-ttu-id="175ea-143">请运行 `dotnet --version` 查看所使用的版本。</span><span class="sxs-lookup"><span data-stu-id="175ea-143">Run `dotnet --version` to see which version you are using.</span></span> <span data-ttu-id="175ea-144">[`dotnet migrate`](../tools/dotnet-migrate.md) 在 .NET Core SDK 1.0.0 中引入，并在版本 3.0.100 中删除。</span><span class="sxs-lookup"><span data-stu-id="175ea-144">[`dotnet migrate`](../tools/dotnet-migrate.md) was introduced in .NET Core SDK 1.0.0 and removed in version 3.0.100.</span></span>
<span data-ttu-id="175ea-145">如果当前目录或父级目录中有 global.json 文件，且它指定的 `sdk` 版本在此范围外，则会收到此错误。</span><span class="sxs-lookup"><span data-stu-id="175ea-145">You'll get this error if you have a *global.json* file in the current or parent directory, and the `sdk` version it specifies is outside this range.</span></span>

## <a name="migration-from-dnx-to-csproj"></a><span data-ttu-id="175ea-146">从 DNX 迁移到 csproj</span><span class="sxs-lookup"><span data-stu-id="175ea-146">Migration from DNX to csproj</span></span>

<span data-ttu-id="175ea-147">如果仍在使用 DNX 进行 .NET Core 开发，则应分两个阶段完成迁移过程：</span><span class="sxs-lookup"><span data-stu-id="175ea-147">If you are still using DNX for .NET Core development, your migration process should be done in two stages:</span></span>

1. <span data-ttu-id="175ea-148">使用[现有 DNX 迁移指南](from-dnx.md)从 DNX 迁移到启用了 project-json 的 CLI。</span><span class="sxs-lookup"><span data-stu-id="175ea-148">Use the [existing DNX migration guidance](from-dnx.md) to migrate from DNX to project-json enabled CLI.</span></span>
2. <span data-ttu-id="175ea-149">请按照上一部分中的步骤，从 project.json 迁移到 .csproj。</span><span class="sxs-lookup"><span data-stu-id="175ea-149">Follow the steps from the previous section to migrate from *project.json* to *.csproj*.</span></span>

> [!NOTE]
> <span data-ttu-id="175ea-150">已于 .NET Core CLI 的预览版 1 发布期间正式弃用 DNX。</span><span class="sxs-lookup"><span data-stu-id="175ea-150">DNX has become officially deprecated during the Preview 1 release of the .NET Core CLI.</span></span>

## <a name="migration-from-earlier-net-core-csproj-formats-to-rtm-csproj"></a><span data-ttu-id="175ea-151">从较早的 .NET Core csproj 格式迁移到 RTM csproj</span><span class="sxs-lookup"><span data-stu-id="175ea-151">Migration from earlier .NET Core csproj formats to RTM csproj</span></span>

<span data-ttu-id="175ea-152">随着工具的每个新的预发布版本的推出，.NET Core csproj 格式也在不断变化发展。</span><span class="sxs-lookup"><span data-stu-id="175ea-152">The .NET Core csproj format has been changing and evolving with each new pre-release version of the tooling.</span></span> <span data-ttu-id="175ea-153">没有工具可以将项目文件从早期版本的 csproj 迁移到最新版本，因此需要手动编辑项目文件。</span><span class="sxs-lookup"><span data-stu-id="175ea-153">There is no tool that will migrate your project file from earlier versions of csproj to the latest, so you need to manually edit the project file.</span></span> <span data-ttu-id="175ea-154">实际步骤取决于要迁移的项目文件的版本。</span><span class="sxs-lookup"><span data-stu-id="175ea-154">The actual steps depend on the version of the project file you are migrating.</span></span> <span data-ttu-id="175ea-155">根据版本之间的变化，需考虑以下指导信息：</span><span class="sxs-lookup"><span data-stu-id="175ea-155">The following is some guidance to consider based on the changes that happened between versions:</span></span>

- <span data-ttu-id="175ea-156">从 `<Project>` 元素中删除工具版本属性（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="175ea-156">Remove the tools version property from the `<Project>` element, if it exists.</span></span>
- <span data-ttu-id="175ea-157">从 `<Project>` 元素中删除 XML 命名空间 (`xmlns`)。</span><span class="sxs-lookup"><span data-stu-id="175ea-157">Remove the XML namespace (`xmlns`) from the `<Project>` element.</span></span>
- <span data-ttu-id="175ea-158">如果不存在，请将 `Sdk` 属性添加到 `<Project>` 元素，并将其设置为 `Microsoft.NET.Sdk` 或 `Microsoft.NET.Sdk.Web`。</span><span class="sxs-lookup"><span data-stu-id="175ea-158">If it doesn't exist, add the `Sdk` attribute to the `<Project>` element and set it to `Microsoft.NET.Sdk` or `Microsoft.NET.Sdk.Web`.</span></span> <span data-ttu-id="175ea-159">此属性指定项目使用要使用的 SDK。</span><span class="sxs-lookup"><span data-stu-id="175ea-159">This attribute specifies that the project uses the SDK to be used.</span></span> <span data-ttu-id="175ea-160">`Microsoft.NET.Sdk.Web` 用于 Web 应用。</span><span class="sxs-lookup"><span data-stu-id="175ea-160">`Microsoft.NET.Sdk.Web` is used for web apps.</span></span>
- <span data-ttu-id="175ea-161">从项目的顶部和底部删除 `<Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" />` 和 `<Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />` 语句。</span><span class="sxs-lookup"><span data-stu-id="175ea-161">Remove the `<Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" />` and `<Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />` statements from the top and bottom of the project.</span></span> <span data-ttu-id="175ea-162">SDK 隐含这些 import 语句，因此项目中不需要这些语句。</span><span class="sxs-lookup"><span data-stu-id="175ea-162">These import statements are implied by the SDK, so there is no need for them to be in the project.</span></span>
- <span data-ttu-id="175ea-163">如果项目中含 `Microsoft.NETCore.App` 或 `NETStandard.Library``<PackageReference>` 项，应将其删除。</span><span class="sxs-lookup"><span data-stu-id="175ea-163">If you have `Microsoft.NETCore.App` or `NETStandard.Library` `<PackageReference>` items in your project, you should remove them.</span></span> <span data-ttu-id="175ea-164">[SDK 隐含](../project-sdk/overview.md)这些包引用。</span><span class="sxs-lookup"><span data-stu-id="175ea-164">These package references are [implied by the SDK](../project-sdk/overview.md).</span></span>
- <span data-ttu-id="175ea-165">删除 `Microsoft.NET.Sdk` `<PackageReference>` 元素（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="175ea-165">Remove the `Microsoft.NET.Sdk` `<PackageReference>` element, if it exists.</span></span> <span data-ttu-id="175ea-166">SDK 引用来自 `<Project>` 元素上的 `Sdk` 属性。</span><span class="sxs-lookup"><span data-stu-id="175ea-166">The SDK reference comes through the `Sdk` attribute on the `<Project>` element.</span></span>
- <span data-ttu-id="175ea-167">删除 [SDK](../project-sdk/overview.md#default-includes-and-excludes) 隐含的 [glob](https://en.wikipedia.org/wiki/Glob_(programming))。</span><span class="sxs-lookup"><span data-stu-id="175ea-167">Remove the [globs](https://en.wikipedia.org/wiki/Glob_(programming)) that are [implied by the SDK](../project-sdk/overview.md#default-includes-and-excludes).</span></span> <span data-ttu-id="175ea-168">在项目中留下这些 glob 会引发生成错误，因为编译项会发生重复。</span><span class="sxs-lookup"><span data-stu-id="175ea-168">Leaving these globs in your project will cause an error on build because compile items will be duplicated.</span></span>

<span data-ttu-id="175ea-169">完成这些步骤后，项目应与 RTM .NET Core csproj 格式完全兼容。</span><span class="sxs-lookup"><span data-stu-id="175ea-169">After these steps your project should be fully compatible with the RTM .NET Core csproj format.</span></span>

<span data-ttu-id="175ea-170">有关从旧的 csproj 格式迁移到新的 csproj 格式之前和之后情况的示例，请参阅 .NET 博客上的 [Updating Visual Studio 2017 RC – .NET Core Tooling improvements](https://devblogs.microsoft.com/dotnet/updating-visual-studio-2017-rc-net-core-tooling-improvements/)（更新 Visual Studio 2017 RC - .NET Core 工具改进）文章。</span><span class="sxs-lookup"><span data-stu-id="175ea-170">For examples of before and after the migration from old csproj format to the new one, see the [Updating Visual Studio 2017 RC – .NET Core Tooling improvements](https://devblogs.microsoft.com/dotnet/updating-visual-studio-2017-rc-net-core-tooling-improvements/) article on the .NET blog.</span></span>

## <a name="see-also"></a><span data-ttu-id="175ea-171">请参阅</span><span class="sxs-lookup"><span data-stu-id="175ea-171">See also</span></span>

- [<span data-ttu-id="175ea-172">移植、迁移和升级 Visual Studio 项目</span><span class="sxs-lookup"><span data-stu-id="175ea-172">Port, Migrate, and Upgrade Visual Studio Projects</span></span>](/visualstudio/porting/port-migrate-and-upgrade-visual-studio-projects)
