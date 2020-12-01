---
ms.openlocfilehash: fb23418816abcae125106c93b339a546aa9bc2ee
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032283"
---
### <a name="kestrel-transport-abstractions-removed-and-made-public"></a><span data-ttu-id="b039b-101">Kestrel：删除并公开传输抽象</span><span class="sxs-lookup"><span data-stu-id="b039b-101">Kestrel: Transport abstractions removed and made public</span></span>

<span data-ttu-id="b039b-102">作为远离“pubternal”API 的一部分，Kestrel 传输层 API 被公开为 `Microsoft.AspNetCore.Connections.Abstractions` 库中的公共接口。</span><span class="sxs-lookup"><span data-stu-id="b039b-102">As part of moving away from "pubternal" APIs, the Kestrel transport layer APIs are exposed as a public interface in the `Microsoft.AspNetCore.Connections.Abstractions` library.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b039b-103">引入的版本</span><span class="sxs-lookup"><span data-stu-id="b039b-103">Version introduced</span></span>

<span data-ttu-id="b039b-104">3.0</span><span class="sxs-lookup"><span data-stu-id="b039b-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="b039b-105">旧行为</span><span class="sxs-lookup"><span data-stu-id="b039b-105">Old behavior</span></span>

- <span data-ttu-id="b039b-106">`Microsoft.AspNetCore.Server.Kestrel.Transport.Abstractions` 库中提供传输相关的抽象。</span><span class="sxs-lookup"><span data-stu-id="b039b-106">Transport-related abstractions were available in the `Microsoft.AspNetCore.Server.Kestrel.Transport.Abstractions` library.</span></span>
- <span data-ttu-id="b039b-107">`ListenOptions.NoDelay` 属性可用。</span><span class="sxs-lookup"><span data-stu-id="b039b-107">The `ListenOptions.NoDelay` property was available.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="b039b-108">新行为</span><span class="sxs-lookup"><span data-stu-id="b039b-108">New behavior</span></span>

- <span data-ttu-id="b039b-109">在 `Microsoft.AspNetCore.Connections.Abstractions` 库中引入 `IConnectionListener` 接口以公开 `...Transport.Abstractions` 库最常用的功能。</span><span class="sxs-lookup"><span data-stu-id="b039b-109">The `IConnectionListener` interface was introduced in the `Microsoft.AspNetCore.Connections.Abstractions` library to expose the most used functionality from the `...Transport.Abstractions` library.</span></span>
- <span data-ttu-id="b039b-110">现在提供传输选项 `NoDelay`（`LibuvTransportOptions` 和 `SocketTransportOptions`）。</span><span class="sxs-lookup"><span data-stu-id="b039b-110">The `NoDelay` is now available in transport options (`LibuvTransportOptions` and `SocketTransportOptions`).</span></span>
- <span data-ttu-id="b039b-111">`SchedulingMode` 不再可用。</span><span class="sxs-lookup"><span data-stu-id="b039b-111">`SchedulingMode` is no longer available.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="b039b-112">更改原因</span><span class="sxs-lookup"><span data-stu-id="b039b-112">Reason for change</span></span>

<span data-ttu-id="b039b-113">ASP.NET Core 3.0 已从“pubternal”API 移出。</span><span class="sxs-lookup"><span data-stu-id="b039b-113">ASP.NET Core 3.0 has moved away from "pubternal" APIs.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b039b-114">建议操作</span><span class="sxs-lookup"><span data-stu-id="b039b-114">Recommended action</span></span>

#### <a name="category"></a><span data-ttu-id="b039b-115">类别</span><span class="sxs-lookup"><span data-stu-id="b039b-115">Category</span></span>

<span data-ttu-id="b039b-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b039b-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b039b-117">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="b039b-117">Affected APIs</span></span>

<span data-ttu-id="b039b-118">None</span><span class="sxs-lookup"><span data-stu-id="b039b-118">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
