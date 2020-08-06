---
title: XDocument 类概述 (C#)
description: C# 中的 XDocument 类包含有效的 XML 文档所需的信息，其中包括 XML 声明、处理指令和注释。
ms.date: 07/20/2015
ms.assetid: 63305603-ab54-49fc-84e4-f76eecc59549
ms.openlocfilehash: 6d522cef25e99e4a5ea54e644855c8dfa7a05f4a
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302186"
---
# <a name="xdocument-class-overview-c"></a><span data-ttu-id="88a91-103">XDocument 类概述 (C#)</span><span class="sxs-lookup"><span data-stu-id="88a91-103">XDocument Class Overview (C#)</span></span>
<span data-ttu-id="88a91-104">本主题介绍 <xref:System.Xml.Linq.XDocument> 类。</span><span class="sxs-lookup"><span data-stu-id="88a91-104">This topic introduces the <xref:System.Xml.Linq.XDocument> class.</span></span>  
  
## <a name="overview-of-the-xdocument-class"></a><span data-ttu-id="88a91-105">XDocument 类概述</span><span class="sxs-lookup"><span data-stu-id="88a91-105">Overview of the XDocument class</span></span>  
 <span data-ttu-id="88a91-106"><xref:System.Xml.Linq.XDocument> 类包含有效的 XML 文档所需的信息。</span><span class="sxs-lookup"><span data-stu-id="88a91-106">The <xref:System.Xml.Linq.XDocument> class contains the information necessary for a valid XML document.</span></span> <span data-ttu-id="88a91-107">其中包括 XML 声明、处理指令和注释。</span><span class="sxs-lookup"><span data-stu-id="88a91-107">This includes an XML declaration, processing instructions, and comments.</span></span>  
  
 <span data-ttu-id="88a91-108">请注意，如果需要 <xref:System.Xml.Linq.XDocument> 类提供的特定功能，您只需创建 <xref:System.Xml.Linq.XDocument> 对象。</span><span class="sxs-lookup"><span data-stu-id="88a91-108">Note that you only have to create <xref:System.Xml.Linq.XDocument> objects if you require the specific functionality provided by the <xref:System.Xml.Linq.XDocument> class.</span></span> <span data-ttu-id="88a91-109">在很多情况下，可以直接使用 <xref:System.Xml.Linq.XElement>。</span><span class="sxs-lookup"><span data-stu-id="88a91-109">In many circumstances, you can work directly with <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="88a91-110">直接使用 <xref:System.Xml.Linq.XElement> 是一种比较简单的编程模型。</span><span class="sxs-lookup"><span data-stu-id="88a91-110">Working directly with <xref:System.Xml.Linq.XElement> is a simpler programming model.</span></span>  
  
 <span data-ttu-id="88a91-111"><xref:System.Xml.Linq.XDocument> 派生自 <xref:System.Xml.Linq.XContainer>。</span><span class="sxs-lookup"><span data-stu-id="88a91-111"><xref:System.Xml.Linq.XDocument> derives from <xref:System.Xml.Linq.XContainer>.</span></span> <span data-ttu-id="88a91-112">因此，它可以包含子节点。</span><span class="sxs-lookup"><span data-stu-id="88a91-112">Therefore, it can contain child nodes.</span></span> <span data-ttu-id="88a91-113">但是，<xref:System.Xml.Linq.XDocument> 对象只能有一个子 <xref:System.Xml.Linq.XElement> 节点。</span><span class="sxs-lookup"><span data-stu-id="88a91-113">However, <xref:System.Xml.Linq.XDocument> objects can have only one child <xref:System.Xml.Linq.XElement> node.</span></span> <span data-ttu-id="88a91-114">这反映了 XML 标准，即在 XML 文档中只能有一个根元素。</span><span class="sxs-lookup"><span data-stu-id="88a91-114">This reflects the XML standard that there can be only one root element in an XML document.</span></span>  
  
## <a name="components-of-xdocument"></a><span data-ttu-id="88a91-115">Xdocument 的组件</span><span class="sxs-lookup"><span data-stu-id="88a91-115">Components of XDocument</span></span>  
 <span data-ttu-id="88a91-116"><xref:System.Xml.Linq.XDocument> 可以包含以下元素：</span><span class="sxs-lookup"><span data-stu-id="88a91-116">An <xref:System.Xml.Linq.XDocument> can contain the following elements:</span></span>  
  
- <span data-ttu-id="88a91-117">一个 <xref:System.Xml.Linq.XDeclaration> 对象。</span><span class="sxs-lookup"><span data-stu-id="88a91-117">One <xref:System.Xml.Linq.XDeclaration> object.</span></span> <span data-ttu-id="88a91-118"><xref:System.Xml.Linq.XDeclaration> 使您能够指定 XML 声明的相关部分：XML 版本、文档的编码以及 XML 文档是否是独立的。</span><span class="sxs-lookup"><span data-stu-id="88a91-118"><xref:System.Xml.Linq.XDeclaration> enables you to specify the pertinent parts of an XML declaration: the XML version, the encoding of the document, and whether the XML document is stand-alone.</span></span>  
  
- <span data-ttu-id="88a91-119">一个 <xref:System.Xml.Linq.XElement> 对象。</span><span class="sxs-lookup"><span data-stu-id="88a91-119">One <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="88a91-120">这是 XML 文档的根节点。</span><span class="sxs-lookup"><span data-stu-id="88a91-120">This is the root node of the XML document.</span></span>  
  
- <span data-ttu-id="88a91-121">任意数目的 <xref:System.Xml.Linq.XProcessingInstruction> 对象。</span><span class="sxs-lookup"><span data-stu-id="88a91-121">Any number of <xref:System.Xml.Linq.XProcessingInstruction> objects.</span></span> <span data-ttu-id="88a91-122">处理指令将信息传递给处理 XML 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="88a91-122">A processing instruction communicates information to an application that processes the XML.</span></span>  
  
- <span data-ttu-id="88a91-123">任意数目的 <xref:System.Xml.Linq.XComment> 对象。</span><span class="sxs-lookup"><span data-stu-id="88a91-123">Any number of <xref:System.Xml.Linq.XComment> objects.</span></span> <span data-ttu-id="88a91-124">注释将与根元素同级。</span><span class="sxs-lookup"><span data-stu-id="88a91-124">The comments will be siblings to the root element.</span></span> <span data-ttu-id="88a91-125"><xref:System.Xml.Linq.XComment> 对象不能是列表中的第一个参数，因为 XML 文档以注释开头无效。</span><span class="sxs-lookup"><span data-stu-id="88a91-125">The <xref:System.Xml.Linq.XComment> object cannot be the first argument in the list, because it is not valid for an XML document to start with a comment.</span></span>  
  
- <span data-ttu-id="88a91-126">一个用于 DTD 的 <xref:System.Xml.Linq.XDocumentType>。</span><span class="sxs-lookup"><span data-stu-id="88a91-126">One <xref:System.Xml.Linq.XDocumentType> for the DTD.</span></span>  
  
 <span data-ttu-id="88a91-127">序列化 <xref:System.Xml.Linq.XDocument> 时，即使 `XDocument.Declaration` 为 `null`，输出也将具有 XML 声明，前提是编写器已经将 `Writer.Settings.OmitXmlDeclaration` 设置为 `false`（默认值）。</span><span class="sxs-lookup"><span data-stu-id="88a91-127">When you serialize an <xref:System.Xml.Linq.XDocument>, even if `XDocument.Declaration` is `null`, the output will have an XML declaration if the writer has `Writer.Settings.OmitXmlDeclaration` set to `false` (the default).</span></span>  
  
 <span data-ttu-id="88a91-128">默认情况下，[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 将版本设置为“1.0”，将编码设置为“utf-8”。</span><span class="sxs-lookup"><span data-stu-id="88a91-128">By default, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] sets the version to "1.0", and sets the encoding to "utf-8".</span></span>  
  
## <a name="using-xelement-without-xdocument"></a><span data-ttu-id="88a91-129">在没有 Xdocument 的情况下使用 XElement</span><span class="sxs-lookup"><span data-stu-id="88a91-129">Using XElement without XDocument</span></span>  
 <span data-ttu-id="88a91-130">如上所述，<xref:System.Xml.Linq.XElement> 类是 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 编程接口中的主类。</span><span class="sxs-lookup"><span data-stu-id="88a91-130">As previously mentioned, the <xref:System.Xml.Linq.XElement> class is the main class in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] programming interface.</span></span> <span data-ttu-id="88a91-131">在很多情况下，您的应用程序不需要您创建文档。</span><span class="sxs-lookup"><span data-stu-id="88a91-131">In many cases, your application will not require that you create a document.</span></span> <span data-ttu-id="88a91-132">通过使用 <xref:System.Xml.Linq.XElement> 类，可以创建 XML 树，向它添加其他 XML 树，修改 XML 树并进行保存。</span><span class="sxs-lookup"><span data-stu-id="88a91-132">By using the <xref:System.Xml.Linq.XElement> class, you can create an XML tree, add other XML trees to it, modify the XML tree, and save it.</span></span>  
  
