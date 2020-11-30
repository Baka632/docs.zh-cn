---
title: 推断架构节点类型和结构的规则
ms.date: 03/30/2017
ms.assetid: d74ce896-717d-4871-8fd9-b070e2f53cb0
ms.openlocfilehash: e49e50dc21951d739b12cdfa60c6a48f67576873
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697592"
---
# <a name="rules-for-inferring-schema-node-types-and-structure"></a><span data-ttu-id="52b8c-102">推断架构节点类型和结构的规则</span><span class="sxs-lookup"><span data-stu-id="52b8c-102">Rules for Inferring Schema Node Types and Structure</span></span>

<span data-ttu-id="52b8c-103">本主题介绍架构推断过程如何将 XML 文档中的节点类型转换为 XML 架构定义语言 (XSD) 结构。</span><span class="sxs-lookup"><span data-stu-id="52b8c-103">This topic describes how the schema inference process translates the node types in an XML document to an XML Schema definition language (XSD) structure.</span></span>  
  
## <a name="element-inference-rules"></a><span data-ttu-id="52b8c-104">元素推断规则</span><span class="sxs-lookup"><span data-stu-id="52b8c-104">Element Inference Rules</span></span>  

 <span data-ttu-id="52b8c-105">本节说明元素声明的推断规则。</span><span class="sxs-lookup"><span data-stu-id="52b8c-105">This section describes the inference rules for element declarations.</span></span> <span data-ttu-id="52b8c-106">其中将推断八种元素声明结构：</span><span class="sxs-lookup"><span data-stu-id="52b8c-106">There are eight structures of element declarations that will be inferred:</span></span>  
  
1. <span data-ttu-id="52b8c-107">简单类型的元素</span><span class="sxs-lookup"><span data-stu-id="52b8c-107">Element of simple type</span></span>  
  
2. <span data-ttu-id="52b8c-108">空元素</span><span class="sxs-lookup"><span data-stu-id="52b8c-108">Empty element</span></span>  
  
3. <span data-ttu-id="52b8c-109">具有属性的空元素</span><span class="sxs-lookup"><span data-stu-id="52b8c-109">Empty element with attributes</span></span>  
  
4. <span data-ttu-id="52b8c-110">具有属性和简单内容的元素</span><span class="sxs-lookup"><span data-stu-id="52b8c-110">Element with attributes and simple content</span></span>  
  
5. <span data-ttu-id="52b8c-111">具有一系列子元素的元素</span><span class="sxs-lookup"><span data-stu-id="52b8c-111">Element with a sequence of child elements</span></span>  
  
6. <span data-ttu-id="52b8c-112">具有一系列子元素和属性的元素</span><span class="sxs-lookup"><span data-stu-id="52b8c-112">Element with a sequence of child elements and attributes</span></span>  
  
7. <span data-ttu-id="52b8c-113">具有一系列子元素选择的元素</span><span class="sxs-lookup"><span data-stu-id="52b8c-113">Element with a sequence of choices of child elements</span></span>  
  
8. <span data-ttu-id="52b8c-114">具有一系列子元素和属性选择的元素</span><span class="sxs-lookup"><span data-stu-id="52b8c-114">Element with a sequence of choices of child elements and attributes</span></span>  
  
> [!NOTE]
> <span data-ttu-id="52b8c-115">所有 `complexType` 声明均推断为匿名类型。</span><span class="sxs-lookup"><span data-stu-id="52b8c-115">All `complexType` declarations are inferred as anonymous types.</span></span> <span data-ttu-id="52b8c-116">唯一推断的全局元素是根元素；所有其他元素都是局部元素。</span><span class="sxs-lookup"><span data-stu-id="52b8c-116">The only global element inferred is the root element; all other elements are local.</span></span>  
  
 <span data-ttu-id="52b8c-117">若要详细了解架构推理进程，请参阅[从 XML 文档推理架构](inferring-schemas-from-xml-documents.md)。</span><span class="sxs-lookup"><span data-stu-id="52b8c-117">For more information about the schema inference process, see [Inferring Schemas from XML Documents](inferring-schemas-from-xml-documents.md).</span></span>  
  
