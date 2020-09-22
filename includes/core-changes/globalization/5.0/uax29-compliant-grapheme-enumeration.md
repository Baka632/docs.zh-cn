---
ms.openlocfilehash: 70b71fc55f76514dd17e5b9ba0e76151a966eebb
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539439"
---
### <a name="stringinfo-and-textelementenumerator-are-now-uax29-compliant"></a><span data-ttu-id="8bae3-101">StringInfo 和 TextElementEnumerator 现在与 UAX29 兼容</span><span class="sxs-lookup"><span data-stu-id="8bae3-101">StringInfo and TextElementEnumerator are now UAX29-compliant</span></span>

<span data-ttu-id="8bae3-102">在此更改之前，<xref:System.Globalization.StringInfo?displayProperty=fullName> 和 <xref:System.Globalization.TextElementEnumerator?displayProperty=fullName> 无法正确处理所有字形群集。</span><span class="sxs-lookup"><span data-stu-id="8bae3-102">Prior to this change, <xref:System.Globalization.StringInfo?displayProperty=fullName> and <xref:System.Globalization.TextElementEnumerator?displayProperty=fullName> didn't properly handle all grapheme clusters.</span></span> <span data-ttu-id="8bae3-103">某些字形已拆分为其构成部分，而不是合并在一起。</span><span class="sxs-lookup"><span data-stu-id="8bae3-103">Some graphemes were split into their constituent components instead of being kept together.</span></span> <span data-ttu-id="8bae3-104">现在，<xref:System.Globalization.StringInfo> 和 <xref:System.Globalization.TextElementEnumerator> 将根据 Unicode 标准的最新版本处理字形群集。</span><span class="sxs-lookup"><span data-stu-id="8bae3-104">Now, <xref:System.Globalization.StringInfo> and <xref:System.Globalization.TextElementEnumerator> process grapheme clusters according to the latest version of the Unicode Standard.</span></span>

<span data-ttu-id="8bae3-105">此外，<xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName> 方法（用于反转 Visual Basic 中的字符串）现在也遵循 Unicode 标准来处理字形群集。</span><span class="sxs-lookup"><span data-stu-id="8bae3-105">In addition, the <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName> method, which reverses the characters in a string in Visual Basic, now also follows the Unicode standard for grapheme clusters.</span></span>

#### <a name="change-description"></a><span data-ttu-id="8bae3-106">更改描述</span><span class="sxs-lookup"><span data-stu-id="8bae3-106">Change description</span></span>