## <a name="using-xdocument"></a><span data-ttu-id="88a91-133">使用 XDocument</span><span class="sxs-lookup"><span data-stu-id="88a91-133">Using XDocument</span></span>  
 <span data-ttu-id="88a91-134">若要构造一个 <xref:System.Xml.Linq.XDocument>，可使用函数构造，正如您构造 <xref:System.Xml.Linq.XElement> 对象那样。</span><span class="sxs-lookup"><span data-stu-id="88a91-134">To construct an <xref:System.Xml.Linq.XDocument>, use functional construction, just like you do to construct <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="88a91-135">下面的代码创建一个 <xref:System.Xml.Linq.XDocument> 对象及其关联的包含对象。</span><span class="sxs-lookup"><span data-stu-id="88a91-135">The following code creates an <xref:System.Xml.Linq.XDocument> object and its associated contained objects.</span></span>  
  
```csharp  
XDocument d = new XDocument(  
    new XComment("This is a comment."),  
    new XProcessingInstruction("xml-stylesheet",  
        "href='mystyle.css' title='Compact' type='text/css'"),  
    new XElement("Pubs",  
        new XElement("Book",  
            new XElement("Title", "Artifacts of Roman Civilization"),  
            new XElement("Author", "Moreno, Jordao")  
        ),  
        new XElement("Book",  
            new XElement("Title", "Midieval Tools and Implements"),  
            new XElement("Author", "Gazit, Inbar")  
        )  
    ),  
    new XComment("This is another comment.")  
);  
d.Declaration = new XDeclaration("1.0", "utf-8", "true");  
Console.WriteLine(d);  
  
d.Save("test.xml");  
```  
  
 <span data-ttu-id="88a91-136">当你检查文件 test.xml 时, 会得到以下输出：</span><span class="sxs-lookup"><span data-stu-id="88a91-136">When you examine the file test.xml, you get the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<!--This is a comment.-->  
<?xml-stylesheet href='mystyle.css' title='Compact' type='text/css'?>  
<Pubs>  
  <Book>  
    <Title>Artifacts of Roman Civilization</Title>  
    <Author>Moreno, Jordao</Author>  
  </Book>  
  <Book>  
    <Title>Midieval Tools and Implements</Title>  
    <Author>Gazit, Inbar</Author>  
  </Book>  
</Pubs>  
<!--This is another comment.-->  
```  
  
## <a name="see-also"></a><span data-ttu-id="88a91-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="88a91-137">See also</span></span>

- [<span data-ttu-id="88a91-138">LINQ to XML 编程概述 (C#)</span><span class="sxs-lookup"><span data-stu-id="88a91-138">LINQ to XML Programming Overview (C#)</span></span>](./linq-to-xml-overview.md)
