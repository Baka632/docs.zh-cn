---
ms.openlocfilehash: 15ba678431b97e7c961c119d83546569bdf9bad2
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032272"
---
### <a name="http-some-cookie-samesite-defaults-changed-to-none"></a><span data-ttu-id="e6d7d-101">HTTP：某些 cookie SameSite 默认值更改为“None”</span><span class="sxs-lookup"><span data-stu-id="e6d7d-101">HTTP: Some cookie SameSite defaults changed to None</span></span>

<span data-ttu-id="e6d7d-102">`SameSite` 是 cookie 的一个选项，可以帮助减轻某些跨站点请求伪造 (CSRF) 攻击。</span><span class="sxs-lookup"><span data-stu-id="e6d7d-102">`SameSite` is an option for cookies that can help mitigate some Cross-Site Request Forgery (CSRF) attacks.</span></span> <span data-ttu-id="e6d7d-103">最初引入此选项时，各种 ASP.NET Core API 中使用了不一致的默认值。</span><span class="sxs-lookup"><span data-stu-id="e6d7d-103">When this option was initially introduced, inconsistent defaults were used across various ASP.NET Core APIs.</span></span> <span data-ttu-id="e6d7d-104">不一致会导致结果混乱。</span><span class="sxs-lookup"><span data-stu-id="e6d7d-104">The inconsistency has led to confusing results.</span></span> <span data-ttu-id="e6d7d-105">从 ASP.NET Core 3.0 开始，这些默认值更一致了。</span><span class="sxs-lookup"><span data-stu-id="e6d7d-105">As of ASP.NET Core 3.0, these defaults are better aligned.</span></span> <span data-ttu-id="e6d7d-106">必须为每个组件选择启用此功能。</span><span class="sxs-lookup"><span data-stu-id="e6d7d-106">You must opt in to this feature on a per-component basis.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e6d7d-107">引入的版本</span><span class="sxs-lookup"><span data-stu-id="e6d7d-107">Version introduced</span></span>

<span data-ttu-id="e6d7d-108">3.0</span><span class="sxs-lookup"><span data-stu-id="e6d7d-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="e6d7d-109">旧行为</span><span class="sxs-lookup"><span data-stu-id="e6d7d-109">Old behavior</span></span>

<span data-ttu-id="e6d7d-110">类似的 ASP.NET Core API 使用不同的默认值 <xref:Microsoft.AspNetCore.Http.SameSiteMode>。</span><span class="sxs-lookup"><span data-stu-id="e6d7d-110">Similar ASP.NET Core APIs used different default <xref:Microsoft.AspNetCore.Http.SameSiteMode> values.</span></span> <span data-ttu-id="e6d7d-111">在 `HttpResponse.Cookies.Append(String, String)` 和 `HttpResponse.Cookies.Append(String, String, CookieOptions)` 中可以看到不一致的示例，它们分别默认为 `SameSiteMode.None` 和 `SameSiteMode.Lax`。</span><span class="sxs-lookup"><span data-stu-id="e6d7d-111">An example of the inconsistency is seen in `HttpResponse.Cookies.Append(String, String)` and `HttpResponse.Cookies.Append(String, String, CookieOptions)`, which defaulted to `SameSiteMode.None` and `SameSiteMode.Lax`, respectively.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="e6d7d-112">新行为</span><span class="sxs-lookup"><span data-stu-id="e6d7d-112">New behavior</span></span>

<span data-ttu-id="e6d7d-113">所有受影响的 API 都默认为 `SameSiteMode.None`。</span><span class="sxs-lookup"><span data-stu-id="e6d7d-113">All the affected APIs default to `SameSiteMode.None`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="e6d7d-114">更改原因</span><span class="sxs-lookup"><span data-stu-id="e6d7d-114">Reason for change</span></span>

<span data-ttu-id="e6d7d-115">更改了默认值，使 `SameSite` 成为可选功能。</span><span class="sxs-lookup"><span data-stu-id="e6d7d-115">The default value was changed to make `SameSite` an opt-in feature.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e6d7d-116">建议操作</span><span class="sxs-lookup"><span data-stu-id="e6d7d-116">Recommended action</span></span>

<span data-ttu-id="e6d7d-117">发出 cookie 的每个组件都需要决定 `SameSite` 是否适用于其方案。</span><span class="sxs-lookup"><span data-stu-id="e6d7d-117">Each component that emits cookies needs to decide if `SameSite` is appropriate for its scenarios.</span></span> <span data-ttu-id="e6d7d-118">检查受影响 API 的使用情况，并根据需要重新配置 `SameSite`。</span><span class="sxs-lookup"><span data-stu-id="e6d7d-118">Review your usage of the affected APIs and reconfigure `SameSite` as needed.</span></span>

#### <a name="category"></a><span data-ttu-id="e6d7d-119">类别</span><span class="sxs-lookup"><span data-stu-id="e6d7d-119">Category</span></span>

<span data-ttu-id="e6d7d-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e6d7d-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e6d7d-121">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="e6d7d-121">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Http.IResponseCookies.Append(System.String,System.String,Microsoft.AspNetCore.Http.CookieOptions)?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Builder.CookiePolicyOptions.MinimumSameSitePolicy%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:Microsoft.AspNetCore.Http.IResponseCookies.Append(System.String,System.String,Microsoft.AspNetCore.Http.CookieOptions)`
- `Overload:Microsoft.AspNetCore.Builder.CookiePolicyOptions.MinimumSameSitePolicy`

-->