### <a name="simple-typed-element"></a><span data-ttu-id="52b8c-118">简单类型化的元素</span><span class="sxs-lookup"><span data-stu-id="52b8c-118">Simple Typed Element</span></span>  

 <span data-ttu-id="52b8c-119">下表显示 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> 方法的 XML 输入以及生成的 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="52b8c-119">The following table shows the XML input to the <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> method, and the XML schema generated.</span></span> <span data-ttu-id="52b8c-120">粗体的元素显示为简单类型元素推断的架构。</span><span class="sxs-lookup"><span data-stu-id="52b8c-120">The bolded element shows the schema inferred for the simple type element.</span></span>  
  
 <span data-ttu-id="52b8c-121">若要详细了解架构推理进程，请参阅[从 XML 文档推理架构](inferring-schemas-from-xml-documents.md)。</span><span class="sxs-lookup"><span data-stu-id="52b8c-121">For more information about the schema inference process, see [Inferring Schemas from XML Documents](inferring-schemas-from-xml-documents.md).</span></span>  
  
|<span data-ttu-id="52b8c-122">XML</span><span class="sxs-lookup"><span data-stu-id="52b8c-122">XML</span></span>|<span data-ttu-id="52b8c-123">架构</span><span class="sxs-lookup"><span data-stu-id="52b8c-123">Schema</span></span>|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root>text</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root" type="xs:string" />`<br /><br /> `</xs:schema>`|  
  
### <a name="empty-element"></a><span data-ttu-id="52b8c-124">空元素</span><span class="sxs-lookup"><span data-stu-id="52b8c-124">Empty Element</span></span>  

 <span data-ttu-id="52b8c-125">下表显示 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> 方法的 XML 输入以及生成的 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="52b8c-125">The following table shows the XML input to the <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> method, and the XML schema generated.</span></span> <span data-ttu-id="52b8c-126">粗体的元素显示为空元素推断的架构。</span><span class="sxs-lookup"><span data-stu-id="52b8c-126">The bolded element shows the schema inferred for the empty element.</span></span>  
  
 <span data-ttu-id="52b8c-127">若要详细了解架构推理进程，请参阅[从 XML 文档推理架构](inferring-schemas-from-xml-documents.md)。</span><span class="sxs-lookup"><span data-stu-id="52b8c-127">For more information about the schema inference process, see [Inferring Schemas from XML Documents](inferring-schemas-from-xml-documents.md).</span></span>  
  
