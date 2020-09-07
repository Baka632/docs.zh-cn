---
ms.openlocfilehash: 76425ca03c98cd6a23b8366257f9e0d53b486edb
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497009"
---
### <a name="sharing-session-state-with-aspnet-stateserver-requires-all-servers-in-the-web-farm-to-use-the-same-net-framework-version"></a><span data-ttu-id="be5ca-101">与 Asp.Net StateServer 共享会话状态需要 Web 场中的所有服务器使用相同版本的 .NET Framework</span><span class="sxs-lookup"><span data-stu-id="be5ca-101">Sharing session state with Asp.Net StateServer requires all servers in the web farm to use the same .NET Framework version</span></span>

#### <a name="details"></a><span data-ttu-id="be5ca-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="be5ca-102">Details</span></span>

<span data-ttu-id="be5ca-103">启用 <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=fullName> 会话状态时，给定 Web 场中的所有服务器必须使用相同版本的 .NET Framework 以便正确共享状态。</span><span class="sxs-lookup"><span data-stu-id="be5ca-103">When enabling <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=fullName> session state, all of the servers in the given web farm must use the same version of the .NET Framework in order for state to be properly shared.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="be5ca-104">建议</span><span class="sxs-lookup"><span data-stu-id="be5ca-104">Suggestion</span></span>

<span data-ttu-id="be5ca-105">请务必在同时共享状态的 Web 服务器上升级 .NET Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="be5ca-105">Be sure to upgrade .NET Framework versions on web servers that share state at the same time.</span></span>

| <span data-ttu-id="be5ca-106">“属性”</span><span class="sxs-lookup"><span data-stu-id="be5ca-106">Name</span></span>    | <span data-ttu-id="be5ca-107">“值”</span><span class="sxs-lookup"><span data-stu-id="be5ca-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="be5ca-108">范围</span><span class="sxs-lookup"><span data-stu-id="be5ca-108">Scope</span></span>   |<span data-ttu-id="be5ca-109">边缘</span><span class="sxs-lookup"><span data-stu-id="be5ca-109">Edge</span></span>|
|<span data-ttu-id="be5ca-110">Version</span><span class="sxs-lookup"><span data-stu-id="be5ca-110">Version</span></span>|<span data-ttu-id="be5ca-111">4.5</span><span class="sxs-lookup"><span data-stu-id="be5ca-111">4.5</span></span>|
|<span data-ttu-id="be5ca-112">类型</span><span class="sxs-lookup"><span data-stu-id="be5ca-112">Type</span></span>|<span data-ttu-id="be5ca-113">运行时</span><span class="sxs-lookup"><span data-stu-id="be5ca-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="be5ca-114">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="be5ca-114">Affected APIs</span></span>

- <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=nameWithType>

<!--

#### Affected APIs

- `F:System.Web.SessionState.SessionStateMode.StateServer`

-->
