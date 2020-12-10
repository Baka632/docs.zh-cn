---
ms.openlocfilehash: 639cd13978cc33bd7c4524a17e92d566404bbaea
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2020
ms.locfileid: "96478083"
---
### <a name="contractinvariant-or-contractrequirestexception-do-not-consider-stringisnullorempty-to-be-pure"></a><span data-ttu-id="f2668-101">Contract.Invariant 或 Contract.Requires\<TException> 不认为 String.IsNullOrEmpty 为 pure</span><span class="sxs-lookup"><span data-stu-id="f2668-101">Contract.Invariant or Contract.Requires\<TException> do not consider String.IsNullOrEmpty to be pure</span></span>

#### <a name="details"></a><span data-ttu-id="f2668-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="f2668-102">Details</span></span>

<span data-ttu-id="f2668-103">对于面向 .NET Framework 4.6.1 的应用，如果 <xref:System.Diagnostics.Contracts.Contract.Invariant%2A?displayProperty=nameWithType> 的不变协定或 <xref:System.Diagnostics.Contracts.Contract.Requires%2A?displayProperty=nameWithType)> 的前提条件协定调用 <xref:System.String.IsNullOrEmpty%2A?displayProperty=nameWithType> 方法，则重写器会发出编译器警告 CC1036：&quot;在方法中没有 [Pure] 的情况下检测到对方法“System.String.IsNullOrWhiteSpace(System.String)”的调用。&quot;这是编译器警告，不是编译器错误。</span><span class="sxs-lookup"><span data-stu-id="f2668-103">For apps that target the .NET Framework 4.6.1, if the invariant contract for <xref:System.Diagnostics.Contracts.Contract.Invariant%2A?displayProperty=nameWithType> or the precondition contract for <xref:System.Diagnostics.Contracts.Contract.Requires%2A?displayProperty=nameWithType)> calls the <xref:System.String.IsNullOrEmpty%2A?displayProperty=nameWithType> method, the rewriter emits compiler warning CC1036: &quot;Detected call to method 'System.String.IsNullOrWhiteSpace(System.String)' without [Pure] in method.&quot; This is a compiler warning rather than a compiler error.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f2668-104">建议</span><span class="sxs-lookup"><span data-stu-id="f2668-104">Suggestion</span></span>

<span data-ttu-id="f2668-105">此行为在 [GitHub 问题 #339](https://github.com/Microsoft/CodeContracts/issues/339) 中已得到解决。</span><span class="sxs-lookup"><span data-stu-id="f2668-105">This behavior was addressed in [GitHub Issue #339](https://github.com/Microsoft/CodeContracts/issues/339).</span></span> <span data-ttu-id="f2668-106">要去除此警告，可以从 [GitHub](https://github.com/Microsoft/CodeContracts/blob/master/README.md) 下载并编译代码协定工具的已更新版本的源代码。</span><span class="sxs-lookup"><span data-stu-id="f2668-106">To eliminate this warning, you can download and compile an updated version of the source code for the Code Contracts tool from [GitHub](https://github.com/Microsoft/CodeContracts/blob/master/README.md).</span></span> <span data-ttu-id="f2668-107">可在页面底部找到下载信息。</span><span class="sxs-lookup"><span data-stu-id="f2668-107">Download information is found at the bottom of the page.</span></span>

| <span data-ttu-id="f2668-108">“属性”</span><span class="sxs-lookup"><span data-stu-id="f2668-108">Name</span></span>    | <span data-ttu-id="f2668-109">“值”</span><span class="sxs-lookup"><span data-stu-id="f2668-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f2668-110">范围</span><span class="sxs-lookup"><span data-stu-id="f2668-110">Scope</span></span>   |<span data-ttu-id="f2668-111">次要</span><span class="sxs-lookup"><span data-stu-id="f2668-111">Minor</span></span>|
|<span data-ttu-id="f2668-112">Version</span><span class="sxs-lookup"><span data-stu-id="f2668-112">Version</span></span>|<span data-ttu-id="f2668-113">4.6.1</span><span class="sxs-lookup"><span data-stu-id="f2668-113">4.6.1</span></span>|
|<span data-ttu-id="f2668-114">类型</span><span class="sxs-lookup"><span data-stu-id="f2668-114">Type</span></span>|<span data-ttu-id="f2668-115">运行时</span><span class="sxs-lookup"><span data-stu-id="f2668-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="f2668-116">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="f2668-116">Affected APIs</span></span>

- <xref:System.Diagnostics.Contracts.Contract.Invariant(System.Boolean)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Contracts.Contract.Requires(System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Diagnostics.Contracts.Contract.Invariant(System.Boolean)`
- `M:System.Diagnostics.Contracts.Contract.Requires(System.Boolean)`

-->
