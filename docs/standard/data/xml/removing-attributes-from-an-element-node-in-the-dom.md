---
title: 移除 DOM 中元素节点的属性
ms.date: 03/30/2017
ms.assetid: 7ede6f9e-a3ac-49a4-8488-ab8360a44aa4
ms.openlocfilehash: 53922c55295e852a1aa62d847313fbd657a42541
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686756"
---
# <a name="removing-attributes-from-an-element-node-in-the-dom"></a><span data-ttu-id="2da2d-102">移除 DOM 中元素节点的属性</span><span class="sxs-lookup"><span data-stu-id="2da2d-102">Removing Attributes from an Element Node in the DOM</span></span>

<span data-ttu-id="2da2d-103">有多种方法可以移除属性。</span><span class="sxs-lookup"><span data-stu-id="2da2d-103">There are many ways to remove attributes.</span></span> <span data-ttu-id="2da2d-104">一种方法是从属性集合中移除它们。</span><span class="sxs-lookup"><span data-stu-id="2da2d-104">One technique is to remove them from the attribute collection.</span></span> <span data-ttu-id="2da2d-105">为此，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="2da2d-105">To do this, the following steps are performed:</span></span>  
  
1. <span data-ttu-id="2da2d-106">使用 `XmlAttributeCollection attrs = elem.Attributes;` 获取元素的属性集合。</span><span class="sxs-lookup"><span data-stu-id="2da2d-106">Get the attribute collection from the element using `XmlAttributeCollection attrs = elem.Attributes;`.</span></span>  
  
2. <span data-ttu-id="2da2d-107">使用以下三种方法之一移除属性集合中的属性：</span><span class="sxs-lookup"><span data-stu-id="2da2d-107">Remove the attribute from the attribute collection using one of three methods:</span></span>  
  
    - <span data-ttu-id="2da2d-108">使用 <xref:System.Xml.XmlAttributeCollection.Remove%2A> 移除特定的属性。</span><span class="sxs-lookup"><span data-stu-id="2da2d-108">Use <xref:System.Xml.XmlAttributeCollection.Remove%2A> to remove a specific attribute.</span></span>  
  
    - <span data-ttu-id="2da2d-109">使用 <xref:System.Xml.XmlAttributeCollection.RemoveAll%2A> 移除集合中的所有属性并保留没有属性的元素。</span><span class="sxs-lookup"><span data-stu-id="2da2d-109">Use <xref:System.Xml.XmlAttributeCollection.RemoveAll%2A> to remove all attributes from the collection and leave the element with no attributes.</span></span>  
  
    - <span data-ttu-id="2da2d-110">使用 <xref:System.Xml.XmlAttributeCollection.RemoveAt%2A> 通过索引号从属性集合中移除属性。</span><span class="sxs-lookup"><span data-stu-id="2da2d-110">Use <xref:System.Xml.XmlAttributeCollection.RemoveAt%2A> to remove an attribute from the attribute collection by using its index number.</span></span>  
  
 <span data-ttu-id="2da2d-111">下列方法移除元素节点中的属性。</span><span class="sxs-lookup"><span data-stu-id="2da2d-111">The following methods remove attributes from the element node.</span></span>  
  
- <span data-ttu-id="2da2d-112">使用 <xref:System.Xml.XmlElement.RemoveAllAttributes%2A> 移除属性集合。</span><span class="sxs-lookup"><span data-stu-id="2da2d-112">Use <xref:System.Xml.XmlElement.RemoveAllAttributes%2A> to remove the attribute collection.</span></span>  
  
- <span data-ttu-id="2da2d-113">使用 <xref:System.Xml.XmlElement.RemoveAttribute%2A> 可按名称从集合中移除单个属性。</span><span class="sxs-lookup"><span data-stu-id="2da2d-113">Use <xref:System.Xml.XmlElement.RemoveAttribute%2A> to remove a single attribute by name from the collection.</span></span>  
  
