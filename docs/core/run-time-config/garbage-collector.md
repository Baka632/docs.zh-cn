---
title: 垃圾回收器配置设置
description: 了解用于配置垃圾回收器如何为 .NET Core 应用管理内存的运行时设置。
ms.date: 07/10/2020
ms.topic: reference
ms.openlocfilehash: 6ae5b7447fb0df4978ea9dcaa5e76fcc7a6cc4ca
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2020
ms.locfileid: "86441397"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="ed7d1-103">用于垃圾回收的运行时配置选项</span><span class="sxs-lookup"><span data-stu-id="ed7d1-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="ed7d1-104">此页包含有关可在运行时更改的垃圾回收器 (GC) 设置的信息。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="ed7d1-105">如果你要尝试让正在运行的应用达到最佳性能，请考虑使用这些设置。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="ed7d1-106">然而，在特定情况下，默认值为大多数应用程序提供最佳性能。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="ed7d1-107">设置在此页上被排入组中。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="ed7d1-108">每个组内的设置通常彼此结合使用以实现特定的结果。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="ed7d1-109">这些设置也可以在应用运行时由应用动态地进行更改，因此，你设置的任何运行时设置都可能会被覆盖。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="ed7d1-110">某些设置（如[延迟级别](../../standard/garbage-collection/latency.md)）通常仅在设计时通过 API 进行设置。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="ed7d1-111">此页面省略了此类设置。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="ed7d1-112">对于数值，请对 runtimeconfig.json 文件中的设置使用十进制表示法，而对环境变量设置使用十六进制表示法。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="ed7d1-113">对于十六进制值，可以使用或不使用“0x”前缀来指定它们。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="ed7d1-114">垃圾回收的风格</span><span class="sxs-lookup"><span data-stu-id="ed7d1-114">Flavors of garbage collection</span></span>

<span data-ttu-id="ed7d1-115">垃圾回收的两种主要风格是工作站 GC 和服务器 GC。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="ed7d1-116">有关两者之间的差异的详细信息，请参阅[工作站和服务器垃圾回收](../../standard/garbage-collection/workstation-server-gc.md)。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-116">For more information about differences between the two, see [Workstation and server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span>

<span data-ttu-id="ed7d1-117">垃圾回收的次要风格是后台垃圾回收和非并发垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="ed7d1-118">使用以下设置，选择垃圾回收的风格：</span><span class="sxs-lookup"><span data-stu-id="ed7d1-118">Use the following settings to select flavors of garbage collection:</span></span>

### <a name="systemgcservercomplus_gcserver"></a><span data-ttu-id="ed7d1-119">System.GC.Server/COMPlus_gcServer</span><span class="sxs-lookup"><span data-stu-id="ed7d1-119">System.GC.Server/COMPlus_gcServer</span></span>

- <span data-ttu-id="ed7d1-120">配置应用程序是使用工作站垃圾回收还是服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-120">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="ed7d1-121">默认：工作站垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-121">Default: Workstation garbage collection.</span></span> <span data-ttu-id="ed7d1-122">它等效于将值设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-122">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="ed7d1-123">设置名</span><span class="sxs-lookup"><span data-stu-id="ed7d1-123">Setting name</span></span> | <span data-ttu-id="ed7d1-124">值</span><span class="sxs-lookup"><span data-stu-id="ed7d1-124">Values</span></span> | <span data-ttu-id="ed7d1-125">引入的版本</span><span class="sxs-lookup"><span data-stu-id="ed7d1-125">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="ed7d1-126">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-126">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="ed7d1-127">`false` - 工作站</span><span class="sxs-lookup"><span data-stu-id="ed7d1-127">`false` - workstation</span></span><br/><span data-ttu-id="ed7d1-128">`true` - 服务器</span><span class="sxs-lookup"><span data-stu-id="ed7d1-128">`true` - server</span></span> | <span data-ttu-id="ed7d1-129">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="ed7d1-129">.NET Core 1.0</span></span> |
| <span data-ttu-id="ed7d1-130">MSBuild 属性</span><span class="sxs-lookup"><span data-stu-id="ed7d1-130">**MSBuild property**</span></span> | `ServerGarbageCollection` | <span data-ttu-id="ed7d1-131">`false` - 工作站</span><span class="sxs-lookup"><span data-stu-id="ed7d1-131">`false` - workstation</span></span><br/><span data-ttu-id="ed7d1-132">`true` - 服务器</span><span class="sxs-lookup"><span data-stu-id="ed7d1-132">`true` - server</span></span> | <span data-ttu-id="ed7d1-133">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="ed7d1-133">.NET Core 1.0</span></span> |
| <span data-ttu-id="ed7d1-134">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-134">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="ed7d1-135">`0` - 工作站</span><span class="sxs-lookup"><span data-stu-id="ed7d1-135">`0` - workstation</span></span><br/><span data-ttu-id="ed7d1-136">`1` - 服务器</span><span class="sxs-lookup"><span data-stu-id="ed7d1-136">`1` - server</span></span> | <span data-ttu-id="ed7d1-137">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="ed7d1-137">.NET Core 1.0</span></span> |
| <span data-ttu-id="ed7d1-138">**.NET Framework 的 app.config**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-138">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="ed7d1-139">GCServer</span><span class="sxs-lookup"><span data-stu-id="ed7d1-139">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="ed7d1-140">`false` - 工作站</span><span class="sxs-lookup"><span data-stu-id="ed7d1-140">`false` - workstation</span></span><br/><span data-ttu-id="ed7d1-141">`true` - 服务器</span><span class="sxs-lookup"><span data-stu-id="ed7d1-141">`true` - server</span></span> |  |

### <a name="examples"></a><span data-ttu-id="ed7d1-142">示例</span><span class="sxs-lookup"><span data-stu-id="ed7d1-142">Examples</span></span>

<span data-ttu-id="ed7d1-143">runtimeconfig.json 文件：</span><span class="sxs-lookup"><span data-stu-id="ed7d1-143">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

<span data-ttu-id="ed7d1-144">项目文件：</span><span class="sxs-lookup"><span data-stu-id="ed7d1-144">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>