|<span data-ttu-id="52b8c-128">XML</span><span class="sxs-lookup"><span data-stu-id="52b8c-128">XML</span></span>|<span data-ttu-id="52b8c-129">架构</span><span class="sxs-lookup"><span data-stu-id="52b8c-129">Schema</span></span>|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<empty/>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="empty" />`<br /><br /> `</xs:schema>`|  
  
### <a name="empty-element-with-attributes"></a><span data-ttu-id="52b8c-130">具有属性的空元素</span><span class="sxs-lookup"><span data-stu-id="52b8c-130">Empty Element with Attributes</span></span>  

 <span data-ttu-id="52b8c-131">下表显示 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> 方法的 XML 输入以及生成的 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="52b8c-131">The following table shows the XML input to the <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> method, and the XML schema generated.</span></span> <span data-ttu-id="52b8c-132">粗体的元素显示为具有属性的空元素推断的架构。</span><span class="sxs-lookup"><span data-stu-id="52b8c-132">The bolded elements show the schema inferred for the empty element with attributes.</span></span>  
  
 <span data-ttu-id="52b8c-133">若要详细了解架构推理进程，请参阅[从 XML 文档推理架构](inferring-schemas-from-xml-documents.md)。</span><span class="sxs-lookup"><span data-stu-id="52b8c-133">For more information about the schema inference process, see [Inferring Schemas from XML Documents](inferring-schemas-from-xml-documents.md).</span></span>  
  
|<span data-ttu-id="52b8c-134">XML</span><span class="sxs-lookup"><span data-stu-id="52b8c-134">XML</span></span>|<span data-ttu-id="52b8c-135">架构</span><span class="sxs-lookup"><span data-stu-id="52b8c-135">Schema</span></span>|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<empty attribute1="text"/>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="empty">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:attribute name="attribute1" type="xs:string" use="required" />`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="element-with-attributes-and-simple-content"></a><span data-ttu-id="52b8c-136">具有属性和简单内容的元素</span><span class="sxs-lookup"><span data-stu-id="52b8c-136">Element with Attributes and Simple Content</span></span>  

 <span data-ttu-id="52b8c-137">下表显示 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> 方法的 XML 输入以及生成的 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="52b8c-137">The following table shows the XML input to the <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> method, and the XML schema generated.</span></span> <span data-ttu-id="52b8c-138">粗体的元素显示为具有属性和简单内容的元素推断的架构。</span><span class="sxs-lookup"><span data-stu-id="52b8c-138">The bolded elements show the schema inferred for an element with attributes and simple content.</span></span>  
  
 <span data-ttu-id="52b8c-139">若要详细了解架构推理进程，请参阅[从 XML 文档推理架构](inferring-schemas-from-xml-documents.md)。</span><span class="sxs-lookup"><span data-stu-id="52b8c-139">For more information about the schema inference process, see [Inferring Schemas from XML Documents](inferring-schemas-from-xml-documents.md).</span></span>  
  
|<span data-ttu-id="52b8c-140">XML</span><span class="sxs-lookup"><span data-stu-id="52b8c-140">XML</span></span>|<span data-ttu-id="52b8c-141">架构</span><span class="sxs-lookup"><span data-stu-id="52b8c-141">Schema</span></span>|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root attribute1="text">value</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:simpleContent>`<br /><br /> `<xs:extension base="xs:string">`<br /><br /> `<xs:attribute name="attribute1" type="xs:string" use="required" />`<br /><br /> `</xs:extension>`<br /><br /> `</xs:simpleContent>`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="element-with-a-sequence-of-child-elements"></a><span data-ttu-id="52b8c-142">具有一系列子元素的元素</span><span class="sxs-lookup"><span data-stu-id="52b8c-142">Element with a Sequence of Child Elements</span></span>  

 <span data-ttu-id="52b8c-143">下表显示 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> 方法的 XML 输入以及生成的 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="52b8c-143">The following table shows the XML input to the <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> method, and the XML schema generated.</span></span> <span data-ttu-id="52b8c-144">粗体的元素显示为具有一系列子元素的元素推断的架构。</span><span class="sxs-lookup"><span data-stu-id="52b8c-144">The bolded elements show the schema inferred for an element with a sequence of child elements.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="52b8c-145">即使元素只有一个子元素，仍作为一系列子元素对待。</span><span class="sxs-lookup"><span data-stu-id="52b8c-145">Even if an element has only one child element, it is still treated as a sequence.</span></span>  
  
 <span data-ttu-id="52b8c-146">若要详细了解架构推理进程，请参阅[从 XML 文档推理架构](inferring-schemas-from-xml-documents.md)。</span><span class="sxs-lookup"><span data-stu-id="52b8c-146">For more information about the schema inference process, see [Inferring Schemas from XML Documents](inferring-schemas-from-xml-documents.md).</span></span>  
  
|<span data-ttu-id="52b8c-147">XML</span><span class="sxs-lookup"><span data-stu-id="52b8c-147">XML</span></span>|<span data-ttu-id="52b8c-148">架构</span><span class="sxs-lookup"><span data-stu-id="52b8c-148">Schema</span></span>|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root>`<br /><br /> `<subElement/>`<br /><br /> `</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:sequence>`<br /><br /> `<xs:element name="subElement" />`<br /><br /> `</xs:sequence>`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="element-with-a-sequence-of-child-elements-and-attributes"></a><span data-ttu-id="52b8c-149">具有一系列子元素和属性的元素</span><span class="sxs-lookup"><span data-stu-id="52b8c-149">Element with a Sequence of Child Elements and Attributes</span></span>  

 <span data-ttu-id="52b8c-150">下表显示 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> 方法的 XML 输入以及生成的 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="52b8c-150">The following table shows the XML input to the <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> method, and the XML schema generated.</span></span> <span data-ttu-id="52b8c-151">粗体的元素显示为具有一系列子元素和属性的元素推断的架构。</span><span class="sxs-lookup"><span data-stu-id="52b8c-151">The bolded elements show the schema inferred for an element with a sequence of child elements and attributes.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="52b8c-152">即使元素只有一个子元素，仍作为一系列子元素对待。</span><span class="sxs-lookup"><span data-stu-id="52b8c-152">Even if an element has only one child element, it is still treated as a sequence.</span></span>  
  
 <span data-ttu-id="52b8c-153">若要详细了解架构推理进程，请参阅[从 XML 文档推理架构](inferring-schemas-from-xml-documents.md)。</span><span class="sxs-lookup"><span data-stu-id="52b8c-153">For more information about the schema inference process, see [Inferring Schemas from XML Documents](inferring-schemas-from-xml-documents.md).</span></span>  
  
