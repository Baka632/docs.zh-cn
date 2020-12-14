---
title: 在 .NET 5 及更高版本中比较字符串时的行为更改
description: 了解在 Windows 上的 .NET 5 及更高版本中比较字符串时的行为更改。
ms.date: 12/07/2020
ms.openlocfilehash: a53c36b31785fb43c0aa5f5040042abb6d40031a
ms.sourcegitcommit: 45c7148f2483db2501c1aa696ab6ed2ed8cb71b2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/08/2020
ms.locfileid: "96851746"
---
# <a name="behavior-changes-when-comparing-strings-on-net-5"></a><span data-ttu-id="3852c-103">在 .NET 5 及更高版本中比较字符串时的行为更改</span><span class="sxs-lookup"><span data-stu-id="3852c-103">Behavior changes when comparing strings on .NET 5+</span></span>

<span data-ttu-id="3852c-104">.NET 5.0 引入了一项运行时行为更改，其中，全球化 API 目前在所有支持的平台上[默认使用 ICU](../../core/compatibility/globalization/5.0/icu-globalization-api.md)。</span><span class="sxs-lookup"><span data-stu-id="3852c-104">.NET 5.0 introduces a runtime behavioral change where globalization APIs [now use ICU by default](../../core/compatibility/globalization/5.0/icu-globalization-api.md) across all supported platforms.</span></span> <span data-ttu-id="3852c-105">这明显有别于较早的 .NET Core 和 .NET Framework 版本，在 Windows 上运行这些版本时，它们利用操作系统的区域语言支持 (NLS) 功能。</span><span class="sxs-lookup"><span data-stu-id="3852c-105">This is a departure from earlier versions of .NET Core and from .NET Framework, which utilize the operating system's national language support (NLS) functionality when running on Windows.</span></span> <span data-ttu-id="3852c-106">有关这些更改的详细信息，包括还原该行为更改的兼容性开关，请参阅 [.NET 全球化和 ICU](../globalization-localization/globalization-icu.md)。</span><span class="sxs-lookup"><span data-stu-id="3852c-106">For more information on these changes, including compatibility switches that can revert the behavior change, see [.NET globalization and ICU](../globalization-localization/globalization-icu.md).</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="3852c-107">更改原因</span><span class="sxs-lookup"><span data-stu-id="3852c-107">Reason for change</span></span>

<span data-ttu-id="3852c-108">引入此更改是为了统一所有支持的操作系统上的 .NET 的全球化行为。</span><span class="sxs-lookup"><span data-stu-id="3852c-108">This change was introduced to unify .NET's globalization behavior across all supported operating systems.</span></span> <span data-ttu-id="3852c-109">它还能让应用程序捆绑自己的全球化库，而不是依赖于操作系统的内置库。</span><span class="sxs-lookup"><span data-stu-id="3852c-109">It also provides the ability for applications to bundle their own globalization libraries rather than depend on the OS's built-in libraries.</span></span> <span data-ttu-id="3852c-110">有关详细信息，请参阅[中断性变更](../../core/compatibility/globalization/5.0/icu-globalization-api.md)。</span><span class="sxs-lookup"><span data-stu-id="3852c-110">For more information, see [the breaking change notification](../../core/compatibility/globalization/5.0/icu-globalization-api.md).</span></span>

## <a name="behavioral-differences"></a><span data-ttu-id="3852c-111">行为差异</span><span class="sxs-lookup"><span data-stu-id="3852c-111">Behavioral differences</span></span>

<span data-ttu-id="3852c-112">如果在使用 `string.IndexOf(string)` 这样的函数时不调用使用 <xref:System.StringComparison> 参数的重载，则可能在计划执行序号搜索时无意中依赖于特定于区域性的行为。</span><span class="sxs-lookup"><span data-stu-id="3852c-112">If you use functions like `string.IndexOf(string)` without calling the overload that takes a <xref:System.StringComparison> argument, you might intend to perform an *ordinal* search, but instead you inadvertently take a dependency on culture-specific behavior.</span></span> <span data-ttu-id="3852c-113">由于 NLS 和 ICU 在其语言比较器中实现的逻辑有所不同，因此 `string.IndexOf(string)` 等方法的结果可能会返回意外的值。</span><span class="sxs-lookup"><span data-stu-id="3852c-113">Since NLS and ICU implement different logic in their linguistic comparers, the results of methods like `string.IndexOf(string)` can return unexpected values.</span></span>

<span data-ttu-id="3852c-114">即使在全球化功能并非总是处于活动状态的地方，也会出现这类问题。</span><span class="sxs-lookup"><span data-stu-id="3852c-114">This can manifest itself even in places where you aren't always expecting globalization facilities to be active.</span></span> <span data-ttu-id="3852c-115">例如，根据当前运行时，下面的代码可能会生成不同的答案。</span><span class="sxs-lookup"><span data-stu-id="3852c-115">For example, the following code can produce a different answer depending on the current runtime.</span></span>

```cs
string s = "Hello\r\nworld!";
int idx = s.IndexOf("\n");
Console.WriteLine(idx);

// The snippet prints:
//
// '6' when running on .NET Framework (Windows)
// '6' when running on .NET Core 2.x - 3.x (Windows)
// '-1' when running on .NET 5 (Windows)
// '-1' when running on .NET Core 2.x - 3.x or .NET 5 (non-Windows)
// '6' when running on .NET Core 2.x or .NET 5 (in invariant mode)
```

## <a name="guard-against-unexpected-behavior"></a><span data-ttu-id="3852c-116">防范意外行为</span><span class="sxs-lookup"><span data-stu-id="3852c-116">Guard against unexpected behavior</span></span>

<span data-ttu-id="3852c-117">本节提供了处理 .NET 5.0 中的意外行为更改的两种方法。</span><span class="sxs-lookup"><span data-stu-id="3852c-117">This section provides two options for dealing with unexpected behavior changes in .NET 5.0.</span></span>

### <a name="enable-code-analyzers"></a><span data-ttu-id="3852c-118">启用代码分析器</span><span class="sxs-lookup"><span data-stu-id="3852c-118">Enable code analyzers</span></span>

<span data-ttu-id="3852c-119">[代码分析器](../../fundamentals/code-analysis/overview.md)可以检测可能存在错误的调用站点。</span><span class="sxs-lookup"><span data-stu-id="3852c-119">[Code analyzers](../../fundamentals/code-analysis/overview.md) can detect possibly buggy call sites.</span></span> <span data-ttu-id="3852c-120">为了帮助防范任何意外行为，建议在项目中启用 .NET Compiler Platform (Roslyn) 分析器。</span><span class="sxs-lookup"><span data-stu-id="3852c-120">To help guard against any surprising behaviors, we recommend enabling .NET compiler platform (Roslyn) analyzers in your project.</span></span> <span data-ttu-id="3852c-121">该分析器有助于标记在计划使用序号比较器时可能无意中使用语言比较器的代码。</span><span class="sxs-lookup"><span data-stu-id="3852c-121">The analyzers help flag code that might inadvertently be using a linguistic comparer when an ordinal comparer was likely intended.</span></span> <span data-ttu-id="3852c-122">以下规则应有助于标记这些问题：</span><span class="sxs-lookup"><span data-stu-id="3852c-122">The following rules should help flag these issues:</span></span>

