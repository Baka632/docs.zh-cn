---
ms.openlocfilehash: 4dcb357570cb6597fde86c9e8f2acb74364cfaa3
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032409"
---
### <a name="session-state-obsolete-apis-removed"></a><span data-ttu-id="656af-101">会话状态：已删除过时的 API</span><span class="sxs-lookup"><span data-stu-id="656af-101">Session state: Obsolete APIs removed</span></span>

<span data-ttu-id="656af-102">已删除用于配置会话 cookie 的过时 API。</span><span class="sxs-lookup"><span data-stu-id="656af-102">Obsolete APIs for configuring session cookies were removed.</span></span> <span data-ttu-id="656af-103">有关详细信息，请参阅 [aspnet/Announcements#257](https://github.com/aspnet/Announcements/issues/257)。</span><span class="sxs-lookup"><span data-stu-id="656af-103">For more information, see [aspnet/Announcements#257](https://github.com/aspnet/Announcements/issues/257).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="656af-104">引入的版本</span><span class="sxs-lookup"><span data-stu-id="656af-104">Version introduced</span></span>

<span data-ttu-id="656af-105">3.0</span><span class="sxs-lookup"><span data-stu-id="656af-105">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="656af-106">更改原因</span><span class="sxs-lookup"><span data-stu-id="656af-106">Reason for change</span></span>

<span data-ttu-id="656af-107">此更改强制实施跨 API 的一致性来配置使用 cookie 的功能。</span><span class="sxs-lookup"><span data-stu-id="656af-107">This change enforces consistency across APIs for configuring features that use cookies.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="656af-108">建议操作</span><span class="sxs-lookup"><span data-stu-id="656af-108">Recommended action</span></span>

<span data-ttu-id="656af-109">将已删除的 API 的使用迁移到其更新的替换项。</span><span class="sxs-lookup"><span data-stu-id="656af-109">Migrate usage of the removed APIs to their newer replacements.</span></span> <span data-ttu-id="656af-110">请看下面 `Startup.ConfigureServices` 中的示例：</span><span class="sxs-lookup"><span data-stu-id="656af-110">Consider the following example in `Startup.ConfigureServices`:</span></span>

```csharp
public void ConfigureServices(ServiceCollection services)
{
    services.AddSession(options =>
    {
        // Removed obsolete APIs
        options.CookieName = "SessionCookie";
        options.CookieDomain = "contoso.com";
        options.CookiePath = "/";
        options.CookieHttpOnly = true;
        options.CookieSecure = CookieSecurePolicy.Always;

        // new API
        options.Cookie.Name = "SessionCookie";
        options.Cookie.Domain = "contoso.com";
        options.Cookie.Path = "/";
        options.Cookie.HttpOnly = true;
        options.Cookie.SecurePolicy = CookieSecurePolicy.Always;
    });
}
```

#### <a name="category"></a><span data-ttu-id="656af-111">类别</span><span class="sxs-lookup"><span data-stu-id="656af-111">Category</span></span>

<span data-ttu-id="656af-112">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="656af-112">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="656af-113">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="656af-113">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Builder.SessionOptions.CookieDomain?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Builder.SessionOptions.CookieHttpOnly?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Builder.SessionOptions.CookieName?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Builder.SessionOptions.CookiePath?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Builder.SessionOptions.CookieSecure?displayProperty=fullName>

<!-- 

#### Affected APIs

- `P:Microsoft.AspNetCore.Builder.SessionOptions.CookieDomain`
- `P:Microsoft.AspNetCore.Builder.SessionOptions.CookieHttpOnly`
- `P:Microsoft.AspNetCore.Builder.SessionOptions.CookieName`
- `P:Microsoft.AspNetCore.Builder.SessionOptions.CookiePath`
- `P:Microsoft.AspNetCore.Builder.SessionOptions.CookieSecure`

-->
