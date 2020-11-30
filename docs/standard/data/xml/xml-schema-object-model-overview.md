---
title: XML 架构对象模型概述
ms.date: 03/30/2017
ms.assetid: 896a1e12-5655-42c6-8cdd-89c12862b34b
ms.openlocfilehash: 62560b641c43f2210b052e9880f2d945dbae0c6f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733095"
---
# <a name="xml-schema-object-model-overview"></a><span data-ttu-id="4829f-102">XML 架构对象模型概述</span><span class="sxs-lookup"><span data-stu-id="4829f-102">XML Schema Object Model Overview</span></span>

<span data-ttu-id="4829f-103">Microsoft .NET Framework 中的架构对象模型 (SOM) 是一个丰富 API，可以通过编程创建、编辑和验证架构。</span><span class="sxs-lookup"><span data-stu-id="4829f-103">The Schema Object Model (SOM) in the Microsoft .NET Framework is a rich API that allows you to create, edit, and validate schemas programmatically.</span></span> <span data-ttu-id="4829f-104">SOM 对 XML 架构文档的作用类似与文档对象模型 (DOM) 对 XML 文档的作用。</span><span class="sxs-lookup"><span data-stu-id="4829f-104">The SOM operates on XML schema documents similarly to the way the Document Object Model (DOM) operates on XML documents.</span></span> <span data-ttu-id="4829f-105">XML 架构文档是有效的 XML 文件，在加载到 SOM 之后，传达其他符合该架构的 XML 文档的结构和有效性的含义。</span><span class="sxs-lookup"><span data-stu-id="4829f-105">XML schema documents are valid XML files that, once loaded into the SOM, convey meaning about the structure and validity of other XML documents which conform to the schema.</span></span>  
  
 <span data-ttu-id="4829f-106">架构是一个 XML 文档，通过为特定架构指定 XML 文档的结构或模型来定义 XML 文档的类。</span><span class="sxs-lookup"><span data-stu-id="4829f-106">A schema is an XML document that defines a class of XML documents by specifying the structure or model of XML documents for a particular schema.</span></span> <span data-ttu-id="4829f-107">架构标识对于 XML 文档内容的约束，并描述符合该架构的 XML 文档为针对该特定架构视为有效而必须遵循的词汇（规则或语法）。</span><span class="sxs-lookup"><span data-stu-id="4829f-107">A schema identifies the constraints on the content of the XML documents, and describes the vocabulary (rules or grammar) that compliant XML documents must follow in order to be considered schema-valid with that particular schema.</span></span> <span data-ttu-id="4829f-108">XML 文档验证是确保文档符合架构所指定的语法的过程。</span><span class="sxs-lookup"><span data-stu-id="4829f-108">Validation of an XML document is the process that ensures that the document conforms to the grammar specified by the schema.</span></span>  
  
 <span data-ttu-id="4829f-109">.NET Framework 中的 SOM API 可以通过下列方式创建、编辑和验证架构。</span><span class="sxs-lookup"><span data-stu-id="4829f-109">The following are ways the SOM API in the .NET Framework enables you to create, edit, and validate schemas.</span></span>  
  
- <span data-ttu-id="4829f-110">从文件中加载有效架构或将有效架构保存到文件中。</span><span class="sxs-lookup"><span data-stu-id="4829f-110">Load and save valid schemas to and from files.</span></span>  
  
- <span data-ttu-id="4829f-111">使用强类型类创建内存中架构。</span><span class="sxs-lookup"><span data-stu-id="4829f-111">Create in-memory schemas using strongly typed classes.</span></span>  
  
- <span data-ttu-id="4829f-112">与 <xref:System.Xml.Schema.XmlSchemaSet> 类进行交互，以缓存、编译和检索架构。</span><span class="sxs-lookup"><span data-stu-id="4829f-112">Interact with the <xref:System.Xml.Schema.XmlSchemaSet> class to cache, compile, and retrieve schemas.</span></span>  
  
- <span data-ttu-id="4829f-113">与 <xref:System.Xml.XmlReader.Create%2A> 类的 <xref:System.Xml.XmlReader> 方法进行交互，以针对架构验证 XML 实例文档。</span><span class="sxs-lookup"><span data-stu-id="4829f-113">Interact with the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> class to validate XML instance documents against schemas.</span></span>  
  
- <span data-ttu-id="4829f-114">生成用于创建和维护架构的编辑器。</span><span class="sxs-lookup"><span data-stu-id="4829f-114">Build editors for creating and maintaining schemas.</span></span>  
  
- <span data-ttu-id="4829f-115">动态编辑架构，可以编译并保存该架构，供验证 XML 实例文档时使用。</span><span class="sxs-lookup"><span data-stu-id="4829f-115">Dynamically edit a schema that can be complied and saved for use in the validation of XML instance documents.</span></span>  
  
