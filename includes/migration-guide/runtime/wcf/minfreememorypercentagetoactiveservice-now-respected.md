---
ms.openlocfilehash: b23182ad1da8208a69b78fc7bc872780d386a59a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496212"
---
### <a name="minfreememorypercentagetoactiveservice-is-now-respected"></a><span data-ttu-id="7ca79-101">MinFreeMemoryPercentageToActiveService 现在受到遵从</span><span class="sxs-lookup"><span data-stu-id="7ca79-101">MinFreeMemoryPercentageToActiveService is now respected</span></span>

#### <a name="details"></a><span data-ttu-id="7ca79-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="7ca79-102">Details</span></span>

<span data-ttu-id="7ca79-103">此设置可确立激活 WCF 服务之前必须在服务器上可用的最小内存。</span><span class="sxs-lookup"><span data-stu-id="7ca79-103">This setting establishes the minimum memory that must be available on the server before a WCF service can be activated.</span></span> <span data-ttu-id="7ca79-104">它旨在阻止 <xref:System.OutOfMemoryException?displayProperty=fullName> 异常。</span><span class="sxs-lookup"><span data-stu-id="7ca79-104">It is designed to prevent <xref:System.OutOfMemoryException?displayProperty=fullName> exceptions.</span></span> <span data-ttu-id="7ca79-105">在 .NET Framework 4.5 中，此设置没有效果。</span><span class="sxs-lookup"><span data-stu-id="7ca79-105">In the .NET Framework 4.5, this setting had no effect.</span></span> <span data-ttu-id="7ca79-106">在 .NET Framework 4.5.1 中，观察到该设置。</span><span class="sxs-lookup"><span data-stu-id="7ca79-106">In the .NET Framework 4.5.1, the setting is observed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7ca79-107">建议</span><span class="sxs-lookup"><span data-stu-id="7ca79-107">Suggestion</span></span>

<span data-ttu-id="7ca79-108">如果 Web 服务器上的可用内存少于由配置设置定义的百分比，将引发异常。</span><span class="sxs-lookup"><span data-stu-id="7ca79-108">An exception occurs if the free memory available on the web server is less than the percentage defined by the configuration setting.</span></span> <span data-ttu-id="7ca79-109">某些成功启动并且在受约束的内存环境中运行的 WCF 服务现在可能失败。</span><span class="sxs-lookup"><span data-stu-id="7ca79-109">Some WCF services that successfully started and ran in a constrained memory environment may now fail.</span></span>

| <span data-ttu-id="7ca79-110">“属性”</span><span class="sxs-lookup"><span data-stu-id="7ca79-110">Name</span></span>    | <span data-ttu-id="7ca79-111">“值”</span><span class="sxs-lookup"><span data-stu-id="7ca79-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7ca79-112">范围</span><span class="sxs-lookup"><span data-stu-id="7ca79-112">Scope</span></span>   |<span data-ttu-id="7ca79-113">次要</span><span class="sxs-lookup"><span data-stu-id="7ca79-113">Minor</span></span>|
|<span data-ttu-id="7ca79-114">Version</span><span class="sxs-lookup"><span data-stu-id="7ca79-114">Version</span></span>|<span data-ttu-id="7ca79-115">4.5.1</span><span class="sxs-lookup"><span data-stu-id="7ca79-115">4.5.1</span></span>|
|<span data-ttu-id="7ca79-116">类型</span><span class="sxs-lookup"><span data-stu-id="7ca79-116">Type</span></span>|<span data-ttu-id="7ca79-117">运行时</span><span class="sxs-lookup"><span data-stu-id="7ca79-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="7ca79-118">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="7ca79-118">Affected APIs</span></span>

<span data-ttu-id="7ca79-119">无法通过 API 分析检测到。</span><span class="sxs-lookup"><span data-stu-id="7ca79-119">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
