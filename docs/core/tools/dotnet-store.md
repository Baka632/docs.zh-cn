---
title: dotnet store 命令
description: “dotnet store”命令可将指定的程序集存储到运行时包存储区。
ms.date: 02/14/2020
ms.openlocfilehash: 8efb11c6bf648bc7787d5627e02b180abb8a0afd
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634332"
---
# <a name="dotnet-store"></a><span data-ttu-id="8aaf0-103">dotnet store</span><span class="sxs-lookup"><span data-stu-id="8aaf0-103">dotnet store</span></span>

<span data-ttu-id="8aaf0-104">**本文适用于：** ✔️ .NET Core 2.x SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="8aaf0-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="8aaf0-105">名称</span><span class="sxs-lookup"><span data-stu-id="8aaf0-105">Name</span></span>

<span data-ttu-id="8aaf0-106">`dotnet store` - 将指定的程序集存储到[运行时包存储区](../deploying/runtime-store.md)。</span><span class="sxs-lookup"><span data-stu-id="8aaf0-106">`dotnet store` - Stores the specified assemblies in the [runtime package store](../deploying/runtime-store.md).</span></span>

## <a name="synopsis"></a><span data-ttu-id="8aaf0-107">摘要</span><span class="sxs-lookup"><span data-stu-id="8aaf0-107">Synopsis</span></span>

```dotnetcli
dotnet store -m|--manifest <PATH_TO_MANIFEST_FILE>
    -f|--framework <FRAMEWORK_VERSION> -r|--runtime <RUNTIME_IDENTIFIER>
    [--framework-version <FRAMEWORK_VERSION>] [--output <OUTPUT_DIRECTORY>]
    [--skip-optimization] [--skip-symbols] [-v|--verbosity <LEVEL>]
    [--working-dir <WORKING_DIRECTORY>]

dotnet store -h|--help
```

## <a name="description"></a><span data-ttu-id="8aaf0-108">说明</span><span class="sxs-lookup"><span data-stu-id="8aaf0-108">Description</span></span>

<span data-ttu-id="8aaf0-109">`dotnet store` 将指定的程序集存储到[运行时包存储区](../deploying/runtime-store.md)。</span><span class="sxs-lookup"><span data-stu-id="8aaf0-109">`dotnet store` stores the specified assemblies in the [runtime package store](../deploying/runtime-store.md).</span></span> <span data-ttu-id="8aaf0-110">默认情况下，程序集更适用于目标运行时和框架。</span><span class="sxs-lookup"><span data-stu-id="8aaf0-110">By default, assemblies are optimized for the target runtime and framework.</span></span> <span data-ttu-id="8aaf0-111">有关详细信息，请参阅[运行时包存储区](../deploying/runtime-store.md)主题。</span><span class="sxs-lookup"><span data-stu-id="8aaf0-111">For more information, see the [runtime package store](../deploying/runtime-store.md) topic.</span></span>

## <a name="required-options"></a><span data-ttu-id="8aaf0-112">必需选项</span><span class="sxs-lookup"><span data-stu-id="8aaf0-112">Required options</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="8aaf0-113">指定[目标框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="8aaf0-113">Specifies the [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="8aaf0-114">目标框架必须在项目文件中进行指定。</span><span class="sxs-lookup"><span data-stu-id="8aaf0-114">The target framework has to be specified in the project file.</span></span>

- **`-m|--manifest <PATH_TO_MANIFEST_FILE>`**

  <span data-ttu-id="8aaf0-115">包存储区清单文件  是包含要存储的包列表的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="8aaf0-115">The *package store manifest file* is an XML file that contains the list of packages to store.</span></span> <span data-ttu-id="8aaf0-116">清单文件的格式与 SDK 样式项目格式兼容。</span><span class="sxs-lookup"><span data-stu-id="8aaf0-116">The format of the manifest file is compatible with the SDK-style project format.</span></span> <span data-ttu-id="8aaf0-117">因此，引用所需的包的项目文件能够与 `-m|--manifest` 选项结合使用，以便于将程序集存储到运行时包存储区。</span><span class="sxs-lookup"><span data-stu-id="8aaf0-117">So, a project file that references the desired packages can be used with the `-m|--manifest` option to store assemblies in the runtime package store.</span></span> <span data-ttu-id="8aaf0-118">若要指定多个清单文件，请为各个文件重复指定选项和路径。</span><span class="sxs-lookup"><span data-stu-id="8aaf0-118">To specify multiple manifest files, repeat the option and path for each file.</span></span> <span data-ttu-id="8aaf0-119">例如：`--manifest packages1.csproj --manifest packages2.csproj`。</span><span class="sxs-lookup"><span data-stu-id="8aaf0-119">For example: `--manifest packages1.csproj --manifest packages2.csproj`.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="8aaf0-120">目标[运行时标识符](../rid-catalog.md)。</span><span class="sxs-lookup"><span data-stu-id="8aaf0-120">The [runtime identifier](../rid-catalog.md) to target.</span></span>