</Project>
```

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a><span data-ttu-id="ed7d1-145">System.GC.Concurrent/COMPlus_gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="ed7d1-145">System.GC.Concurrent/COMPlus_gcConcurrent</span></span>

- <span data-ttu-id="ed7d1-146">配置是否启用后台（并发）垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-146">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="ed7d1-147">默认：使用后台垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-147">Default: Use background GC.</span></span> <span data-ttu-id="ed7d1-148">它等效于将值设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-148">This is equivalent to setting the value to `true`.</span></span>
- <span data-ttu-id="ed7d1-149">有关详细信息，请参阅[后台垃圾回收](../../standard/garbage-collection/background-gc.md)。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-149">For more information, see [Background garbage collection](../../standard/garbage-collection/background-gc.md).</span></span>

| | <span data-ttu-id="ed7d1-150">设置名</span><span class="sxs-lookup"><span data-stu-id="ed7d1-150">Setting name</span></span> | <span data-ttu-id="ed7d1-151">值</span><span class="sxs-lookup"><span data-stu-id="ed7d1-151">Values</span></span> | <span data-ttu-id="ed7d1-152">引入的版本</span><span class="sxs-lookup"><span data-stu-id="ed7d1-152">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="ed7d1-153">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-153">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="ed7d1-154">`true` - 后台 GC</span><span class="sxs-lookup"><span data-stu-id="ed7d1-154">`true` - background GC</span></span><br/><span data-ttu-id="ed7d1-155">`false` - 非并发 GC</span><span class="sxs-lookup"><span data-stu-id="ed7d1-155">`false` - non-concurrent GC</span></span> | <span data-ttu-id="ed7d1-156">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="ed7d1-156">.NET Core 1.0</span></span> |
| <span data-ttu-id="ed7d1-157">MSBuild 属性</span><span class="sxs-lookup"><span data-stu-id="ed7d1-157">**MSBuild property**</span></span> | `ConcurrentGarbageCollection` | <span data-ttu-id="ed7d1-158">`true` - 后台 GC</span><span class="sxs-lookup"><span data-stu-id="ed7d1-158">`true` - background GC</span></span><br/><span data-ttu-id="ed7d1-159">`false` - 非并发 GC</span><span class="sxs-lookup"><span data-stu-id="ed7d1-159">`false` - non-concurrent GC</span></span> | <span data-ttu-id="ed7d1-160">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="ed7d1-160">.NET Core 1.0</span></span> |
| <span data-ttu-id="ed7d1-161">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-161">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="ed7d1-162">`1` - 后台 GC</span><span class="sxs-lookup"><span data-stu-id="ed7d1-162">`1` - background GC</span></span><br/><span data-ttu-id="ed7d1-163">`0` - 非并发 GC</span><span class="sxs-lookup"><span data-stu-id="ed7d1-163">`0` - non-concurrent GC</span></span> | <span data-ttu-id="ed7d1-164">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="ed7d1-164">.NET Core 1.0</span></span> |
| <span data-ttu-id="ed7d1-165">**.NET Framework 的 app.config**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-165">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="ed7d1-166">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="ed7d1-166">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="ed7d1-167">`true` - 后台 GC</span><span class="sxs-lookup"><span data-stu-id="ed7d1-167">`true` - background GC</span></span><br/><span data-ttu-id="ed7d1-168">`false` - 非并发 GC</span><span class="sxs-lookup"><span data-stu-id="ed7d1-168">`false` - non-concurrent GC</span></span> |  |

### <a name="examples"></a><span data-ttu-id="ed7d1-169">示例</span><span class="sxs-lookup"><span data-stu-id="ed7d1-169">Examples</span></span>

<span data-ttu-id="ed7d1-170">runtimeconfig.json 文件：</span><span class="sxs-lookup"><span data-stu-id="ed7d1-170">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

<span data-ttu-id="ed7d1-171">项目文件：</span><span class="sxs-lookup"><span data-stu-id="ed7d1-171">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="manage-resource-usage"></a><span data-ttu-id="ed7d1-172">管理资源使用情况</span><span class="sxs-lookup"><span data-stu-id="ed7d1-172">Manage resource usage</span></span>

<span data-ttu-id="ed7d1-173">使用此部分中所述的设置，管理垃圾回收器的内存和处理器使用情况。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-173">Use the settings described in this section to manage the garbage collector's memory and processor usage.</span></span>

<span data-ttu-id="ed7d1-174">有关其中某些设置的详细信息，请参阅 [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/)（服务器和工作站 GC 之间的中间地带）博客条目。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-174">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="systemgcheapcountcomplus_gcheapcount"></a><span data-ttu-id="ed7d1-175">System.GC.HeapCount/COMPlus_GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="ed7d1-175">System.GC.HeapCount/COMPlus_GCHeapCount</span></span>

- <span data-ttu-id="ed7d1-176">限制通过垃圾回收器创建的堆数。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-176">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="ed7d1-177">仅适用于服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-177">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="ed7d1-178">如果启用了默认的 [GC 处理器关联](#systemgcnoaffinitizecomplus_gcnoaffinitize)，堆计数设置会将 `n` 个 GC 堆/线程关联到前 `n` 个处理器。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-178">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="ed7d1-179">（使用[关联掩码](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask)或[关联范围](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges)设置可精确指定要关联的处理器。）</span><span class="sxs-lookup"><span data-stu-id="ed7d1-179">(Use the [affinitize mask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) or [affinitize ranges](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges) settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="ed7d1-180">如果禁用了 [GC 处理器关联](#systemgcnoaffinitizecomplus_gcnoaffinitize)，则此设置会限制 GC 堆的数量。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-180">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="ed7d1-181">有关详细信息，请参阅 [GCHeapCount 备注](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks)。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-181">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="ed7d1-182">设置名</span><span class="sxs-lookup"><span data-stu-id="ed7d1-182">Setting name</span></span> | <span data-ttu-id="ed7d1-183">值</span><span class="sxs-lookup"><span data-stu-id="ed7d1-183">Values</span></span> | <span data-ttu-id="ed7d1-184">引入的版本</span><span class="sxs-lookup"><span data-stu-id="ed7d1-184">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="ed7d1-185">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-185">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="ed7d1-186">十进制值</span><span class="sxs-lookup"><span data-stu-id="ed7d1-186">*decimal value*</span></span> | <span data-ttu-id="ed7d1-187">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="ed7d1-187">.NET Core 3.0</span></span> |
| <span data-ttu-id="ed7d1-188">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-188">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="ed7d1-189">十六进制值</span><span class="sxs-lookup"><span data-stu-id="ed7d1-189">*hexadecimal value*</span></span> | <span data-ttu-id="ed7d1-190">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="ed7d1-190">.NET Core 3.0</span></span> |
| <span data-ttu-id="ed7d1-191">**.NET Framework 的 app.config**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-191">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="ed7d1-192">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="ed7d1-192">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="ed7d1-193">十进制值</span><span class="sxs-lookup"><span data-stu-id="ed7d1-193">*decimal value*</span></span> | <span data-ttu-id="ed7d1-194">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="ed7d1-194">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="ed7d1-195">示例：</span><span class="sxs-lookup"><span data-stu-id="ed7d1-195">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapCount": 16
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="ed7d1-196">如果要在 runtimeconfig.template.json 中设置该选项，请指定一个十进制值。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-196">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="ed7d1-197">如果要将选项设置为一个环境变量，请指定一个十六进制值。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-197">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="ed7d1-198">例如，若要将堆数限制为 16，则该值对于 JSON 文件为 16，对于环境变量则为 0x10 或 10。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-198">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a><span data-ttu-id="ed7d1-199">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="ed7d1-199">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span></span>

- <span data-ttu-id="ed7d1-200">指定垃圾回收器线程应使用的确切处理器数。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-200">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="ed7d1-201">如果禁用了 [GC 处理器关联](#systemgcnoaffinitizecomplus_gcnoaffinitize)，则忽略此设置。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-201">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="ed7d1-202">仅适用于服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-202">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="ed7d1-203">该值是一个位掩码，用于定义可用于该进程的处理器。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-203">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="ed7d1-204">例如，十进制值 1023 或十六进制值 0x3FF 或 3FF（如果使用环境变量）在二进制记数法中为 0011 1111 1111。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-204">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="ed7d1-205">这指定将使用前 10 个处理器。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-205">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="ed7d1-206">若要指定接下来使用的 10 个处理器（即处理器 10-19），请指定一个十进制值 1047552（或十六进制值 0xFFC00 或 FFC00），它等效于二进制值 1111 1111 1100 0000 0000。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-206">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="ed7d1-207">设置名</span><span class="sxs-lookup"><span data-stu-id="ed7d1-207">Setting name</span></span> | <span data-ttu-id="ed7d1-208">值</span><span class="sxs-lookup"><span data-stu-id="ed7d1-208">Values</span></span> | <span data-ttu-id="ed7d1-209">引入的版本</span><span class="sxs-lookup"><span data-stu-id="ed7d1-209">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="ed7d1-210">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-210">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="ed7d1-211">十进制值</span><span class="sxs-lookup"><span data-stu-id="ed7d1-211">*decimal value*</span></span> | <span data-ttu-id="ed7d1-212">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="ed7d1-212">.NET Core 3.0</span></span> |
| <span data-ttu-id="ed7d1-213">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-213">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="ed7d1-214">十六进制值</span><span class="sxs-lookup"><span data-stu-id="ed7d1-214">*hexadecimal value*</span></span> | <span data-ttu-id="ed7d1-215">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="ed7d1-215">.NET Core 3.0</span></span> |
| <span data-ttu-id="ed7d1-216">**.NET Framework 的 app.config**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-216">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="ed7d1-217">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="ed7d1-217">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="ed7d1-218">十进制值</span><span class="sxs-lookup"><span data-stu-id="ed7d1-218">*decimal value*</span></span> | <span data-ttu-id="ed7d1-219">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="ed7d1-219">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="ed7d1-220">示例：</span><span class="sxs-lookup"><span data-stu-id="ed7d1-220">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a><span data-ttu-id="ed7d1-221">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span><span class="sxs-lookup"><span data-stu-id="ed7d1-221">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span></span>

- <span data-ttu-id="ed7d1-222">指定用于垃圾回收器线程的处理器列表。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-222">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="ed7d1-223">此设置与 [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) 类似，只是它允许你指定超过 64 个的处理器。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-223">This setting is similar to [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask), except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="ed7d1-224">对于 Windows 操作系统，请为处理器编号或范围加上相应的 [CPU 组](/windows/win32/procthread/processor-groups)作为前缀，例如“0:1-10,0:12,1:50-52,1:70”。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-224">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="ed7d1-225">如果禁用了 [GC 处理器关联](#systemgcnoaffinitizecomplus_gcnoaffinitize)，则忽略此设置。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-225">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="ed7d1-226">仅适用于服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-226">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="ed7d1-227">有关详细信息，请参阅 Maoni Stephens 的博客文章 [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/)（在 CPU 大于 64 个的计算机上，为 GC 提供更好的 CPU 配置）。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-227">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="ed7d1-228">设置名</span><span class="sxs-lookup"><span data-stu-id="ed7d1-228">Setting name</span></span> | <span data-ttu-id="ed7d1-229">值</span><span class="sxs-lookup"><span data-stu-id="ed7d1-229">Values</span></span> | <span data-ttu-id="ed7d1-230">引入的版本</span><span class="sxs-lookup"><span data-stu-id="ed7d1-230">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="ed7d1-231">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-231">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="ed7d1-232">以逗号分隔的处理器编号列表或处理器编号范围。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-232">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="ed7d1-233">Unix 示例：“1-10,12,50-52,70”</span><span class="sxs-lookup"><span data-stu-id="ed7d1-233">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="ed7d1-234">Windows 示例：“0:1-10,0:12,1:50-52,1:70”</span><span class="sxs-lookup"><span data-stu-id="ed7d1-234">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="ed7d1-235">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="ed7d1-235">.NET Core 3.0</span></span> |
| <span data-ttu-id="ed7d1-236">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-236">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="ed7d1-237">以逗号分隔的处理器编号列表或处理器编号范围。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-237">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="ed7d1-238">Unix 示例：“1-10,12,50-52,70”</span><span class="sxs-lookup"><span data-stu-id="ed7d1-238">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="ed7d1-239">Windows 示例：“0:1-10,0:12,1:50-52,1:70”</span><span class="sxs-lookup"><span data-stu-id="ed7d1-239">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="ed7d1-240">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="ed7d1-240">.NET Core 3.0</span></span> |

<span data-ttu-id="ed7d1-241">示例：</span><span class="sxs-lookup"><span data-stu-id="ed7d1-241">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="complus_gccpugroup"></a><span data-ttu-id="ed7d1-242">COMPlus_GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="ed7d1-242">COMPlus_GCCpuGroup</span></span>

- <span data-ttu-id="ed7d1-243">配置垃圾回收器是否使用 [CPU 组](/windows/win32/procthread/processor-groups)。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-243">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="ed7d1-244">当 64 位 Windows 计算机具有多个 CPU 组（即，有超过 64 个处理器）时，通过启用此元素，可跨所有 CPU 组扩展垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-244">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="ed7d1-245">垃圾回收器使用所有核心来创建和平衡堆。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-245">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="ed7d1-246">仅适用于 64 位 Windows 操作系统上的服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-246">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="ed7d1-247">默认：垃圾回收不会跨 CPU 组扩展。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-247">Default: GC does not extend across CPU groups.</span></span> <span data-ttu-id="ed7d1-248">它等效于将值设置为 `0`。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-248">This is equivalent to setting the value to `0`.</span></span>
- <span data-ttu-id="ed7d1-249">有关详细信息，请参阅 Maoni Stephens 的博客文章 [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/)（在 CPU 大于 64 个的计算机上，为 GC 提供更好的 CPU 配置）。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-249">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="ed7d1-250">设置名</span><span class="sxs-lookup"><span data-stu-id="ed7d1-250">Setting name</span></span> | <span data-ttu-id="ed7d1-251">值</span><span class="sxs-lookup"><span data-stu-id="ed7d1-251">Values</span></span> | <span data-ttu-id="ed7d1-252">引入的版本</span><span class="sxs-lookup"><span data-stu-id="ed7d1-252">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="ed7d1-253">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-253">**runtimeconfig.json**</span></span> | <span data-ttu-id="ed7d1-254">不可用</span><span class="sxs-lookup"><span data-stu-id="ed7d1-254">N/A</span></span> | <span data-ttu-id="ed7d1-255">不可用</span><span class="sxs-lookup"><span data-stu-id="ed7d1-255">N/A</span></span> | <span data-ttu-id="ed7d1-256">不可用</span><span class="sxs-lookup"><span data-stu-id="ed7d1-256">N/A</span></span> |
| <span data-ttu-id="ed7d1-257">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-257">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="ed7d1-258">`0` - 禁用</span><span class="sxs-lookup"><span data-stu-id="ed7d1-258">`0` - disabled</span></span><br/><span data-ttu-id="ed7d1-259">`1` - 启用</span><span class="sxs-lookup"><span data-stu-id="ed7d1-259">`1` - enabled</span></span> | <span data-ttu-id="ed7d1-260">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="ed7d1-260">.NET Core 1.0</span></span> |
| <span data-ttu-id="ed7d1-261">**.NET Framework 的 app.config**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-261">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="ed7d1-262">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="ed7d1-262">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="ed7d1-263">`false` - 禁用</span><span class="sxs-lookup"><span data-stu-id="ed7d1-263">`false` - disabled</span></span><br/><span data-ttu-id="ed7d1-264">`true` - 启用</span><span class="sxs-lookup"><span data-stu-id="ed7d1-264">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="ed7d1-265">若要配置公共语言运行时 (CLR)，使其也在所有 CPU 组之间分配线程池中的线程，请启用 [Thread_UseAllCpuGroups 元素](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md)选项。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-265">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="ed7d1-266">对于 .NET Core 应用，可以通过将 `COMPlus_Thread_UseAllCpuGroups` 环境变量的值设置为 `1` 以启用此选项。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-266">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a><span data-ttu-id="ed7d1-267">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="ed7d1-267">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span></span>

- <span data-ttu-id="ed7d1-268">指定是否将垃圾回收线程与处理器关联。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-268">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="ed7d1-269">若要关联一个 GC 线程，则意味着它只能在其特定的 CPU 上运行。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-269">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="ed7d1-270">为每个 GC 线程创建一个堆。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-270">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="ed7d1-271">仅适用于服务器垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-271">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="ed7d1-272">默认：将垃圾回收线程与处理器关联。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-272">Default: Affinitize garbage collection threads with processors.</span></span> <span data-ttu-id="ed7d1-273">它等效于将值设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-273">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="ed7d1-274">设置名</span><span class="sxs-lookup"><span data-stu-id="ed7d1-274">Setting name</span></span> | <span data-ttu-id="ed7d1-275">值</span><span class="sxs-lookup"><span data-stu-id="ed7d1-275">Values</span></span> | <span data-ttu-id="ed7d1-276">引入的版本</span><span class="sxs-lookup"><span data-stu-id="ed7d1-276">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="ed7d1-277">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-277">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="ed7d1-278">`false` - 关联</span><span class="sxs-lookup"><span data-stu-id="ed7d1-278">`false` - affinitize</span></span><br/><span data-ttu-id="ed7d1-279">`true` - 不关联</span><span class="sxs-lookup"><span data-stu-id="ed7d1-279">`true` - don't affinitize</span></span> | <span data-ttu-id="ed7d1-280">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="ed7d1-280">.NET Core 3.0</span></span> |
| <span data-ttu-id="ed7d1-281">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-281">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="ed7d1-282">`0` - 关联</span><span class="sxs-lookup"><span data-stu-id="ed7d1-282">`0` - affinitize</span></span><br/><span data-ttu-id="ed7d1-283">`1` - 不关联</span><span class="sxs-lookup"><span data-stu-id="ed7d1-283">`1` - don't affinitize</span></span> | <span data-ttu-id="ed7d1-284">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="ed7d1-284">.NET Core 3.0</span></span> |
| <span data-ttu-id="ed7d1-285">**.NET Framework 的 app.config**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-285">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="ed7d1-286">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="ed7d1-286">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="ed7d1-287">`false` - 关联</span><span class="sxs-lookup"><span data-stu-id="ed7d1-287">`false` - affinitize</span></span><br/><span data-ttu-id="ed7d1-288">`true` - 不关联</span><span class="sxs-lookup"><span data-stu-id="ed7d1-288">`true` - don't affinitize</span></span> | <span data-ttu-id="ed7d1-289">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="ed7d1-289">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="ed7d1-290">示例：</span><span class="sxs-lookup"><span data-stu-id="ed7d1-290">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a><span data-ttu-id="ed7d1-291">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span><span class="sxs-lookup"><span data-stu-id="ed7d1-291">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span></span>

- <span data-ttu-id="ed7d1-292">指定 GC 堆和 GC 簿记的最大提交大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-292">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>
- <span data-ttu-id="ed7d1-293">此设置仅适用于 64 位计算机。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-293">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="ed7d1-294">如果已配置[每对象堆限制](#per-object-heap-limits)，则忽略此设置。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-294">This setting is ignored if the [Per-object-heap limits](#per-object-heap-limits) are configured.</span></span>
- <span data-ttu-id="ed7d1-295">默认值（仅在某些情况下适用）是 20 MB 或容器内存限制的 75%（以较大者为准）。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-295">The default value, which only applies in certain cases, is the greater of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="ed7d1-296">此默认值在以下情况下适用：</span><span class="sxs-lookup"><span data-stu-id="ed7d1-296">The default value applies if:</span></span>

  - <span data-ttu-id="ed7d1-297">进程正在具有指定内存限制的容器中运行。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-297">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="ed7d1-298">[HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) 未设置。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-298">[System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) is not set.</span></span>

| | <span data-ttu-id="ed7d1-299">设置名</span><span class="sxs-lookup"><span data-stu-id="ed7d1-299">Setting name</span></span> | <span data-ttu-id="ed7d1-300">值</span><span class="sxs-lookup"><span data-stu-id="ed7d1-300">Values</span></span> | <span data-ttu-id="ed7d1-301">引入的版本</span><span class="sxs-lookup"><span data-stu-id="ed7d1-301">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="ed7d1-302">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-302">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="ed7d1-303">十进制值</span><span class="sxs-lookup"><span data-stu-id="ed7d1-303">*decimal value*</span></span> | <span data-ttu-id="ed7d1-304">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="ed7d1-304">.NET Core 3.0</span></span> |
| <span data-ttu-id="ed7d1-305">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-305">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="ed7d1-306">十六进制值</span><span class="sxs-lookup"><span data-stu-id="ed7d1-306">*hexadecimal value*</span></span> | <span data-ttu-id="ed7d1-307">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="ed7d1-307">.NET Core 3.0</span></span> |

<span data-ttu-id="ed7d1-308">示例：</span><span class="sxs-lookup"><span data-stu-id="ed7d1-308">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapHardLimit": 209715200
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="ed7d1-309">如果要在 runtimeconfig.template.json 中设置该选项，请指定一个十进制值。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-309">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="ed7d1-310">如果要将选项设置为一个环境变量，请指定一个十六进制值。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-310">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="ed7d1-311">例如，若要将堆硬限制指定为 200 个兆字节 (MiB)，则该值对于 JSON 文件为 209715200，对于环境变量则为 0xC800000 或 C800000。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-311">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a><span data-ttu-id="ed7d1-312">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span><span class="sxs-lookup"><span data-stu-id="ed7d1-312">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span></span>

- <span data-ttu-id="ed7d1-313">指定允许的 GC 堆使用量占总物理内存的百分比。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-313">Specifies the allowable GC heap usage as a percentage of the total physical memory.</span></span>
- <span data-ttu-id="ed7d1-314">如果还设置了 [System.GC.heaphdlimit](#systemgcheaphardlimitcomplus_gcheaphardlimit)，则忽略此设置。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-314">If [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is also set, this setting is ignored.</span></span>
- <span data-ttu-id="ed7d1-315">此设置仅适用于 64 位计算机。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-315">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="ed7d1-316">如果进程正在具有指定内存限制的容器中运行，则百分比的计算结果将为该内存限制的百分比。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-316">If the process is running inside a container that has a specified memory limit, the percentage is calculated as a percentage of that memory limit.</span></span>
- <span data-ttu-id="ed7d1-317">如果已配置[每对象堆限制](#per-object-heap-limits)，则忽略此设置。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-317">This setting is ignored if the [Per-object-heap limits](#per-object-heap-limits) are configured.</span></span>
- <span data-ttu-id="ed7d1-318">默认值（仅在某些情况下适用）是 20 MB 或容器内存限制的 75%（以较小者为准）。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-318">The default value, which only applies in certain cases, is the lesser of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="ed7d1-319">此默认值在以下情况下适用：</span><span class="sxs-lookup"><span data-stu-id="ed7d1-319">The default value applies if:</span></span>

  - <span data-ttu-id="ed7d1-320">进程正在具有指定内存限制的容器中运行。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-320">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="ed7d1-321">[System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) 未设置。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-321">[System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is not set.</span></span>

| | <span data-ttu-id="ed7d1-322">设置名</span><span class="sxs-lookup"><span data-stu-id="ed7d1-322">Setting name</span></span> | <span data-ttu-id="ed7d1-323">值</span><span class="sxs-lookup"><span data-stu-id="ed7d1-323">Values</span></span> | <span data-ttu-id="ed7d1-324">引入的版本</span><span class="sxs-lookup"><span data-stu-id="ed7d1-324">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="ed7d1-325">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-325">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="ed7d1-326">十进制值</span><span class="sxs-lookup"><span data-stu-id="ed7d1-326">*decimal value*</span></span> | <span data-ttu-id="ed7d1-327">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="ed7d1-327">.NET Core 3.0</span></span> |
| <span data-ttu-id="ed7d1-328">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-328">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="ed7d1-329">十六进制值</span><span class="sxs-lookup"><span data-stu-id="ed7d1-329">*hexadecimal value*</span></span> | <span data-ttu-id="ed7d1-330">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="ed7d1-330">.NET Core 3.0</span></span> |

<span data-ttu-id="ed7d1-331">示例：</span><span class="sxs-lookup"><span data-stu-id="ed7d1-331">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapHardLimitPercent": 30
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="ed7d1-332">如果要在 runtimeconfig.template.json 中设置该选项，请指定一个十进制值。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-332">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="ed7d1-333">如果要将选项设置为一个环境变量，请指定一个十六进制值。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-333">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="ed7d1-334">例如，若要将堆使用率限制为 30%，则该值对于 JSON 文件为 30，对于环境变量则为 0x1E 或 1E。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-334">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="per-object-heap-limits"></a><span data-ttu-id="ed7d1-335">每对象堆限制</span><span class="sxs-lookup"><span data-stu-id="ed7d1-335">Per-object-heap limits</span></span>

<span data-ttu-id="ed7d1-336">可以根据每个对象堆指定 GC 的允许堆使用量。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-336">You can specify the GC's allowable heap usage on a per-object-heap basis.</span></span> <span data-ttu-id="ed7d1-337">不同的堆包括大型对象堆 (LOH)、小型对象堆 (SOH) 和固定对象堆 (POH)。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-337">The different heaps are the large object heap (LOH), small object heap (SOH), and pinned object heap (POH).</span></span>

#### <a name="complus_gcheaphardlimitsoh-complus_gcheaphardlimitloh-complus_gcheaphardlimitpoh"></a><span data-ttu-id="ed7d1-338">COMPLUS_GCHeapHardLimitSOH、COMPLUS_GCHeapHardLimitLOH、COMPLUS_GCHeapHardLimitPOH</span><span class="sxs-lookup"><span data-stu-id="ed7d1-338">COMPLUS_GCHeapHardLimitSOH, COMPLUS_GCHeapHardLimitLOH, COMPLUS_GCHeapHardLimitPOH</span></span>

- <span data-ttu-id="ed7d1-339">如果为任何 `COMPLUS_GCHeapHardLimitSOH`、`COMPLUS_GCHeapHardLimitLOH` 或 `COMPLUS_GCHeapHardLimitPOH` 设置指定值，则还必须为 `COMPLUS_GCHeapHardLimitSOH` 和 `COMPLUS_GCHeapHardLimitLOH` 指定值。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-339">If you specify a value for any of the `COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH`, or `COMPLUS_GCHeapHardLimitPOH` settings, you must also specify a value for `COMPLUS_GCHeapHardLimitSOH` and `COMPLUS_GCHeapHardLimitLOH`.</span></span> <span data-ttu-id="ed7d1-340">否则，运行时将无法初始化。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-340">If you don't, the runtime will fail to initialize.</span></span>
- <span data-ttu-id="ed7d1-341">`COMPLUS_GCHeapHardLimitPOH` 的默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-341">The default value for `COMPLUS_GCHeapHardLimitPOH` is 0.</span></span> <span data-ttu-id="ed7d1-342">`COMPLUS_GCHeapHardLimitSOH` 和 `COMPLUS_GCHeapHardLimitLOH` 没有默认值。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-342">`COMPLUS_GCHeapHardLimitSOH` and `COMPLUS_GCHeapHardLimitLOH` don't have default values.</span></span>

| | <span data-ttu-id="ed7d1-343">设置名</span><span class="sxs-lookup"><span data-stu-id="ed7d1-343">Setting name</span></span> | <span data-ttu-id="ed7d1-344">值</span><span class="sxs-lookup"><span data-stu-id="ed7d1-344">Values</span></span> | <span data-ttu-id="ed7d1-345">引入的版本</span><span class="sxs-lookup"><span data-stu-id="ed7d1-345">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="ed7d1-346">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-346">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitSOH` | <span data-ttu-id="ed7d1-347">十六进制值</span><span class="sxs-lookup"><span data-stu-id="ed7d1-347">*hexadecimal value*</span></span> | <span data-ttu-id="ed7d1-348">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="ed7d1-348">.NET 5.0</span></span> |
| <span data-ttu-id="ed7d1-349">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-349">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitLOH` | <span data-ttu-id="ed7d1-350">十六进制值</span><span class="sxs-lookup"><span data-stu-id="ed7d1-350">*hexadecimal value*</span></span> | <span data-ttu-id="ed7d1-351">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="ed7d1-351">.NET 5.0</span></span> |
| <span data-ttu-id="ed7d1-352">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-352">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitPOH` | <span data-ttu-id="ed7d1-353">十六进制值</span><span class="sxs-lookup"><span data-stu-id="ed7d1-353">*hexadecimal value*</span></span> | <span data-ttu-id="ed7d1-354">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="ed7d1-354">.NET 5.0</span></span> |

