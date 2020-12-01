---
ms.openlocfilehash: 6be98e7ced6608ba0793c635adfe61c8b1a7e9d9
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032416"
---
### <a name="signalr-hubconnectioncontext-constructors-changed"></a><span data-ttu-id="77e3a-101">SignalR：已更改 HubConnectionContext 构造函数</span><span class="sxs-lookup"><span data-stu-id="77e3a-101">SignalR: HubConnectionContext constructors changed</span></span>

<span data-ttu-id="77e3a-102">SignalR 的 `HubConnectionContext` 构造函数已更改为接受选项类型（而不是多个参数），以接受经得起未来考验的添加选项。</span><span class="sxs-lookup"><span data-stu-id="77e3a-102">SignalR's `HubConnectionContext` constructors changed to accept an options type, rather than multiple parameters, to future-proof adding options.</span></span> <span data-ttu-id="77e3a-103">此更改使用单个接受选项类型的构造函数替换两个构造函数。</span><span class="sxs-lookup"><span data-stu-id="77e3a-103">This change replaces two constructors with a single constructor that accepts an options type.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="77e3a-104">引入的版本</span><span class="sxs-lookup"><span data-stu-id="77e3a-104">Version introduced</span></span>

<span data-ttu-id="77e3a-105">3.0</span><span class="sxs-lookup"><span data-stu-id="77e3a-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="77e3a-106">旧行为</span><span class="sxs-lookup"><span data-stu-id="77e3a-106">Old behavior</span></span>

<span data-ttu-id="77e3a-107">`HubConnectionContext` 有两个构造函数：</span><span class="sxs-lookup"><span data-stu-id="77e3a-107">`HubConnectionContext` has two constructors:</span></span>

```csharp
public HubConnectionContext(ConnectionContext connectionContext, TimeSpan keepAliveInterval, ILoggerFactory loggerFactory);
public HubConnectionContext(ConnectionContext connectionContext, TimeSpan keepAliveInterval, ILoggerFactory loggerFactory, TimeSpan clientTimeoutInterval);
```

#### <a name="new-behavior"></a><span data-ttu-id="77e3a-108">新行为</span><span class="sxs-lookup"><span data-stu-id="77e3a-108">New behavior</span></span>

<span data-ttu-id="77e3a-109">这两个构造函数已被删除并已替换为一个构造函数：</span><span class="sxs-lookup"><span data-stu-id="77e3a-109">The two constructors were removed and replaced with one constructor:</span></span>

```csharp
public HubConnectionContext(ConnectionContext connectionContext, HubConnectionContextOptions contextOptions, ILoggerFactory loggerFactory)
```

#### <a name="reason-for-change"></a><span data-ttu-id="77e3a-110">更改原因</span><span class="sxs-lookup"><span data-stu-id="77e3a-110">Reason for change</span></span>

<span data-ttu-id="77e3a-111">新的构造函数使用新的选项对象。</span><span class="sxs-lookup"><span data-stu-id="77e3a-111">The new constructor uses a new options object.</span></span> <span data-ttu-id="77e3a-112">因此，可以在以后展开 `HubConnectionContext` 的功能，而无需执行更多的构造函数和中断性变更。</span><span class="sxs-lookup"><span data-stu-id="77e3a-112">Consequently, the features of `HubConnectionContext` can be expanded in the future without making more constructors and breaking changes.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="77e3a-113">建议操作</span><span class="sxs-lookup"><span data-stu-id="77e3a-113">Recommended action</span></span>

<span data-ttu-id="77e3a-114">而不是使用以下构造函数：</span><span class="sxs-lookup"><span data-stu-id="77e3a-114">Instead of using the following constructor:</span></span>

```csharp
HubConnectionContext connectionContext = new HubConnectionContext(
    connectionContext,
    keepAliveInterval: TimeSpan.FromSeconds(15),
    loggerFactory,
    clientTimeoutInterval: TimeSpan.FromSeconds(15));
```

<span data-ttu-id="77e3a-115">使用以下构造函数：</span><span class="sxs-lookup"><span data-stu-id="77e3a-115">Use the following constructor:</span></span>

```csharp
HubConnectionContextOptions contextOptions = new HubConnectionContextOptions()
{
    KeepAliveInterval = TimeSpan.FromSeconds(15),
    ClientTimeoutInterval = TimeSpan.FromSeconds(15)
};
HubConnectionContext connectionContext = new HubConnectionContext(connectionContext, contextOptions, loggerFactory);
```

#### <a name="category"></a><span data-ttu-id="77e3a-116">类别</span><span class="sxs-lookup"><span data-stu-id="77e3a-116">Category</span></span>

<span data-ttu-id="77e3a-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="77e3a-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="77e3a-118">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="77e3a-118">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.SignalR.HubConnectionContext.%23ctor(Microsoft.AspNetCore.Connections.ConnectionContext,System.TimeSpan,Microsoft.Extensions.Logging.ILoggerFactory)>
- <xref:Microsoft.AspNetCore.SignalR.HubConnectionContext.%23ctor(Microsoft.AspNetCore.Connections.ConnectionContext,System.TimeSpan,Microsoft.Extensions.Logging.ILoggerFactory,System.TimeSpan)>

<!--

#### Affected APIs

- `M:Microsoft.AspNetCore.SignalR.HubConnectionContext.#ctor(Microsoft.AspNetCore.Connections.ConnectionContext,System.TimeSpan,Microsoft.Extensions.Logging.ILoggerFactory)`
- `M:Microsoft.AspNetCore.SignalR.HubConnectionContext.#ctor(Microsoft.AspNetCore.Connections.ConnectionContext,System.TimeSpan,Microsoft.Extensions.Logging.ILoggerFactory,System.TimeSpan)`

-->