|<span data-ttu-id="52b8c-154">XML</span><span class="sxs-lookup"><span data-stu-id="52b8c-154">XML</span></span>|<span data-ttu-id="52b8c-155">架构</span><span class="sxs-lookup"><span data-stu-id="52b8c-155">Schema</span></span>|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root attribute1="text">`<br /><br /> `<subElement1/>`<br /><br /> `<subElement2/>`<br /><br /> `</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:sequence>`<br /><br /> `<xs:element name="subElement1" />`<br /><br /> `<xs:element name="subElement2" />`<br /><br /> `</xs:sequence>`<br /><br /> `<xs:attribute name="attribute1" type="xs:string" use="required" />`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="element-with-a-sequence-and-choices-of-child-elements"></a><span data-ttu-id="52b8c-156">具有一系列子元素选择的元素</span><span class="sxs-lookup"><span data-stu-id="52b8c-156">Element with a Sequence and Choices of Child Elements</span></span>  

 <span data-ttu-id="52b8c-157">下表显示 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> 方法的 XML 输入以及生成的 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="52b8c-157">The following table shows the XML input to the <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> method, and the XML schema generated.</span></span> <span data-ttu-id="52b8c-158">粗体的元素显示为具有一系列子元素选择的元素推断的架构。</span><span class="sxs-lookup"><span data-stu-id="52b8c-158">The bolded elements show the schema inferred for an element with a sequence and choice of child elements.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="52b8c-159">在推断出的架构中，`maxOccurs` 元素的 `xs:choice` 属性设置为 `"unbounded"`。</span><span class="sxs-lookup"><span data-stu-id="52b8c-159">The `maxOccurs` attribute of the `xs:choice` element is set to `"unbounded"` in the inferred schema.</span></span>  
  
 <span data-ttu-id="52b8c-160">若要详细了解架构推理进程，请参阅[从 XML 文档推理架构](inferring-schemas-from-xml-documents.md)。</span><span class="sxs-lookup"><span data-stu-id="52b8c-160">For more information about the schema inference process, see [Inferring Schemas from XML Documents](inferring-schemas-from-xml-documents.md).</span></span>  
  
|<span data-ttu-id="52b8c-161">XML</span><span class="sxs-lookup"><span data-stu-id="52b8c-161">XML</span></span>|<span data-ttu-id="52b8c-162">架构</span><span class="sxs-lookup"><span data-stu-id="52b8c-162">Schema</span></span>|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root>`<br /><br /> `<subElement1/>`<br /><br /> `<subElement2/>`<br /><br /> `<subElement1/>`<br /><br /> `</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:sequence>`<br /><br /> `<xs:choice maxOccurs="unbounded">`<br /><br /> `<xs:element name="subElement1" />`<br /><br /> `<xs:element name="subElement2" />`<br /><br /> `</xs:choice>`<br /><br /> `</xs:sequence>`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="element-with-a-sequence-and-choice-of-child-elements-and-attributes"></a><span data-ttu-id="52b8c-163">具有一系列子元素和属性选择的元素</span><span class="sxs-lookup"><span data-stu-id="52b8c-163">Element with a Sequence and Choice of Child Elements and Attributes</span></span>  

 <span data-ttu-id="52b8c-164">下表显示 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> 方法的 XML 输入以及生成的 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="52b8c-164">The following table shows the XML input to the <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> method, and the XML schema generated.</span></span> <span data-ttu-id="52b8c-165">粗体的元素显示为具有一系列子元素和属性选择的元素推断的架构。</span><span class="sxs-lookup"><span data-stu-id="52b8c-165">The bolded elements show the schema inferred for an element with a sequence and choice of child elements and attributes.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="52b8c-166">在推断出的架构中，`maxOccurs` 元素的 `xs:choice` 属性设置为 `"unbounded"`。</span><span class="sxs-lookup"><span data-stu-id="52b8c-166">The `maxOccurs` attribute of the `xs:choice` element is set to `"unbounded"` in the inferred schema.</span></span>  
  
 <span data-ttu-id="52b8c-167">若要详细了解架构推理进程，请参阅[从 XML 文档推理架构](inferring-schemas-from-xml-documents.md)。</span><span class="sxs-lookup"><span data-stu-id="52b8c-167">For more information about the schema inference process, see [Inferring Schemas from XML Documents](inferring-schemas-from-xml-documents.md).</span></span>  
  