## <a name="optional-options"></a><span data-ttu-id="8aaf0-121">可选选项</span><span class="sxs-lookup"><span data-stu-id="8aaf0-121">Optional options</span></span>

- **`--framework-version <FRAMEWORK_VERSION>`**

  <span data-ttu-id="8aaf0-122">指定 .NET SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="8aaf0-122">Specifies the .NET SDK version.</span></span> <span data-ttu-id="8aaf0-123">使用此选项，可以选择特定的框架版本，不再局限于 `-f|--framework` 选项指定的框架。</span><span class="sxs-lookup"><span data-stu-id="8aaf0-123">This option enables you to select a specific framework version beyond the framework specified by the `-f|--framework` option.</span></span>

- **`-h|--help`**

  <span data-ttu-id="8aaf0-124">显示帮助信息。</span><span class="sxs-lookup"><span data-stu-id="8aaf0-124">Shows help information.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="8aaf0-125">指定运行时包存储区的路径。</span><span class="sxs-lookup"><span data-stu-id="8aaf0-125">Specifies the path to the runtime package store.</span></span> <span data-ttu-id="8aaf0-126">如果未指定，默认路径为用户配置文件 .NET 安装目录的 store 子目录。</span><span class="sxs-lookup"><span data-stu-id="8aaf0-126">If not specified, it defaults to the *store* subdirectory of the user profile .NET installation directory.</span></span>

- **`--skip-optimization`**

  <span data-ttu-id="8aaf0-127">跳过优化阶段。</span><span class="sxs-lookup"><span data-stu-id="8aaf0-127">Skips the optimization phase.</span></span>

- **`--skip-symbols`**

  <span data-ttu-id="8aaf0-128">跳过符号生成。</span><span class="sxs-lookup"><span data-stu-id="8aaf0-128">Skips symbol generation.</span></span> <span data-ttu-id="8aaf0-129">目前，只能在 Windows 和 Linux 上生成符号。</span><span class="sxs-lookup"><span data-stu-id="8aaf0-129">Currently, you can only generate symbols on Windows and Linux.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="8aaf0-130">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="8aaf0-130">Sets the verbosity level of the command.</span></span> <span data-ttu-id="8aaf0-131">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="8aaf0-131">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

- **`-w|--working-dir <WORKING_DIRECTORY>`**

  <span data-ttu-id="8aaf0-132">此命令使用的工作目录。</span><span class="sxs-lookup"><span data-stu-id="8aaf0-132">The working directory used by the command.</span></span> <span data-ttu-id="8aaf0-133">如果未指定，使用当前目录的 obj  子目录。</span><span class="sxs-lookup"><span data-stu-id="8aaf0-133">If not specified, it uses the *obj* subdirectory of the current directory.</span></span>

## <a name="examples"></a><span data-ttu-id="8aaf0-134">示例</span><span class="sxs-lookup"><span data-stu-id="8aaf0-134">Examples</span></span>

- <span data-ttu-id="8aaf0-135">存储 packages.csproj  项目文件中为 .NET Core 2.0.0 指定的包：</span><span class="sxs-lookup"><span data-stu-id="8aaf0-135">Store the packages specified in the *packages.csproj* project file for .NET Core 2.0.0:</span></span>

  ```dotnetcli
  dotnet store --manifest packages.csproj --framework-version 2.0.0
  ```

- <span data-ttu-id="8aaf0-136">存储 packages.csproj  中指定的包，但不进行优化：</span><span class="sxs-lookup"><span data-stu-id="8aaf0-136">Store the packages specified in the *packages.csproj* without optimization:</span></span>

  ```dotnetcli
  dotnet store --manifest packages.csproj --skip-optimization
  ```

## <a name="see-also"></a><span data-ttu-id="8aaf0-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8aaf0-137">See also</span></span>

- [<span data-ttu-id="8aaf0-138">运行时包存储</span><span class="sxs-lookup"><span data-stu-id="8aaf0-138">Runtime package store</span></span>](../deploying/runtime-store.md)
