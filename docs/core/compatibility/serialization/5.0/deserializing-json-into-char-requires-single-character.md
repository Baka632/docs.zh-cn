---
title: 中断性变更：Deserialize 需要单字符的字符串
description: 了解 .NET 5.0 中的以下中断性变更：JsonSerializer.Deserialize 需要单字符的字符串。
ms.date: 10/18/2020
ms.openlocfilehash: 780f2928d776ecb6db9a7fc05a720e889eb363e7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759275"
---
# <a name="jsonserializerdeserialize-requires-single-character-string"></a><span data-ttu-id="b566d-103">JsonSerializer.Deserialize 需要单字符的字符串</span><span class="sxs-lookup"><span data-stu-id="b566d-103">JsonSerializer.Deserialize requires single-character string</span></span>

<span data-ttu-id="b566d-104">如果类型参数是 <xref:System.Char>，<xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> 的字符串参数必须包含单个字符才能成功进行反序列化。</span><span class="sxs-lookup"><span data-stu-id="b566d-104">When the type parameter is <xref:System.Char>, the string argument to <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> must contain a single character for deserialization to succeed.</span></span>

## <a name="change-description"></a><span data-ttu-id="b566d-105">更改描述</span><span class="sxs-lookup"><span data-stu-id="b566d-105">Change description</span></span>

<span data-ttu-id="b566d-106">在以前的 .NET 版本中，如果将多字符字符串传递到 <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>，并且类型参数为 <xref:System.Char>，则反序列化会成功，并且仅反序列化第一个字符。</span><span class="sxs-lookup"><span data-stu-id="b566d-106">In previous .NET versions, if you pass a multi-character string to <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> and the type parameter is <xref:System.Char>, the deserialization succeeds and only the first character is deserialized.</span></span>

<span data-ttu-id="b566d-107">在 .NET 5.0 和更高版本中，如果类型参数为 <xref:System.Char>，传递除单字符字符串外的任何内容都会导致引发 <xref:System.Text.Json.JsonException>。</span><span class="sxs-lookup"><span data-stu-id="b566d-107">In .NET 5.0 and later, when the type parameter is <xref:System.Char>, passing anything other than a single-character string causes a <xref:System.Text.Json.JsonException> to be thrown.</span></span>

```csharp
// .NET Core 3.0 and 3.1: Returns the first character 'a'.
// .NET 5.0 and later: Throws JsonException because payload has more than one character.
JsonSerializer.Deserialize<char>("\"abc\"");

// Correct usage.
JsonSerializer.Deserialize<char>("\"a\"");
```

## <a name="version-introduced"></a><span data-ttu-id="b566d-108">引入的版本</span><span class="sxs-lookup"><span data-stu-id="b566d-108">Version introduced</span></span>

<span data-ttu-id="b566d-109">5.0</span><span class="sxs-lookup"><span data-stu-id="b566d-109">5.0</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="b566d-110">更改原因</span><span class="sxs-lookup"><span data-stu-id="b566d-110">Reason for change</span></span>

<span data-ttu-id="b566d-111"><xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> 将表示单个 JSON 值的文本分析为泛型类型参数指定的类型的实例。</span><span class="sxs-lookup"><span data-stu-id="b566d-111"><xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> parses text that represents a single JSON value into an instance of the type specified by the generic type parameter.</span></span> <span data-ttu-id="b566d-112">仅当提供的有效负载对指定的泛型类型参数有效时，分析才会成功。</span><span class="sxs-lookup"><span data-stu-id="b566d-112">Parsing should only succeed when the provided payload is valid for the specified generic type parameter.</span></span> <span data-ttu-id="b566d-113">对于 <xref:System.Char> 值类型，有效的负载是单字符字符串。</span><span class="sxs-lookup"><span data-stu-id="b566d-113">For a <xref:System.Char> value type, a valid payload is a single character string.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="b566d-114">建议的操作</span><span class="sxs-lookup"><span data-stu-id="b566d-114">Recommended action</span></span>

<span data-ttu-id="b566d-115">使用 <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> 将字符串分析为 <xref:System.Char> 类型时，请确保字符串包含单个字符。</span><span class="sxs-lookup"><span data-stu-id="b566d-115">When parsing a string into a <xref:System.Char> type using <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>, make sure the string consists of a single character.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="b566d-116">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="b566d-116">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Text.Json.JsonSerializer.Deserialize``1(System.String,System.Text.Json.JsonSerializerOptions)`

### Category

Serialization

-->
