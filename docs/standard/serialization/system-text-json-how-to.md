---
title: 如何使用 C# 对 JSON 进行序列化和反序列化 - .NET
description: 了解如何使用 System.Text.Json 命名空间在 .NET 中向/从 JSON 进行序列化和反序列化。 包含示例代码。
ms.date: 11/05/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: aba45a99562b67df17e1ff33ecc3c8bbad63ec30
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440811"
---
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a>如何在 .NET 中对 JSON 进行序列化和反序列化（封送和拆收）

本文演示如何使用 <xref:System.Text.Json?displayProperty=fullName> 命名空间向/从 JavaScript 对象表示法 (JSON) 进行序列化和反序列化。 如果要从 `Newtonsoft.Json` 移植现有代码，请参阅[如何迁移到 `System.Text.Json`](system-text-json-migrate-from-newtonsoft-how-to.md)。

方向和示例代码直接使用库，而不是通过框架（如 [ASP.NET Core](/aspnet/core/)）。

大多数序列化示例代码将 <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> 设置为 `true`，以 JSON 进行优质打印（包含缩进和空格，以提高可读性）。 对于生产用途，通常对于此设置会接受默认值 `false`。

代码示例引用下面的类及其变体：

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="namespaces"></a>命名空间

<xref:System.Text.Json> 命名空间包含所有入口点和主要类型。 <xref:System.Text.Json.Serialization> 命名空间包含用于高级方案的特性和 API，以及特定于序列化和反序列化的自定义。 本文中演示的代码示例要求将 `using` 指令用于其中一个或两个命名空间：

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

`System.Text.Json` 中不支持 <xref:System.Runtime.Serialization> 命名空间中的特性。

## <a name="how-to-write-net-objects-to-json-serialize"></a>如何将 .NET 对象编写为 JSON（序列化）

若要将 JSON 编写为字符串或文件，请调用 <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> 方法。

下面的示例将 JSON 创建为字符串：

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerialize)]

下面的示例使用同步代码创建 JSON 文件：

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFile.cs?name=SnippetSerialize)]

下面的示例使用异步代码创建 JSON 文件：

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs?name=SnippetSerialize)]

前面的示例对要序列化的类型使用类型推理。 `Serialize()` 的重载采用泛型类型参数：

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerializeWithGenericParameter)]

### <a name="serialization-example"></a>序列化示例

下面是一个包含集合类型属性和用户定义类型的示例类：

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPOCOs)]

> [!TIP]
> “POCO”代表[普通旧 CLR 对象](https://en.wikipedia.org/wiki/Plain_old_CLR_object)。 POCO 是一种 .NET 类型，它不通过继承或特性等依赖于任何框架特定类型。

序列化以上类型的实例的 JSON 输出类似于下面的示例。 默认情况下，JSON 输出会缩小：

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

下面的示例演示相同的 JSON，但进行了格式设置（即，具有空格和缩进的优质打印版本）：

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "TemperatureRanges": {
    "Cold": {
      "High": 20,
      "Low": -10
    },
    "Hot": {
      "High": 60,
      "Low": 20
    }
  },
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

### <a name="serialize-to-utf-8"></a>序列化为 UTF-8

若要序列化为 UTF-8，请调用 <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> 方法：

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetSerialize)]

还有一个采用 <xref:System.Text.Json.Utf8JsonWriter> 的 <xref:System.Text.Json.JsonSerializer.Serialize%2A> 重载可用。

序列化为 UTF-8 比使用基于字符串的方法大约快 5-10%。 出现这种差别的原因是字节（作为 UTF-8）不需要转换为字符串 (UTF-16)。

## <a name="serialization-behavior"></a>序列化行为
::: zone pivot="dotnet-5-0"