|<span data-ttu-id="52b8c-168">XML</span><span class="sxs-lookup"><span data-stu-id="52b8c-168">XML</span></span>|<span data-ttu-id="52b8c-169">架构</span><span class="sxs-lookup"><span data-stu-id="52b8c-169">Schema</span></span>|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root attribute1="text">`<br /><br /> `<subElement1/>`<br /><br /> `<subElement2/>`<br /><br /> `<subElement1/>`<br /><br /> `</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:sequence>`<br /><br /> `<xs:choice maxOccurs="unbounded">`<br /><br /> `<xs:element name="subElement1" />`<br /><br /> `<xs:element name="subElement2" />`<br /><br /> `</xs:choice>`<br /><br /> `</xs:sequence>`<br /><br /> `<xs:attribute name="attribute1" type="xs:string" use="required" />`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="attribute-processing"></a><span data-ttu-id="52b8c-170">属性处理</span><span class="sxs-lookup"><span data-stu-id="52b8c-170">Attribute Processing</span></span>  

 <span data-ttu-id="52b8c-171">只要在节点中遇到新属性，就会使用 `use="required"` 将新属性添加到推断出的节点定义中。</span><span class="sxs-lookup"><span data-stu-id="52b8c-171">Whenever a new attribute is encountered within a node, it is added to the inferred definition of the node with `use="required"`.</span></span> <span data-ttu-id="52b8c-172">下次在该实例中发现同一个节点时，推断过程会将当前实例的属性与已推断出的属性进行比较。</span><span class="sxs-lookup"><span data-stu-id="52b8c-172">The next time the same node is found in the instance, the inference process will compare attributes of the current instance with the ones already inferred.</span></span> <span data-ttu-id="52b8c-173">如果该实例中缺少某些已推断出的属性，`use="optional"` 将添加到属性定义中。</span><span class="sxs-lookup"><span data-stu-id="52b8c-173">If some of the already inferred ones are missing in the instance, `use="optional"` is added to the attribute definition.</span></span> <span data-ttu-id="52b8c-174">新属性将使用 `use="optional"` 添加到现有声明中。</span><span class="sxs-lookup"><span data-stu-id="52b8c-174">New attributes are added to existing declarations with `use="optional"`.</span></span>  
  
### <a name="occurrence-constraints"></a><span data-ttu-id="52b8c-175">匹配项约束</span><span class="sxs-lookup"><span data-stu-id="52b8c-175">Occurrence Constraints</span></span>  

 <span data-ttu-id="52b8c-176">在架构推断过程中，会为推断出的架构组件生成 `minOccurs` 和 `maxOccurs` 属性，值为 `"0"` 或 `"1"` 以及 `"1"` 或 `"unbounded"`。</span><span class="sxs-lookup"><span data-stu-id="52b8c-176">During the schema inference process, the `minOccurs` and `maxOccurs` attributes are generated, for inferred components of a schema, with the values `"0"` or `"1"` and `"1"` or `"unbounded"`.</span></span> <span data-ttu-id="52b8c-177">只有值 `"1"` 和 `"unbounded"` 无法验证 XML 文档时，才会使用值 `"0"` 和 `"1"`（例如，如果 `MinOccurs="0"` 没有准确描述某个元素，则使用 `minOccurs="1"`）。</span><span class="sxs-lookup"><span data-stu-id="52b8c-177">The values `"1"` and `"unbounded"` are used only when the values `"0"` and `"1"` cannot validate the XML document (for example, if `MinOccurs="0"` does not accurately describe an element, `minOccurs="1"` is used).</span></span>  
  
### <a name="mixed-content"></a><span data-ttu-id="52b8c-178">混合内容</span><span class="sxs-lookup"><span data-stu-id="52b8c-178">Mixed Content</span></span>  

 <span data-ttu-id="52b8c-179">如果某个元素包含混合内容（例如混合了文本和元素），将为推断出的复杂类型定义生成 `mixed="true"` 属性。</span><span class="sxs-lookup"><span data-stu-id="52b8c-179">If an element contains mixed content (for example text interspersed with elements), the `mixed="true"` attribute is generated for the inferred complex type definition.</span></span>  
  
## <a name="other-node-type-inference-rules"></a><span data-ttu-id="52b8c-180">其他节点类型推断规则</span><span class="sxs-lookup"><span data-stu-id="52b8c-180">Other Node Type Inference Rules</span></span>  

 <span data-ttu-id="52b8c-181">下表说明处理指令、注释、实体引用、CDATA、文档类型和命名空间节点的推断规则。</span><span class="sxs-lookup"><span data-stu-id="52b8c-181">The following table describes the inference rules for processing instruction, comment, entity reference, CDATA, document type, and namespace nodes.</span></span>  
  
|<span data-ttu-id="52b8c-182">节点类型</span><span class="sxs-lookup"><span data-stu-id="52b8c-182">Node Type</span></span>|<span data-ttu-id="52b8c-183">转换</span><span class="sxs-lookup"><span data-stu-id="52b8c-183">Translation</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="52b8c-184">处理指令</span><span class="sxs-lookup"><span data-stu-id="52b8c-184">Processing instruction</span></span>|<span data-ttu-id="52b8c-185">已忽略。</span><span class="sxs-lookup"><span data-stu-id="52b8c-185">Ignored.</span></span>|  
|<span data-ttu-id="52b8c-186">注释</span><span class="sxs-lookup"><span data-stu-id="52b8c-186">Comment</span></span>|<span data-ttu-id="52b8c-187">已忽略。</span><span class="sxs-lookup"><span data-stu-id="52b8c-187">Ignored.</span></span>|  
|<span data-ttu-id="52b8c-188">实体引用</span><span class="sxs-lookup"><span data-stu-id="52b8c-188">Entity reference</span></span>|<span data-ttu-id="52b8c-189"><xref:System.Xml.Schema.XmlSchemaInference> 类不处理实体引用。</span><span class="sxs-lookup"><span data-stu-id="52b8c-189">The <xref:System.Xml.Schema.XmlSchemaInference> class does not handle entity references.</span></span> <span data-ttu-id="52b8c-190">如果 XML 文档包含实体引用，需要使用可以展开实体的读取器。</span><span class="sxs-lookup"><span data-stu-id="52b8c-190">If an XML document contains entity references, you need to use a reader that expands the entities.</span></span> <span data-ttu-id="52b8c-191">例如，可以将 <xref:System.Xml.XmlTextReader> 属性设置为 <xref:System.Xml.XmlTextReader.EntityHandling%2A> 的 <xref:System.Xml.EntityHandling.ExpandEntities> 作为参数传递。</span><span class="sxs-lookup"><span data-stu-id="52b8c-191">For example, you can pass an <xref:System.Xml.XmlTextReader> with the <xref:System.Xml.XmlTextReader.EntityHandling%2A> property set to <xref:System.Xml.EntityHandling.ExpandEntities> as a parameter.</span></span> <span data-ttu-id="52b8c-192">如果遇到实体引用，并且读取器没有展开实体，将引发异常。</span><span class="sxs-lookup"><span data-stu-id="52b8c-192">If entity references are encountered and the reader does not expand entities, an exception is throw.</span></span>|  
|<span data-ttu-id="52b8c-193">CDATA</span><span class="sxs-lookup"><span data-stu-id="52b8c-193">CDATA</span></span>|<span data-ttu-id="52b8c-194">XML 文档中的任何 `<![CDATA[ … ]]` 节均将推断为 `xs:string`。</span><span class="sxs-lookup"><span data-stu-id="52b8c-194">Any `<![CDATA[ … ]]` sections in an XML document will be inferred as `xs:string`.</span></span>|  
|<span data-ttu-id="52b8c-195">文档类型</span><span class="sxs-lookup"><span data-stu-id="52b8c-195">Document type</span></span>|<span data-ttu-id="52b8c-196">已忽略。</span><span class="sxs-lookup"><span data-stu-id="52b8c-196">Ignored.</span></span>|  
|<span data-ttu-id="52b8c-197">命名空间</span><span class="sxs-lookup"><span data-stu-id="52b8c-197">Namespaces</span></span>|<span data-ttu-id="52b8c-198">已忽略。</span><span class="sxs-lookup"><span data-stu-id="52b8c-198">Ignored.</span></span>|  
  
 <span data-ttu-id="52b8c-199">若要详细了解架构推理进程，请参阅[从 XML 文档推理架构](inferring-schemas-from-xml-documents.md)。</span><span class="sxs-lookup"><span data-stu-id="52b8c-199">For more information about the schema inference process, see [Inferring Schemas from XML Documents](inferring-schemas-from-xml-documents.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52b8c-200">请参阅</span><span class="sxs-lookup"><span data-stu-id="52b8c-200">See also</span></span>

- <xref:System.Xml.Schema.XmlSchemaInference>
- [<span data-ttu-id="52b8c-201">XML 架构对象模型 (SOM)</span><span class="sxs-lookup"><span data-stu-id="52b8c-201">XML Schema Object Model (SOM)</span></span>](xml-schema-object-model-som.md)
- [<span data-ttu-id="52b8c-202">推断 XML 架构</span><span class="sxs-lookup"><span data-stu-id="52b8c-202">Inferring an XML Schema</span></span>](inferring-an-xml-schema.md)
- [<span data-ttu-id="52b8c-203">从 XML 文档推断架构</span><span class="sxs-lookup"><span data-stu-id="52b8c-203">Inferring Schemas from XML Documents</span></span>](inferring-schemas-from-xml-documents.md)
- [<span data-ttu-id="52b8c-204">推断简单类型的规则</span><span class="sxs-lookup"><span data-stu-id="52b8c-204">Rules for Inferring Simple Types</span></span>](rules-for-inferring-simple-types.md)
