---
title: 如何声明和使用读/写属性 - C# 编程指南
description: 了解如何使用 C# 中的读/写属性。 此示例包含两个属性，每个属性都具有 get 和 set 访问器，因此这些属性是可读/写的。
ms.date: 07/20/2015
helpviewer_keywords:
- get accessor [C#], declaring properties
- set accessor [C#]
- properties [C#], declaring
- read/write properties [C#]
- accessors [C#], declaring properties with
ms.topic: how-to
ms.custom: contperfq2
ms.assetid: a4962fef-af7e-4c4b-a929-4ae4d646ab8a
ms.openlocfilehash: a0ef36ebff54d6e55e6fd5c72558bf114816d1ca
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099395"
---
# <a name="how-to-declare-and-use-read-write-properties-c-programming-guide"></a><span data-ttu-id="2fd8a-104">如何声明和使用读/写属性（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="2fd8a-104">How to declare and use read write properties (C# Programming Guide)</span></span>

<span data-ttu-id="2fd8a-105">属性提供了公共数据成员的便利性，且不会产生未受保护、不可控制和未经验证地访问对象的数据的风险。</span><span class="sxs-lookup"><span data-stu-id="2fd8a-105">Properties provide the convenience of public data members without the risks that come with unprotected, uncontrolled, and unverified access to an object's data.</span></span> <span data-ttu-id="2fd8a-106">这通过访问器实现：从基础数据成员中赋值和检索值的特殊方法。</span><span class="sxs-lookup"><span data-stu-id="2fd8a-106">This is accomplished through *accessors*: special methods that assign and retrieve values from the underlying data member.</span></span> <span data-ttu-id="2fd8a-107">[set](../../language-reference/keywords/set.md) 访问器可分配数据成员，[get](../../language-reference/keywords/get.md) 访问器检索数据成员值。</span><span class="sxs-lookup"><span data-stu-id="2fd8a-107">The [set](../../language-reference/keywords/set.md) accessor enables data members to be assigned, and the [get](../../language-reference/keywords/get.md) accessor retrieves data member values.</span></span>  
  
 <span data-ttu-id="2fd8a-108">此示例演示具有两个属性的 `Person` 类：`Name`（字符串）和 `Age`（整型）。</span><span class="sxs-lookup"><span data-stu-id="2fd8a-108">This sample shows a `Person` class that has two properties: `Name` (string) and `Age` (int).</span></span> <span data-ttu-id="2fd8a-109">这两个属性均提供 `get` 和 `set` 访问器，因此它们被视为读/写属性。</span><span class="sxs-lookup"><span data-stu-id="2fd8a-109">Both properties provide `get` and `set` accessors, so they are considered read/write properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2fd8a-110">示例</span><span class="sxs-lookup"><span data-stu-id="2fd8a-110">Example</span></span>  

 [!code-csharp[csProgGuideObjects#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#33)]  
  
## <a name="robust-programming"></a><span data-ttu-id="2fd8a-111">可靠编程</span><span class="sxs-lookup"><span data-stu-id="2fd8a-111">Robust Programming</span></span>  

 <span data-ttu-id="2fd8a-112">在前面的示例中，`Name` 和 `Age` 属性为 [public](../../language-reference/keywords/public.md)，同时包含 `get` 和 `set` 访问器。</span><span class="sxs-lookup"><span data-stu-id="2fd8a-112">In the previous example, the `Name` and `Age` properties are [public](../../language-reference/keywords/public.md) and include both a `get` and a `set` accessor.</span></span> <span data-ttu-id="2fd8a-113">这使得任何对象均可读取和写入这些属性。</span><span class="sxs-lookup"><span data-stu-id="2fd8a-113">This allows any object to read and write these properties.</span></span> <span data-ttu-id="2fd8a-114">但是，有时需要排除其中的一个访问器。</span><span class="sxs-lookup"><span data-stu-id="2fd8a-114">It is sometimes desirable, however, to exclude one of the accessors.</span></span> <span data-ttu-id="2fd8a-115">例如，省略 `set` 访问器可使属性为只读：</span><span class="sxs-lookup"><span data-stu-id="2fd8a-115">Omitting the `set` accessor, for example, makes the property read-only:</span></span>  
  
 [!code-csharp[csProgGuideObjects#87](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#87)]  
  
 <span data-ttu-id="2fd8a-116">或者，可以公开一个访问器，但使另一个访问器为私有或受保护。</span><span class="sxs-lookup"><span data-stu-id="2fd8a-116">Alternatively, you can expose one accessor publicly but make the other private or protected.</span></span> <span data-ttu-id="2fd8a-117">有关详细信息，请参阅[非对称性访问器可访问性](./restricting-accessor-accessibility.md)。</span><span class="sxs-lookup"><span data-stu-id="2fd8a-117">For more information, see [Asymmetric Accessor Accessibility](./restricting-accessor-accessibility.md).</span></span>  
  
 <span data-ttu-id="2fd8a-118">声明属性后，便可使用这些属性，就像它们是类的字段一样。</span><span class="sxs-lookup"><span data-stu-id="2fd8a-118">Once the properties are declared, they can be used as if they were fields of the class.</span></span> <span data-ttu-id="2fd8a-119">在获取和设置属性的值时，这允许一种非常自然的语法，如以下语句所示：</span><span class="sxs-lookup"><span data-stu-id="2fd8a-119">This allows for a very natural syntax when both getting and setting the value of a property, as in the following statements:</span></span>  
  
 [!code-csharp[csProgGuideObjects#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#35)]  
  
 <span data-ttu-id="2fd8a-120">请注意，在属性 `set` 方法中，特殊的 `value` 变量为可用。</span><span class="sxs-lookup"><span data-stu-id="2fd8a-120">Note that in a property `set` method a special `value` variable is available.</span></span> <span data-ttu-id="2fd8a-121">此变量包含用户指定的值，例如：</span><span class="sxs-lookup"><span data-stu-id="2fd8a-121">This variable contains the value that the user specified, for example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#36)]  
  
 <span data-ttu-id="2fd8a-122">请注意在 `Person` 对象上递增 `Age` 属性的简洁语法：</span><span class="sxs-lookup"><span data-stu-id="2fd8a-122">Notice the clean syntax for incrementing the `Age` property on a `Person` object:</span></span>  
  
 [!code-csharp[csProgGuideObjects#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#37)]  
  
 <span data-ttu-id="2fd8a-123">如果将单独的 `set` 和 `get` 方法用于模型属性，则等效的代码可能如下所示：</span><span class="sxs-lookup"><span data-stu-id="2fd8a-123">If separate `set` and `get` methods were used to model properties, the equivalent code might look like this:</span></span>  
  
```csharp  
person.SetAge(person.GetAge() + 1);
```  
  
 <span data-ttu-id="2fd8a-124">`ToString` 方法在此示例中被重写：</span><span class="sxs-lookup"><span data-stu-id="2fd8a-124">The `ToString` method is overridden in this example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#38)]  
  
 <span data-ttu-id="2fd8a-125">请注意，`ToString` 未显式用于程序中。</span><span class="sxs-lookup"><span data-stu-id="2fd8a-125">Notice that `ToString` is not explicitly used in the program.</span></span> <span data-ttu-id="2fd8a-126">默认情况下，通过 `WriteLine` 调用对其进行调用。</span><span class="sxs-lookup"><span data-stu-id="2fd8a-126">It is invoked by default by the `WriteLine` calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fd8a-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="2fd8a-127">See also</span></span>

- [<span data-ttu-id="2fd8a-128">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="2fd8a-128">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="2fd8a-129">属性</span><span class="sxs-lookup"><span data-stu-id="2fd8a-129">Properties</span></span>](./properties.md)
- [<span data-ttu-id="2fd8a-130">类和结构</span><span class="sxs-lookup"><span data-stu-id="2fd8a-130">Classes and Structs</span></span>](./index.md)