> [!TIP]
> <span data-ttu-id="ed7d1-355">如果要将选项设置为一个环境变量，请指定一个十六进制值。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-355">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="ed7d1-356">例如，要将堆硬限制指定为 200 个兆字节 (MiB)，则该值为 0xC800000 或 C800000。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-356">For example, to specify a heap hard limit of 200 mebibytes (MiB), the value would be 0xC800000 or C800000.</span></span>

#### <a name="complus_gcheaphardlimitsohpercent-complus_gcheaphardlimitlohpercent-complus_gcheaphardlimitpohpercent"></a><span data-ttu-id="ed7d1-357">COMPLUS_GCHeapHardLimitSOHPercent、COMPLUS_GCHeapHardLimitLOHPercent、COMPLUS_GCHeapHardLimitPOHPercent</span><span class="sxs-lookup"><span data-stu-id="ed7d1-357">COMPLUS_GCHeapHardLimitSOHPercent, COMPLUS_GCHeapHardLimitLOHPercent, COMPLUS_GCHeapHardLimitPOHPercent</span></span>

- <span data-ttu-id="ed7d1-358">如果为任何 `COMPLUS_GCHeapHardLimitSOHPercent`、`COMPLUS_GCHeapHardLimitLOHPercent` 或 `COMPLUS_GCHeapHardLimitPOHPercent` 设置指定值，则还必须为 `COMPLUS_GCHeapHardLimitSOHPercent` 和 `COMPLUS_GCHeapHardLimitLOHPercent` 指定值。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-358">If you specify a value for any of the `COMPLUS_GCHeapHardLimitSOHPercent`, `COMPLUS_GCHeapHardLimitLOHPercent`, or `COMPLUS_GCHeapHardLimitPOHPercent` settings, you must also specify a value for `COMPLUS_GCHeapHardLimitSOHPercent` and `COMPLUS_GCHeapHardLimitLOHPercent`.</span></span> <span data-ttu-id="ed7d1-359">否则，运行时将无法初始化。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-359">If you don't, the runtime will fail to initialize.</span></span>
- <span data-ttu-id="ed7d1-360">如果指定了 `COMPLUS_GCHeapHardLimitSOH`、`COMPLUS_GCHeapHardLimitLOH` 和 `COMPLUS_GCHeapHardLimitPOH`，则忽略这些设置。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-360">These settings are ignored if `COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH`, and `COMPLUS_GCHeapHardLimitPOH` are specified.</span></span>
- <span data-ttu-id="ed7d1-361">值为 1 表示 GC 使用该对象堆的总物理内存的 1%。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-361">A value of 1 means that GC uses 1% of total physical memory for that object heap.</span></span>
- <span data-ttu-id="ed7d1-362">每个值都必须大于 0 并小于 100。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-362">Each value must be greater than zero and less than 100.</span></span> <span data-ttu-id="ed7d1-363">此外，3 个百分比值的总和必须小于 100。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-363">Additionally, the sum of the three percentage values must be less than 100.</span></span> <span data-ttu-id="ed7d1-364">否则，运行时将无法初始化。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-364">Otherwise, the runtime will fail to initialize.</span></span>