* 默认情况下，所有公共属性都会序列化。 可以[指定要忽略的属性](#ignore-properties)。
* [默认编码器](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default)会转义非 ASCII 字符、ASCII 范围内的 HTML 敏感字符以及根据 [RFC 8259 JSON 规范](https://tools.ietf.org/html/rfc8259#section-7)必须进行转义的字符。
* 默认情况下，JSON 会缩小。 可以[对 JSON 进行优质打印](#serialize-to-formatted-json)。
* 默认情况下，JSON 名称的大小写与 .NET 名称匹配。 可以[自定义 JSON 名称大小写](#customize-json-names-and-values)。
* 默认情况下，检测到循环引用并引发异常。 可以[保留引用并处理循环引用](#preserve-references-and-handle-circular-references)。
* 默认情况下忽略[字段](../../csharp/programming-guide/classes-and-structs/fields.md)。 可以[包含字段](#include-fields)。

当你在 ASP.NET Core 应用中间接使用 System.Text.Json 时，某些默认行为会有所不同。 有关详细信息，请参阅 [JsonSerializerOptions 的 Web 默认值](#web-defaults-for-jsonserializeroptions)。
::: zone-end

::: zone pivot="dotnet-core-3-1"

* 默认情况下，所有公共属性都会序列化。 可以[指定要忽略的属性](#ignore-properties)。
* [默认编码器](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default)会转义非 ASCII 字符、ASCII 范围内的 HTML 敏感字符以及根据 [RFC 8259 JSON 规范](https://tools.ietf.org/html/rfc8259#section-7)必须进行转义的字符。
* 默认情况下，JSON 会缩小。 可以[对 JSON 进行优质打印](#serialize-to-formatted-json)。
* 默认情况下，JSON 名称的大小写与 .NET 名称匹配。 可以[自定义 JSON 名称大小写](#customize-json-names-and-values)。
* 检测到循环引用并引发异常。
* 将忽略[字段](../../csharp/programming-guide/classes-and-structs/fields.md)。
::: zone-end

支持的类型包括：
::: zone pivot="dotnet-5-0"

* 映射到 JavaScript 基元的 .NET 基元，如数值类型、字符串和布尔。
* 用户定义的[普通旧 CLR 对象 (POCO)](https://en.wikipedia.org/wiki/Plain_old_CLR_object)。
* 一维和交错数组 (`T[][]`)。
* 以下命名空间中的集合和字典。
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>
  * <xref:System.Collections.Concurrent>
  * <xref:System.Collections.Specialized>
  * <xref:System.Collections.ObjectModel>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* 映射到 JavaScript 基元的 .NET 基元，如数值类型、字符串和布尔。
* 用户定义的[普通旧 CLR 对象 (POCO)](https://en.wikipedia.org/wiki/Plain_old_CLR_object)。
* 一维和交错数组 (`ArrayName[][]`)。
* `Dictionary<string,TValue>`其中 `TValue` 是 `object`、`JsonElement` 或 POCO。
* 以下命名空间中的集合。
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>
  * <xref:System.Collections.Concurrent>
  * <xref:System.Collections.Specialized>
  * <xref:System.Collections.ObjectModel>
::: zone-end

可以[实现自定义转换器](system-text-json-converters-how-to.md)以处理其他类型或提供内置转换器不支持的功能。

## <a name="how-to-read-json-into-net-objects-deserialize"></a>如何将 JSON 读入 .NET 对象（反序列化）

若要从字符串或文件进行反序列化，请调用 <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 方法。

下面的示例从字符串读取 JSON，并创建前面为[序列化示例](#serialization-example)显示的 `WeatherForecastWithPOCOs` 类的实例：

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetDeserialize)]

若要使用同步代码从文件进行反序列化，请将文件读入字符串中，如下面的示例中所示：

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFile.cs?name=SnippetDeserialize)]

若要使用异步代码从文件进行反序列化，请调用 <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> 方法：

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs?name=SnippetDeserialize)]

### <a name="deserialize-from-utf-8"></a>从 UTF-8 进行反序列化

若要从 UTF-8 进行反序列化，请调用采用 `Utf8JsonReader` 或 `ReadOnlySpan<byte>` 的 <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 重载，如下面的示例中所示。 这些示例假设 JSON 处于名为 jsonUtf8Bytes 的字节数组中。

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize1)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize2)]

## <a name="deserialization-behavior"></a>反序列化行为

对 JSON 进行反序列化时，以下行为适用：

::: zone pivot="dotnet-5-0"

* 默认情况下，属性名称匹配区分大小写。 可以[指定不区分大小写](#case-insensitive-property-matching)。
* 如果 JSON 包含只读属性的值，则会忽略该值，并且不引发异常。
* 序列化程序会忽略非公共构造函数。
* 支持反序列化为不可变对象或只读属性。 请参阅[不可变类型和记录](#immutable-types-and-records)。
* 默认情况下，支持将枚举作为数字。 可以[将枚举名称序列化为字符串](#enums-as-strings)。
* 默认情况下忽略字段。 可以[包含字段](#include-fields)。
* 默认情况下，JSON 中的注释或尾随逗号会引发异常。 可以[允许注释和尾随逗号](#allow-comments-and-trailing-commas)。
* [默认最大深度](xref:System.Text.Json.JsonReaderOptions.MaxDepth)为 64。

当你在 ASP.NET Core 应用中间接使用 System.Text.Json 时，某些默认行为会有所不同。 有关详细信息，请参阅 [JsonSerializerOptions 的 Web 默认值](#web-defaults-for-jsonserializeroptions)。
::: zone-end

::: zone pivot="dotnet-core-3-1"

* 默认情况下，属性名称匹配区分大小写。 可以[指定不区分大小写](#case-insensitive-property-matching)。 ASP.NET Core 应用[默认指定不区分大小写](#web-defaults-for-jsonserializeroptions)。
* 如果 JSON 包含只读属性的值，则会忽略该值，并且不引发异常。
* 无参数构造函数（可以是公共的、内部的或专用的）用于反序列化。
* 不支持反序列化为不可变对象或只读属性。
* 默认情况下，支持将枚举作为数字。 可以[将枚举名称序列化为字符串](#enums-as-strings)。
* 不支持字段。
* 默认情况下，JSON 中的注释或尾随逗号会引发异常。 可以[允许注释和尾随逗号](#allow-comments-and-trailing-commas)。
* [默认最大深度](xref:System.Text.Json.JsonReaderOptions.MaxDepth)为 64。

当你在 ASP.NET Core 应用中间接使用 System.Text.Json 时，某些默认行为会有所不同。 有关详细信息，请参阅 [JsonSerializerOptions 的 Web 默认值](#web-defaults-for-jsonserializeroptions)。
::: zone-end

可以[实现自定义转换器](system-text-json-converters-how-to.md)以提供内置转换器不支持的功能。

## <a name="serialize-to-formatted-json"></a>序列化为格式化 JSON

若要对 JSON 输出进行优质打印，请将 <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> 设置为 `true`：

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerializePrettyPrint)]

下面是一个要进行序列化的示例类型，以及进行了优质打印的 JSON 输出：

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="include-fields"></a>包含字段

::: zone pivot="dotnet-5-0"
在序列化或反序列化时，使用 <xref:System.Text.Json.JsonSerializerOptions.IncludeFields?displayProperty=nameWithType> 全局设置或 [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute) 特性来包含字段，如以下示例中所示：

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Fields.cs" highlight="15,17,19,31":::

若要忽略只读字段，请使用 <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType> 全局设置。
::: zone-end

::: zone pivot="dotnet-core-3-1"
.NET Core 3.1 的 System.Text.Json 中不支持字段。 [自定义转换器](system-text-json-converters-how-to.md)可提供此功能。
::: zone-end

## <a name="customize-json-names-and-values"></a>自定义 JSON 名称和值

默认情况下，属性名称和字典键在 JSON 输出中保持不变，包括大小写。 枚举值表示为数字。 本部分介绍如何：

* [自定义单个属性名称](#customize-individual-property-names)
* [将所有属性名称转换为 camel 大小写](#use-camel-case-for-all-json-property-names)
* [实现自定义属性命名策略](#use-a-custom-json-property-naming-policy)
* [将字典键转换为 camel 大小写](#camel-case-dictionary-keys)
* [将枚举转换为字符串和 camel 大小写](#enums-as-strings)

对于需要对 JSON 属性名称和值进行特殊处理的其他方案，可以[实现自定义转换器](system-text-json-converters-how-to.md)。

### <a name="customize-individual-property-names"></a>自定义单个属性名称

若要设置单个属性的名称，请使用 [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) 特性。

下面是要进行序列化的示例类型和生成的 JSON：

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

此特性设置的属性名称：

* 同时适用于两个方向（序列化和反序列化）。
* 优先于属性命名策略。

### <a name="use-camel-case-for-all-json-property-names"></a>对所有 JSON 属性名称使用 camel 大小写

若要对所有 JSON 属性名称使用 camel 大小写，请将 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> 设置为 `JsonNamingPolicy.CamelCase`，如下面的示例中所示：

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundTripCamelCasePropertyNames.cs?name=Serialize)]

下面是要进行序列化的示例类和 JSON 输出：

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

camel 大小写属性命名策略：

* 适用于序列化和反序列化。
* 由 `[JsonPropertyName]` 特性替代。 这便是示例中的 JSON 属性名称 `Wind` 不是 camel 大小写的原因。

### <a name="use-a-custom-json-property-naming-policy"></a>使用自定义 JSON 属性命名策略

若要使用自定义 JSON 属性命名策略，请创建派生自 <xref:System.Text.Json.JsonNamingPolicy> 的类，并替代 <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> 方法，如下面的示例中所示：

[!code-csharp[](snippets/system-text-json-how-to/csharp/UpperCaseNamingPolicy.cs)]

然后，将 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> 属性设置为命名策略类的实例：

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripPropertyNamingPolicy.cs?name=SnippetSerialize)]

下面是要进行序列化的示例类和 JSON 输出：

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

JSON 属性命名策略：

* 适用于序列化和反序列化。
* 由 `[JsonPropertyName]` 特性替代。 这便是示例中的 JSON 属性名称 `Wind` 不是大写的原因。

### <a name="camel-case-dictionary-keys"></a>Camel 大小写字典键

如果要序列化的对象的属性为 `Dictionary<string,TValue>` 类型，则 `string` 键可转换为 camel 大小写。 为此，请将 <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> 设置为 `JsonNamingPolicy.CamelCase`，如下面的示例中所示：

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCamelCaseDictionaryKeys.cs?name=SnippetSerialize)]

使用名为 `TemperatureRanges` 且具有键值对 `"ColdMinTemp", 20` 和 `"HotMinTemp", 40` 的字典序列化对象会产生类似于以下示例的 JSON 输出：

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "coldMinTemp": 20,
    "hotMinTemp": 40
  }
}
```

字典键的 camel 大小写命名策略仅适用于序列化。 如果对字典进行反序列化，即使为 `DictionaryKeyPolicy`指定 `JsonNamingPolicy.CamelCase`，键也会与 JSON 文件匹配。

### <a name="enums-as-strings"></a>作为字符串的枚举

默认情况下，枚举会序列化为数字。 若要将枚举名称序列化为字符串，请使用 <xref:System.Text.Json.Serialization.JsonStringEnumConverter>。

例如，假设需要序列化以下具有枚举的类：

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithEnum)]

如果 Summary 为 `Hot`，则默认情况下序列化的 JSON 具有数值 3：

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

下面的示例代码序列化枚举名称(而不是数值)，并将名称转换为 camel 大小写：

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs?name=SnippetSerialize)]

生成的 JSON 类似于以下示例：

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

还可以反序列化枚举字符串名称，如以下示例中所示：

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs?name=SnippetDeserialize)]

## <a name="ignore-properties"></a>忽略属性

默认情况下，所有公共属性都会序列化。 如果不想让某些属性出现在 JSON 输出中，则有几个选项可用。 本部分介绍如何忽略：

::: zone pivot="dotnet-5-0"

* [单个属性](#ignore-individual-properties)
* [所有只读属性](#ignore-all-read-only-properties)
* [所有 null 值属性](#ignore-all-null-value-properties)
* [所有默认值属性](#ignore-all-default-value-properties)
::: zone-end

::: zone pivot="dotnet-core-3-1"

* [单个属性](#ignore-individual-properties)
* [所有只读属性](#ignore-all-read-only-properties)
* [所有 null 值属性](#ignore-all-null-value-properties)
::: zone-end

### <a name="ignore-individual-properties"></a>忽略单个属性

若要忽略单个属性，请使用 [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) 特性。

下面是要进行序列化的示例类型和 JSON 输出：

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithIgnoreAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

::: zone pivot="dotnet-5-0"
可以通过设置 [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) 特性的 `Condition` 属性来指定条件排除。 <xref:System.Text.Json.Serialization.JsonIgnoreCondition> 枚举提供下列选项：

* `Always` - 始终忽略属性。 如果未指定 `Condition`，则假设此选项。
* `Never` - 无论 `DefaultIgnoreCondition`、`IgnoreReadOnlyProperties` 和 `IgnoreReadOnlyFields` 全局设置如何，始终序列化和反序列化属性。
* `WhenWritingDefault` - 如果属性是引用类型 `null` 或值类型 `default`，则在序列化中忽略属性。
* `WhenWritingNull` - 如果属性是引用类型 `null`，则在序列化中忽略属性。

下面的示例说明 [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) 特性的 `Condition` 属性的用法：

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/JsonIgnoreAttributeExample.cs" highlight="10,13,16":::
::: zone-end

### <a name="ignore-all-read-only-properties"></a>忽略所有只读属性

如果属性包含公共 getter 而不是公共 setter，则属性为只读。 若要在序列化时忽略所有只读属性，请将 <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> 设置为 `true`，如以下示例中所示：

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeExcludeReadOnlyProperties.cs?name=SnippetSerialize)]

下面是要进行序列化的示例类型和 JSON 输出：

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithROProperty)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

此选项仅适用于序列化。 在反序列化过程中，默认情况下会忽略只读属性。

::: zone pivot="dotnet-5-0"
此选项仅适用于属性。 若要在[序列化字段](#include-fields)时忽略只读字段，请使用 <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType> 全局设置。
::: zone-end

### <a name="ignore-all-null-value-properties"></a>忽略所有 null 值属性

::: zone pivot="dotnet-5-0"
若要忽略所有 null 值属性，请将 <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> 属性设置为 <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingNull>，如以下示例中所示：

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/IgnoreNullOnSerialize.cs" highlight="28":::

::: zone-end

::: zone pivot="dotnet-core-3-1"
若要在序列化时忽略所有 null 值属性，请将 <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> 属性设置为 `true`，如以下示例中所示：

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeExcludeNullValueProperties.cs?name=SnippetSerialize)]

下面是要进行序列化的示例对象和 JSON 输出：

|Property |“值”  |
|---------|---------|
| 日期    | 8/1/2019 12:00:00 AM -07:00|
| TemperatureCelsius| 25 |
| 总结| null|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

::: zone-end

### <a name="ignore-all-default-value-properties"></a>忽略所有默认值属性

::: zone pivot="dotnet-5-0"
若要防止对值类型属性中的默认值进行序列化，请将 <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> 属性设置为 <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingDefault>，如以下示例中所示：

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/IgnoreValueDefaultOnSerialize.cs" highlight="28":::
::: zone-end

`WhenWritingDefault` 设置还会阻止对 null 值引用类型属性进行序列化。

::: zone pivot="dotnet-core-3-1"
在 .NET Core 3.1 的 System.Text.Json 中，无内置方式来阻止对值类型为默认值的属性进行序列化。
::: zone-end

## <a name="customize-character-encoding"></a>自定义字符编码

默认情况下，序列化程序会转义所有非 ASCII 字符。  即，会将它们替换为 `\uxxxx`，其中 `xxxx` 为字符的 Unicode 代码。  例如，如果 `Summary` 属性设置为西里尔文 жарко，则 `WeatherForecast` 对象会进行序列化，如以下示例中所示：

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a>序列化语言字符集

若要序列化一种或多种语言的字符集而不进行转义，请在创建 <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName> 的实例时指定 [Unicode 范围](xref:System.Text.Unicode.UnicodeRanges)，如以下示例中所示：

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetLanguageSets)]

此代码不转义西里尔文或希腊语字符。 如果 `Summary` 属性设置为西里尔文 жарко，则 `WeatherForecast` 对象会进行序列化，如以下示例中所示：

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

若要序列化所有语言集而不进行转义，请使用 <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>。

### <a name="serialize-specific-characters"></a>序列化特定字符

一种替代方法是指定要允许的单个字符，而不进行转义。 下面的示例仅序列化 жарко 的前两个字符：

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetSelectedCharacters)]

下面是前面代码生成的 JSON 的示例：

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a>序列化所有字符

若要最大程度地减少转义，可以使用 <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>，如以下示例中所示：

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUnsafeRelaxed)]

> [!CAUTION]
> 与默认编码器相比，`UnsafeRelaxedJsonEscaping` 编码器在允许字符通过而不进行转义方面更加宽松：
>
> * 它不转义 HTML 敏感字符，如 `<`、`>`、`&` 和 `'`。
> * 它不提供任何针对 XSS 或信息泄露攻击（如客户端和服务器在字符集方面不一致所可能导致的攻击）的额外深度防御保护。
>
> 仅当知道客户端将生成的有效负载解释为 UTF-8 编码的 JSON 时，才使用不安全编码器。 例如，如果服务器在发送响应标头 `Content-Type: application/json; charset=utf-8`，则可以使用它。 永远不允许将原始 `UnsafeRelaxedJsonEscaping` 输出发出到 HTML 页面或 `<script>` 元素。

## <a name="serialize-properties-of-derived-classes"></a>序列化派生类的属性

不支持多态类型层次结构的序列化。 例如，如果属性定义为接口或抽象类，则即使运行时类型具有其他属性，也只会序列化对接口或抽象类定义的属性。 此部分中介绍了此行为的例外情况。

例如，假设有一个 `WeatherForecast` 类和一个派生类 `WeatherForecastDerived`：

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFDerived)]

并且假设 `Serialize` 方法的类型参数在编译时为 `WeatherForecast`：

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeDefault)]

在这种情况下，即使 `weatherForecast` 对象实际上是 `WeatherForecastDerived` 对象，也不会序列化 `WindSpeed` 属性。 仅序列化基类属性：

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

此行为旨在帮助防止在运行时创建的派生类型中发生意外数据泄露。

若要序列化前面示例中派生类型的属性，请使用以下方法之一：

* 调用 <xref:System.Text.Json.JsonSerializer.Serialize%2A> 的重载，以便在运行时指定类型：

  [!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeGetType)]

* 将要序列化的对象声明为 `object`。

  [!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeObject)]

在前面的示例方案中，这两种方法都会使 `WindSpeed` 属性包含在 JSON 输出中：

```json
{
  "WindSpeed": 35,
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

> [!IMPORTANT]
> 这些方法只为要序列化的根对象提供多态序列化，而不为该根对象的属性提供。

如果将较低级别的对象定义为类型 `object`，则可以对它们进行多态序列化。 例如，假设 `WeatherForecast` 类具有一个名为 `PreviousForecast` 的属性，该属性可以定义为类型 `WeatherForecast` 或 `object`：

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPrevious)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPreviousAsObject)]

如果 `PreviousForecast` 属性包含 `WeatherForecastDerived` 的实例：

* 序列化 `WeatherForecastWithPrevious` 的 JSON 输出不包含 `WindSpeed`。
* 序列化 `WeatherForecastWithPreviousAsObject` 的 JSON 输出包含 `WindSpeed`。

若要序列化 `WeatherForecastWithPreviousAsObject`，无需调用 `Serialize<object>` 或 `GetType`，因为根对象不是可能属于派生类型的对象。 下面的代码示例不调用 `Serialize<object>` 或 `GetType`：

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeSecondLevel)]

前面的代码会正确地序列化 `WeatherForecastWithPreviousAsObject`：

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "PreviousForecast": {
    "WindSpeed": 35,
    "Date": "2019-08-01T00:00:00-07:00",
    "TemperatureCelsius": 25,
    "Summary": "Hot"
  }
}
```

将属性定义为 `object` 的相同方法适用于接口。 假设具有以下接口和实现，并且要使用包含实现实例的属性序列化类：

[!code-csharp[](snippets/system-text-json-how-to/csharp/IForecast.cs)]

序列化 `Forecasts` 的实例时，只有 `Tuesday` 显示 `WindSpeed` 属性，因为 `Tuesday` 定义为 `object`：

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeInterface)]

下面的示例显示前面代码生成的 JSON：

```json
{
  "Monday": {
    "Date": "2020-01-06T00:00:00-08:00",
    "TemperatureCelsius": 10,
    "Summary": "Cool"
  },
  "Tuesday": {
    "Date": "2020-01-07T00:00:00-08:00",
    "TemperatureCelsius": 11,
    "Summary": "Rainy",
    "WindSpeed": 10
  }
}
```

有关多态序列化的详细信息，以及有关反序列化的信息，请参阅[如何从 Newtonsoft.Json 迁移到 System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization)。

## <a name="allow-comments-and-trailing-commas"></a>允许注释和尾随逗号

默认情况下，JSON 中不允许使用注释和尾随逗号。 若要在 JSON 中允许注释，请将 <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> 属性设置为 `JsonCommentHandling.Skip`。
若要允许尾随逗号，请将 <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> 属性设置为 `true`。 下面的示例演示如何允许这两者：

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeCommasComments.cs?name=SnippetDeserialize)]

