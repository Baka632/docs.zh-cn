---
title: 使用 XPathNavigator 选择 XML 数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c268c49e-32b9-4171-b782-dcb7b065fa73
ms.openlocfilehash: 791c1d16db6a2079ccccebf4dc33d5a0eb12d3c5
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824969"
---
# <a name="select-xml-data-using-xpathnavigator"></a><span data-ttu-id="685b8-102">使用 XPathNavigator 选择 XML 数据</span><span class="sxs-lookup"><span data-stu-id="685b8-102">Select XML Data Using XPathNavigator</span></span>
<span data-ttu-id="685b8-103"><xref:System.Xml.XPath.XPathNavigator> 类提供一组方法，用于使用 XPath 表达式在 <xref:System.Xml.XPath.XPathDocument> 或 <xref:System.Xml.XmlDocument> 对象中选择节点集。</span><span class="sxs-lookup"><span data-stu-id="685b8-103">The <xref:System.Xml.XPath.XPathNavigator> class provides a set of methods used to select a set of nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using an XPath expression.</span></span> <span data-ttu-id="685b8-104">选择后，可以循环访问所选的节点集。</span><span class="sxs-lookup"><span data-stu-id="685b8-104">Once selected, you can iterate over the selected set of nodes.</span></span>  
  
## <a name="xpathnavigator-selection-methods"></a><span data-ttu-id="685b8-105">XPathNavigator 选择方法</span><span class="sxs-lookup"><span data-stu-id="685b8-105">XPathNavigator Selection Methods</span></span>  
 <span data-ttu-id="685b8-106"><xref:System.Xml.XPath.XPathNavigator> 类提供一组方法，用于使用 XPath 表达式在 <xref:System.Xml.XPath.XPathDocument> 或 <xref:System.Xml.XmlDocument> 对象中选择节点集。</span><span class="sxs-lookup"><span data-stu-id="685b8-106">The <xref:System.Xml.XPath.XPathNavigator> class provides a set of methods used to select a set of nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using an XPath expression.</span></span> <span data-ttu-id="685b8-107"><xref:System.Xml.XPath.XPathNavigator> 类还提供一组经过优化的方法，选择上级节点、子节点和子代节点的速度比使用 XPath 表达式更快。</span><span class="sxs-lookup"><span data-stu-id="685b8-107">The <xref:System.Xml.XPath.XPathNavigator> class also provides a set of optimized methods for selecting ancestor, child and descendant nodes faster than using an XPath expression.</span></span> <span data-ttu-id="685b8-108">如果选择单个节点，所选的节点集将在 <xref:System.Xml.XPath.XPathNodeIterator> 对象或 <xref:System.Xml.XPath.XPathNavigator> 对象中返回。</span><span class="sxs-lookup"><span data-stu-id="685b8-108">The selected set of nodes is returned in an <xref:System.Xml.XPath.XPathNodeIterator> object or an <xref:System.Xml.XPath.XPathNavigator> object in the case of a single selected node.</span></span>  
  
### <a name="selecting-nodes-using-xpath-expressions"></a><span data-ttu-id="685b8-109">使用 XPath 表达式选择节点</span><span class="sxs-lookup"><span data-stu-id="685b8-109">Selecting Nodes Using XPath Expressions</span></span>  
 <span data-ttu-id="685b8-110">要使用 XPath 表达式选择节点集，请使用下列选择方法之一。</span><span class="sxs-lookup"><span data-stu-id="685b8-110">To select a set of nodes using an XPath expression, use one of the following selection methods.</span></span>  
  
- <xref:System.Xml.XPath.XPathNavigator.Select%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A>  
  
 <span data-ttu-id="685b8-111">在调用时，如果选择单个节点，这些方法将返回一组节点，您可以使用 <xref:System.Xml.XPath.XPathNodeIterator> 对象或 <xref:System.Xml.XPath.XPathNavigator> 对象随意浏览。</span><span class="sxs-lookup"><span data-stu-id="685b8-111">When called, these methods return a set of nodes that you can navigate freely using an <xref:System.Xml.XPath.XPathNodeIterator> object or an <xref:System.Xml.XPath.XPathNavigator> object in the case of a single selected node.</span></span>  
  
 <span data-ttu-id="685b8-112">使用 <xref:System.Xml.XPath.XPathNodeIterator> 对象浏览不会影响用于创建该对象的 <xref:System.Xml.XPath.XPathNavigator> 对象的位置。</span><span class="sxs-lookup"><span data-stu-id="685b8-112">Navigating with an <xref:System.Xml.XPath.XPathNodeIterator> object does not affect the position of the <xref:System.Xml.XPath.XPathNavigator> object used to create it.</span></span> <span data-ttu-id="685b8-113">从 <xref:System.Xml.XPath.XPathNavigator> 方法返回的 <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A> 对象位于单个返回的节点上，同样不会影响用于创建该对象的 <xref:System.Xml.XPath.XPathNavigator> 对象的位置。</span><span class="sxs-lookup"><span data-stu-id="685b8-113">The <xref:System.Xml.XPath.XPathNavigator> object returned from the <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A> methods is positioned on the single returned node and also does not affect the position of the <xref:System.Xml.XPath.XPathNavigator> object used to create it.</span></span>  
  
 <span data-ttu-id="685b8-114">以下示例显示如何通过 <xref:System.Xml.XPath.XPathNavigator> 对象创建 <xref:System.Xml.XPath.XPathDocument> 对象、如何使用 <xref:System.Xml.XPath.XPathNavigator.Select%2A> 方法选择 <xref:System.Xml.XPath.XPathDocument> 对象中的节点以及如何使用 <xref:System.Xml.XPath.XPathNodeIterator> 对象循环访问所选的节点。</span><span class="sxs-lookup"><span data-stu-id="685b8-114">The following example shows the creation of an <xref:System.Xml.XPath.XPathNavigator> object from an <xref:System.Xml.XPath.XPathDocument> object, the use of the <xref:System.Xml.XPath.XPathNavigator.Select%2A> method to select nodes in the <xref:System.Xml.XPath.XPathDocument> object, and the use of the <xref:System.Xml.XPath.XPathNodeIterator> object to iterate over the selected nodes.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
