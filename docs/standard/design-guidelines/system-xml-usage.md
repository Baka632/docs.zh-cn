---
title: System.Xml 使用情况
ms.date: 10/22/2008
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
ms.openlocfilehash: a01799bd130de0222d4d66dee4955375c1a1911f
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828590"
---
# <a name="systemxml-usage"></a><span data-ttu-id="31b64-102">System.Xml 使用情况</span><span class="sxs-lookup"><span data-stu-id="31b64-102">System.Xml Usage</span></span>
<span data-ttu-id="31b64-103">本部分介绍如何使用 <xref:System.Xml?displayProperty=nameWithType> 可用于表示 XML 数据的命名空间中的多个类型。</span><span class="sxs-lookup"><span data-stu-id="31b64-103">This section talks about usage of several types residing in <xref:System.Xml?displayProperty=nameWithType> namespaces that can be used to represent XML data.</span></span>

 <span data-ttu-id="31b64-104">❌ 不要使用 <xref:System.Xml.XmlNode> 或 <xref:System.Xml.XmlDocument> 来表示 XML 数据。</span><span class="sxs-lookup"><span data-stu-id="31b64-104">❌ DO NOT use <xref:System.Xml.XmlNode> or <xref:System.Xml.XmlDocument> to represent XML data.</span></span> <span data-ttu-id="31b64-105">优选 <xref:System.Xml.XPath.IXPathNavigable> 改用的、 <xref:System.Xml.XmlReader> 、 <xref:System.Xml.XmlWriter> 或子类型 <xref:System.Xml.Linq.XNode> 的实例。</span><span class="sxs-lookup"><span data-stu-id="31b64-105">Favor using instances of <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, or subtypes of <xref:System.Xml.Linq.XNode> instead.</span></span> <span data-ttu-id="31b64-106">`XmlNode` 和 `XmlDocument` 不用于公开公共 api。</span><span class="sxs-lookup"><span data-stu-id="31b64-106">`XmlNode` and `XmlDocument` are not designed for exposing in public APIs.</span></span>

 <span data-ttu-id="31b64-107">✔️使用 `XmlReader` 、 `IXPathNavigable` 或子类型 `XNode` 作为接受或返回 XML 的成员的输入或输出。</span><span class="sxs-lookup"><span data-stu-id="31b64-107">✔️ DO use `XmlReader`, `IXPathNavigable`, or subtypes of `XNode` as input or output of members that accept or return XML.</span></span>

 <span data-ttu-id="31b64-108">使用这些抽象，而不是 `XmlDocument` 、 `XmlNode` 或 <xref:System.Xml.XPath.XPathDocument> ，因为这会使方法与内存中 XML 文档的特定实现分离，并允许它们使用公开、或的虚拟 XML 数据 `XNode` 源 `XmlReader` <xref:System.Xml.XPath.XPathNavigator> 。</span><span class="sxs-lookup"><span data-stu-id="31b64-108">Use these abstractions instead of `XmlDocument`, `XmlNode`, or <xref:System.Xml.XPath.XPathDocument>, because this decouples the methods from specific implementations of an in-memory XML document and allows them to work with virtual XML data sources that expose `XNode`, `XmlReader`, or <xref:System.Xml.XPath.XPathNavigator>.</span></span>

 <span data-ttu-id="31b64-109">❌`XmlDocument`如果要创建表示基础对象模型或数据源的 XML 视图的类型，请不要创建子类。</span><span class="sxs-lookup"><span data-stu-id="31b64-109">❌ DO NOT subclass `XmlDocument` if you want to create a type representing an XML view of an underlying object model or data source.</span></span>

 <span data-ttu-id="31b64-110">*部分©2005，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="31b64-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="31b64-111">*经许可重印皮尔逊教育，Inc. 的作者 [：从框架设计指导原则：用于可重复使用的 .Net 库的约定、惯例和模式; 第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) By Krzysztof Cwalina，Brad Abrams，通过 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分2008发布。*</span><span class="sxs-lookup"><span data-stu-id="31b64-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="31b64-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31b64-112">See also</span></span>

- [<span data-ttu-id="31b64-113">框架设计准则</span><span class="sxs-lookup"><span data-stu-id="31b64-113">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="31b64-114">使用准则</span><span class="sxs-lookup"><span data-stu-id="31b64-114">Usage Guidelines</span></span>](usage-guidelines.md)
