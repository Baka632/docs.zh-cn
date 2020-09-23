---
title: XML 文本概述
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], about XML literals
- declaring XML literals [Visual Basic]
- LINQ to XML [Visual Basic], XML literals
- literals [Visual Basic], XML
ms.assetid: 37987c15-4ab8-471b-bd45-399816bfb57f
ms.openlocfilehash: c65cac4f6e8f5f314587f20d5c373c92ea0c51e5
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085381"
---
# <a name="xml-literals-overview-visual-basic"></a><span data-ttu-id="628d8-102">XML 文本概述 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="628d8-102">XML Literals Overview (Visual Basic)</span></span>

<span data-ttu-id="628d8-103">*Xml 文本*允许将 xml 直接合并到 Visual Basic 代码。</span><span class="sxs-lookup"><span data-stu-id="628d8-103">An *XML literal* allows you to incorporate XML directly into your Visual Basic code.</span></span> <span data-ttu-id="628d8-104">XML 文本语法表示 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 对象，它类似于 XML 1.0 语法。</span><span class="sxs-lookup"><span data-stu-id="628d8-104">The XML literal syntax represents [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects, and it is the similar to the XML 1.0 syntax.</span></span> <span data-ttu-id="628d8-105">这样可以更轻松地以编程方式创建 XML 元素和文档，因为你的代码具有与最终 XML 相同的结构。</span><span class="sxs-lookup"><span data-stu-id="628d8-105">This makes it easier to create XML elements and documents programmatically because your code has the same structure as the final XML.</span></span>  
  
 <span data-ttu-id="628d8-106">Visual Basic 将 XML 文本编译为 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 对象。</span><span class="sxs-lookup"><span data-stu-id="628d8-106">Visual Basic compiles XML literals into [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="628d8-107">提供了一个用于创建和操作 XML 的简单对象模型，此模型可很好地与语言集成查询 (LINQ) 集成。</span><span class="sxs-lookup"><span data-stu-id="628d8-107">provides a simple object model for creating and manipulating XML, and this model integrates well with Language-Integrated Query (LINQ).</span></span> <span data-ttu-id="628d8-108">有关详细信息，请参阅 <xref:System.Xml.Linq.XElement>。</span><span class="sxs-lookup"><span data-stu-id="628d8-108">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
 <span data-ttu-id="628d8-109">您可以在 XML 文本中嵌入 Visual Basic 表达式。</span><span class="sxs-lookup"><span data-stu-id="628d8-109">You can embed a Visual Basic expression in an XML literal.</span></span> <span data-ttu-id="628d8-110">在运行时，应用程序将 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 为每个文本创建一个对象，并合并嵌入式表达式的值。</span><span class="sxs-lookup"><span data-stu-id="628d8-110">At run time, your application creates a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object for each literal, incorporating the values of the embedded expressions.</span></span> <span data-ttu-id="628d8-111">这使您可以在 XML 文本中指定动态内容。</span><span class="sxs-lookup"><span data-stu-id="628d8-111">This lets you specify dynamic content inside an XML literal.</span></span> <span data-ttu-id="628d8-112">有关详细信息，请参阅 [XML 中的嵌入式表达式](embedded-expressions-in-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="628d8-112">For more information, see [Embedded Expressions in XML](embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="628d8-113">有关 XML 文本语法和 XML 1.0 语法之间的差异的详细信息，请参阅 [Xml 文本和 xml 1.0 规范](xml-literals-and-the-xml-1-0-specification.md)。</span><span class="sxs-lookup"><span data-stu-id="628d8-113">For more information about the differences between the XML literal syntax and the XML 1.0 syntax, see [XML Literals and the XML 1.0 Specification](xml-literals-and-the-xml-1-0-specification.md).</span></span>  
  
## <a name="simple-literals"></a><span data-ttu-id="628d8-114">简单文本</span><span class="sxs-lookup"><span data-stu-id="628d8-114">Simple Literals</span></span>  

 <span data-ttu-id="628d8-115">可以 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 通过在有效的 XML 中键入或粘贴，在 Visual Basic 代码中创建对象。</span><span class="sxs-lookup"><span data-stu-id="628d8-115">You can create a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object in your Visual Basic code by typing or pasting in valid XML.</span></span> <span data-ttu-id="628d8-116">XML 元素文本返回 <xref:System.Xml.Linq.XElement> 对象。</span><span class="sxs-lookup"><span data-stu-id="628d8-116">An XML element literal returns an <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="628d8-117">有关详细信息，请参阅 [Xml 元素文本](../../../language-reference/xml-literals/xml-element-literal.md) 和 [XML 文本和 xml 1.0 规范](xml-literals-and-the-xml-1-0-specification.md)。</span><span class="sxs-lookup"><span data-stu-id="628d8-117">For more information, see [XML Element Literal](../../../language-reference/xml-literals/xml-element-literal.md) and [XML Literals and the XML 1.0 Specification](xml-literals-and-the-xml-1-0-specification.md).</span></span> <span data-ttu-id="628d8-118">下面的示例创建一个具有多个子元素的 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="628d8-118">The following example creates an XML element that has several child elements.</span></span>  
  
 [!code-vb[VbXMLSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
 <span data-ttu-id="628d8-119">可以通过使用启动 XML 文本来创建 XML 文档 `<?xml version="1.0"?>` ，如以下示例中所示。</span><span class="sxs-lookup"><span data-stu-id="628d8-119">You can create an XML document by starting an XML literal with `<?xml version="1.0"?>`, as shown in the following example.</span></span> <span data-ttu-id="628d8-120">XML 文档文本返回 <xref:System.Xml.Linq.XDocument> 对象。</span><span class="sxs-lookup"><span data-stu-id="628d8-120">An XML document literal returns an <xref:System.Xml.Linq.XDocument> object.</span></span> <span data-ttu-id="628d8-121">有关详细信息，请参阅 [XML 文档文本](../../../language-reference/xml-literals/xml-document-literal.md)。</span><span class="sxs-lookup"><span data-stu-id="628d8-121">For more information, see [XML Document Literal](../../../language-reference/xml-literals/xml-document-literal.md).</span></span>  
  
 [!code-vb[VbXMLSamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#6)]  
  
> [!NOTE]
> <span data-ttu-id="628d8-122">Visual Basic 中的 XML 文本语法与 XML 1.0 规范中的语法不完全相同。</span><span class="sxs-lookup"><span data-stu-id="628d8-122">The XML literal syntax in Visual Basic is not identical to the syntax in the XML 1.0 specification.</span></span> <span data-ttu-id="628d8-123">有关详细信息，请参阅 [Xml 文本和 xml 1.0 规范](xml-literals-and-the-xml-1-0-specification.md)。</span><span class="sxs-lookup"><span data-stu-id="628d8-123">For more information, see [XML Literals and the XML 1.0 Specification](xml-literals-and-the-xml-1-0-specification.md).</span></span>  
  
## <a name="line-continuation"></a><span data-ttu-id="628d8-124">续行符</span><span class="sxs-lookup"><span data-stu-id="628d8-124">Line Continuation</span></span>  

 <span data-ttu-id="628d8-125">XML 文本可以跨多行，而无需使用行继续符 (空格-下划线-enter 序列) 。</span><span class="sxs-lookup"><span data-stu-id="628d8-125">An XML literal can span multiple lines without using line continuation characters (the space-underscore-enter sequence).</span></span> <span data-ttu-id="628d8-126">这样就可以更轻松地在代码中将 XML 文本与 XML 文档进行比较。</span><span class="sxs-lookup"><span data-stu-id="628d8-126">This makes it easier to compare XML literals in code with XML documents.</span></span>  
  
 <span data-ttu-id="628d8-127">编译器将行继续符视为 XML 文本的一部分。</span><span class="sxs-lookup"><span data-stu-id="628d8-127">The compiler treats line continuation characters as part of an XML literal.</span></span> <span data-ttu-id="628d8-128">因此，仅当它属于对象时，才应使用空格-下划线-enter 序列 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 。</span><span class="sxs-lookup"><span data-stu-id="628d8-128">Therefore, you should use the space-underscore-enter sequence only when it belongs in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object.</span></span>  
  
 <span data-ttu-id="628d8-129">但是，如果在嵌入式表达式中有多行表达式，则需要行继续符。</span><span class="sxs-lookup"><span data-stu-id="628d8-129">However, you do need line continuation characters if you have a multiline expression in an embedded expression.</span></span> <span data-ttu-id="628d8-130">有关详细信息，请参阅 [XML 中的嵌入式表达式](embedded-expressions-in-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="628d8-130">For more information, see [Embedded Expressions in XML](embedded-expressions-in-xml.md).</span></span>  
  
## <a name="embedding-queries-in-xml-literals"></a><span data-ttu-id="628d8-131">在 XML 文本中嵌入查询</span><span class="sxs-lookup"><span data-stu-id="628d8-131">Embedding Queries in XML Literals</span></span>  

 <span data-ttu-id="628d8-132">您可以在嵌入式表达式中使用查询。</span><span class="sxs-lookup"><span data-stu-id="628d8-132">You can use a query in an embedded expression.</span></span> <span data-ttu-id="628d8-133">执行此操作时，查询返回的元素将添加到 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="628d8-133">When you do this, the elements returned by the query are added to the XML element.</span></span> <span data-ttu-id="628d8-134">这使你可以向 XML 文本添加动态内容（例如用户的查询结果）。</span><span class="sxs-lookup"><span data-stu-id="628d8-134">This lets you add dynamic content, such as the result of a user's query, to an XML literal.</span></span>  
  
 <span data-ttu-id="628d8-135">例如，下面的代码使用嵌入式查询从数组成员创建 XML 元素 `phoneNumbers2` ，然后将这些元素作为的子级添加 `contact2` 。</span><span class="sxs-lookup"><span data-stu-id="628d8-135">For example, the following code uses an embedded query to create XML elements from the members of the `phoneNumbers2` array and then add those elements as children of `contact2`.</span></span>  
  
 [!code-vb[VbXMLSamples#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#7)]  
  
## <a name="how-the-compiler-creates-objects-from-xml-literals"></a><span data-ttu-id="628d8-136">编译器如何从 XML 文本创建对象</span><span class="sxs-lookup"><span data-stu-id="628d8-136">How the Compiler Creates Objects from XML Literals</span></span>  

 <span data-ttu-id="628d8-137">Visual Basic 编译器将 XML 文本转换为对等效 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 构造函数的调用，以生成 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 对象。</span><span class="sxs-lookup"><span data-stu-id="628d8-137">The Visual Basic compiler translates XML literals into calls to the equivalent [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] constructors to build up the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object.</span></span> <span data-ttu-id="628d8-138">例如，Visual Basic 编译器会将下面的代码示例转换为对 <xref:System.Xml.Linq.XProcessingInstruction> XML 版本指令的构造函数的调用，对 <xref:System.Xml.Linq.XElement> `<contact>` 、和元素调用构造函数，并调用该特性的 `<name>` `<phone>` <xref:System.Xml.Linq.XAttribute> 构造函数 `type` 。</span><span class="sxs-lookup"><span data-stu-id="628d8-138">For example, the Visual Basic compiler will translate the following code example into a call to the <xref:System.Xml.Linq.XProcessingInstruction> constructor for the XML version instruction, calls to the <xref:System.Xml.Linq.XElement> constructor for the `<contact>`, `<name>`, and `<phone>` elements, and calls to the <xref:System.Xml.Linq.XAttribute> constructor for the `type` attribute.</span></span> <span data-ttu-id="628d8-139">具体来说，假设下面的示例中的特性，Visual Basic 编译器将调用 <xref:System.Xml.Linq.XAttribute.%23ctor%28System.Xml.Linq.XName%2CSystem.Object%29> 构造函数两次。</span><span class="sxs-lookup"><span data-stu-id="628d8-139">Specifically, given the attributes in the following sample, the Visual Basic compiler will call the <xref:System.Xml.Linq.XAttribute.%23ctor%28System.Xml.Linq.XName%2CSystem.Object%29> constructor twice.</span></span> <span data-ttu-id="628d8-140">第一个参数将传递 `type` 参数的值 `name` 和参数的值 `home` `value` 。</span><span class="sxs-lookup"><span data-stu-id="628d8-140">The first will pass the value `type` for the `name` parameter and the value `home` for the `value` parameter.</span></span> <span data-ttu-id="628d8-141">第二个还将传递 `type` 参数的值 `name` ，但不传递参数的值 `work` `value` 。</span><span class="sxs-lookup"><span data-stu-id="628d8-141">The second will also pass the value `type` for the `name` parameter, but the value `work` for the `value` parameter.</span></span>  
  
 [!code-vb[VbXMLSamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="628d8-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="628d8-142">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="628d8-143">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="628d8-143">Creating XML in Visual Basic</span></span>](creating-xml.md)
- [<span data-ttu-id="628d8-144">XML 中的嵌入式表达式</span><span class="sxs-lookup"><span data-stu-id="628d8-144">Embedded Expressions in XML</span></span>](embedded-expressions-in-xml.md)
- [<span data-ttu-id="628d8-145">XML 文档文本</span><span class="sxs-lookup"><span data-stu-id="628d8-145">XML Document Literal</span></span>](../../../language-reference/xml-literals/xml-document-literal.md)
- [<span data-ttu-id="628d8-146">XML 元素文本</span><span class="sxs-lookup"><span data-stu-id="628d8-146">XML Element Literal</span></span>](../../../language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="628d8-147">XML 文本</span><span class="sxs-lookup"><span data-stu-id="628d8-147">XML Literals</span></span>](../../../language-reference/xml-literals/index.md)
