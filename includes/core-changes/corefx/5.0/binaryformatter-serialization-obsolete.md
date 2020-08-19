---
ms.openlocfilehash: 7cb146d19486618a4cee9976abe2220ea4b72790
ms.sourcegitcommit: d337df55f83325918cbbd095eb573400bea49064
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2020
ms.locfileid: "88203925"
---
### <a name="binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps"></a>BinaryFormatter 序列化方法已过时，并且已在 ASP.NET 应用中禁用

<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>、<xref:System.Runtime.Serialization.Formatter>和 <xref:System.Runtime.Serialization.IFormatter> 上的 `Serialize` 和 `Deserialize` 方法现已过时。 此外，ASP.NET 应用默认情况下禁止 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 序列化。

#### <a name="change-description"></a>更改描述

由于 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 存在[安全漏洞](../../../../docs/standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities)，因此，以下方法现已过时。 此外，在 ASP.NET Core 5.0 及更高版本的应用中，除非 Web 应用已重新启用 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 功能，否则它们会引发 <xref:System.NotSupportedException>。

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>

在 .NET 生态系统中逐步停用 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 的过程中，这些方法被标记为“过时”。

以下序列化方法现在也已过时，但没有行为变更：

- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>

#### <a name="version-introduced"></a>引入的版本

5.0 预览版 8

#### <a name="recommended-action"></a>建议操作

- 停止在代码中使用 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>。 此时，考虑使用 <xref:System.Text.Json.JsonSerializer> 或 <xref:System.Xml.Serialization.XmlSerializer>。 有关详细信息，请参阅 [BinaryFormatter 安全指南](../../../../docs/standard/serialization/binaryformatter-security-guide.md)。

- 可以暂时取消 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 编译时警告 `SYSLIB0011`。 建议在选择此选项之前，全面评估代码风险。 取消警告的最简单方法是用 `#pragma` 指令将单个调用站点括起来。

  ```csharp
  // Now read the purchase order back from disk
  using (var readStream = new FileStream("myfile.bin", FileMode.Open))
  {
      var formatter = new BinaryFormatter();
  #pragma warning disable SYSLIB0011
      return (PurchaseOrder)formatter.Deserialize(readStream);
  #pragma warning restore SYSLIB0011
  }
  ```

  另外，还可以在项目文件中取消警告。

  ```xml
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Disable "BinaryFormatter is obsolete" warnings for entire project -->
    <NoWarn>$(NoWarn);SYSLIB0011</NoWarn>
  </PropertyGroup>
  ```

  如果在项目文件中取消警告，会取消项目中所有代码文件的警告。 取消 SYSLIB0011 不会取消因使用其他过时 API 导致的警告。

- 若要继续在 ASP.NET 应用中使用 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>，可以在项目文件中重新启用它。 不过，非常不建议这样做。 有关详细信息，请参阅 [BinaryFormatter 安全指南](../../../../docs/standard/serialization/binaryformatter-security-guide.md)。

  ```xml
  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Warning: Setting the following switch is *NOT* recommended in web apps. -->
    <EnableUnsafeBinaryFormatterSerialization>true</EnableUnsafeBinaryFormatterSerialization>
  </PropertyGroup>
  ```

若要详细了解建议的操作，请参阅[修复 BinaryFormatter 过时和禁用错误](https://aka.ms/binaryformatter)。

#### <a name="category"></a>类别

- Core .NET 库
- ASP.NET

#### <a name="affected-apis"></a>受影响的 API

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=fullName>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize`
- `Overload:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize`
- `M:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)`
- `M:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)`
- `M:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)`
- `M:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)`

-->
