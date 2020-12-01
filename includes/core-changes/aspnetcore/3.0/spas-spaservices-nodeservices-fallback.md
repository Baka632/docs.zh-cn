---
ms.openlocfilehash: e5355387d5cb6d9e6de89f5b85e64bc100b32ae1
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032434"
---
### <a name="spas-spaservices-and-nodeservices-no-longer-fall-back-to-console-logger"></a><span data-ttu-id="f95ee-101">SPA：SpaServices 和 NodeServices 不再回退到控制台记录器</span><span class="sxs-lookup"><span data-stu-id="f95ee-101">SPAs: SpaServices and NodeServices no longer fall back to console logger</span></span>

<span data-ttu-id="f95ee-102">除非配置了日志记录，否则 <xref:Microsoft.AspNetCore.SpaServices?displayProperty=nameWithType> 和 <xref:Microsoft.AspNetCore.NodeServices?displayProperty=nameWithType> 不会显示控制台日志。</span><span class="sxs-lookup"><span data-stu-id="f95ee-102"><xref:Microsoft.AspNetCore.SpaServices?displayProperty=nameWithType> and <xref:Microsoft.AspNetCore.NodeServices?displayProperty=nameWithType> won't display console logs unless logging is configured.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f95ee-103">引入的版本</span><span class="sxs-lookup"><span data-stu-id="f95ee-103">Version introduced</span></span>

<span data-ttu-id="f95ee-104">3.0</span><span class="sxs-lookup"><span data-stu-id="f95ee-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="f95ee-105">旧行为</span><span class="sxs-lookup"><span data-stu-id="f95ee-105">Old behavior</span></span>

<span data-ttu-id="f95ee-106">`Microsoft.AspNetCore.SpaServices` 和 `Microsoft.AspNetCore.NodeServices` 用于在未配置日志记录时自动创建控制台记录器。</span><span class="sxs-lookup"><span data-stu-id="f95ee-106">`Microsoft.AspNetCore.SpaServices` and `Microsoft.AspNetCore.NodeServices` used to automatically create a console logger when logging isn't configured.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="f95ee-107">新行为</span><span class="sxs-lookup"><span data-stu-id="f95ee-107">New behavior</span></span>

<span data-ttu-id="f95ee-108">除非配置了日志记录，否则 `Microsoft.AspNetCore.SpaServices` 和 `Microsoft.AspNetCore.NodeServices` 不会显示控制台日志。</span><span class="sxs-lookup"><span data-stu-id="f95ee-108">`Microsoft.AspNetCore.SpaServices` and `Microsoft.AspNetCore.NodeServices` won't display console logs unless logging is configured.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="f95ee-109">更改原因</span><span class="sxs-lookup"><span data-stu-id="f95ee-109">Reason for change</span></span>

<span data-ttu-id="f95ee-110">需要与其他 ASP.NET Core 包实现日志记录的方式保持一致。</span><span class="sxs-lookup"><span data-stu-id="f95ee-110">There's a need to align with how other ASP.NET Core packages implement logging.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f95ee-111">建议操作</span><span class="sxs-lookup"><span data-stu-id="f95ee-111">Recommended action</span></span>

<span data-ttu-id="f95ee-112">如果需要旧行为，若要配置控制台日志记录，请将 `services.AddLogging(builder => builder.AddConsole())` 添加到 `Setup.ConfigureServices` 方法。</span><span class="sxs-lookup"><span data-stu-id="f95ee-112">If the old behavior is required, to configure console logging, add `services.AddLogging(builder => builder.AddConsole())` to your `Setup.ConfigureServices` method.</span></span>

#### <a name="category"></a><span data-ttu-id="f95ee-113">类别</span><span class="sxs-lookup"><span data-stu-id="f95ee-113">Category</span></span>

<span data-ttu-id="f95ee-114">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f95ee-114">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f95ee-115">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="f95ee-115">Affected APIs</span></span>

<span data-ttu-id="f95ee-116">None</span><span class="sxs-lookup"><span data-stu-id="f95ee-116">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
