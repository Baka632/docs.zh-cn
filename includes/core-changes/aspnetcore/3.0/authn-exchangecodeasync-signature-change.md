---
ms.openlocfilehash: a4e20e0468d861138ad801c9dbfa15340b3f388c
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032258"
---
### <a name="authentication-oauthhandler-exchangecodeasync-signature-changed"></a><span data-ttu-id="14fc9-101">身份验证：已更改 OAuthHandler ExchangeCodeAsync 签名</span><span class="sxs-lookup"><span data-stu-id="14fc9-101">Authentication: OAuthHandler ExchangeCodeAsync signature changed</span></span>

<span data-ttu-id="14fc9-102">在 ASP.NET Core 3.0 中，`OAuthHandler.ExchangeCodeAsync` 的签名已从以下位置更改：</span><span class="sxs-lookup"><span data-stu-id="14fc9-102">In ASP.NET Core 3.0, the signature of `OAuthHandler.ExchangeCodeAsync` was changed from:</span></span>

```csharp
protected virtual System.Threading.Tasks.Task<Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse> ExchangeCodeAsync(string code, string redirectUri) { throw null; }
```

<span data-ttu-id="14fc9-103">到:</span><span class="sxs-lookup"><span data-stu-id="14fc9-103">To:</span></span>

```csharp
protected virtual System.Threading.Tasks.Task<Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse> ExchangeCodeAsync(Microsoft.AspNetCore.Authentication.OAuth.OAuthCodeExchangeContext context) { throw null; }
```

#### <a name="version-introduced"></a><span data-ttu-id="14fc9-104">引入的版本</span><span class="sxs-lookup"><span data-stu-id="14fc9-104">Version introduced</span></span>

<span data-ttu-id="14fc9-105">3.0</span><span class="sxs-lookup"><span data-stu-id="14fc9-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="14fc9-106">旧行为</span><span class="sxs-lookup"><span data-stu-id="14fc9-106">Old behavior</span></span>

<span data-ttu-id="14fc9-107">`code` 和 `redirectUri` 字符串作为单独的参数传递。</span><span class="sxs-lookup"><span data-stu-id="14fc9-107">The `code` and `redirectUri` strings were passed as separate arguments.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="14fc9-108">新行为</span><span class="sxs-lookup"><span data-stu-id="14fc9-108">New behavior</span></span>

<span data-ttu-id="14fc9-109">`Code` 和 `RedirectUri` 是 `OAuthCodeExchangeContext` 上的属性，可通过 `OAuthCodeExchangeContext` 构造函数进行设置。</span><span class="sxs-lookup"><span data-stu-id="14fc9-109">`Code` and `RedirectUri` are properties on `OAuthCodeExchangeContext` that can be set via the `OAuthCodeExchangeContext` constructor.</span></span> <span data-ttu-id="14fc9-110">新的 `OAuthCodeExchangeContext` 类型是传递到 `OAuthHandler.ExchangeCodeAsync` 的唯一参数。</span><span class="sxs-lookup"><span data-stu-id="14fc9-110">The new `OAuthCodeExchangeContext` type is the only argument passed to `OAuthHandler.ExchangeCodeAsync`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="14fc9-111">更改原因</span><span class="sxs-lookup"><span data-stu-id="14fc9-111">Reason for change</span></span>

<span data-ttu-id="14fc9-112">此更改允许以非中断方式提供其他参数。</span><span class="sxs-lookup"><span data-stu-id="14fc9-112">This change allows additional parameters to be provided in a non-breaking manner.</span></span> <span data-ttu-id="14fc9-113">无需创建新的 `ExchangeCodeAsync` 重载。</span><span class="sxs-lookup"><span data-stu-id="14fc9-113">There's no need to create new `ExchangeCodeAsync` overloads.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="14fc9-114">建议操作</span><span class="sxs-lookup"><span data-stu-id="14fc9-114">Recommended action</span></span>

<span data-ttu-id="14fc9-115">使用适当的 `code` 和 `redirectUri` 值构造 `OAuthCodeExchangeContext`。</span><span class="sxs-lookup"><span data-stu-id="14fc9-115">Construct an `OAuthCodeExchangeContext` with the appropriate `code` and `redirectUri` values.</span></span> <span data-ttu-id="14fc9-116">必须提供 <xref:Microsoft.AspNetCore.Authentication.AuthenticationProperties> 实例。</span><span class="sxs-lookup"><span data-stu-id="14fc9-116">An <xref:Microsoft.AspNetCore.Authentication.AuthenticationProperties> instance must be provided.</span></span> <span data-ttu-id="14fc9-117">此单个 `OAuthCodeExchangeContext` 实例可传递到 `OAuthHandler.ExchangeCodeAsync` 而不是多个参数。</span><span class="sxs-lookup"><span data-stu-id="14fc9-117">This single `OAuthCodeExchangeContext` instance can be passed to `OAuthHandler.ExchangeCodeAsync` instead of multiple arguments.</span></span>

#### <a name="category"></a><span data-ttu-id="14fc9-118">类别</span><span class="sxs-lookup"><span data-stu-id="14fc9-118">Category</span></span>

<span data-ttu-id="14fc9-119">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="14fc9-119">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="14fc9-120">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="14fc9-120">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthHandler%601.ExchangeCodeAsync(System.String,System.String)?displayProperty=nameWithType>

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Authentication.OAuth.OAuthHandler`1.ExchangeCodeAsync(System.String,System.String)`

-->