- [<span data-ttu-id="3852c-123">CA1307:为了清晰起见，请指定 StringComparison</span><span class="sxs-lookup"><span data-stu-id="3852c-123">CA1307: Specify StringComparison for clarity</span></span>](../../fundamentals/code-analysis/quality-rules/ca1307.md)
- [<span data-ttu-id="3852c-124">CA1309:使用按顺序的 StringComparison</span><span class="sxs-lookup"><span data-stu-id="3852c-124">CA1309: Use ordinal StringComparison</span></span>](../../fundamentals/code-analysis/quality-rules/ca1309.md)
- [<span data-ttu-id="3852c-125">CA1310：为了确保正确，请指定 StringComparison</span><span class="sxs-lookup"><span data-stu-id="3852c-125">CA1310: Specify StringComparison for correctness</span></span>](../../fundamentals/code-analysis/quality-rules/ca1310.md)

<span data-ttu-id="3852c-126">默认不启用这些特定规则。</span><span class="sxs-lookup"><span data-stu-id="3852c-126">These specific rules aren't enabled by default.</span></span> <span data-ttu-id="3852c-127">若要启用它们并将任何冲突显示为生成错误，请在项目文件中设置以下属性：</span><span class="sxs-lookup"><span data-stu-id="3852c-127">To enable them and show any violations as build errors, set the following properties in your project file:</span></span>

```xml
<PropertyGroup>
  <AnalysisMode>AllEnabledByDefault</AnalysisMode>
  <WarningsAsErrors>$(WarningsAsErrors);CA1307;CA1309;CA1310</WarningsAsErrors>
</PropertyGroup>
```

<span data-ttu-id="3852c-128">以下代码片段显示生成相关代码分析器警告或错误的代码示例。</span><span class="sxs-lookup"><span data-stu-id="3852c-128">The following snippet shows examples of code that produces the relevant code analyzer warnings or errors.</span></span>

```cs
//
// Potentially incorrect code - answer might vary based on locale.
//
string s = GetString();
// Produces analyzer warning CA1310 for string; CA1307 matches on char ','
int idx = s.IndexOf(",");
Console.WriteLine(idx);

//
// Corrected code - matches the literal substring ",".
//
string s = GetString();
int idx = s.IndexOf(",", StringComparison.Ordinal);
Console.WriteLine(idx);

//
// Corrected code (alternative) - searches for the literal ',' character.
//
string s = GetString();
int idx = s.IndexOf(',');
Console.WriteLine(idx);
```

<span data-ttu-id="3852c-129">同样，在实例化已排序的字符串集合或对现有基于字符串的集合进行排序时，请指定显式比较器。</span><span class="sxs-lookup"><span data-stu-id="3852c-129">Similarly, when instantiating a sorted collection of strings or sorting an existing string-based collection, specify an explicit comparer.</span></span>

```cs
//
// Potentially incorrect code - behavior might vary based on locale.
//
SortedSet<string> mySet = new SortedSet<string>();
List<string> list = GetListOfStrings();
list.Sort();

//
// Corrected code - uses ordinal sorting; doesn't vary by locale.
//
SortedSet<string> mySet = new SortedSet<string>(StringComparer.Ordinal);
List<string> list = GetListOfStrings();
list.Sort(StringComparer.Ordinal);
```

### <a name="revert-back-to-nls-behaviors"></a><span data-ttu-id="3852c-130">还原到 NLS 行为</span><span class="sxs-lookup"><span data-stu-id="3852c-130">Revert back to NLS behaviors</span></span>

<span data-ttu-id="3852c-131">在 Windows 上运行 .NET 5 应用程序时，若要将其还原到早前的 NLS 行为，请按照 [.NET 全球化和 ICU](../globalization-localization/globalization-icu.md) 中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="3852c-131">To revert .NET 5 applications back to older NLS behaviors when running on Windows, follow the steps in [.NET Globalization and ICU](../globalization-localization/globalization-icu.md).</span></span> <span data-ttu-id="3852c-132">必须在应用程序级别设置此应用程序范围的兼容性开关。</span><span class="sxs-lookup"><span data-stu-id="3852c-132">This application-wide compatibility switch must be set at the application level.</span></span> <span data-ttu-id="3852c-133">单个库不能选择加入或选择退出此行为。</span><span class="sxs-lookup"><span data-stu-id="3852c-133">Individual libraries cannot opt-in or opt-out of this behavior.</span></span>