<span data-ttu-id="8bae3-107">[字形](https://www.unicode.org/glossary/#grapheme)或[扩展的字形群集](https://www.unicode.org/glossary/#extended_grapheme_cluster)是一个可以由多个 Unicode 码位组成的用户感知字符。</span><span class="sxs-lookup"><span data-stu-id="8bae3-107">A [grapheme](https://www.unicode.org/glossary/#grapheme) or [extended grapheme cluster](https://www.unicode.org/glossary/#extended_grapheme_cluster) is a single user-perceived character that may be made up of multiple Unicode code points.</span></span> <span data-ttu-id="8bae3-108">例如，包含泰文字符“kam”的字符串（:::no-loc text="กำ":::）由以下两个字符组成：</span><span class="sxs-lookup"><span data-stu-id="8bae3-108">For example, the string containing the Thai character "kam" (:::no-loc text="กำ":::) consists of the following two characters:</span></span>

- <span data-ttu-id="8bae3-109">:::no-loc text="ก"::: (= '\u0e01') THAI CHARACTER KO KAI</span><span class="sxs-lookup"><span data-stu-id="8bae3-109">:::no-loc text="ก"::: (= '\u0e01') THAI CHARACTER KO KAI</span></span>
- <span data-ttu-id="8bae3-110">:::no-loc text=" ำ"::: (= '\u0e33') THAI CHARACTER SARA AM</span><span class="sxs-lookup"><span data-stu-id="8bae3-110">:::no-loc text=" ำ"::: (= '\u0e33') THAI CHARACTER SARA AM</span></span>

<span data-ttu-id="8bae3-111">当向用户显示时，操作系统会将这两个字符组合在一起以形成单个显示字符（或字形）“kam”或 :::no-loc text="กำ":::。</span><span class="sxs-lookup"><span data-stu-id="8bae3-111">When displayed to the user, the operating system combines the two characters to form the single display character (or grapheme) "kam" or :::no-loc text="กำ":::.</span></span> <span data-ttu-id="8bae3-112">表情符号也可以包含以这种类似方式显示的多个组合字符。</span><span class="sxs-lookup"><span data-stu-id="8bae3-112">Emoji can also consist of multiple characters that are combined for display in a similar way.</span></span>

> [!TIP]
> <span data-ttu-id="8bae3-113">引用字形时，.NET 文档有时会使用术语“文本元素”。</span><span class="sxs-lookup"><span data-stu-id="8bae3-113">The .NET documentation sometimes uses the term "text element" when referring to a grapheme.</span></span>

<span data-ttu-id="8bae3-114"><xref:System.Globalization.StringInfo> 和 <xref:System.Globalization.TextElementEnumerator> 类检查字符串并返回有关它们包含的字形信息。</span><span class="sxs-lookup"><span data-stu-id="8bae3-114">The <xref:System.Globalization.StringInfo> and <xref:System.Globalization.TextElementEnumerator> classes inspect strings and return information about the graphemes they contain.</span></span> <span data-ttu-id="8bae3-115">在 .NET Framework（所有版本）和 .NET Core 3.x 及更早版本中，这两个类将使用自定义逻辑，这种逻辑可处理一些合并类但并不完全符合 [Unicode 标准](https://www.unicode.org/reports/tr29/tr29-35.html#Grapheme_Cluster_Boundaries)。</span><span class="sxs-lookup"><span data-stu-id="8bae3-115">In .NET Framework (all versions) and .NET Core 3.x and earlier, these two classes use custom logic that handles some combining classes but doesn't fully comply with the [Unicode Standard](https://www.unicode.org/reports/tr29/tr29-35.html#Grapheme_Cluster_Boundaries).</span></span> <span data-ttu-id="8bae3-116">例如，<xref:System.Globalization.StringInfo> 和 <xref:System.Globalization.TextElementEnumerator> 类会将单个“kam”错误地拆分回其构成部分，而不是将它们合并在一起。</span><span class="sxs-lookup"><span data-stu-id="8bae3-116">For example, the <xref:System.Globalization.StringInfo> and <xref:System.Globalization.TextElementEnumerator> classes incorrectly split the single Thai character "kam" back into its constituent components instead of keeping them together.</span></span> <span data-ttu-id="8bae3-117">这些类还会将表情符号“🤷🏽♀️”错误地拆分为四个群集（人耸肩、肤色调整、性别调整和不可见组合部分），而不是将它们合并为单个字形群集。</span><span class="sxs-lookup"><span data-stu-id="8bae3-117">These classes also incorrectly split the emoji character "🤷🏽‍♀️" into four clusters (person shrugging, skin tone modifier, gender modifier, and an invisible combiner) instead of keeping them together as a single grapheme cluster.</span></span>

<span data-ttu-id="8bae3-118">从 .NET 5 开始，<xref:System.Globalization.StringInfo> 和 <xref:System.Globalization.TextElementEnumerator> 类可实现 Unicode 标准，如 [Unicode 标准附录 \#29（修订号 35）第 3 章节所述](https://www.unicode.org/reports/tr29/tr29-35.html)。</span><span class="sxs-lookup"><span data-stu-id="8bae3-118">Starting with .NET 5, the <xref:System.Globalization.StringInfo> and <xref:System.Globalization.TextElementEnumerator> classes implement the Unicode standard as defined by [Unicode Standard Annex \#29, rev. 35, sec. 3](https://www.unicode.org/reports/tr29/tr29-35.html).</span></span> <span data-ttu-id="8bae3-119">特别是，它们现在将对所有包含类返回[扩展的字形群集](https://www.unicode.org/glossary/#extended_grapheme_cluster)。</span><span class="sxs-lookup"><span data-stu-id="8bae3-119">In particular, they now return [extended grapheme clusters](https://www.unicode.org/glossary/#extended_grapheme_cluster) for all combining classes.</span></span>

<span data-ttu-id="8bae3-120">考虑下列 C# 代码：</span><span class="sxs-lookup"><span data-stu-id="8bae3-120">Consider the following C# code:</span></span>

```csharp
using System.Globalization;

static void Main(string[] args)
{
    PrintGraphemes("กำ");
    PrintGraphemes("🤷🏽‍♀️");
}

static void PrintGraphemes(string str)
{
    Console.WriteLine($"Printing graphemes of \"{str}\"...");
    int i = 0;

    TextElementEnumerator enumerator = StringInfo.GetTextElementEnumerator(str);
    while (enumerator.MoveNext())
    {
        Console.WriteLine($"Grapheme {++i}: \"{enumerator.Current}\"");
    }

    Console.WriteLine($"({i} grapheme(s) total.)");
    Console.WriteLine();
}
```

<span data-ttu-id="8bae3-121">在 .NET Framework 和 .NET Core 3.x 及更早版本中，字形是拆分的，控制台输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="8bae3-121">In .NET Framework and .NET Core 3.x and earlier versions, the graphemes are split up, and the console output is as follows:</span></span>

```txt
Printing graphemes of "กำ"...
Grapheme 1: "ก"
Grapheme 2: "ำ"
(2 grapheme(s) total.)

Printing graphemes of "🤷🏽‍♀️"...
Grapheme 1: "🤷"
Grapheme 2: "🏽"
Grapheme 3: "‍"
Grapheme 4: "♀️"
(4 grapheme(s) total.)
```

<span data-ttu-id="8bae3-122">在 .NET 5 及更高版本中，字形是合并在一起的，控制台输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="8bae3-122">In .NET 5 and later versions, the graphemes are kept together, and the console output is as follows:</span></span>

```txt
Printing graphemes of "กำ"...
Grapheme 1: "กำ"
(1 grapheme(s) total.)

Printing graphemes of "🤷🏽‍♀️"...
Grapheme 1: "🤷🏽‍♀️"
(1 grapheme(s) total.)
```

<span data-ttu-id="8bae3-123">此外，从 .NET 5 开始，<xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName> 方法（用于反转 Visual Basic 中的字符串）现在也遵循 Unicode 标准来处理字形群集。</span><span class="sxs-lookup"><span data-stu-id="8bae3-123">In addition, starting in .NET 5, the <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName> method, which reverses the characters in a string in Visual Basic, now also follows the Unicode standard for grapheme clusters.</span></span>

<span data-ttu-id="8bae3-124">这些更改是 .NET 中更广泛的一组 Unicode 和 UTF-8 改进的一部分，包括扩展的字形群集枚举 API，用于补充在 .NET Core 3.0 中随 <xref:System.Text.Rune?displayProperty=fullName> 类型引入的 Unicode 标量值枚举 API。</span><span class="sxs-lookup"><span data-stu-id="8bae3-124">These changes are part of a wider set of Unicode and UTF-8 improvements in .NET, including an extended grapheme cluster enumeration API to complement the Unicode scalar-value enumeration APIs that were introduced with the <xref:System.Text.Rune?displayProperty=fullName> type in .NET Core 3.0.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="8bae3-125">引入的版本</span><span class="sxs-lookup"><span data-stu-id="8bae3-125">Version introduced</span></span>

<span data-ttu-id="8bae3-126">.NET 5.0 预览版 1</span><span class="sxs-lookup"><span data-stu-id="8bae3-126">.NET 5.0 Preview 1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="8bae3-127">建议操作</span><span class="sxs-lookup"><span data-stu-id="8bae3-127">Recommended action</span></span>

<span data-ttu-id="8bae3-128">你不必执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="8bae3-128">You don't need to take any action.</span></span> <span data-ttu-id="8bae3-129">你的应用将在各种全球化相关场景中以更符合标准的方式自动运行。</span><span class="sxs-lookup"><span data-stu-id="8bae3-129">Your apps will automatically behave in a more standards-compliant manner in a variety of globalization-related scenarios.</span></span>

#### <a name="category"></a><span data-ttu-id="8bae3-130">类别</span><span class="sxs-lookup"><span data-stu-id="8bae3-130">Category</span></span>

<span data-ttu-id="8bae3-131">全球化</span><span class="sxs-lookup"><span data-stu-id="8bae3-131">Globalization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8bae3-132">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="8bae3-132">Affected APIs</span></span>

- <xref:System.Globalization.StringInfo?displayProperty=fullName>
- <xref:System.Globalization.TextElementEnumerator?displayProperty=fullName>
- <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Globalization.StringInfo`
- `T:System.Globalization.TextElementEnumerator`
- `Overload:Microsoft.VisualBasic.Strings.StrReverse`

-->
