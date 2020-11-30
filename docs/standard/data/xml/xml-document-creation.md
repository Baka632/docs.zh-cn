---
title: 创建 XML 文档
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 877e9c62-b082-4bfb-bc5b-f47297eb30ef
ms.openlocfilehash: 18c391e33e0c43f2407ccbc87c12b6c25a12509d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686522"
---
# <a name="xml-document-creation"></a><span data-ttu-id="078d1-102">创建 XML 文档</span><span class="sxs-lookup"><span data-stu-id="078d1-102">XML Document Creation</span></span>

<span data-ttu-id="078d1-103">有两种创建 XML 文档的方法。</span><span class="sxs-lookup"><span data-stu-id="078d1-103">There are two ways to create an XML document.</span></span> <span data-ttu-id="078d1-104">一种方法是，创建不含参数的 XmlDocument  。</span><span class="sxs-lookup"><span data-stu-id="078d1-104">One way is to create an **XmlDocument** with no parameters.</span></span> <span data-ttu-id="078d1-105">另一种方法是，创建 XmlDocument  ，并向它传递 XmlNameTable 参数。</span><span class="sxs-lookup"><span data-stu-id="078d1-105">The other way is to create an **XmlDocument** and pass it an XmlNameTable as a parameter.</span></span> <span data-ttu-id="078d1-106">下面的示例展示了如何不使用任何参数新建空 XmlDocument  。</span><span class="sxs-lookup"><span data-stu-id="078d1-106">The following example shows how to create a new, empty **XmlDocument** using no parameters.</span></span>  
  
```vb  
Dim doc As New XmlDocument()  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
```  
  
 <span data-ttu-id="078d1-107">创建文档后，可以使用 Load  方法在文档中加载字符串、流、URL、文本读取器或 XmlReader  派生类中的数据。</span><span class="sxs-lookup"><span data-stu-id="078d1-107">Once a document is created, you can load it with data from a string, stream, URL, text reader, or an **XmlReader** derived class using the **Load** method.</span></span> <span data-ttu-id="078d1-108">还有另一种加载方法 LoadXML  方法，可用于从字符串中读取 XML。</span><span class="sxs-lookup"><span data-stu-id="078d1-108">There is also another load method, the **LoadXML** method, which reads XML from a string.</span></span> <span data-ttu-id="078d1-109">若要详细了解各种 Load  方法，请参阅[将 XML 文档读取到 DOM 中](reading-an-xml-document-into-the-dom.md)。</span><span class="sxs-lookup"><span data-stu-id="078d1-109">For more information on the various **Load** methods, see [Reading an XML Document into the DOM](reading-an-xml-document-into-the-dom.md).</span></span>  
  
 <span data-ttu-id="078d1-110">有一个类名为 XmlNameTable  。</span><span class="sxs-lookup"><span data-stu-id="078d1-110">There is a class called the **XmlNameTable**.</span></span> <span data-ttu-id="078d1-111">此类是原子化字符串对象的表。</span><span class="sxs-lookup"><span data-stu-id="078d1-111">This class is a table of atomized string objects.</span></span> <span data-ttu-id="078d1-112">该表使 XML 分析器可以高效地对 XML 文档中所有重复的元素和属性的名称使用相同的字符串对象。</span><span class="sxs-lookup"><span data-stu-id="078d1-112">This table provides an efficient means for the XML parser to use the same string object for all repeated element and attribute names in an XML document.</span></span> <span data-ttu-id="078d1-113">XmlNameTable  在文档创建（如上所示）时自动创建，并在文档加载时加载属性名和元素名称。</span><span class="sxs-lookup"><span data-stu-id="078d1-113">An **XmlNameTable** is automatically created when a document is created as shown above and is loaded with attribute and element names when the document is loaded.</span></span> <span data-ttu-id="078d1-114">如果已有包含名称表的文档，且这些名称在另一个文档中很有用，可以使用需要使用 XmlNameTable  参数的 Load  方法新建文档。</span><span class="sxs-lookup"><span data-stu-id="078d1-114">If you already have a document with a name table, and those names would be useful in another document, you can create a new document using the **Load** method that takes an **XmlNameTable** as a parameter.</span></span> <span data-ttu-id="078d1-115">使用此方法创建文档时，它使用现有 XmlNameTable  ，其中包含已从其他文档加载到其中的所有属性和元素。</span><span class="sxs-lookup"><span data-stu-id="078d1-115">When the document is created with this method, it uses the existing **XmlNameTable** with all the attributes and elements already loaded into it from the other document.</span></span> <span data-ttu-id="078d1-116">它可用于有效地比较元素和属性的名称。</span><span class="sxs-lookup"><span data-stu-id="078d1-116">It can be used for efficiently comparing element and attribute names.</span></span> <span data-ttu-id="078d1-117">若要详细了解 XmlNameTable  ，请参阅[使用 XmlNameTable 比较对象](object-comparison-using-xmlnametable.md)。</span><span class="sxs-lookup"><span data-stu-id="078d1-117">For more information on the **XmlNameTable**, see [Object Comparison Using XmlNameTable](object-comparison-using-xmlnametable.md).</span></span> <span data-ttu-id="078d1-118">有关参考，请参阅 <xref:System.Xml.XmlNameTable>。</span><span class="sxs-lookup"><span data-stu-id="078d1-118">For reference, see <xref:System.Xml.XmlNameTable>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="078d1-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="078d1-119">See also</span></span>

- [<span data-ttu-id="078d1-120">XML 文档对象模型 (DOM)</span><span class="sxs-lookup"><span data-stu-id="078d1-120">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