Dim nodes As XPathNodeIterator = navigator.Select("/bookstore/book")  
  
While nodes.MoveNext()  
    Console.WriteLine(nodes.Current.Name)  
End While  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
XPathNodeIterator nodes = navigator.Select("/bookstore/book");  
  
while(nodes.MoveNext())  
{  
    Console.WriteLine(nodes.Current.Name);  
}  
```  
  
 <span data-ttu-id="685b8-115">该示例使用 `books.xml` 文件作为输入。</span><span class="sxs-lookup"><span data-stu-id="685b8-115">The example takes the `books.xml` file as input.</span></span>  
  
 [!code-xml[XPathXMLExamples#1](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/books.xml#1)]  
  
### <a name="optimized-selection-methods"></a><span data-ttu-id="685b8-116">经过优化的选择方法</span><span class="sxs-lookup"><span data-stu-id="685b8-116">Optimized Selection Methods</span></span>  
 <span data-ttu-id="685b8-117"><xref:System.Xml.XPath.XPathNavigator.SelectChildren%2A> 类的 <xref:System.Xml.XPath.XPathNavigator.SelectAncestors%2A>、<xref:System.Xml.XPath.XPathNavigator.SelectDescendants%2A> 和 <xref:System.Xml.XPath.XPathNavigator> 方法表示通常用于检索子节点、子代节点和上级节点的 XPath 表达式。</span><span class="sxs-lookup"><span data-stu-id="685b8-117">The <xref:System.Xml.XPath.XPathNavigator.SelectChildren%2A>, <xref:System.Xml.XPath.XPathNavigator.SelectAncestors%2A>, and <xref:System.Xml.XPath.XPathNavigator.SelectDescendants%2A> methods of the <xref:System.Xml.XPath.XPathNavigator> class represent XPath expressions commonly used to retrieve child, descendant, and ancestor nodes.</span></span> <span data-ttu-id="685b8-118">这些方法的性能已得到优化，比相应的 XPath 表达式速度更快。</span><span class="sxs-lookup"><span data-stu-id="685b8-118">These methods are optimized for performance and are faster than their corresponding XPath expressions.</span></span> <span data-ttu-id="685b8-119"><xref:System.Xml.XPath.XPathNavigator.SelectChildren%2A>、<xref:System.Xml.XPath.XPathNavigator.SelectAncestors%2A> 和 <xref:System.Xml.XPath.XPathNavigator.SelectDescendants%2A> 方法基于 <xref:System.Xml.XPath.XPathNodeType> 值或要选择的节点的本地名称和命名空间 URI 选择上级节点、子节点和子代节点。</span><span class="sxs-lookup"><span data-stu-id="685b8-119">The <xref:System.Xml.XPath.XPathNavigator.SelectChildren%2A>, <xref:System.Xml.XPath.XPathNavigator.SelectAncestors%2A>, and <xref:System.Xml.XPath.XPathNavigator.SelectDescendants%2A> methods selects ancestor, child, and descendant nodes based on an <xref:System.Xml.XPath.XPathNodeType> value or the local name and namespace URI of the nodes to select.</span></span> <span data-ttu-id="685b8-120">所选的上级节点、子节点和子代节点将在 <xref:System.Xml.XPath.XPathNodeIterator> 对象中返回。</span><span class="sxs-lookup"><span data-stu-id="685b8-120">The selected ancestor, child, and descendant nodes are returned in an <xref:System.Xml.XPath.XPathNodeIterator> object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="685b8-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="685b8-121">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="685b8-122">使用 XPath 数据模型处理 XML 数据</span><span class="sxs-lookup"><span data-stu-id="685b8-122">Process XML Data Using the XPath Data Model</span></span>](process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="685b8-123">使用 XPathNavigator 计算 XPath 表达式</span><span class="sxs-lookup"><span data-stu-id="685b8-123">Evaluate XPath Expressions using XPathNavigator</span></span>](evaluate-xpath-expressions-using-xpathnavigator.md)
- [<span data-ttu-id="685b8-124">使用 XPathNavigator 匹配节点</span><span class="sxs-lookup"><span data-stu-id="685b8-124">Matching Nodes using XPathNavigator</span></span>](matching-nodes-using-xpathnavigator.md)
- [<span data-ttu-id="685b8-125">XPath 查询识别的节点类型</span><span class="sxs-lookup"><span data-stu-id="685b8-125">Node Types Recognized with XPath Queries</span></span>](node-types-recognized-with-xpath-queries.md)
- [<span data-ttu-id="685b8-126">XPath 查询和命名空间</span><span class="sxs-lookup"><span data-stu-id="685b8-126">XPath Queries and Namespaces</span></span>](xpath-queries-and-namespaces.md)
- [<span data-ttu-id="685b8-127">已编译的 XPath 表达式</span><span class="sxs-lookup"><span data-stu-id="685b8-127">Compiled XPath Expressions</span></span>](compiled-xpath-expressions.md)