> [!TIP]
> <span data-ttu-id="3852c-134">强烈建议启用 [CA1307](../../fundamentals/code-analysis/quality-rules/ca1307.md)、[CA1309](../../fundamentals/code-analysis/quality-rules/ca1309.md) 和 [CA1310](../../fundamentals/code-analysis/quality-rules/ca1310.md) 代码分析规则，以帮助改进代码卫生和发现任何现有的潜在 bug。</span><span class="sxs-lookup"><span data-stu-id="3852c-134">We strongly recommend you enable the [CA1307](../../fundamentals/code-analysis/quality-rules/ca1307.md), [CA1309](../../fundamentals/code-analysis/quality-rules/ca1309.md), and [CA1310](../../fundamentals/code-analysis/quality-rules/ca1310.md) code analysis rules to help improve code hygiene and discover any existing latent bugs.</span></span> <span data-ttu-id="3852c-135">有关详细信息，请参阅[启用代码分析器](#enable-code-analyzers)。</span><span class="sxs-lookup"><span data-stu-id="3852c-135">For more information, see [Enable code analyzers](#enable-code-analyzers).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="3852c-136">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="3852c-136">Affected APIs</span></span>

<span data-ttu-id="3852c-137">大多数 .NET 应用程序不会遇到因 .NET 5.0 中的更改而导致的任何意外行为。</span><span class="sxs-lookup"><span data-stu-id="3852c-137">Most .NET applications won't encounter any unexpected behaviors due to the changes in .NET 5.0.</span></span> <span data-ttu-id="3852c-138">但是，由于受影响的 API 数量以及这些 API 对更广泛的 .NET 生态系统的基础性，你应知道 .NET 5.0 可能会引入不需要的行为或公开应用程序中已存在的潜在 bug。</span><span class="sxs-lookup"><span data-stu-id="3852c-138">However, due to the number of affected APIs and how foundational these APIs are to the wider .NET ecosystem, you should be aware of the potential for .NET 5.0 to introduce unwanted behaviors or to expose latent bugs that already exist in your application.</span></span>

<span data-ttu-id="3852c-139">受影响的 API 包括：</span><span class="sxs-lookup"><span data-stu-id="3852c-139">The affected APIs include:</span></span>

- <xref:System.String.Compare%2A?displayProperty=fullName>
- <xref:System.String.EndsWith%2A?displayProperty=fullName>
- <xref:System.String.IndexOf%2A?displayProperty=fullName>
- <xref:System.String.StartsWith%2A?displayProperty=fullName>
- <xref:System.String.ToLower%2A?displayProperty=fullName>
- <xref:System.String.ToLowerInvariant%2A?displayProperty=fullName>
- <xref:System.String.ToUpper%2A?displayProperty=fullName>
- <xref:System.String.ToUpperInvariant%2A?displayProperty=fullName>
- <span data-ttu-id="3852c-140"><xref:System.Globalization.TextInfo?displayProperty=fullName>（大多数成员）</span><span class="sxs-lookup"><span data-stu-id="3852c-140"><xref:System.Globalization.TextInfo?displayProperty=fullName> (most members)</span></span>
- <span data-ttu-id="3852c-141"><xref:System.Globalization.CompareInfo?displayProperty=fullName>（大多数成员）</span><span class="sxs-lookup"><span data-stu-id="3852c-141"><xref:System.Globalization.CompareInfo?displayProperty=fullName> (most members)</span></span>
- <span data-ttu-id="3852c-142"><xref:System.Array.Sort%2A?displayProperty=fullName>（对字符串数组进行排序时）</span><span class="sxs-lookup"><span data-stu-id="3852c-142"><xref:System.Array.Sort%2A?displayProperty=fullName> (when sorting arrays of strings)</span></span>
- <span data-ttu-id="3852c-143"><xref:System.Collections.Generic.List%601.Sort?displayProperty=fullName>（当列表元素为字符串时）</span><span class="sxs-lookup"><span data-stu-id="3852c-143"><xref:System.Collections.Generic.List%601.Sort?displayProperty=fullName> (when the list elements are strings)</span></span>
- <span data-ttu-id="3852c-144"><xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName>（当键为字符串时）</span><span class="sxs-lookup"><span data-stu-id="3852c-144"><xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName> (when the keys are strings)</span></span>
- <span data-ttu-id="3852c-145"><xref:System.Collections.Generic.SortedList%602?displayProperty=fullName>（当键为字符串时）</span><span class="sxs-lookup"><span data-stu-id="3852c-145"><xref:System.Collections.Generic.SortedList%602?displayProperty=fullName> (when the keys are strings)</span></span>
- <span data-ttu-id="3852c-146"><xref:System.Collections.Generic.SortedSet%601?displayProperty=fullName>（当集包含字符串时）</span><span class="sxs-lookup"><span data-stu-id="3852c-146"><xref:System.Collections.Generic.SortedSet%601?displayProperty=fullName> (when the set contains strings)</span></span>

> [!NOTE]
> <span data-ttu-id="3852c-147">这不是受影响的 API 的详尽列表。</span><span class="sxs-lookup"><span data-stu-id="3852c-147">This is not an exhaustive list of affected APIs.</span></span>

<span data-ttu-id="3852c-148">默认情况下，上述所有 API 都使用语言字符串搜索与比较，它们使用线程的[当前区域性](xref:System.Threading.Thread.CurrentCulture)。</span><span class="sxs-lookup"><span data-stu-id="3852c-148">All of the above APIs use *linguistic* string searching and comparison using the thread's [current culture](xref:System.Threading.Thread.CurrentCulture), by default.</span></span> <span data-ttu-id="3852c-149">[序号和语言搜索与比较](#ordinal-vs-linguistic-search-and-comparison)中指明了语言和序号搜索与比较之间的区别。</span><span class="sxs-lookup"><span data-stu-id="3852c-149">The differences between *linguistic* and *ordinal* search and comparison are called out in the [Ordinal vs. linguistic search and comparison](#ordinal-vs-linguistic-search-and-comparison).</span></span>

<span data-ttu-id="3852c-150">由于 ICU 实现语言字符串比较的方式与 NLS 不同，从早期版本的 .NET Core 或 .NET Framework 升级到 .NET 5.0 的基于 Windows 的应用程序，在调用受影响的 API 之一时可能会注意到，这些 API 开始表现出不同的行为。</span><span class="sxs-lookup"><span data-stu-id="3852c-150">Because ICU implements linguistic string comparisons differently from NLS, Windows-based applications that upgrade to .NET 5.0 from an earlier version of .NET Core or .NET Framework and that call one of the affected APIs may notice that the APIs begin exhibiting different behaviors.</span></span>

### <a name="exceptions"></a><span data-ttu-id="3852c-151">异常</span><span class="sxs-lookup"><span data-stu-id="3852c-151">Exceptions</span></span>

* <span data-ttu-id="3852c-152">如果 API 接受显式 `StringComparison` 或 `CultureInfo` 参数，则该参数将覆盖 API 的默认行为。</span><span class="sxs-lookup"><span data-stu-id="3852c-152">If an API accepts an explicit `StringComparison` or `CultureInfo` parameter, that parameter overrides the API's default behavior.</span></span>
* <span data-ttu-id="3852c-153">第一个参数类型为 `char` 的 `System.String` 成员（例如 <xref:System.String.IndexOf(System.Char)?displayProperty=nameWithType>）使用序号搜索，除非调用方传递指定 `CurrentCulture[IgnoreCase]` 或 `InvariantCulture[IgnoreCase]` 的显式 `StringComparison` 参数。</span><span class="sxs-lookup"><span data-stu-id="3852c-153">`System.String` members where the first parameter is of type `char` (for example, <xref:System.String.IndexOf(System.Char)?displayProperty=nameWithType>) use ordinal searching, unless the caller passes an explicit `StringComparison` argument that specifies `CurrentCulture[IgnoreCase]` or `InvariantCulture[IgnoreCase]`.</span></span>

<span data-ttu-id="3852c-154">若要详细分析每个 <xref:System.String> API 的默认行为，请参阅[默认搜索和比较类型](#default-search-and-comparison-types)部分。</span><span class="sxs-lookup"><span data-stu-id="3852c-154">For a more detailed analysis of the default behavior of each <xref:System.String> API, see the [Default search and comparison types](#default-search-and-comparison-types) section.</span></span>

## <a name="ordinal-vs-linguistic-search-and-comparison"></a><span data-ttu-id="3852c-155">序号和语言搜索与比较</span><span class="sxs-lookup"><span data-stu-id="3852c-155">Ordinal vs. linguistic search and comparison</span></span>

<span data-ttu-id="3852c-156">序号（也称为“非语言”）搜索与比较将字符串拆分为其单独的 `char` 元素，并执行逐字符搜索或比较。</span><span class="sxs-lookup"><span data-stu-id="3852c-156">*Ordinal* (also known as *non-linguistic*) search and comparison decomposes a string into its individual `char` elements and performs a char-by-char search or comparison.</span></span> <span data-ttu-id="3852c-157">例如，字符串 `"dog"` 和 `"dog"` 在 `Ordinal` 比较器下的比较结果为“相等”，因为这两个字符串由完全相同的字符序列组成。</span><span class="sxs-lookup"><span data-stu-id="3852c-157">For example, the strings `"dog"` and `"dog"` compare as *equal* under an `Ordinal` comparer, since the two strings consist of the exact same sequence of chars.</span></span> <span data-ttu-id="3852c-158">但是，`"dog"` 和 `"Dog"` 在 `Ordinal` 比较器下的比较结果为“不相等”，因为它们由不完全相同的字符序列组成。</span><span class="sxs-lookup"><span data-stu-id="3852c-158">However, `"dog"` and `"Dog"` compare as *not equal* under an `Ordinal` comparer, because they don't consist of the exact same sequence of chars.</span></span> <span data-ttu-id="3852c-159">也就是说，大写 `'D'` 的码位 `U+0044` 出现在小写 `'d'` 的码位 `U+0064` 之前，因此 `"dog"` 排在 `"Dog"` 之前。</span><span class="sxs-lookup"><span data-stu-id="3852c-159">That is, uppercase `'D'`'s code point `U+0044` occurs before lowercase `'d'`'s code point `U+0064`, resulting in `"dog"` sorting before `"Dog"`.</span></span>

<span data-ttu-id="3852c-160">`OrdinalIgnoreCase` 比较器仍执行逐字符操作，但它在执行该操作时消除了大小写差异。</span><span class="sxs-lookup"><span data-stu-id="3852c-160">An `OrdinalIgnoreCase` comparer still operates on a char-by-char basis, but it eliminates case differences while performing the operation.</span></span> <span data-ttu-id="3852c-161">在 `OrdinalIgnoreCase` 比较器下，字符对 `'d'` 和 `'D'` 的比较结果为“相等”，字符对 `'á'` 和 `'Á'` 亦是如此。</span><span class="sxs-lookup"><span data-stu-id="3852c-161">Under an `OrdinalIgnoreCase` comparer, the char pairs `'d'` and `'D'` compare as *equal*, as do the char pairs `'á'` and `'Á'`.</span></span> <span data-ttu-id="3852c-162">但非重音字符 `'a'` 与重音字符 `'á'` 的比较结果为“不相等”。</span><span class="sxs-lookup"><span data-stu-id="3852c-162">But the unaccented char `'a'` compares as *not equal* to the accented char `'á'`.</span></span>

<span data-ttu-id="3852c-163">下表提供了此操作的一些示例：</span><span class="sxs-lookup"><span data-stu-id="3852c-163">Some examples of this are provided in the following table:</span></span>

| <span data-ttu-id="3852c-164">字符串 1</span><span class="sxs-lookup"><span data-stu-id="3852c-164">String 1</span></span> | <span data-ttu-id="3852c-165">字符串 2</span><span class="sxs-lookup"><span data-stu-id="3852c-165">String 2</span></span> | <span data-ttu-id="3852c-166">`Ordinal` 比较</span><span class="sxs-lookup"><span data-stu-id="3852c-166">`Ordinal` comparison</span></span> | <span data-ttu-id="3852c-167">`OrdinalIgnoreCase` 比较</span><span class="sxs-lookup"><span data-stu-id="3852c-167">`OrdinalIgnoreCase` comparison</span></span> |
|---|---|---|---|
| `"dog"` | `"dog"` | <span data-ttu-id="3852c-168">equal</span><span class="sxs-lookup"><span data-stu-id="3852c-168">equal</span></span> | <span data-ttu-id="3852c-169">equal</span><span class="sxs-lookup"><span data-stu-id="3852c-169">equal</span></span> |
| `"dog"` | `"Dog"` | <span data-ttu-id="3852c-170">不等于</span><span class="sxs-lookup"><span data-stu-id="3852c-170">not equal</span></span> | <span data-ttu-id="3852c-171">equal</span><span class="sxs-lookup"><span data-stu-id="3852c-171">equal</span></span> |
| `"resume"` | `"Resume"` | <span data-ttu-id="3852c-172">不等于</span><span class="sxs-lookup"><span data-stu-id="3852c-172">not equal</span></span> | <span data-ttu-id="3852c-173">equal</span><span class="sxs-lookup"><span data-stu-id="3852c-173">equal</span></span> |
| `"resume"` | `"résumé"` | <span data-ttu-id="3852c-174">不等于</span><span class="sxs-lookup"><span data-stu-id="3852c-174">not equal</span></span> | <span data-ttu-id="3852c-175">不等于</span><span class="sxs-lookup"><span data-stu-id="3852c-175">not equal</span></span> |

<span data-ttu-id="3852c-176">Unicode 还允许字符串具有多个不同的内存中表示形式。</span><span class="sxs-lookup"><span data-stu-id="3852c-176">Unicode also allows strings to have several different in-memory representations.</span></span> <span data-ttu-id="3852c-177">例如，带锐音符的 e (é) 可以用两种方式表示：</span><span class="sxs-lookup"><span data-stu-id="3852c-177">For example, an e-acute (é) can be represented in two possible ways:</span></span>

* <span data-ttu-id="3852c-178">单个文本 `'é'` 字符（亦可写为 `'\u00E9'`）。</span><span class="sxs-lookup"><span data-stu-id="3852c-178">A single literal `'é'` character (also written as `'\u00E9'`).</span></span>
* <span data-ttu-id="3852c-179">文本无重音 `'e'` 字符，后跟一个组合用重音修饰符字符 `'\u0301'`。</span><span class="sxs-lookup"><span data-stu-id="3852c-179">A literal unaccented `'e'` character, followed by a combining accent modifier character `'\u0301'`.</span></span>

<span data-ttu-id="3852c-180">这意味着下面的四个字符串的显示结果都为 `"résumé"`，即使它们的组成部分有所不同。</span><span class="sxs-lookup"><span data-stu-id="3852c-180">This means that the following _four_ strings all result in `"résumé"` when displayed, even though their constituent pieces are different.</span></span> <span data-ttu-id="3852c-181">该字符串使用文本 `'é'` 字符或文本无重音 `'e'` 字符，以及组合用重音修饰符 `'\u0301'`。</span><span class="sxs-lookup"><span data-stu-id="3852c-181">The strings use a combination of literal `'é'` characters or literal unaccented `'e'` characters plus the combining accent modifier `'\u0301'`.</span></span>

* `"r\u00E9sum\u00E9"`
* `"r\u00E9sume\u0301"`
* `"re\u0301sum\u00E9"`
* `"re\u0301sume\u0301"`

<span data-ttu-id="3852c-182">在序号比较器下，这些字符串相互比较后的结果都不是“相等”。</span><span class="sxs-lookup"><span data-stu-id="3852c-182">Under an ordinal comparer, none of these strings compare as equal to each other.</span></span> <span data-ttu-id="3852c-183">这是因为它们都包含不同的基础字符序列，即使在屏幕上显示时，它们看起来都是相同的。</span><span class="sxs-lookup"><span data-stu-id="3852c-183">This is because they all contain different underlying char sequences, even though when they're rendered to the screen, they all look the same.</span></span>

<span data-ttu-id="3852c-184">执行 `string.IndexOf(..., StringComparison.Ordinal)` 操作时，运行时查找完全匹配的子字符串。</span><span class="sxs-lookup"><span data-stu-id="3852c-184">When performing a `string.IndexOf(..., StringComparison.Ordinal)` operation, the runtime looks for an exact substring match.</span></span> <span data-ttu-id="3852c-185">结果如下所示：</span><span class="sxs-lookup"><span data-stu-id="3852c-185">The results are as follows.</span></span>

```cs
Console.WriteLine("resume".IndexOf("e", StringComparison.Ordinal)); // prints '1'
Console.WriteLine("r\u00E9sum\u00E9".IndexOf("e", StringComparison.Ordinal)); // prints '-1'
Console.WriteLine("r\u00E9sume\u0301".IndexOf("e", StringComparison.Ordinal)); // prints '5'
Console.WriteLine("re\u0301sum\u00E9".IndexOf("e", StringComparison.Ordinal)); // prints '1'
Console.WriteLine("re\u0301sume\u0301".IndexOf("e", StringComparison.Ordinal)); // prints '1'
Console.WriteLine("resume".IndexOf("E", StringComparison.OrdinalIgnoreCase)); // prints '1'
Console.WriteLine("r\u00E9sum\u00E9".IndexOf("E", StringComparison.OrdinalIgnoreCase)); // prints '-1'
Console.WriteLine("r\u00E9sume\u0301".IndexOf("E", StringComparison.OrdinalIgnoreCase)); // prints '5'
Console.WriteLine("re\u0301sum\u00E9".IndexOf("E", StringComparison.OrdinalIgnoreCase)); // prints '1'
Console.WriteLine("re\u0301sume\u0301".IndexOf("E", StringComparison.OrdinalIgnoreCase)); // prints '1'
```

<span data-ttu-id="3852c-186">序号搜索与比较例程从来不受当前线程的区域性设置的影响。</span><span class="sxs-lookup"><span data-stu-id="3852c-186">Ordinal search and comparison routines are never affected by the current thread's culture setting.</span></span>

<span data-ttu-id="3852c-187">语言搜索与比较例程将字符串拆分为排序元素，并对这些元素执行搜索或比较。</span><span class="sxs-lookup"><span data-stu-id="3852c-187">*Linguistic* search and comparison routines decompose a string into *collation elements* and perform searches or comparisons on these elements.</span></span> <span data-ttu-id="3852c-188">字符串的字符和其构成的排序元素之间不一定存在 1:1 映射。</span><span class="sxs-lookup"><span data-stu-id="3852c-188">There's not necessarily a 1:1 mapping between a string's characters and its constituent collation elements.</span></span> <span data-ttu-id="3852c-189">例如，长度为 2 的字符串可能只包含单个排序元素。</span><span class="sxs-lookup"><span data-stu-id="3852c-189">For example, a string of length 2 may consist of only a single collation element.</span></span> <span data-ttu-id="3852c-190">使用识别语言的方式比较两个字符串时，比较器会检查两个字符串的排序元素是否具有相同的语义含义，即使这两个字符串的文本字符并不相同。</span><span class="sxs-lookup"><span data-stu-id="3852c-190">When two strings are compared in a linguistic-aware fashion, the comparer checks whether the two strings' collation elements have the same semantic meaning, even if the string's literal characters are different.</span></span>

<span data-ttu-id="3852c-191">再次考虑字符串 `"résumé"` 及其四种不同的表示形式。</span><span class="sxs-lookup"><span data-stu-id="3852c-191">Consider again the string `"résumé"` and its four different representations.</span></span> <span data-ttu-id="3852c-192">下表展示了拆分为其排序元素的每种表示形式。</span><span class="sxs-lookup"><span data-stu-id="3852c-192">The following table shows each representation broken down into its collation elements.</span></span>

| <span data-ttu-id="3852c-193">String</span><span class="sxs-lookup"><span data-stu-id="3852c-193">String</span></span> | <span data-ttu-id="3852c-194">作为排序元素</span><span class="sxs-lookup"><span data-stu-id="3852c-194">As collation elements</span></span> |
|---|---|
| `"r\u00E9sum\u00E9"` | `"r" + "\u00E9" + "s" + "u" + "m" + "\u00E9"` |
| `"r\u00E9sume\u0301"` | `"r" + "\u00E9" + "s" + "u" + "m" + "e\u0301"` |
| `"re\u0301sum\u00E9"` | `"r" + "e\u0301" + "s" + "u" + "m" + "\u00E9"` |
| `"re\u0301sume\u0301"` | `"r" + "e\u00E9" + "s" + "u" + "m" + "e\u0301"` |

<span data-ttu-id="3852c-195">排序元素松散地对应于读取器视为单个字符或字符群集的字符串。</span><span class="sxs-lookup"><span data-stu-id="3852c-195">A collation element corresponds loosely to what readers would think of as a single character or cluster of characters.</span></span> <span data-ttu-id="3852c-196">它在概念上类似于[字形群集](character-encoding-introduction.md#grapheme-clusters)，但包含更大的字符串。</span><span class="sxs-lookup"><span data-stu-id="3852c-196">It's conceptually similar to a [grapheme cluster](character-encoding-introduction.md#grapheme-clusters) but encompasses a somewhat larger umbrella.</span></span>

<span data-ttu-id="3852c-197">在语言比较器下，不需要完全匹配。</span><span class="sxs-lookup"><span data-stu-id="3852c-197">Under a linguistic comparer, exact matches aren't necessary.</span></span> <span data-ttu-id="3852c-198">排序元素根据其语义含义进行比较。</span><span class="sxs-lookup"><span data-stu-id="3852c-198">Collation elements are instead compared based on their semantic meaning.</span></span> <span data-ttu-id="3852c-199">例如，语言比较器对子字符串 `"\u00E9"` 和 `"e\u0301"` 的比较结果为“相等”，因为它们在语义上都是指“带锐音符修饰符的小写字母 e”。</span><span class="sxs-lookup"><span data-stu-id="3852c-199">For example, a linguistic comparer treats the substrings `"\u00E9"` and `"e\u0301"` as equal since they both semantically mean "a lowercase e with an acute accent modifier."</span></span> <span data-ttu-id="3852c-200">这允许 `IndexOf` 方法匹配更大字符串中的子字符串 `"e\u0301"`，该更大字符串包含语义上等效的子字符串 `"\u00E9"`，如下面的代码示例中所示。</span><span class="sxs-lookup"><span data-stu-id="3852c-200">This allows the `IndexOf` method to match the substring `"e\u0301"` within a larger string that contains the semantically equivalent substring `"\u00E9"`, as shown in the following code sample.</span></span>

```cs
Console.WriteLine("r\u00E9sum\u00E9".IndexOf("e")); // prints '-1' (not found)
Console.WriteLine("r\u00E9sum\u00E9".IndexOf("e\u00E9")); // prints '1'
Console.WriteLine("\u00E9".IndexOf("e\u00E9")); // prints '0'
```

<span data-ttu-id="3852c-201">因此，如果使用语言比较，则两个不同长度的字符串的比较结果可能为“相等”。</span><span class="sxs-lookup"><span data-stu-id="3852c-201">As a consequence of this, two strings of different lengths may compare as equal if a linguistic comparison is used.</span></span> <span data-ttu-id="3852c-202">调用方应注意，在这种情况下处理字符串长度时，不要使用特殊情况逻辑。</span><span class="sxs-lookup"><span data-stu-id="3852c-202">Callers should take care not to special-case logic that deals with string length in such scenarios.</span></span>

<span data-ttu-id="3852c-203">识别区域性搜索与比较例程是语言搜索与比较例程的一种特殊形式。</span><span class="sxs-lookup"><span data-stu-id="3852c-203">*Culture-aware* search and comparison routines are a special form of linguistic search and comparison routines.</span></span> <span data-ttu-id="3852c-204">在识别区域性比较器下，排序元素的概念扩展为包含特定于指定区域性的信息。</span><span class="sxs-lookup"><span data-stu-id="3852c-204">Under a culture-aware comparer, the concept of a collation element is extended to include information specific to the specified culture.</span></span>

<span data-ttu-id="3852c-205">例如，[在匈牙利字母中](https://en.wikipedia.org/wiki/Hungarian_alphabet)，如果两个字符 \<dz\> 连续出现，则它们被认为是与 \<d\> 或 \<z\> 不同的独特字母。</span><span class="sxs-lookup"><span data-stu-id="3852c-205">For example, [in the Hungarian alphabet](https://en.wikipedia.org/wiki/Hungarian_alphabet), when the two characters \<dz\> appear back-to-back, they are considered their own unique letter distinct from either \<d\> or \<z\>.</span></span> <span data-ttu-id="3852c-206">这意味着，如果在字符串中出现 \<dz\>，则匈牙利语识别区域性比较器会将其视为单个排序元素。</span><span class="sxs-lookup"><span data-stu-id="3852c-206">This means that when \<dz\> is seen in a string, a Hungarian culture-aware comparer treats it as a single collation element.</span></span>

| <span data-ttu-id="3852c-207">String</span><span class="sxs-lookup"><span data-stu-id="3852c-207">String</span></span> | <span data-ttu-id="3852c-208">作为排序元素</span><span class="sxs-lookup"><span data-stu-id="3852c-208">As collation elements</span></span> | <span data-ttu-id="3852c-209">注解</span><span class="sxs-lookup"><span data-stu-id="3852c-209">Remarks</span></span> |
|---|---|---|
| `"endz"` | `"e" + "n" + "d" + "z"` | <span data-ttu-id="3852c-210">（使用标准语言比较器）</span><span class="sxs-lookup"><span data-stu-id="3852c-210">(using a standard linguistic comparer)</span></span> |
| `"endz"` | `"e" + "n" + "dz"` | <span data-ttu-id="3852c-211">（使用匈牙利语识别区域性比较器）</span><span class="sxs-lookup"><span data-stu-id="3852c-211">(using a Hungarian culture-aware comparer)</span></span> |

<span data-ttu-id="3852c-212">使用匈牙利语识别区域性比较器时，字符串 `"endz"` 不以子字符串 `"z"` 结尾，因为 <\dz\> 和 <\z\> 被视为具有不同语义含义的排序元素。</span><span class="sxs-lookup"><span data-stu-id="3852c-212">When using a Hungarian culture-aware comparer, this means that the string `"endz"` *does not* end with the substring `"z"`, as <\dz\> and <\z\> are considered collation elements with different semantic meaning.</span></span>

```cs
// Set thread culture to Hungarian
CultureInfo.CurrentCulture = CultureInfo.GetCultureInfo("hu-HU");
Console.WriteLine("endz".EndsWith("z")); // Prints 'False'

// Set thread culture to invariant culture
CultureInfo.CurrentCulture = CultureInfo.InvariantCulture;
Console.WriteLine("endz".EndsWith("z")); // Prints 'True'
```

> [!NOTE]
>
> - <span data-ttu-id="3852c-213">行为：语言和识别区域性比较器可以不时地进行行为调整。</span><span class="sxs-lookup"><span data-stu-id="3852c-213">Behavior: Linguistic and culture-aware comparers can undergo behavioral adjustments from time to time.</span></span> <span data-ttu-id="3852c-214">ICU 和较旧的 Windows NLS 功能都将更新，以考虑世界语言的变化。</span><span class="sxs-lookup"><span data-stu-id="3852c-214">Both ICU and the older Windows NLS facility are updated to account for how world languages change.</span></span> <span data-ttu-id="3852c-215">有关详细信息，请参阅博客文章[区域设置（区域性）数据改动](/archive/blogs/shawnste/locale-culture-data-churn)。</span><span class="sxs-lookup"><span data-stu-id="3852c-215">For more information, see the blog post [Locale (culture) data churn](/archive/blogs/shawnste/locale-culture-data-churn).</span></span> <span data-ttu-id="3852c-216">序号比较器的行为将永远不会发生更改，因为它执行严格的按位搜索和比较。</span><span class="sxs-lookup"><span data-stu-id="3852c-216">The *Ordinal* comparer's behavior will never change since it performs exact bitwise searching and comparison.</span></span> <span data-ttu-id="3852c-217">但是，OrdinalIgnoreCase 比较器的行为可能会随着 Unicode 的增加而改变，以包含更多的字符集，并纠正现有大小写数据中的遗漏。</span><span class="sxs-lookup"><span data-stu-id="3852c-217">However, the *OrdinalIgnoreCase* comparer's behavior may change as Unicode grows to encompass more character sets and corrects omissions in existing casing data.</span></span>
> - <span data-ttu-id="3852c-218">使用情况：比较器 `StringComparison.InvariantCulture` 和 `StringComparison.InvariantCultureIgnoreCase` 是不能识别区域性的语言比较器。</span><span class="sxs-lookup"><span data-stu-id="3852c-218">Usage: The comparers `StringComparison.InvariantCulture` and `StringComparison.InvariantCultureIgnoreCase` are linguistic comparers that are not culture-aware.</span></span> <span data-ttu-id="3852c-219">也就是说，这些比较器理解一些概念，例如，重音字符 é 具有多种可能的基础表示形式，且所有这些表示形式都应视为“相等”。</span><span class="sxs-lookup"><span data-stu-id="3852c-219">That is, these comparers understand concepts such as the accented character é having multiple possible underlying representations, and that all such representations should be treated equal.</span></span> <span data-ttu-id="3852c-220">但不识别区域性的语言比较器不包含对 \<dz\> 区别于 \<d\> 或 \<z\> 的特殊处理，如上所示。</span><span class="sxs-lookup"><span data-stu-id="3852c-220">But non-culture-aware linguistic comparers won't contain special handling for \<dz\> as distinct from \<d\> or \<z\>, as shown above.</span></span> <span data-ttu-id="3852c-221">它们也不能处理像德语 Eszett (ß) 这样的特殊字符。</span><span class="sxs-lookup"><span data-stu-id="3852c-221">They also won't special-case characters like the German Eszett (ß).</span></span>

<span data-ttu-id="3852c-222">.NET 还提供固定全球化模式。</span><span class="sxs-lookup"><span data-stu-id="3852c-222">.NET also offers the *invariant globalization mode*.</span></span> <span data-ttu-id="3852c-223">此选择加入模式禁用处理语言搜索与比较例程的代码路径。</span><span class="sxs-lookup"><span data-stu-id="3852c-223">This opt-in mode disables code paths that deal with linguistic search and comparison routines.</span></span> <span data-ttu-id="3852c-224">在此模式下，无论调用方提供何种 `CultureInfo` 或 `StringComparison` 参数，所有操作都使用序号或 OrdinalIgnoreCase 行为。</span><span class="sxs-lookup"><span data-stu-id="3852c-224">In this mode, all operations use *Ordinal* or *OrdinalIgnoreCase* behaviors, regardless of what `CultureInfo` or `StringComparison` argument the caller provides.</span></span> <span data-ttu-id="3852c-225">有关详细信息，请参阅[全球化运行时配置选项](../../core/run-time-config/globalization.md)和 [.NET Core 全球化固定模式](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md)。</span><span class="sxs-lookup"><span data-stu-id="3852c-225">For more information, see [Run-time configuration options for globalization](../../core/run-time-config/globalization.md) and [.NET Core Globalization Invariant Mode](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span></span>

<span data-ttu-id="3852c-226">有关详细信息，请参阅[比较 .NET 中的字符串的最佳做法](best-practices-strings.md)。</span><span class="sxs-lookup"><span data-stu-id="3852c-226">For more information, see [Best practices for comparing strings in .NET](best-practices-strings.md).</span></span>

## <a name="security-implications"></a><span data-ttu-id="3852c-227">安全隐患</span><span class="sxs-lookup"><span data-stu-id="3852c-227">Security implications</span></span>

<span data-ttu-id="3852c-228">如果你的应用使用受影响的 API 进行筛选，我们建议启用 CA1307 和 CA1309 代码分析规则，以帮助查找可能无意中使用了语言搜索而不是序号搜索的位置。</span><span class="sxs-lookup"><span data-stu-id="3852c-228">If your app uses an affected API for filtering, we recommend enabling the CA1307 and CA1309 code analysis rules to help locate places where a linguistic search may have inadvertently been used instead of an ordinal search.</span></span> <span data-ttu-id="3852c-229">下面这样的代码模式可能易受安全漏洞的攻击。</span><span class="sxs-lookup"><span data-stu-id="3852c-229">Code patterns like the following may be susceptible to security exploits.</span></span>

```cs
//
// THIS SAMPLE CODE IS INCORRECT.
// DO NOT USE IT IN PRODUCTION.
//
public bool ContainsHtmlSensitiveCharacters(string input)
{
    if (input.IndexOf("<") >= 0) { return true; }
    if (input.IndexOf("&") >= 0) { return true; }
    return false;
}
```

<span data-ttu-id="3852c-230">由于 `string.IndexOf(string)` 方法默认使用语言搜索，因此字符串可能包含文本 `'<'` 或 `'&'` 字符，且 `string.IndexOf(string)` 例程可能返回 `-1`，表示找不到搜索子字符串。</span><span class="sxs-lookup"><span data-stu-id="3852c-230">Because the `string.IndexOf(string)` method uses a linguistic search by default, it's possible for a string to contain a literal `'<'` or `'&'` character and for the `string.IndexOf(string)` routine to return `-1`, indicating that the search substring was not found.</span></span> <span data-ttu-id="3852c-231">代码分析规则 CA1307 和 CA1309 标记此类调用站点，并警告开发人员存在潜在的问题。</span><span class="sxs-lookup"><span data-stu-id="3852c-231">Code analysis rules CA1307 and CA1309 flag such call sites and alert the developer that there's a potential problem.</span></span>

## <a name="default-search-and-comparison-types"></a><span data-ttu-id="3852c-232">默认搜索和比较类型</span><span class="sxs-lookup"><span data-stu-id="3852c-232">Default search and comparison types</span></span>

<span data-ttu-id="3852c-233">下表列出了各种字符串和类似于字符串的 API 的默认搜索和比较类型。</span><span class="sxs-lookup"><span data-stu-id="3852c-233">The following table lists the default search and comparison types for various string and string-like APIs.</span></span> <span data-ttu-id="3852c-234">如果调用方提供显式 `CultureInfo` 或 `StringComparison` 参数，则该参数将优先于任何默认值。</span><span class="sxs-lookup"><span data-stu-id="3852c-234">If the caller provides an explicit `CultureInfo` or `StringComparison` parameter, that parameter will be honored over any default.</span></span>

| <span data-ttu-id="3852c-235">API</span><span class="sxs-lookup"><span data-stu-id="3852c-235">API</span></span> | <span data-ttu-id="3852c-236">默认行为</span><span class="sxs-lookup"><span data-stu-id="3852c-236">Default behavior</span></span> | <span data-ttu-id="3852c-237">注解</span><span class="sxs-lookup"><span data-stu-id="3852c-237">Remarks</span></span> |
|---|---|---|
| `string.Compare` | <span data-ttu-id="3852c-238">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="3852c-238">CurrentCulture</span></span> | |
| `string.CompareTo` | <span data-ttu-id="3852c-239">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="3852c-239">CurrentCulture</span></span> | |
| `string.Contains` | <span data-ttu-id="3852c-240">Ordinal</span><span class="sxs-lookup"><span data-stu-id="3852c-240">Ordinal</span></span> | |
| `string.EndsWith` | <span data-ttu-id="3852c-241">Ordinal</span><span class="sxs-lookup"><span data-stu-id="3852c-241">Ordinal</span></span> | <span data-ttu-id="3852c-242">（当第一个参数为 `char` 时）</span><span class="sxs-lookup"><span data-stu-id="3852c-242">(when the first parameter is a `char`)</span></span> |
| `string.EndsWith` | <span data-ttu-id="3852c-243">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="3852c-243">CurrentCulture</span></span> | <span data-ttu-id="3852c-244">（当第一个参数为 `string` 时）</span><span class="sxs-lookup"><span data-stu-id="3852c-244">(when the first parameter is a `string`)</span></span> |
| `string.Equals` | <span data-ttu-id="3852c-245">Ordinal</span><span class="sxs-lookup"><span data-stu-id="3852c-245">Ordinal</span></span> | |
| `string.GetHashCode` | <span data-ttu-id="3852c-246">Ordinal</span><span class="sxs-lookup"><span data-stu-id="3852c-246">Ordinal</span></span> | |
| `string.IndexOf` | <span data-ttu-id="3852c-247">Ordinal</span><span class="sxs-lookup"><span data-stu-id="3852c-247">Ordinal</span></span> | <span data-ttu-id="3852c-248">（当第一个参数为 `char` 时）</span><span class="sxs-lookup"><span data-stu-id="3852c-248">(when the first parameter is a `char`)</span></span> |
| `string.IndexOf` | <span data-ttu-id="3852c-249">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="3852c-249">CurrentCulture</span></span> | <span data-ttu-id="3852c-250">（当第一个参数为 `string` 时）</span><span class="sxs-lookup"><span data-stu-id="3852c-250">(when the first parameter is a `string`)</span></span> |
| `string.IndexOfAny` | <span data-ttu-id="3852c-251">Ordinal</span><span class="sxs-lookup"><span data-stu-id="3852c-251">Ordinal</span></span> | |
| `string.LastIndexOf` | <span data-ttu-id="3852c-252">Ordinal</span><span class="sxs-lookup"><span data-stu-id="3852c-252">Ordinal</span></span> | <span data-ttu-id="3852c-253">（当第一个参数为 `char` 时）</span><span class="sxs-lookup"><span data-stu-id="3852c-253">(when the first parameter is a `char`)</span></span> |
| `string.LastIndexOf` | <span data-ttu-id="3852c-254">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="3852c-254">CurrentCulture</span></span> | <span data-ttu-id="3852c-255">（当第一个参数为 `string` 时）</span><span class="sxs-lookup"><span data-stu-id="3852c-255">(when the first parameter is a `string`)</span></span> |
| `string.LastIndexOfAny` | <span data-ttu-id="3852c-256">Ordinal</span><span class="sxs-lookup"><span data-stu-id="3852c-256">Ordinal</span></span> | |
| `string.Replace` | <span data-ttu-id="3852c-257">Ordinal</span><span class="sxs-lookup"><span data-stu-id="3852c-257">Ordinal</span></span> | |
| `string.Split` | <span data-ttu-id="3852c-258">Ordinal</span><span class="sxs-lookup"><span data-stu-id="3852c-258">Ordinal</span></span> | |
| `string.StartsWith` | <span data-ttu-id="3852c-259">Ordinal</span><span class="sxs-lookup"><span data-stu-id="3852c-259">Ordinal</span></span> | <span data-ttu-id="3852c-260">（当第一个参数为 `char` 时）</span><span class="sxs-lookup"><span data-stu-id="3852c-260">(when the first parameter is a `char`)</span></span> |
| `string.StartsWith` | <span data-ttu-id="3852c-261">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="3852c-261">CurrentCulture</span></span> | <span data-ttu-id="3852c-262">（当第一个参数为 `string` 时）</span><span class="sxs-lookup"><span data-stu-id="3852c-262">(when the first parameter is a `string`)</span></span> |
| `string.ToLower` | <span data-ttu-id="3852c-263">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="3852c-263">CurrentCulture</span></span> | |
| `string.ToLowerInvariant` | <span data-ttu-id="3852c-264">InvariantCulture</span><span class="sxs-lookup"><span data-stu-id="3852c-264">InvariantCulture</span></span> | |
| `string.ToUpper` | <span data-ttu-id="3852c-265">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="3852c-265">CurrentCulture</span></span> | |
| `string.ToUpperInvariant` | <span data-ttu-id="3852c-266">InvariantCulture</span><span class="sxs-lookup"><span data-stu-id="3852c-266">InvariantCulture</span></span> | |
| `string.Trim` | <span data-ttu-id="3852c-267">Ordinal</span><span class="sxs-lookup"><span data-stu-id="3852c-267">Ordinal</span></span> | |
| `string.TrimEnd` | <span data-ttu-id="3852c-268">Ordinal</span><span class="sxs-lookup"><span data-stu-id="3852c-268">Ordinal</span></span> | |
| `string.TrimStart` | <span data-ttu-id="3852c-269">Ordinal</span><span class="sxs-lookup"><span data-stu-id="3852c-269">Ordinal</span></span> | |
| `string == string` | <span data-ttu-id="3852c-270">Ordinal</span><span class="sxs-lookup"><span data-stu-id="3852c-270">Ordinal</span></span> | |
| `string != string` | <span data-ttu-id="3852c-271">Ordinal</span><span class="sxs-lookup"><span data-stu-id="3852c-271">Ordinal</span></span> | |

<span data-ttu-id="3852c-272">与 `string` API 不同，默认情况下，所有 `MemoryExtensions` API 都执行序号搜索与比较，但以下情况例外。</span><span class="sxs-lookup"><span data-stu-id="3852c-272">Unlike `string` APIs, all `MemoryExtensions` APIs perform *Ordinal* searches and comparisons by default, with the following exceptions.</span></span>

| <span data-ttu-id="3852c-273">API</span><span class="sxs-lookup"><span data-stu-id="3852c-273">API</span></span> | <span data-ttu-id="3852c-274">默认行为</span><span class="sxs-lookup"><span data-stu-id="3852c-274">Default behavior</span></span> | <span data-ttu-id="3852c-275">注解</span><span class="sxs-lookup"><span data-stu-id="3852c-275">Remarks</span></span> |
|---|---|---|
| `MemoryExtensions.ToLower` | <span data-ttu-id="3852c-276">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="3852c-276">CurrentCulture</span></span> | <span data-ttu-id="3852c-277">（当传递 null `CultureInfo` 参数时）</span><span class="sxs-lookup"><span data-stu-id="3852c-277">(when passed a null `CultureInfo` argument)</span></span> |
| `MemoryExtensions.ToLowerInvariant` | <span data-ttu-id="3852c-278">InvariantCulture</span><span class="sxs-lookup"><span data-stu-id="3852c-278">InvariantCulture</span></span> | |
| `MemoryExtensions.ToUpper` | <span data-ttu-id="3852c-279">CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="3852c-279">CurrentCulture</span></span> | <span data-ttu-id="3852c-280">（当传递 null `CultureInfo` 参数时）</span><span class="sxs-lookup"><span data-stu-id="3852c-280">(when passed a null `CultureInfo` argument)</span></span> |
| `MemoryExtensions.ToUpperInvariant` | <span data-ttu-id="3852c-281">InvariantCulture</span><span class="sxs-lookup"><span data-stu-id="3852c-281">InvariantCulture</span></span> | |

<span data-ttu-id="3852c-282">结果是，在将代码从使用 `string` 转换为使用 `ReadOnlySpan<char>`时，可能会无意中引入行为更改。</span><span class="sxs-lookup"><span data-stu-id="3852c-282">A consequence is that when converting code from consuming `string` to consuming `ReadOnlySpan<char>`, behavioral changes may be introduced inadvertently.</span></span> <span data-ttu-id="3852c-283">相关示例如下。</span><span class="sxs-lookup"><span data-stu-id="3852c-283">An example of this follows.</span></span>

```cs
string str = GetString();
if (str.StartsWith("Hello")) { /* do something */ } // this is a CULTURE-AWARE (linguistic) comparison

ReadOnlySpan<char> span = s.AsSpan();
if (span.StartsWith("Hello")) { /* do something */ } // this is an ORDINAL (non-linguistic) comparison
```

<span data-ttu-id="3852c-284">解决此问题的建议方法是将显式 `StringComparison` 参数传递给这些 API。</span><span class="sxs-lookup"><span data-stu-id="3852c-284">The recommended way to address this is to pass an explicit `StringComparison` parameter to these APIs.</span></span> <span data-ttu-id="3852c-285">代码分析规则 CA1307 和 CA1309 可帮助解决此问题。</span><span class="sxs-lookup"><span data-stu-id="3852c-285">The code analysis rules CA1307 and CA1309 can assist with this.</span></span>

```cs
string str = GetString();
if (str.StartsWith("Hello", StringComparison.Ordinal)) { /* do something */ } // ordinal comparison

ReadOnlySpan<char> span = s.AsSpan();
if (span.StartsWith("Hello", StringComparison.Ordinal)) { /* do something */ } // ordinal comparison
```

## <a name="see-also"></a><span data-ttu-id="3852c-286">请参阅</span><span class="sxs-lookup"><span data-stu-id="3852c-286">See also</span></span>

- [<span data-ttu-id="3852c-287">全球化中断性变更</span><span class="sxs-lookup"><span data-stu-id="3852c-287">Globalization breaking changes</span></span>](../../core/compatibility/globalization.md)
- [<span data-ttu-id="3852c-288">有关比较 .NET 中字符串的最佳做法</span><span class="sxs-lookup"><span data-stu-id="3852c-288">Best practices for comparing strings in .NET</span></span>](best-practices-strings.md)
- [<span data-ttu-id="3852c-289">如何比较 C# 中的字符串</span><span class="sxs-lookup"><span data-stu-id="3852c-289">How to compare strings in C#</span></span>](../../csharp/how-to/compare-strings.md)
- [<span data-ttu-id="3852c-290">.NET 全球化和 ICU</span><span class="sxs-lookup"><span data-stu-id="3852c-290">.NET globalization and ICU</span></span>](../globalization-localization/globalization-icu.md)
- [<span data-ttu-id="3852c-291">序号与识别区域性字符串操作</span><span class="sxs-lookup"><span data-stu-id="3852c-291">Ordinal vs. culture-sensitive string operations</span></span>](/dotnet/api/system.string#ordinal-vs-culture-sensitive-operations)
- [<span data-ttu-id="3852c-292">.NET 源代码分析概述</span><span class="sxs-lookup"><span data-stu-id="3852c-292">Overview of .NET source code analysis</span></span>](../../fundamentals/code-analysis/overview.md)