下面是包含注释和尾随逗号的示例 JSON：

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a>不区分大小写的属性匹配

默认情况下，反序列化会查找 JSON 与目标对象属性之间区分大小写的属性名称匹配。 若要更改该行为，请将 <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> 设置为 `true`：

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeCaseInsensitive.cs?name=SnippetDeserialize)]

下面是具有 camel 大小写属性名称的示例 JSON。 它可以反序列化为具有帕斯卡拼写法属性名称的以下类型。

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="handle-overflow-json"></a>处理溢出 JSON

反序列化时，可能会在 JSON 中收到不是由目标类型的属性表示的数据。 例如，假设目标类型如下：

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

要反序列化的 JSON 如下：

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

如果将显示的 JSON 反序列化为显示的类型，则 `DatesAvailable` 和 `SummaryWords` 属性无处可去，会丢失。 若要捕获额外数据（如这些属性），请将 [[JsonExtensionData]](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) 特性应用于类型 `Dictionary<string,object>` 或 `Dictionary<string,JsonElement>` 的属性：

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithExtensionData)]

将前面显示的 JSON 反序列化为此示例类型时，额外数据会成为 `ExtensionData` 属性的键值对：

|Property |值  |说明  |
|---------|---------|---------|
| 日期    | 8/1/2019 12:00:00 AM -07:00||
| TemperatureCelsius| 0 | 区分大小写的不匹配（JSON 中的 `temperatureCelsius`），因此未设置属性。 |
| 总结 | 热 ||
| ExtensionData | temperatureCelsius：25 |因为大小写不匹配，所以此 JSON 属性是额外属性，会成为字典中的键值对。|
|| DatesAvailable：<br>  8/1/2019 12:00:00 AM -07:00<br>8/2/2019 12:00:00 AM -07:00 |JSON 中的额外属性会成为键值对，将数组作为值对象。|
| |SummaryWords：<br>酷<br>Windy<br>Humid |JSON 中的额外属性会成为键值对，将数组作为值对象。|