- <span data-ttu-id="2da2d-114">使用 <xref:System.Xml.XmlElement.RemoveAttributeAt%2A> 按索引号从集合中移除单个属性。</span><span class="sxs-lookup"><span data-stu-id="2da2d-114">Use <xref:System.Xml.XmlElement.RemoveAttributeAt%2A> to remove a single attribute by index number from the collection.</span></span>  
  
 <span data-ttu-id="2da2d-115">另一个替换方法是获取元素，获取属性集合中的属性并直接移除属性节点。</span><span class="sxs-lookup"><span data-stu-id="2da2d-115">One more alternative is to get the element, get the attribute from the attribute collection, and remove the attribute node directly.</span></span> <span data-ttu-id="2da2d-116">若要获取属性集合中的属性，可使用名称 `XmlAttribute attr = attrs["attr_name"];`、索引 `XmlAttribute attr = attrs[0];` 或用命名空间 `XmlAttribute attr = attrs["attr_localName", "attr_namespace"]` 完全限定该名称。</span><span class="sxs-lookup"><span data-stu-id="2da2d-116">To get the attribute from the attribute collection, you can use a name, `XmlAttribute attr = attrs["attr_name"];`, an index `XmlAttribute attr = attrs[0];`, or by fully qualifying the name with the namespace `XmlAttribute attr = attrs["attr_localName", "attr_namespace"]`.</span></span>  
  
 <span data-ttu-id="2da2d-117">无论用于移除属性的方法是什么，当移除在文档类型定义 (DTD) 中定义为默认属性的属性时有特殊限制。</span><span class="sxs-lookup"><span data-stu-id="2da2d-117">Regardless of the method used to remove attributes, there are special limitations on removing attributes that are defined as default attributes in the document type definition (DTD).</span></span> <span data-ttu-id="2da2d-118">除非移除了默认属性所属的元素，否则不能移除默认属性。</span><span class="sxs-lookup"><span data-stu-id="2da2d-118">Default attributes cannot be removed unless the element they belong to is removed.</span></span> <span data-ttu-id="2da2d-119">已声明了默认属性的元素总是存在默认属性。</span><span class="sxs-lookup"><span data-stu-id="2da2d-119">Default attributes are always present for elements that have default attributes declared.</span></span> <span data-ttu-id="2da2d-120">如果从 <xref:System.Xml.XmlAttributeCollection> 或 <xref:System.Xml.XmlElement> 中移除默认属性，将使替换属性插入元素的 <xref:System.Xml.XmlAttributeCollection>，并初始化为所声明的默认值。</span><span class="sxs-lookup"><span data-stu-id="2da2d-120">Removing a default attribute from an <xref:System.Xml.XmlAttributeCollection> or from the <xref:System.Xml.XmlElement> results in a replacement attribute inserted into the <xref:System.Xml.XmlAttributeCollection> of the element, initialized to the default value that was declared.</span></span> <span data-ttu-id="2da2d-121">如果将某个元素定义为 `<book att1="1" att2="2" att3="3"></book>`，则将得到一个具有三个已声明的默认属性的 `book` 元素。</span><span class="sxs-lookup"><span data-stu-id="2da2d-121">If you have an element defined as `<book att1="1" att2="2" att3="3"></book>`, then you have a `book` element with three default attributes declared.</span></span> <span data-ttu-id="2da2d-122">XML 文档对象模型 (DOM) 实现保证，只要此 `book` 元素存在，就会有三个默认属性（`att1`、`att2` 和 `att3`）。</span><span class="sxs-lookup"><span data-stu-id="2da2d-122">The XML Document Object Model (DOM) implementation guarantees that as long as this `book` element exists, it has these three default attributes of `att1`, `att2`, and `att3`.</span></span>  
  
 <span data-ttu-id="2da2d-123">在使用 <xref:System.Xml.XmlAttribute> 调用时，<xref:System.Xml.XmlAttributeCollection.RemoveAll%2A> 方法会将属性值设置为 String.Empty，因为属性不能没有值。</span><span class="sxs-lookup"><span data-stu-id="2da2d-123">When called with an <xref:System.Xml.XmlAttribute>, the <xref:System.Xml.XmlAttributeCollection.RemoveAll%2A> method sets the value of the attribute to String.Empty, as an attribute cannot exist without a value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2da2d-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="2da2d-124">See also</span></span>

- [<span data-ttu-id="2da2d-125">XML 文档对象模型 (DOM)</span><span class="sxs-lookup"><span data-stu-id="2da2d-125">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