## <a name="the-schema-object-model"></a><span data-ttu-id="4829f-116">架构对象模型</span><span class="sxs-lookup"><span data-stu-id="4829f-116">The Schema Object Model</span></span>  

 <span data-ttu-id="4829f-117">SOM 由 <xref:System.Xml.Schema?displayProperty=nameWithType> 命名空间中与 XML 架构中的元素对应的丰富类集组成。</span><span class="sxs-lookup"><span data-stu-id="4829f-117">The SOM consists of an extensive set of classes in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace corresponding to the elements in an XML schema.</span></span> <span data-ttu-id="4829f-118">例如，`<xsd:schema>...</xsd:schema>` 元素映射到 <xref:System.Xml.Schema.XmlSchema?displayProperty=nameWithType> 类，所有可以包含在 `<xsd:schema/>` 元素中的信息都可以使用 <xref:System.Xml.Schema.XmlSchema> 类表示。</span><span class="sxs-lookup"><span data-stu-id="4829f-118">For example, the `<xsd:schema>...</xsd:schema>` element maps to the <xref:System.Xml.Schema.XmlSchema?displayProperty=nameWithType> class, and all the information that can be contained within an `<xsd:schema/>` element can be represented using the <xref:System.Xml.Schema.XmlSchema> class.</span></span> <span data-ttu-id="4829f-119">同样，`<xsd:element>...</xsd:element>` 和 `<xsd:attribute>...</xsd:attribute>` 元素分别映射到 <xref:System.Xml.Schema.XmlSchemaElement?displayProperty=nameWithType> 和 <xref:System.Xml.Schema.XmlSchemaAttribute?displayProperty=nameWithType> 类。</span><span class="sxs-lookup"><span data-stu-id="4829f-119">Similarly, the `<xsd:element>...</xsd:element>` and `<xsd:attribute>...</xsd:attribute>` elements map to the <xref:System.Xml.Schema.XmlSchemaElement?displayProperty=nameWithType> and <xref:System.Xml.Schema.XmlSchemaAttribute?displayProperty=nameWithType> classes respectively.</span></span> <span data-ttu-id="4829f-120">此映射继续为 XML 架构的所有元素在 <xref:System.Xml.Schema> 命名空间中创建 XML 架构对象模型，如下图中所示。</span><span class="sxs-lookup"><span data-stu-id="4829f-120">This mapping continues for all the elements of an XML schema creating an XML schema object model in the <xref:System.Xml.Schema> namespace illustrated in the diagram that follows.</span></span>  
  
 ![System.Xml.Schema 对象模型](./media/xml-schema-object-model-overview/xml-schema-object-model.gif)  
  
 <span data-ttu-id="4829f-122">有关 <xref:System.Xml.Schema> 命名空间中的每个类的更多信息，请参见 .NET Framework 类库中的 <xref:System.Xml.Schema> 命名空间参考文档。</span><span class="sxs-lookup"><span data-stu-id="4829f-122">For more information about each class in the <xref:System.Xml.Schema> namespace, see the <xref:System.Xml.Schema> namespace reference documentation in the .NET Framework class library.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4829f-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="4829f-123">See also</span></span>

- [<span data-ttu-id="4829f-124">读取和编写 XML 架构</span><span class="sxs-lookup"><span data-stu-id="4829f-124">Reading and Writing XML Schemas</span></span>](reading-and-writing-xml-schemas.md)
- [<span data-ttu-id="4829f-125">生成 XML 架构</span><span class="sxs-lookup"><span data-stu-id="4829f-125">Building XML Schemas</span></span>](building-xml-schemas.md)
- [<span data-ttu-id="4829f-126">遍历 XML 架构</span><span class="sxs-lookup"><span data-stu-id="4829f-126">Traversing XML Schemas</span></span>](traversing-xml-schemas.md)
- [<span data-ttu-id="4829f-127">编辑 XML 架构</span><span class="sxs-lookup"><span data-stu-id="4829f-127">Editing XML Schemas</span></span>](editing-xml-schemas.md)
- [<span data-ttu-id="4829f-128">包含或导入 XML 架构</span><span class="sxs-lookup"><span data-stu-id="4829f-128">Including or Importing XML Schemas</span></span>](including-or-importing-xml-schemas.md)
- [<span data-ttu-id="4829f-129">用于编译架构的 XmlSchemaSet</span><span class="sxs-lookup"><span data-stu-id="4829f-129">XmlSchemaSet for Schema Compilation</span></span>](xmlschemaset-for-schema-compilation.md)
- [<span data-ttu-id="4829f-130">后架构编译信息集</span><span class="sxs-lookup"><span data-stu-id="4829f-130">Post-Schema Compilation Infoset</span></span>](post-schema-compilation-infoset.md)