序列化目标对象时，扩展数据键值对会成为 JSON 属性，就如同它们处于传入 JSON 中一样：

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 0,
  "Summary": "Hot",
  "temperatureCelsius": 25,
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

请注意，`ExtensionData` 属性名称不会出现在 JSON 中。 此行为使 JSON 可以进行往返，而不会丢失任何不会以其他方式进行反序列化的额外数据。

## <a name="preserve-references-and-handle-circular-references"></a>保留引用并处理循环引用

::: zone pivot="dotnet-5-0"

若要保留引用并处理循环引用，请将 <xref:System.Text.Json.JsonSerializerOptions.ReferenceHandler%2A> 设置为 <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A>。 此设置会导致以下行为：

* 在序列化时：

  编写复杂类型时，序列化程序还会写入元数据属性（`$id`、`$values` 和 `$ref`）。

* 在反序列化时：

  需要元数据（虽然不是必需的），并且反序列化程序会尝试理解它。

下面的代码演示 `Preserve` 属性的用法。

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/PreserveReferences.cs" highlight="34":::

此功能不能用于保留值类型或不可变类型。 在反序列化时，将在读取整个有效负载后创建不可变类型的实例。 因此，如果对同一实例的引用出现在 JSON 有效负载中，则无法对其进行反序列化。

