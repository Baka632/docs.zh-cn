---
ms.openlocfilehash: 958dede03e1c15f69f4ee676f13713ff43c29e96
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032289"
---
### <a name="logging-debuglogger-class-made-internal"></a><span data-ttu-id="9fdf3-101">日志记录：将 DebugLogger 类设为内部类</span><span class="sxs-lookup"><span data-stu-id="9fdf3-101">Logging: DebugLogger class made internal</span></span>

<span data-ttu-id="9fdf3-102">在 ASP.NET Core 3.0 之前，`DebugLogger` 的访问修饰符为 `public`。</span><span class="sxs-lookup"><span data-stu-id="9fdf3-102">Prior to ASP.NET Core 3.0, `DebugLogger`'s access modifier was `public`.</span></span> <span data-ttu-id="9fdf3-103">在 ASP.NET Core 3.0 中，访问修饰符更改为 `internal`。</span><span class="sxs-lookup"><span data-stu-id="9fdf3-103">In ASP.NET Core 3.0, the access modifier changed to `internal`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="9fdf3-104">引入的版本</span><span class="sxs-lookup"><span data-stu-id="9fdf3-104">Version introduced</span></span>

<span data-ttu-id="9fdf3-105">3.0</span><span class="sxs-lookup"><span data-stu-id="9fdf3-105">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="9fdf3-106">更改原因</span><span class="sxs-lookup"><span data-stu-id="9fdf3-106">Reason for change</span></span>

<span data-ttu-id="9fdf3-107">正在进行更改以便：</span><span class="sxs-lookup"><span data-stu-id="9fdf3-107">The change is being made to:</span></span>

* <span data-ttu-id="9fdf3-108">强制执行与其他记录器（如 `ConsoleLogger`）实现的一致性。</span><span class="sxs-lookup"><span data-stu-id="9fdf3-108">Enforce consistency with other logger implementations such as `ConsoleLogger`.</span></span>
* <span data-ttu-id="9fdf3-109">减少 API 图面。</span><span class="sxs-lookup"><span data-stu-id="9fdf3-109">Reduce the API surface.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="9fdf3-110">建议操作</span><span class="sxs-lookup"><span data-stu-id="9fdf3-110">Recommended action</span></span>

<span data-ttu-id="9fdf3-111">使用 <xref:Microsoft.Extensions.Logging.DebugLoggerFactoryExtensions.AddDebug%2A> `ILoggingBuilder` 扩展方法来启用调试日志记录。</span><span class="sxs-lookup"><span data-stu-id="9fdf3-111">Use the <xref:Microsoft.Extensions.Logging.DebugLoggerFactoryExtensions.AddDebug%2A> `ILoggingBuilder` extension method to enable debug logging.</span></span> <span data-ttu-id="9fdf3-112">如果需要手动注册服务，<xref:Microsoft.Extensions.Logging.Debug.DebugLoggerProvider> 也仍为 `public`。</span><span class="sxs-lookup"><span data-stu-id="9fdf3-112"><xref:Microsoft.Extensions.Logging.Debug.DebugLoggerProvider> is also still `public` in the event the service needs to be registered manually.</span></span>

#### <a name="category"></a><span data-ttu-id="9fdf3-113">类别</span><span class="sxs-lookup"><span data-stu-id="9fdf3-113">Category</span></span>

<span data-ttu-id="9fdf3-114">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9fdf3-114">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9fdf3-115">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="9fdf3-115">Affected APIs</span></span>

<xref:Microsoft.Extensions.Logging.Debug.DebugLogger?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.Extensions.Logging.Debug.DebugLogger`

-->
