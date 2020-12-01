---
ms.openlocfilehash: 06d5f48566c239e37355496c3f27163d952602c6
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032282"
---
### <a name="kestrel-connection-adapters-removed"></a><span data-ttu-id="b81f1-101">Kestrel：已删除连接适配器</span><span class="sxs-lookup"><span data-stu-id="b81f1-101">Kestrel: Connection adapters removed</span></span>

<span data-ttu-id="b81f1-102">作为将“pubternal”API 移动到 `public` 的移动的一部分，已从 Kestrel 中删除 `IConnectionAdapter` 的概念。</span><span class="sxs-lookup"><span data-stu-id="b81f1-102">As part of the move to move "pubternal" APIs to `public`, the concept of an `IConnectionAdapter` was removed from Kestrel.</span></span> <span data-ttu-id="b81f1-103">正在将连接适配器替换为连接中间件（这与 ASP.NET Core 管道中的 HTTP 中间件类似，但适用于较低级别的连接）。</span><span class="sxs-lookup"><span data-stu-id="b81f1-103">Connection adapters are being replaced with connection middleware (similar to HTTP middleware in the ASP.NET Core pipeline, but for lower-level connections).</span></span> <span data-ttu-id="b81f1-104">HTTPS 和连接日志记录已从连接适配器转移到连接中间件。</span><span class="sxs-lookup"><span data-stu-id="b81f1-104">HTTPS and connection logging have moved from connection adapters to connection middleware.</span></span> <span data-ttu-id="b81f1-105">这些扩展方法应能继续无缝运行，但实现详细信息发生了改变。</span><span class="sxs-lookup"><span data-stu-id="b81f1-105">Those extension methods should continue to work seamlessly, but the implementation details have changed.</span></span>

<span data-ttu-id="b81f1-106">有关详细信息，请参阅 [dotnet/aspnetcore#11412](https://github.com/dotnet/aspnetcore/pull/11412)。</span><span class="sxs-lookup"><span data-stu-id="b81f1-106">For more information, see [dotnet/aspnetcore#11412](https://github.com/dotnet/aspnetcore/pull/11412).</span></span> <span data-ttu-id="b81f1-107">有关讨论，请参阅 [dotnet/aspnetcore#11475](https://github.com/dotnet/aspnetcore/issues/11475)。</span><span class="sxs-lookup"><span data-stu-id="b81f1-107">For discussion, see [dotnet/aspnetcore#11475](https://github.com/dotnet/aspnetcore/issues/11475).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b81f1-108">引入的版本</span><span class="sxs-lookup"><span data-stu-id="b81f1-108">Version introduced</span></span>

<span data-ttu-id="b81f1-109">3.0</span><span class="sxs-lookup"><span data-stu-id="b81f1-109">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="b81f1-110">旧行为</span><span class="sxs-lookup"><span data-stu-id="b81f1-110">Old behavior</span></span>

<span data-ttu-id="b81f1-111">Kestrel 扩展性组件是使用 `IConnectionAdapter` 创建的。</span><span class="sxs-lookup"><span data-stu-id="b81f1-111">Kestrel extensibility components were created using `IConnectionAdapter`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="b81f1-112">新行为</span><span class="sxs-lookup"><span data-stu-id="b81f1-112">New behavior</span></span>

<span data-ttu-id="b81f1-113">Kestrel 扩展性组件被创建为[中间件](https://github.com/dotnet/aspnetcore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f)。</span><span class="sxs-lookup"><span data-stu-id="b81f1-113">Kestrel extensibility components are created as [middleware](https://github.com/dotnet/aspnetcore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f).</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="b81f1-114">更改原因</span><span class="sxs-lookup"><span data-stu-id="b81f1-114">Reason for change</span></span>

<span data-ttu-id="b81f1-115">此更改旨在提供更灵活的扩展性体系结构。</span><span class="sxs-lookup"><span data-stu-id="b81f1-115">This change is intended to provide a more flexible extensibility architecture.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b81f1-116">建议操作</span><span class="sxs-lookup"><span data-stu-id="b81f1-116">Recommended action</span></span>

<span data-ttu-id="b81f1-117">转换 `IConnectionAdapter` 的任何实现以使用新的中间件模式，如[此处](https://github.com/dotnet/aspnetcore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f)所示。</span><span class="sxs-lookup"><span data-stu-id="b81f1-117">Convert any implementations of `IConnectionAdapter` to use the new middleware pattern as shown [here](https://github.com/dotnet/aspnetcore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f).</span></span>

#### <a name="category"></a><span data-ttu-id="b81f1-118">类别</span><span class="sxs-lookup"><span data-stu-id="b81f1-118">Category</span></span>

<span data-ttu-id="b81f1-119">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b81f1-119">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b81f1-120">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="b81f1-120">Affected APIs</span></span>

`Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal.IConnectionAdapter`

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal.IConnectionAdapter`

-->
