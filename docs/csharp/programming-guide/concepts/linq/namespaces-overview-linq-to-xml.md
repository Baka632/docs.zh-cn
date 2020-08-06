---
title: 命名空间概述 (LINQ to XML)
description: 了解命名空间、XName 类、XNamespace 类和 XML 名称的其他方面。
ms.date: 07/20/2015
ms.assetid: 16283322-8238-4918-ab11-802ac6748eb7
ms.openlocfilehash: 56dca481dd5f3066fa5359fc57b3311cf2569ee0
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/28/2020
ms.locfileid: "87300158"
---
# <a name="namespaces-overview-linq-to-xml"></a>命名空间概述 (LINQ to XML)

本文介绍命名空间、<xref:System.Xml.Linq.XName> 类和 <xref:System.Xml.Linq.XNamespace> 类。

## <a name="xml-names"></a>XML 名称

XML 名称常常是导致 XML 编程复杂性的原因。 XML 名称由 XML 命名空间（也称为 XML 命名空间 URI）和本地名称组成。 XML 命名空间类似于 .NET 程序中的命名空间。 它能够唯一限定元素和属性的名称。 这有助于避免 XML 文档各个部分之间的名称冲突。 声明 XML 命名空间后，可以选择只需在此命名空间内唯一的本地名称。

XML 名称的另一个方面是 XML 命名空间前缀。 XML 名称的复杂性大都是由 XML 前缀引起的。 这些前缀可用来创建 XML 命名空间的快捷方式，从而使 XML 文档更加简洁易懂。 但是，XML 前缀仅在其上下文中才有意义，这就增加了复杂性。 例如，XML 前缀 `aw` 可以与 XML 树的一部分中的一个 XML 命名空间关联，也可以与该 XML 树的另一部分中的另一个 XML 命名空间关联。

通过 C# 使用 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 的一个优点是您无须使用 XML 前缀。 当 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 加载或解析 XML 文档时，每个 XML 前缀都解析为它对应的 XML 命名空间。 之后，当您处理使用命名空间的文档时，您几乎总是通过命名空间 URI，而不是通过命名空间前缀来访问命名空间。 开发人员在 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 中使用 XML 名称时，他们始终使用完全限定的 XML 名称（即，XML 命名空间和本地名称）。 但是，如有必要，[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 允许您使用和控制命名空间前缀。

在 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 中，表示 XML 名称的类为 <xref:System.Xml.Linq.XName>。 XML 名称在整个 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API 中频繁出现，任何时候只要需要 XML 名称，您就会发现 <xref:System.Xml.Linq.XName> 参数。 但是，很少会直接使用 <xref:System.Xml.Linq.XName>。 <xref:System.Xml.Linq.XName> 包含一个从字符串的隐式转换。

有关详细信息，请参阅 <xref:System.Xml.Linq.XNamespace> 和 <xref:System.Xml.Linq.XName>。
