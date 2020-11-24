---
title: 嵌入到文档中的样式表指令
ms.date: 03/30/2017
ms.assetid: d79fb295-ebc7-438d-ba1b-05be7d534834
ms.openlocfilehash: 25946fd14a82428ae4367cd33511df68e9929203
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "94818565"
---
# <a name="style-sheet-directives-embedded-in-a-document"></a><span data-ttu-id="56a7e-102">嵌入到文档中的样式表指令</span><span class="sxs-lookup"><span data-stu-id="56a7e-102">Style Sheet Directives Embedded in a Document</span></span>

<span data-ttu-id="56a7e-103">有时，现有 XML 会包含 `<?xml:stylesheet?>` 形式的样式表指令。</span><span class="sxs-lookup"><span data-stu-id="56a7e-103">Occasionally, existing XML contains the style sheet directive of `<?xml:stylesheet?>`.</span></span> <span data-ttu-id="56a7e-104">Microsoft Internet Explorer 接受此指令作为 `<?xml-stylesheet?>` 语法的替换形式。</span><span class="sxs-lookup"><span data-stu-id="56a7e-104">Microsoft Internet Explorer accepts this as an alternative to the `<?xml-stylesheet?>` syntax.</span></span> <span data-ttu-id="56a7e-105">当 XML 数据包含 `<?xml:stylesheet?>` 指令时（如下面的数据所示），试图将此数据加载到 XML 文档对象模型 (DOM) 中将引发异常。</span><span class="sxs-lookup"><span data-stu-id="56a7e-105">When the XML data contains an `<?xml:stylesheet?>` directive, as shown in the following data, attempting to load this data into the XML Document Object Model (DOM) throws an exception.</span></span>

```xml
<?xml version="1.0" ?>
<?xml:stylesheet type="text/xsl" href="test2.xsl"?>
<root>
    <test>Node 1</test>
    <test>Node 2</test>
</root>
```

<span data-ttu-id="56a7e-106">发生这种情况是因为，`<?xml:stylesheet?>` 被视为对 DOM 无效的 ProcessingInstruction  。</span><span class="sxs-lookup"><span data-stu-id="56a7e-106">This occurs because the `<?xml:stylesheet?>` is considered an invalid **ProcessingInstruction** to the DOM.</span></span> <span data-ttu-id="56a7e-107">根据 XML 命名空间规范，任何 ProcessingInstruction  都只能是无冒号名称 (NCNames)，而不是限定名称 (QNames)。</span><span class="sxs-lookup"><span data-stu-id="56a7e-107">Any **ProcessingInstruction**, according to the Namespaces in XML specification, can only be no-colon names (NCNames), as opposed to qualified names (QNames).</span></span>

<span data-ttu-id="56a7e-108">根据 XML 命名空间规范的第 6 节，让 Load  和 LoadXml  方法符合此规范所产生的效应是，在文档中：</span><span class="sxs-lookup"><span data-stu-id="56a7e-108">From Section 6 of the Namespaces in XML specification, the effect of having the **Load** and **LoadXml** methods conform to the specification is that in a document:</span></span>

- <span data-ttu-id="56a7e-109">所有元素类型和属性名都包含零个或一个冒号。</span><span class="sxs-lookup"><span data-stu-id="56a7e-109">All element types and attribute names contain either zero or one colon.</span></span>

- <span data-ttu-id="56a7e-110">任何实体名称、ProcessingInstruction 目标或表示法名称都不包含冒号。</span><span class="sxs-lookup"><span data-stu-id="56a7e-110">No entity names, ProcessingInstruction targets, or notation names contain any colons.</span></span>

<span data-ttu-id="56a7e-111">因为 `<?xml:stylesheet?>` 包含一个冒号，所以您违反了第二条规则。</span><span class="sxs-lookup"><span data-stu-id="56a7e-111">With the `<?xml:stylesheet?>` containing a colon, you now violate the rule in the second bullet.</span></span>

<span data-ttu-id="56a7e-112">根据万维网联合会 (W3C) [将样式表与 XML 文档关联的 1.0 版建议](https://www.w3.org/TR/xml-stylesheet/)，将 XSLT 样式表与 XML 文档关联的处理指令是 `<?xml-stylesheet?>`（用短划线代替冒号）。</span><span class="sxs-lookup"><span data-stu-id="56a7e-112">According to the World Wide Web Consortium (W3C) [Associating Style Sheets with XML documents Version 1.0 Recommendation](https://www.w3.org/TR/xml-stylesheet/),  the processing instruction to associate an XSLT style sheet with an XML document is `<?xml-stylesheet?>`, with a dash replacing the colon.</span></span>

## <a name="see-also"></a><span data-ttu-id="56a7e-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="56a7e-113">See also</span></span>

- [<span data-ttu-id="56a7e-114">XML 文档对象模型 (DOM)</span><span class="sxs-lookup"><span data-stu-id="56a7e-114">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