| | <span data-ttu-id="ed7d1-365">设置名</span><span class="sxs-lookup"><span data-stu-id="ed7d1-365">Setting name</span></span> | <span data-ttu-id="ed7d1-366">值</span><span class="sxs-lookup"><span data-stu-id="ed7d1-366">Values</span></span> | <span data-ttu-id="ed7d1-367">引入的版本</span><span class="sxs-lookup"><span data-stu-id="ed7d1-367">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="ed7d1-368">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-368">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitSOHPercent` | <span data-ttu-id="ed7d1-369">十六进制值</span><span class="sxs-lookup"><span data-stu-id="ed7d1-369">*hexadecimal value*</span></span> | <span data-ttu-id="ed7d1-370">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="ed7d1-370">.NET 5.0</span></span> |
| <span data-ttu-id="ed7d1-371">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-371">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitLOHPercent` | <span data-ttu-id="ed7d1-372">十六进制值</span><span class="sxs-lookup"><span data-stu-id="ed7d1-372">*hexadecimal value*</span></span> | <span data-ttu-id="ed7d1-373">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="ed7d1-373">.NET 5.0</span></span> |
| <span data-ttu-id="ed7d1-374">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-374">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitPOHPercent` | <span data-ttu-id="ed7d1-375">十六进制值</span><span class="sxs-lookup"><span data-stu-id="ed7d1-375">*hexadecimal value*</span></span> | <span data-ttu-id="ed7d1-376">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="ed7d1-376">.NET 5.0</span></span> |

