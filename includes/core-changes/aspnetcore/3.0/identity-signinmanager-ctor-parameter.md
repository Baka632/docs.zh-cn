---
ms.openlocfilehash: ed5a90063b8963d79f412ec1c5c0b9030f980f83
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032279"
---
### <a name="identity-signinmanager-constructor-accepts-new-parameter"></a><span data-ttu-id="032c3-101">标识：SignInManager 构造函数接受新参数</span><span class="sxs-lookup"><span data-stu-id="032c3-101">Identity: SignInManager constructor accepts new parameter</span></span>

<span data-ttu-id="032c3-102">从 ASP.NET Core 3.0 开始，新的 `IUserConfirmation<TUser>` 参数添加到了 `SignInManager` 构造函数中。</span><span class="sxs-lookup"><span data-stu-id="032c3-102">Starting with ASP.NET Core 3.0, a new `IUserConfirmation<TUser>` parameter was added to the `SignInManager` constructor.</span></span> <span data-ttu-id="032c3-103">有关详细信息，请参阅 [dotnet/aspnetcore#8356](https://github.com/dotnet/aspnetcore/issues/8356)。</span><span class="sxs-lookup"><span data-stu-id="032c3-103">For more information, see [dotnet/aspnetcore#8356](https://github.com/dotnet/aspnetcore/issues/8356).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="032c3-104">引入的版本</span><span class="sxs-lookup"><span data-stu-id="032c3-104">Version introduced</span></span>

<span data-ttu-id="032c3-105">3.0</span><span class="sxs-lookup"><span data-stu-id="032c3-105">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="032c3-106">更改原因</span><span class="sxs-lookup"><span data-stu-id="032c3-106">Reason for change</span></span>

<span data-ttu-id="032c3-107">更改的动机是为了添加对标识中的新电子邮件/确认流的支持。</span><span class="sxs-lookup"><span data-stu-id="032c3-107">The motivation for the change was to add support for new email / confirmation flows in Identity.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="032c3-108">建议操作</span><span class="sxs-lookup"><span data-stu-id="032c3-108">Recommended action</span></span>

<span data-ttu-id="032c3-109">如果手动构造 `SignInManager`，请提供 `IUserConfirmation` 的实现，或从依赖项注入获取一个实现来提供。</span><span class="sxs-lookup"><span data-stu-id="032c3-109">If manually constructing a `SignInManager`, provide an implementation of `IUserConfirmation` or grab one from dependency injection to provide.</span></span>

#### <a name="category"></a><span data-ttu-id="032c3-110">类别</span><span class="sxs-lookup"><span data-stu-id="032c3-110">Category</span></span>

<span data-ttu-id="032c3-111">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="032c3-111">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="032c3-112">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="032c3-112">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Identity.SignInManager%601.%23ctor%2A>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Identity.SignInManager`1.#ctor`

-->