对于值类型、不可变类型和数组，不会序列化任何引用元数据。 反序列化时，如果发现 `$ref` 或 `$id`，则会引发异常。 但是，值类型忽略 `$id`（对于集合，则为 `$values`），以便可以反序列化使用 Newtonsoft.Json 序列化的有效负载。  Newtonsoft.Json 为此类类型序列化元数据。

为了确定对象是否相等，System.Text.Json 在比较两个对象实例时使用引用相等性 (<xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=nameWithType>) 而不是值相等性 (<xref:System.Object.Equals(System.Object)?displayProperty=nameWithType> 的 <xref:System.Collections.Generic.ReferenceEqualityComparer.Instance%2A?displayProperty=nameWithType>。

有关如何序列化和反序列化引用的详细信息，请参阅 <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A?displayProperty=nameWithType>。

<xref:System.Text.Json.Serialization.ReferenceResolver> 类定义在序列化和反序列化过程中保留引用的行为。 创建派生类以指定自定义行为。 有关示例，请参阅 [GuidReferenceResolver](https://github.com/dotnet/docs/blob/9d5e88edbd7f12be463775ffebbf07ac8415fe18/docs/standard/serialization/snippets/system-text-json-how-to-5-0/csharp/GuidReferenceResolverExample.cs)。

::: zone-end

::: zone pivot="dotnet-core-3-1"
.NET Core 3.1 中的 System.Text.Json 仅支持按值进行进行序列化，并对循环引用引发异常。
::: zone-end

## <a name="allow-or-write-numbers-in-quotes"></a>允许或写入带引号的数字

::: zone pivot="dotnet-5-0"

某些序列化程序将数字编码为 JSON 字符串（括在引号中）。 例如，`{"DegreesCelsius":"23"}` 而非 `{"DegreesCelsius":23}`。 若要在整个输入对象图中序列化带引号的数字或接受带引号的数字，请设置 <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A?displayProperty=nameWithType>，如以下示例中所示：

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/QuotedNumbers.cs" highlight="27-28":::

在通过 ASP.NET Core 间接使用 System.Text.Json 时，反序列化时允许使用带引号的数字，因为 ASP.NET Core 指定 [Web 默认选项](xref:System.Text.Json.JsonSerializerDefaults.Web)。

若要允许或写入特定属性、字段或类型的带引号的数字，请使用 [[JsonNumberHandling]](xref:System.Text.Json.Serialization.JsonNumberHandlingAttribute) 特性。
::: zone-end

::: zone pivot="dotnet-core-3-1"
.NET Core 3.1 中的 System.Text.Json 不支持序列化或反序列化用引号引起来的数字。 有关详细信息，请参阅[允许或写入带引号的数字](system-text-json-migrate-from-newtonsoft-how-to.md#allow-or-write-numbers-in-quotes)。
::: zone-end

## <a name="immutable-types-and-records"></a>不可变类型和记录

::: zone pivot="dotnet-5-0"
System.Text.Json 可以使用参数化构造函数，这可以反序列化不可变的类或结构。 对于类，如果唯一构造函数是参数化的构造函数，则将使用该构造函数。 对于结构或包含多个构造函数的类，通过应用 [[JsonConstructor]](xref:System.Text.Json.Serialization.JsonConstructorAttribute.%23ctor%2A) 特性来指定要使用的构造函数。 如果未使用该特性，则始终使用公共无参数构造函数（如果存在）。 该特性只能与公共构造函数一起使用。 以下示例使用 `[JsonConstructor]` 特性：

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/ImmutableTypes.cs" highlight="13":::

还支持 C# 9 记录，如以下示例中所示：

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Records.cs":::

对于因其所有属性资源库都是非公共的而不可变的类型，请参阅以下部分，了解[非公共属性访问器](#non-public-property-accessors)。
::: zone-end

::: zone pivot="dotnet-core-3-1"
.NET Core 3.1 不支持 `JsonConstructorAttribute` 和 C# 9 记录。
::: zone-end

## <a name="non-public-property-accessors"></a>非公共属性访问器

::: zone pivot="dotnet-5-0"
若要允许使用非公共属性访问器，请使用 [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute) 特性，如以下示例中所示：

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/NonPublicAccessors.cs" highlight="12,15":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
.NET Core 3.1 不支持非公共属性访问器。 有关详细信息，请参阅[从 Newtonsoft.Json 迁移一文](system-text-json-migrate-from-newtonsoft-how-to.md#non-public-property-setters-and-getters)。
::: zone-end

## <a name="copy-jsonserializeroptions"></a>复制 JsonSerializerOptions

::: zone pivot="dotnet-5-0"
存在 [JsonSerializerOptions constructor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerOptions)) ，可让你使用与现有实例相同的选项来创建新的实例，如以下示例中所示：

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/CopyOptions.cs" highlight="29":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
使用现有实例的 `JsonSerializerOptions` 构造函数在 .NET Core 3.1 中不可用。
::: zone-end

## <a name="web-defaults-for-jsonserializeroptions"></a>JsonSerializerOptions 的 Web 默认值

::: zone pivot="dotnet-5-0"
下面是具有 Web 应用不同默认值的选项：

* <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref:System.Text.Json.JsonNamingPolicy> = <xref:System.Text.Json.JsonNamingPolicy.CamelCase>
* <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A> = <xref:System.Text.Json.Serialization.JsonNumberHandling.AllowReadingFromString>

存在 [JsonSerializerOptions constructor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerDefaults)?view=net-5.0&preserve-view=true)，可让你通过 ASP.NET Core 对 Web 应用使用的默认选项创建新的实例，如以下示例中所示：

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/OptionsDefaults.cs" highlight="24":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
下面是具有 Web 应用不同默认值的选项：

* <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref:System.Text.Json.JsonNamingPolicy> = <xref:System.Text.Json.JsonNamingPolicy.CamelCase>

指定一组默认值的 `JsonSerializerOptions` 构造函数在 .NET Core 3.1 中不可用。
::: zone-end

## <a name="httpclient-and-httpcontent-extension-methods"></a>HttpClient 和 HttpContent 扩展方法

::: zone pivot="dotnet-5-0"

序列化和反序列化来自网络的 JSON 有效负载是常见的操作。 [HttpClient](xref:System.Net.Http.Json.HttpClientJsonExtensions) 和 [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions) 上的扩展方法允许在单个代码行中执行这些操作。 这些扩展方法使用 [JsonSerializerOptions 的 Web 默认值](#web-defaults-for-jsonserializeroptions)。

以下示例说明了 <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> 和 <xref:System.Net.Http.Json.HttpClientJsonExtensions.PostAsJsonAsync%2A?displayProperty=nameWithType> 的用法：

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/HttpClientExtensionMethods.cs" highlight="23,30":::

此外还有 [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions) 上的 System.Text.Json 的扩展方法。
::: zone-end

::: zone pivot="dotnet-core-3-1"
`HttpClient` 和 `HttpContent` 上的扩展方法在 .NET Core 3.1 的 System.Text.Json 中不可用。
::: zone-end

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a>Utf8JsonReader、Utf8JsonWriter 和 JsonDocument

<xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> 是面向 UTF-8 编码 JSON 文本的一个高性能、低分配的只进读取器，从 `ReadOnlySpan<byte>` 或 `ReadOnlySequence<byte>` 读取信息。 `Utf8JsonReader` 是一种低级类型，可用于生成自定义分析器和反序列化程序。 <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 方法在后台使用 `Utf8JsonReader`。

<xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> 是一种高性能方式，从常见 .NET 类型（例如，`String`、`Int32` 和 `DateTime`）编写 UTF-8 编码的 JSON 文本。 该编写器是一种低级类型，可用于生成自定义序列化程序。 <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> 方法在后台使用 `Utf8JsonWriter`。

<xref:System.Text.Json.JsonDocument?displayProperty=fullName> 提供使用 `Utf8JsonReader` 生成只读文档对象模型 (DOM) 的功能。 DOM 提供对 JSON 有效负载中的数据的随机访问。 可以通过 <xref:System.Text.Json.JsonElement> 类型访问构成有效负载的 JSON 元素。 `JsonElement` 类型提供数组和对象枚举器，以及用于将 JSON 文本转换为常见 .NET 类型的 API。 `JsonDocument` 公开了 <xref:System.Text.Json.JsonDocument.RootElement> 属性。

以下部分演示如何使用这些工具读取和写入 JSON。

## <a name="use-jsondocument-for-access-to-data"></a>使用 JsonDocument 访问数据

下面的示例演示如何使用 <xref:System.Text.Json.JsonDocument> 类来随机访问 JSON 字符串中的数据：

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades1)]

前面的代码：

* 假设要分析的 JSON 处于名为 `jsonString` 的字符串中。
* 对 `Students` 数组中具有 `Grade` 属性的对象计算平均成绩。
* 为没有成绩的学生分配默认成绩 70。
* 通过在每次迭代时使 `count` 变量递增来对学生进行计数。 一种替代方法是调用 <xref:System.Text.Json.JsonElement.GetArrayLength%2A>，如以下示例中所示：

  [!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades2)]

下面是此代码处理的 JSON 示例：

[!code-json[](snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json)]

## <a name="use-jsondocument-to-write-json"></a>使用 JsonDocument 写入 JSON

下面的示例演示如何通过 <xref:System.Text.Json.JsonDocument> 写入 JSON：

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentWriteJson.cs?name=SnippetSerialize)]