> [!TIP]
> <span data-ttu-id="ed7d1-377">如果要将选项设置为一个环境变量，请指定一个十六进制值。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-377">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="ed7d1-378">例如，要将堆使用量限制为 30%，则值为 0x1E 或 1E。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-378">For example, to limit the heap usage to 30%, the value would be 0x1E or 1E.</span></span>

### <a name="systemgcretainvmcomplus_gcretainvm"></a><span data-ttu-id="ed7d1-379">System.GC.RetainVM/COMPlus_GCRetainVM</span><span class="sxs-lookup"><span data-stu-id="ed7d1-379">System.GC.RetainVM/COMPlus_GCRetainVM</span></span>

- <span data-ttu-id="ed7d1-380">配置是将应删除的段置于备用列表上供将来使用，还是将其释放回操作系统 (OS)。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-380">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="ed7d1-381">默认：将段释放回操作系统。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-381">Default: Release segments back to the operating system.</span></span> <span data-ttu-id="ed7d1-382">它等效于将值设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-382">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="ed7d1-383">设置名</span><span class="sxs-lookup"><span data-stu-id="ed7d1-383">Setting name</span></span> | <span data-ttu-id="ed7d1-384">值</span><span class="sxs-lookup"><span data-stu-id="ed7d1-384">Values</span></span> | <span data-ttu-id="ed7d1-385">引入的版本</span><span class="sxs-lookup"><span data-stu-id="ed7d1-385">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="ed7d1-386">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-386">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="ed7d1-387">`false` - 释放到 OS</span><span class="sxs-lookup"><span data-stu-id="ed7d1-387">`false` - release to OS</span></span><br/><span data-ttu-id="ed7d1-388">`true` - 置于备用列表上</span><span class="sxs-lookup"><span data-stu-id="ed7d1-388">`true` - put on standby</span></span> | <span data-ttu-id="ed7d1-389">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="ed7d1-389">.NET Core 1.0</span></span> |
| <span data-ttu-id="ed7d1-390">MSBuild 属性</span><span class="sxs-lookup"><span data-stu-id="ed7d1-390">**MSBuild property**</span></span> | `RetainVMGarbageCollection` | <span data-ttu-id="ed7d1-391">`false` - 释放到 OS</span><span class="sxs-lookup"><span data-stu-id="ed7d1-391">`false` - release to OS</span></span><br/><span data-ttu-id="ed7d1-392">`true` - 置于备用列表上</span><span class="sxs-lookup"><span data-stu-id="ed7d1-392">`true` - put on standby</span></span> | <span data-ttu-id="ed7d1-393">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="ed7d1-393">.NET Core 1.0</span></span> |
| <span data-ttu-id="ed7d1-394">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-394">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="ed7d1-395">`0` - 释放到 OS</span><span class="sxs-lookup"><span data-stu-id="ed7d1-395">`0` - release to OS</span></span><br/><span data-ttu-id="ed7d1-396">`1` - 置于备用列表上</span><span class="sxs-lookup"><span data-stu-id="ed7d1-396">`1` - put on standby</span></span> | <span data-ttu-id="ed7d1-397">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="ed7d1-397">.NET Core 1.0</span></span> |

