---
ms.openlocfilehash: 719f336e1b38597674d6ee8f0c5429dd965054b1
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031974"
---
### <a name="floating-point-formatting-and-parsing-behavior-changed"></a><span data-ttu-id="5058f-101">浮点格式设置和分析行为已更改</span><span class="sxs-lookup"><span data-stu-id="5058f-101">Floating-point formatting and parsing behavior changed</span></span>

<span data-ttu-id="5058f-102">浮点分析和格式设置行为（由 <xref:System.Double> 和 <xref:System.Single> 类型实现）现符合 IEEE 标准。</span><span class="sxs-lookup"><span data-stu-id="5058f-102">Floating point parsing and formatting behavior (by the <xref:System.Double> and <xref:System.Single> types) are now IEEE-compliant.</span></span>

#### <a name="change-description"></a><span data-ttu-id="5058f-103">更改描述</span><span class="sxs-lookup"><span data-stu-id="5058f-103">Change description</span></span>

<span data-ttu-id="5058f-104">在 .NET Core 2.2 及更低版本中，通过 <xref:System.Double.ToString%2A?displayProperty=nameWithType> 和 <xref:System.Single.ToString%2A?displayProperty=nameWithType> 进行格式设置的行为，以及使用 <xref:System.Double.Parse%2A?displayProperty=nameWithType>、<xref:System.Double.TryParse%2A?displayProperty=nameWithType>、<xref:System.Single.Parse%2A?displayProperty=nameWithType> 和 <xref:System.Single.TryParse%2A?displayProperty=nameWithType> 进行分析的行为不符合 IEEE 标准。</span><span class="sxs-lookup"><span data-stu-id="5058f-104">In .NET Core 2.2 and earlier versions, formatting with <xref:System.Double.ToString%2A?displayProperty=nameWithType> and <xref:System.Single.ToString%2A?displayProperty=nameWithType>, and parsing with <xref:System.Double.Parse%2A?displayProperty=nameWithType>, <xref:System.Double.TryParse%2A?displayProperty=nameWithType>, <xref:System.Single.Parse%2A?displayProperty=nameWithType>, and <xref:System.Single.TryParse%2A?displayProperty=nameWithType> are not IEEE-compliant.</span></span> <span data-ttu-id="5058f-105">因此，没法保证值在没有任何受支持的标准或自定义格式字符串的情况下双向传输。</span><span class="sxs-lookup"><span data-stu-id="5058f-105">As a result, it is impossible to guarantee that a value will roundtrip with any supported standard or custom format string.</span></span> <span data-ttu-id="5058f-106">对于某些输入，尝试分析已设置格式的值可能会失败；而对于其他输入，分析后的值与原始值不相等。</span><span class="sxs-lookup"><span data-stu-id="5058f-106">For some inputs, the attempt to parse a formatted value can fail, and for others, the parsed value doesn't equal the original value.</span></span>

<span data-ttu-id="5058f-107">自 .NET Core 3.0 起，分析和格式设置操作均符合 IEEE 754 标准。</span><span class="sxs-lookup"><span data-stu-id="5058f-107">Starting with .NET Core 3.0, parsing and formatting operations are IEEE 754-compliant.</span></span> <span data-ttu-id="5058f-108">这可确保 .NET 中浮点类型的行为与符合 IEEE 标准的语言（例如 C#）一致。</span><span class="sxs-lookup"><span data-stu-id="5058f-108">This ensures that the behavior of floating-point types in .NET matches that of IEEE-compliant languages such as C#.</span></span> <span data-ttu-id="5058f-109">有关浮点改进的详细信息，请参阅 [Floating-point parsing and formatting improvements in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/)（.NET Core 3.0 中浮点分析和格式设置改进）博客文章。</span><span class="sxs-lookup"><span data-stu-id="5058f-109">For more information, see the [Floating-point parsing and formatting improvements in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) blog post.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="5058f-110">引入的版本</span><span class="sxs-lookup"><span data-stu-id="5058f-110">Version introduced</span></span>

<span data-ttu-id="5058f-111">3.0</span><span class="sxs-lookup"><span data-stu-id="5058f-111">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="5058f-112">建议操作</span><span class="sxs-lookup"><span data-stu-id="5058f-112">Recommended action</span></span>

<span data-ttu-id="5058f-113">在 [Floating-point parsing and formatting improvements in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/)（.NET Core 3.0 中浮点分析和格式设置改进）博客文章的“对现有代码的潜在影响”部分中，如果你在与 .NET Core 2.2 应用程序比较时观察到行为有变，则通常建议更改代码，这涉及到使用不同的标准或自定义格式字符串来强制执行所需的行为。</span><span class="sxs-lookup"><span data-stu-id="5058f-113">The "Potential impact to existing code" section of the [Floating-point parsing and formatting improvements in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) blog post suggests changes to your code if you observe a change of behavior when compared to .NET Core 2.2 applications Generally, this involves using a different standard or custom format string to enforce the desired behavior.</span></span> <span data-ttu-id="5058f-114">如果一些结果之前都不正确，则它们可能没法修复。</span><span class="sxs-lookup"><span data-stu-id="5058f-114">Some results may not have a workaround if they were previously incorrect.</span></span>

#### <a name="category"></a><span data-ttu-id="5058f-115">类别</span><span class="sxs-lookup"><span data-stu-id="5058f-115">Category</span></span>

<span data-ttu-id="5058f-116">Core .NET 库</span><span class="sxs-lookup"><span data-stu-id="5058f-116">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="5058f-117">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="5058f-117">Affected APIs</span></span>

- <xref:System.Double.ToString%2A?displayProperty=nameWithType>
- <xref:System.Single.ToString%2A?displayProperty=nameWithType>
- <xref:System.Double.Parse%2A?displayProperty=nameWithType>
- <xref:System.Double.TryParse%2A?displayProperty=nameWithType>
- <xref:System.Single.Parse%2A?displayProperty=nameWithType>
- <xref:System.Single.TryParse%2A?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `Overload:System.Double.ToString`
- `Overload:System.Single.ToString`
- `Overload:System.Double.Parse`
- `Overload:System.Double.TryParse`
- `Overload:System.Single.Parse`
- `Overload:System.Single.TryParse`

-->