前面的代码：

* 读取 JSON 文件，将数据加载到 `JsonDocument` 中，并将格式化（进行了优质打印的）JSON 写入文件。
* 使用 <xref:System.Text.Json.JsonDocumentOptions> 可指定允许但会忽略输入 JSON 中的注释。
* 完成后，对编写器调用 <xref:System.Text.Json.Utf8JsonWriter.Flush%2A>。 一种替代方法是让编写器在释放时自动刷新。

下面是要由示例代码处理的 JSON 输入的示例：

[!code-json[](snippets/system-text-json-how-to/csharp/Grades.json)]

结果是以下进行了优质打印的 JSON 输出：

[!code-json[](snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json)]

## <a name="use-utf8jsonwriter"></a>使用 Utf8JsonWriter

下面的示例演示如何使用 <xref:System.Text.Json.Utf8JsonWriter> 类：

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8WriterToStream.cs?name=SnippetSerialize)]

## <a name="use-utf8jsonreader"></a>使用 Utf8JsonReader

下面的示例演示如何使用 <xref:System.Text.Json.Utf8JsonReader> 类：

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderFromBytes.cs?name=SnippetDeserialize)]

前面的代码假设 `jsonUtf8` 变量是包含有效 JSON（编码为 UTF-8）的字节数组。

