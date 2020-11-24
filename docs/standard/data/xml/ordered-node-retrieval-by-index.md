---
title: 按索引检索已排序节点
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5412c90f-2703-4aa8-a9c4-1b8a35183c37
ms.openlocfilehash: 73c31c5249262fe9b6624201bc5b9bd6b1374d1e
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "94823740"
---
# <a name="ordered-node-retrieval-by-index"></a><span data-ttu-id="ad175-102">按索引检索已排序节点</span><span class="sxs-lookup"><span data-stu-id="ad175-102">Ordered Node Retrieval by Index</span></span>
<span data-ttu-id="ad175-103">万维网联合会 (W3C) XML 文档对象模型 (DOM) 还描述了 NodeList，它能够处理已排序节点列表（与 XmlNamedNodeMap  处理的未排序集相对）。</span><span class="sxs-lookup"><span data-stu-id="ad175-103">The World Wide Web Consortium (W3C) XML Document Object Model (DOM) also describes a NodeList, which has the ability to handle an ordered list of nodes, as opposed to the unordered set handled by the **XmlNamedNodeMap**.</span></span> <span data-ttu-id="ad175-104">NodeList 在 Microsoft .NET Framework 中称为 XmlNodeList  。</span><span class="sxs-lookup"><span data-stu-id="ad175-104">The NodeList in the Microsoft .NET Framework is called **XmlNodeList**.</span></span> <span data-ttu-id="ad175-105">返回 XmlNodeList  的方法和属性包括：</span><span class="sxs-lookup"><span data-stu-id="ad175-105">Methods and properties that return an **XmlNodeList** are:</span></span>  
  
- <span data-ttu-id="ad175-106">XmlNode.ChildNodes</span><span class="sxs-lookup"><span data-stu-id="ad175-106">XmlNode.ChildNodes</span></span>  
  
- <span data-ttu-id="ad175-107">XmlDocument.GetElementsByTagName</span><span class="sxs-lookup"><span data-stu-id="ad175-107">XmlDocument.GetElementsByTagName</span></span>  
  
- <span data-ttu-id="ad175-108">XmlElement.GetElementsByTagName</span><span class="sxs-lookup"><span data-stu-id="ad175-108">XmlElement.GetElementsByTagName</span></span>  
  
- <span data-ttu-id="ad175-109">XmlNode.SelectNodes</span><span class="sxs-lookup"><span data-stu-id="ad175-109">XmlNode.SelectNodes</span></span>  
  
 <span data-ttu-id="ad175-110">XmlNodeList  包含的 Count  属性可用于编写循环，以循环访问 XmlNodeList  中的节点，如下面的代码示例所示：</span><span class="sxs-lookup"><span data-stu-id="ad175-110">The **XmlNodeList** has a **Count** property that can be used to write loops to iterate over the nodes in the **XmlNodeList**, as shown in the following code sample:</span></span>  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
   doc.Load("books.xml")  
  
    ' Retrieve all book titles.  
    Dim root as XmlElement = doc.DocumentElement  
    Dim elemList as XmlNodeList = root.GetElementsByTagName("title")  
    Dim i as integer  
    for i=0  to elemList.Count-1  
        ' Display all book titles in the Node List.  
        Console.WriteLine(elemList.ItemOf(i).InnerXml)  
    next  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.Load("books.xml");  
// Retrieve all book titles.  
XmlElement root = doc.DocumentElement;  
XmlNodeList elemList = root.GetElementsByTagName("title");  
for (int i=0; i < elemList.Count; i++)  
{
   // Display all book titles in the Node List.  
   Console.WriteLine(elemList[i].InnerXml);  
}
```  
  
 <span data-ttu-id="ad175-111">除了 Count  属性外，还有一个 GetEnumerator  方法提供对 XmlNodeList  中的节点集合的 `foreach` 式循环访问。</span><span class="sxs-lookup"><span data-stu-id="ad175-111">In addition to the **Count** property, there is a **GetEnumerator** method that provides a, `foreach` style iteration over the collection of nodes in the **XmlNodeList**.</span></span> <span data-ttu-id="ad175-112">下面的代码示例显示如何使用 `foreach` 语句。</span><span class="sxs-lookup"><span data-stu-id="ad175-112">The following code example shows the use of the `foreach` statement.</span></span>  
  
```vb  
Dim doc As New XmlDocument()  
doc.Load("books.xml")  
  
' Get book titles.  
Dim root As XmlElement = doc.DocumentElement  
Dim elemList As XmlNodeList = root.GetElementsByTagName("title")  
Dim ienum As IEnumerator = elemList.GetEnumerator()  
' Loop over the XmlNodeList using the enumerator ienum
While ienum.MoveNext()  
    ' Display the book title.  
    Dim title As XmlNode = CType(ienum.Current, XmlNode)  
    Console.WriteLine(title.InnerText)  
End While  
```  
  
```csharp  
{  
     XmlDocument doc = new XmlDocument();  
     doc.Load("books.xml");  
  
     // Get book titles.  
     XmlElement root = doc.DocumentElement;  
     XmlNodeList elemList = root.GetElementsByTagName("title");  
     IEnumerator ienum = elemList.GetEnumerator();
     // Loop over the XmlNodeList using the enumerator ienum
     while (ienum.MoveNext())  
     {  
          // Display the book title.  
           XmlNode title = (XmlNode) ienum.Current;  
           Console.WriteLine(title.InnerText);  
     }  
  }  
```  
  
 <span data-ttu-id="ad175-113">有关 XmlNodeList  中可用方法和属性的更多信息，请参见 <xref:System.Xml.XmlNodeList>。</span><span class="sxs-lookup"><span data-stu-id="ad175-113">For more information on the methods and properties available on the **XmlNodeList**, see <xref:System.Xml.XmlNodeList>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad175-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="ad175-114">See also</span></span>

- [<span data-ttu-id="ad175-115">XML 文档对象模型 (DOM)</span><span class="sxs-lookup"><span data-stu-id="ad175-115">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