### <a name="examples"></a><span data-ttu-id="ed7d1-398">示例</span><span class="sxs-lookup"><span data-stu-id="ed7d1-398">Examples</span></span>

<span data-ttu-id="ed7d1-399">runtimeconfig.json 文件：</span><span class="sxs-lookup"><span data-stu-id="ed7d1-399">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

<span data-ttu-id="ed7d1-400">项目文件：</span><span class="sxs-lookup"><span data-stu-id="ed7d1-400">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="large-pages"></a><span data-ttu-id="ed7d1-401">大型页面</span><span class="sxs-lookup"><span data-stu-id="ed7d1-401">Large pages</span></span>

### <a name="complus_gclargepages"></a><span data-ttu-id="ed7d1-402">COMPlus_GCLargePages</span><span class="sxs-lookup"><span data-stu-id="ed7d1-402">COMPlus_GCLargePages</span></span>

- <span data-ttu-id="ed7d1-403">指定设置堆硬限制时是否应使用大型页面。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-403">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="ed7d1-404">默认：设置堆硬限制时不要使用大页面。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-404">Default: Don't use large pages when a heap hard limit is set.</span></span> <span data-ttu-id="ed7d1-405">它等效于将值设置为 `0`。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-405">This is equivalent to setting the value to `0`.</span></span>
- <span data-ttu-id="ed7d1-406">这是一项实验性设置。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-406">This is an experimental setting.</span></span>

