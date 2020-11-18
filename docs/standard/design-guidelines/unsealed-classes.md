---
title: 未密封类
ms.date: 10/22/2008
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
ms.openlocfilehash: b2e14b435aa567f231230da34307014210d46ccb
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828512"
---
# <a name="unsealed-classes"></a><span data-ttu-id="1a49e-102">未密封类</span><span class="sxs-lookup"><span data-stu-id="1a49e-102">Unsealed Classes</span></span>
<span data-ttu-id="1a49e-103">密封类不能从继承，它们会阻止可扩展性。</span><span class="sxs-lookup"><span data-stu-id="1a49e-103">Sealed classes cannot be inherited from, and they prevent extensibility.</span></span> <span data-ttu-id="1a49e-104">相反，可以从继承的类称为非密封类。</span><span class="sxs-lookup"><span data-stu-id="1a49e-104">In contrast, classes that can be inherited from are called unsealed classes.</span></span>

 <span data-ttu-id="1a49e-105">✔️考虑使用未密封的类，而不添加虚拟成员或受保护成员，这是为框架提供廉价但非常感谢的扩展性的极佳方式。</span><span class="sxs-lookup"><span data-stu-id="1a49e-105">✔️ CONSIDER using unsealed classes with no added virtual or protected members as a great way to provide inexpensive yet much appreciated extensibility to a framework.</span></span>

 <span data-ttu-id="1a49e-106">开发人员通常需要从未密封的类中继承，以便添加便利成员，如自定义构造函数、新方法或方法重载。</span><span class="sxs-lookup"><span data-stu-id="1a49e-106">Developers often want to inherit from unsealed classes so as to add convenience members such as custom constructors, new methods, or method overloads.</span></span> <span data-ttu-id="1a49e-107">例如，  `System.Messaging.MessageQueue` 是未密封的，因此允许用户创建默认为特定队列路径的自定义队列，或者添加自定义方法来简化特定方案的 API。</span><span class="sxs-lookup"><span data-stu-id="1a49e-107">For example,  `System.Messaging.MessageQueue` is unsealed and thus allows users to create custom queues that default to a particular queue path or to add custom methods that simplify the API for specific scenarios.</span></span>

 <span data-ttu-id="1a49e-108">默认情况下，大多数编程语言中都不密封类，这也是框架中大多数类的建议默认值。</span><span class="sxs-lookup"><span data-stu-id="1a49e-108">Classes are unsealed by default in most programming languages, and this is also the recommended default for most classes in frameworks.</span></span> <span data-ttu-id="1a49e-109">由于与未密封的类型相关的测试成本相对较低，因此框架用户非常感谢非密封类型提供的扩展性，并且提供的扩展成本要高得多。</span><span class="sxs-lookup"><span data-stu-id="1a49e-109">The extensibility afforded by unsealed types is much appreciated by framework users and quite inexpensive to provide because of relatively low test costs associated with unsealed types.</span></span>

 <span data-ttu-id="1a49e-110">*部分©2005，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="1a49e-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="1a49e-111">*经许可重印皮尔逊教育，Inc. 的作者 [：从框架设计指导原则：用于可重复使用的 .Net 库的约定、惯例和模式; 第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) By Krzysztof Cwalina，Brad Abrams，通过 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分2008发布。*</span><span class="sxs-lookup"><span data-stu-id="1a49e-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="1a49e-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1a49e-112">See also</span></span>

- [<span data-ttu-id="1a49e-113">框架设计准则</span><span class="sxs-lookup"><span data-stu-id="1a49e-113">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="1a49e-114">扩展性设计</span><span class="sxs-lookup"><span data-stu-id="1a49e-114">Designing for Extensibility</span></span>](designing-for-extensibility.md)
- [<span data-ttu-id="1a49e-115">密封</span><span class="sxs-lookup"><span data-stu-id="1a49e-115">Sealing</span></span>](sealing.md)
