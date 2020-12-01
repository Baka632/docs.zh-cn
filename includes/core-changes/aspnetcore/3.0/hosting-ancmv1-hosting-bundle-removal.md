---
ms.openlocfilehash: 82103d82a6f68c62f3532608718bc71b0ba126bf
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032267"
---
### <a name="hosting-aspnetcoremodule-v1-removed-from-windows-hosting-bundle"></a><span data-ttu-id="3a008-101">托管：从 Windows 托管捆绑包中删除了 AspNetCoreModule V1</span><span class="sxs-lookup"><span data-stu-id="3a008-101">Hosting: AspNetCoreModule V1 removed from Windows Hosting Bundle</span></span>

<span data-ttu-id="3a008-102">从 ASP.NET Core 3.0 开始，Windows 托管捆绑不包含 AspNetCoreModule (ANCM) V1。</span><span class="sxs-lookup"><span data-stu-id="3a008-102">Starting with ASP.NET Core 3.0, the Windows Hosting Bundle won't contain AspNetCoreModule (ANCM) V1.</span></span>

<span data-ttu-id="3a008-103">ANCM V2 向后兼容 ANCM OutOfProcess，建议与 ASP.NET Core 3.0 应用一起使用。</span><span class="sxs-lookup"><span data-stu-id="3a008-103">ANCM V2 is backwards compatible with ANCM OutOfProcess and is recommended for use with ASP.NET Core 3.0 apps.</span></span>

<span data-ttu-id="3a008-104">有关讨论，请参阅 [dotnet/aspnetcore#7095](https://github.com/dotnet/aspnetcore/issues/7095)。</span><span class="sxs-lookup"><span data-stu-id="3a008-104">For discussion, see [dotnet/aspnetcore#7095](https://github.com/dotnet/aspnetcore/issues/7095).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3a008-105">引入的版本</span><span class="sxs-lookup"><span data-stu-id="3a008-105">Version introduced</span></span>

<span data-ttu-id="3a008-106">3.0</span><span class="sxs-lookup"><span data-stu-id="3a008-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="3a008-107">旧行为</span><span class="sxs-lookup"><span data-stu-id="3a008-107">Old behavior</span></span>

<span data-ttu-id="3a008-108">ANCM V1 包含在 Windows 托管捆绑包中。</span><span class="sxs-lookup"><span data-stu-id="3a008-108">ANCM V1 is included in the Windows Hosting Bundle.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="3a008-109">新行为</span><span class="sxs-lookup"><span data-stu-id="3a008-109">New behavior</span></span>

<span data-ttu-id="3a008-110">ANCM V1 不包含在 Windows 托管捆绑包中。</span><span class="sxs-lookup"><span data-stu-id="3a008-110">ANCM V1 isn't included in the Windows Hosting Bundle.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="3a008-111">更改原因</span><span class="sxs-lookup"><span data-stu-id="3a008-111">Reason for change</span></span>

<span data-ttu-id="3a008-112">ANCM V2 向后兼容 ANCM OutOfProcess，建议与 ASP.NET Core 3.0 应用一起使用。</span><span class="sxs-lookup"><span data-stu-id="3a008-112">ANCM V2 is backwards compatible with ANCM OutOfProcess and is recommended for use with ASP.NET Core 3.0 apps.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3a008-113">建议操作</span><span class="sxs-lookup"><span data-stu-id="3a008-113">Recommended action</span></span>

<span data-ttu-id="3a008-114">将 ANCM V2 与 ASP.NET Core 3.0 应用一起使用。</span><span class="sxs-lookup"><span data-stu-id="3a008-114">Use ANCM V2 with ASP.NET Core 3.0 apps.</span></span>

<span data-ttu-id="3a008-115">如果需要 ANCM V1，则可以使用 ASP.NET Core 2.1 或 2.2 Windows 托管捆绑包进行安装。</span><span class="sxs-lookup"><span data-stu-id="3a008-115">If ANCM V1 is required, it can be installed using the ASP.NET Core 2.1 or 2.2 Windows Hosting Bundle.</span></span>

<span data-ttu-id="3a008-116">此更改将中断以下 ASP.NET Core 3.0 应用：</span><span class="sxs-lookup"><span data-stu-id="3a008-116">This change will break ASP.NET Core 3.0 apps that:</span></span>

- <span data-ttu-id="3a008-117">已明确选择将 ANCM V1 与 `<AspNetCoreModuleName>AspNetCoreModule</AspNetCoreModuleName>` 结合使用。</span><span class="sxs-lookup"><span data-stu-id="3a008-117">Explicitly opted into using ANCM V1 with `<AspNetCoreModuleName>AspNetCoreModule</AspNetCoreModuleName>`.</span></span>
- <span data-ttu-id="3a008-118">具有 `<add name="aspNetCore" path="*" verb="*" modules="AspNetCoreModule" resourceType="Unspecified" />` 的自定义 web.config  文件。</span><span class="sxs-lookup"><span data-stu-id="3a008-118">Have a custom *web.config* file with `<add name="aspNetCore" path="*" verb="*" modules="AspNetCoreModule" resourceType="Unspecified" />`.</span></span>

#### <a name="category"></a><span data-ttu-id="3a008-119">类别</span><span class="sxs-lookup"><span data-stu-id="3a008-119">Category</span></span>

<span data-ttu-id="3a008-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3a008-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3a008-121">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="3a008-121">Affected APIs</span></span>

<span data-ttu-id="3a008-122">None</span><span class="sxs-lookup"><span data-stu-id="3a008-122">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
