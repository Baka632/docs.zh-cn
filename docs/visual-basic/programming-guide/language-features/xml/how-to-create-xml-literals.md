---
title: 如何：创建 XML 文本
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
ms.openlocfilehash: c7ad8d684dde31550b6e1b74c098d152b227f6c1
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058217"
---
# <a name="how-to-create-xml-literals-visual-basic"></a><span data-ttu-id="750c5-102">如何：创建 XML 文本 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="750c5-102">How to: Create XML Literals (Visual Basic)</span></span>

<span data-ttu-id="750c5-103">您可以使用 XML 文本直接在代码中创建 XML 文档、片段或元素。</span><span class="sxs-lookup"><span data-stu-id="750c5-103">You can create an XML document, fragment, or element directly in code by using an XML literal.</span></span> <span data-ttu-id="750c5-104">本主题中的示例演示如何创建包含三个子元素的 XML 元素以及如何创建 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="750c5-104">The examples in this topic demonstrate how to create an XML element that has three child elements, and how to create an XML document.</span></span>  
  
 <span data-ttu-id="750c5-105">你还可以使用 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] api 来创建 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 对象。</span><span class="sxs-lookup"><span data-stu-id="750c5-105">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="750c5-106">有关详细信息，请参阅 <xref:System.Xml.Linq.XElement>。</span><span class="sxs-lookup"><span data-stu-id="750c5-106">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
### <a name="to-create-an-xml-element"></a><span data-ttu-id="750c5-107">创建 XML 元素</span><span class="sxs-lookup"><span data-stu-id="750c5-107">To create an XML element</span></span>  
  
- <span data-ttu-id="750c5-108">使用 XML 文本语法（与实际 XML 语法相同）创建 XML 内联。</span><span class="sxs-lookup"><span data-stu-id="750c5-108">Create the XML inline by using the XML literal syntax, which is the same as the actual XML syntax.</span></span>  
  
     [!code-vb[VbXMLSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
     <span data-ttu-id="750c5-109">运行代码。</span><span class="sxs-lookup"><span data-stu-id="750c5-109">Run the code.</span></span> <span data-ttu-id="750c5-110">此代码的输出为：</span><span class="sxs-lookup"><span data-stu-id="750c5-110">The output of this code is:</span></span>  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a><span data-ttu-id="750c5-111">创建 XML 文档</span><span class="sxs-lookup"><span data-stu-id="750c5-111">To create an XML document</span></span>  
  
- <span data-ttu-id="750c5-112">以内联方式创建 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="750c5-112">Create the XML document inline.</span></span> <span data-ttu-id="750c5-113">下面的代码创建一个 XML 文档，该文档具有文本语法、XML 声明、处理指令、注释以及包含其他元素的元素。</span><span class="sxs-lookup"><span data-stu-id="750c5-113">The following code creates an XML document that has literal syntax, an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
     [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
     <span data-ttu-id="750c5-114">运行代码。</span><span class="sxs-lookup"><span data-stu-id="750c5-114">Run the code.</span></span> <span data-ttu-id="750c5-115">此代码的输出为：</span><span class="sxs-lookup"><span data-stu-id="750c5-115">The output of this code is:</span></span>  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works. -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## <a name="see-also"></a><span data-ttu-id="750c5-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="750c5-116">See also</span></span>

- [<span data-ttu-id="750c5-117">XML</span><span class="sxs-lookup"><span data-stu-id="750c5-117">XML</span></span>](index.md)
- [<span data-ttu-id="750c5-118">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="750c5-118">Creating XML in Visual Basic</span></span>](creating-xml.md)
- [<span data-ttu-id="750c5-119">XML 元素文本</span><span class="sxs-lookup"><span data-stu-id="750c5-119">XML Element Literal</span></span>](../../../language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="750c5-120">XML 文档文本</span><span class="sxs-lookup"><span data-stu-id="750c5-120">XML Document Literal</span></span>](../../../language-reference/xml-literals/xml-document-literal.md)
