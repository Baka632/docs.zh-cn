---
title: dotnet remove package 命令
description: dotnet remove package 命令可便于删除对项目的 NuGet 包引用。
ms.date: 02/14/2020
ms.openlocfilehash: fc74ac1364a0ed027b83dab270d382f238dc00e5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/29/2020
ms.locfileid: "81463460"
---
# <a name="dotnet-remove-package"></a><span data-ttu-id="d66e5-103">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="d66e5-103">dotnet remove package</span></span>

<span data-ttu-id="d66e5-104">**本文适用于：** ✔️ .NET Core 2.x SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="d66e5-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="d66e5-105">名称</span><span class="sxs-lookup"><span data-stu-id="d66e5-105">Name</span></span>

<span data-ttu-id="d66e5-106">`dotnet remove package` - 从项目文件删除包引用。</span><span class="sxs-lookup"><span data-stu-id="d66e5-106">`dotnet remove package` - Removes package reference from a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d66e5-107">摘要</span><span class="sxs-lookup"><span data-stu-id="d66e5-107">Synopsis</span></span>

```dotnetcli
dotnet remove [<PROJECT>] package <PACKAGE_NAME>

dotnet remove package -h|--help
```

## <a name="description"></a><span data-ttu-id="d66e5-108">说明</span><span class="sxs-lookup"><span data-stu-id="d66e5-108">Description</span></span>

<span data-ttu-id="d66e5-109">使用 `dotnet remove package` 命令可方便地从项目删除 NuGet 包引用。</span><span class="sxs-lookup"><span data-stu-id="d66e5-109">The `dotnet remove package` command provides a convenient option to remove a NuGet package reference from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="d66e5-110">参数</span><span class="sxs-lookup"><span data-stu-id="d66e5-110">Arguments</span></span>

`PROJECT`

<span data-ttu-id="d66e5-111">指定项目文件。</span><span class="sxs-lookup"><span data-stu-id="d66e5-111">Specifies the project file.</span></span> <span data-ttu-id="d66e5-112">如果未指定，此命令会搜索当前目录来获取一个项目文件。</span><span class="sxs-lookup"><span data-stu-id="d66e5-112">If not specified, the command searches the current directory for one.</span></span>

`PACKAGE_NAME`

<span data-ttu-id="d66e5-113">要删除的包引用。</span><span class="sxs-lookup"><span data-stu-id="d66e5-113">The package reference to remove.</span></span>

## <a name="options"></a><span data-ttu-id="d66e5-114">选项</span><span class="sxs-lookup"><span data-stu-id="d66e5-114">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="d66e5-115">打印出有关命令的简短帮助。</span><span class="sxs-lookup"><span data-stu-id="d66e5-115">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="d66e5-116">示例</span><span class="sxs-lookup"><span data-stu-id="d66e5-116">Examples</span></span>

- <span data-ttu-id="d66e5-117">从当前目录中的项目删除 `Newtonsoft.Json` NuGet 包：</span><span class="sxs-lookup"><span data-stu-id="d66e5-117">Remove `Newtonsoft.Json` NuGet package from a project in the current directory:</span></span>

  ```dotnetcli
  dotnet remove package Newtonsoft.Json
  ```