| | <span data-ttu-id="ed7d1-407">设置名</span><span class="sxs-lookup"><span data-stu-id="ed7d1-407">Setting name</span></span> | <span data-ttu-id="ed7d1-408">值</span><span class="sxs-lookup"><span data-stu-id="ed7d1-408">Values</span></span> | <span data-ttu-id="ed7d1-409">引入的版本</span><span class="sxs-lookup"><span data-stu-id="ed7d1-409">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="ed7d1-410">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-410">**runtimeconfig.json**</span></span> | <span data-ttu-id="ed7d1-411">不可用</span><span class="sxs-lookup"><span data-stu-id="ed7d1-411">N/A</span></span> | <span data-ttu-id="ed7d1-412">不可用</span><span class="sxs-lookup"><span data-stu-id="ed7d1-412">N/A</span></span> | <span data-ttu-id="ed7d1-413">不可用</span><span class="sxs-lookup"><span data-stu-id="ed7d1-413">N/A</span></span> |
| <span data-ttu-id="ed7d1-414">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-414">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="ed7d1-415">`0` - 禁用</span><span class="sxs-lookup"><span data-stu-id="ed7d1-415">`0` - disabled</span></span><br/><span data-ttu-id="ed7d1-416">`1` - 启用</span><span class="sxs-lookup"><span data-stu-id="ed7d1-416">`1` - enabled</span></span> | <span data-ttu-id="ed7d1-417">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="ed7d1-417">.NET Core 3.0</span></span> |

## <a name="large-objects"></a><span data-ttu-id="ed7d1-418">大型对象</span><span class="sxs-lookup"><span data-stu-id="ed7d1-418">Large objects</span></span>

### <a name="complus_gcallowverylargeobjects"></a><span data-ttu-id="ed7d1-419">COMPlus_gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="ed7d1-419">COMPlus_gcAllowVeryLargeObjects</span></span>