### <a name="filter-data-using-utf8jsonreader"></a>使用 Utf8JsonReader 筛选数据

下面的示例演示如何同步读取文件并搜索值。

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderFromFile.cs)]

（[此示例的异步版本](https://github.com/dotnet/samples/blob/18e31a5f1abd4f347bf96bfdc3e40e2cfb36e319/core/json/Program.cs)可用。）

前面的代码：

* 假设 JSON 包含一个对象数组，并且每个对象都可能包含一个字符串类型的“name”属性。
* 对对象以及以“University”结尾的属性值进行计数。
* 假设文件编码为 UTF-16，并将它转码为 UTF-8。 可以使用以下代码，将编码为 UTF-8 的文件直接读入 `ReadOnlySpan<byte>`：

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName);
  ```

  如果文件包含 UTF-8 字节顺序标记 (BOM)，请在将字节传递给 `Utf8JsonReader` 之前将它删除，因为读取器需要文本。 否则，BOM 被视为无效 JSON，读取器将引发异常。

下面是前面的代码可以读取的 JSON 示例。 生成的摘要消息为“2 out of 4 have names that end with 'University'”：

[!code-json[](snippets/system-text-json-how-to/csharp/Universities.json)]

### <a name="read-from-a-stream-using-utf8jsonreader"></a>使用 Utf8JsonReader 从流中读取

当读取大型文件（例如，1 GB 或更大的文件）时，你可能希望避免一次性将整个文件加载到内存中。 此时，可以使用 <xref:System.IO.FileStream>。

使用 `Utf8JsonReader` 从流中读取时，适用以下规则：

* 包含部分 JSON 有效负载的缓冲区必须至少与其中的最大 JSON 令牌一样大，以便读取器可以推进进度。
* 缓冲区的大小必须至少与 JSON 中的最大空格序列一样大。
* 读取器不会跟踪已读取的数据，直到它完全读取 JSON 有效负载中的下一个 <xref:System.Text.Json.Utf8JsonReader.TokenType%2A>。 因此，当缓冲区中有剩余字节时，必须再次将它们传递给读取器。 你可以使用 <xref:System.Text.Json.Utf8JsonReader.BytesConsumed%2A> 来确定剩余的字节数。

下面的代码演示了如何从流中读取。 本示例显示了 <xref:System.IO.MemoryStream>。 类似的代码将使用 <xref:System.IO.FileStream>，当 `FileStream` 在开头包含 UTF-8 BOM 时除外。 在这种情况下，需要先从缓冲区中去除这三个字节，然后再将剩余字节传递到 `Utf8JsonReader`。 否则，读取器将引发异常，因为 BOM 不被视为 JSON 的有效部分。

示例代码从 4 KB 缓冲区开始，每当发现大小不足以容纳完整的 JSON 令牌（必须容纳完整的令牌，读取器才能推动处理 JSON 有效负载）时，就会使缓冲区大小成倍增加。 仅当设置的初始缓冲区非常小（例如 10 个字节）时，代码片段中提供的 JSON 示例才会触发缓冲区大小增加。 如果将初始缓冲区大小设置为 10，则 `Console.WriteLine` 语句会说明缓冲区大小增加的原因和影响。 在初始缓冲区大小为 4KB 时，每个 `Console.WriteLine` 都会显示整个示例 JSON，并且不必增加缓冲区大小。

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderPartialRead.cs)]

前面的示例未对缓冲区大小的增长设置任何限制。 如果令牌大小太大，则代码可能会失败，并出现 <xref:System.OutOfMemoryException> 异常。 如果 JSON 包含大小约为 1 GB 或更大的令牌，则会发生这种情况，因为将 1 GB 大小加倍会导致令牌太大，无法放入 `int32` 缓冲区。

## <a name="additional-resources"></a>其他资源

* [System.Text.Json 概述](system-text-json-overview.md)
* [如何编写自定义转换器](system-text-json-converters-how-to.md)
* [如何从 Newtonsoft.Json 迁移](system-text-json-migrate-from-newtonsoft-how-to.md)
* [System.Text.Json 中的 DateTime 和 DateTimeOffset 支持](../datetime/system-text-json-support.md)
* [System.Text.Json API 参考](xref:System.Text.Json)
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