- <span data-ttu-id="ed7d1-420">在 64 位平台上，为总大小大于 2 千兆字节 (GB) 的数组配置垃圾回收器支持。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-420">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="ed7d1-421">默认：垃圾回收支持大于 2 GB 的数组。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-421">Default: GC supports arrays greater than 2-GB.</span></span> <span data-ttu-id="ed7d1-422">它等效于将值设置为 `1`。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-422">This is equivalent to setting the value to `1`.</span></span>
- <span data-ttu-id="ed7d1-423">在未来的 .NET 版本中，此选项可能会过时。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-423">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="ed7d1-424">设置名</span><span class="sxs-lookup"><span data-stu-id="ed7d1-424">Setting name</span></span> | <span data-ttu-id="ed7d1-425">值</span><span class="sxs-lookup"><span data-stu-id="ed7d1-425">Values</span></span> | <span data-ttu-id="ed7d1-426">引入的版本</span><span class="sxs-lookup"><span data-stu-id="ed7d1-426">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="ed7d1-427">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-427">**runtimeconfig.json**</span></span> | <span data-ttu-id="ed7d1-428">不可用</span><span class="sxs-lookup"><span data-stu-id="ed7d1-428">N/A</span></span> | <span data-ttu-id="ed7d1-429">不可用</span><span class="sxs-lookup"><span data-stu-id="ed7d1-429">N/A</span></span> | <span data-ttu-id="ed7d1-430">不可用</span><span class="sxs-lookup"><span data-stu-id="ed7d1-430">N/A</span></span> |
| <span data-ttu-id="ed7d1-431">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-431">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="ed7d1-432">`1` - 启用</span><span class="sxs-lookup"><span data-stu-id="ed7d1-432">`1` - enabled</span></span><br/> <span data-ttu-id="ed7d1-433">`0` - 禁用</span><span class="sxs-lookup"><span data-stu-id="ed7d1-433">`0` - disabled</span></span> | <span data-ttu-id="ed7d1-434">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="ed7d1-434">.NET Core 1.0</span></span> |
| <span data-ttu-id="ed7d1-435">**.NET Framework 的 app.config**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-435">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="ed7d1-436">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="ed7d1-436">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="ed7d1-437">`1` - 启用</span><span class="sxs-lookup"><span data-stu-id="ed7d1-437">`1` - enabled</span></span><br/> <span data-ttu-id="ed7d1-438">`0` - 禁用</span><span class="sxs-lookup"><span data-stu-id="ed7d1-438">`0` - disabled</span></span> | <span data-ttu-id="ed7d1-439">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="ed7d1-439">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="ed7d1-440">大型对象堆阈值</span><span class="sxs-lookup"><span data-stu-id="ed7d1-440">Large object heap threshold</span></span>

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a><span data-ttu-id="ed7d1-441">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="ed7d1-441">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span></span>

- <span data-ttu-id="ed7d1-442">指定导致对象进入大型对象堆 (LOH) 的阈值大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-442">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="ed7d1-443">默认阈值为 85,000 字节。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-443">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="ed7d1-444">指定的值必须大于默认阈值。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-444">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="ed7d1-445">设置名</span><span class="sxs-lookup"><span data-stu-id="ed7d1-445">Setting name</span></span> | <span data-ttu-id="ed7d1-446">值</span><span class="sxs-lookup"><span data-stu-id="ed7d1-446">Values</span></span> | <span data-ttu-id="ed7d1-447">引入的版本</span><span class="sxs-lookup"><span data-stu-id="ed7d1-447">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="ed7d1-448">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-448">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="ed7d1-449">十进制值</span><span class="sxs-lookup"><span data-stu-id="ed7d1-449">*decimal value*</span></span> | <span data-ttu-id="ed7d1-450">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="ed7d1-450">.NET Core 1.0</span></span> |
| <span data-ttu-id="ed7d1-451">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-451">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="ed7d1-452">十六进制值</span><span class="sxs-lookup"><span data-stu-id="ed7d1-452">*hexadecimal value*</span></span> | <span data-ttu-id="ed7d1-453">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="ed7d1-453">.NET Core 1.0</span></span> |
| <span data-ttu-id="ed7d1-454">**.NET Framework 的 app.config**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-454">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="ed7d1-455">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="ed7d1-455">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="ed7d1-456">十进制值</span><span class="sxs-lookup"><span data-stu-id="ed7d1-456">*decimal value*</span></span> | <span data-ttu-id="ed7d1-457">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="ed7d1-457">.NET Framework 4.8</span></span> |

<span data-ttu-id="ed7d1-458">示例：</span><span class="sxs-lookup"><span data-stu-id="ed7d1-458">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.LOHThreshold": 120000
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="ed7d1-459">如果要在 runtimeconfig.template.json 中设置该选项，请指定一个十进制值。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-459">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="ed7d1-460">如果要将选项设置为一个环境变量，请指定一个十六进制值。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-460">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="ed7d1-461">例如，若要将阙值大小设置为 120,000 个字节，则该值对于 JSON 文件为 120,000，对于环境变量则为 0x1D4C0 或 1D4C0。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-461">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="ed7d1-462">独立 GC</span><span class="sxs-lookup"><span data-stu-id="ed7d1-462">Standalone GC</span></span>

### <a name="complus_gcname"></a><span data-ttu-id="ed7d1-463">COMPlus_GCName</span><span class="sxs-lookup"><span data-stu-id="ed7d1-463">COMPlus_GCName</span></span>

- <span data-ttu-id="ed7d1-464">指定库的路径，该库包含运行时打算加载的垃圾回收器。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-464">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="ed7d1-465">有关详细信息，请参阅 [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md)（独立 GC 加载程序设计）。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-465">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="ed7d1-466">设置名</span><span class="sxs-lookup"><span data-stu-id="ed7d1-466">Setting name</span></span> | <span data-ttu-id="ed7d1-467">值</span><span class="sxs-lookup"><span data-stu-id="ed7d1-467">Values</span></span> | <span data-ttu-id="ed7d1-468">引入的版本</span><span class="sxs-lookup"><span data-stu-id="ed7d1-468">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="ed7d1-469">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-469">**runtimeconfig.json**</span></span> | <span data-ttu-id="ed7d1-470">不可用</span><span class="sxs-lookup"><span data-stu-id="ed7d1-470">N/A</span></span> | <span data-ttu-id="ed7d1-471">不可用</span><span class="sxs-lookup"><span data-stu-id="ed7d1-471">N/A</span></span> | <span data-ttu-id="ed7d1-472">不可用</span><span class="sxs-lookup"><span data-stu-id="ed7d1-472">N/A</span></span> |
| <span data-ttu-id="ed7d1-473">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="ed7d1-473">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="ed7d1-474">string_path</span><span class="sxs-lookup"><span data-stu-id="ed7d1-474">*string_path*</span></span> | <span data-ttu-id="ed7d1-475">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="ed7d1-475">.NET Core 2.0</span></span> |
