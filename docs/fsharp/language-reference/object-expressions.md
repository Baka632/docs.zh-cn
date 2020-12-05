---
title: 对象表达式
description: '如果要避免创建新的命名类型所需的额外代码和开销，请了解如何使用 F # 对象表达式。'
ms.date: 02/08/2019
ms.openlocfilehash: 8a3e40b7833b551eefb95ec62b935acd1ba7b1f9
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740297"
---
# <a name="object-expressions"></a><span data-ttu-id="4a4f9-103">对象表达式</span><span class="sxs-lookup"><span data-stu-id="4a4f9-103">Object Expressions</span></span>

<span data-ttu-id="4a4f9-104">*对象表达式* 是基于现有的基类型、接口或接口集创建动态创建的匿名对象类型的新实例的表达式。</span><span class="sxs-lookup"><span data-stu-id="4a4f9-104">An *object expression* is an expression that creates a new instance of a dynamically created, anonymous object type that is based on an existing base type, interface, or set of interfaces.</span></span>

## <a name="syntax"></a><span data-ttu-id="4a4f9-105">语法</span><span class="sxs-lookup"><span data-stu-id="4a4f9-105">Syntax</span></span>

```fsharp
// When typename is a class:
{ new typename [type-params]arguments with
    member-definitions
    [ additional-interface-definitions ]
}
// When typename is not a class:
{ new typename [generic-type-args] with
    member-definitions
    [ additional-interface-definitions ]
}
```

## <a name="remarks"></a><span data-ttu-id="4a4f9-106">备注</span><span class="sxs-lookup"><span data-stu-id="4a4f9-106">Remarks</span></span>

<span data-ttu-id="4a4f9-107">在前面的语法中， *typename* 表示现有的类类型或接口类型。</span><span class="sxs-lookup"><span data-stu-id="4a4f9-107">In the previous syntax, the *typename* represents an existing class type or interface type.</span></span> <span data-ttu-id="4a4f9-108">*类型-参数* 描述可选的泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="4a4f9-108">*type-params* describes the optional generic type parameters.</span></span> <span data-ttu-id="4a4f9-109">这些 *参数* 仅用于需要构造函数参数的类类型。</span><span class="sxs-lookup"><span data-stu-id="4a4f9-109">The *arguments* are used only for class types, which require constructor parameters.</span></span> <span data-ttu-id="4a4f9-110">*成员定义* 是基类方法的重写，或基类或接口中抽象方法的实现。</span><span class="sxs-lookup"><span data-stu-id="4a4f9-110">The *member-definitions* are overrides of base class methods, or implementations of abstract methods from either a base class or an interface.</span></span>

<span data-ttu-id="4a4f9-111">下面的示例演示了几种不同类型的对象表达式。</span><span class="sxs-lookup"><span data-stu-id="4a4f9-111">The following example illustrates several different types of object expressions.</span></span>

```fsharp
// This object expression specifies a System.Object but overrides the
// ToString method.
let obj1 = { new System.Object() with member x.ToString() = "F#" }
printfn $"{obj1}"

// This object expression implements the IFormattable interface.
let delimiter(delim1: string, delim2: string, value: string) =
    { new System.IFormattable with
        member x.ToString(format: string, provider: System.IFormatProvider) =
            if format = "D" then
                delim1 + value + delim2
            else
                value }

let obj2 = delimiter("{","}", "Bananas!");

printfn "%A" (System.String.Format("{0:D}", obj2))

// Define two interfaces
type IFirst =
  abstract F : unit -> unit
  abstract G : unit -> unit

type ISecond =
  inherit IFirst
  abstract H : unit -> unit
  abstract J : unit -> unit

// This object expression implements both interfaces.
let implementer() =
    { new ISecond with
        member this.H() = ()
        member this.J() = ()
      interface IFirst with
        member this.F() = ()
        member this.G() = () }
```

## <a name="using-object-expressions"></a><span data-ttu-id="4a4f9-112">使用对象表达式</span><span class="sxs-lookup"><span data-stu-id="4a4f9-112">Using Object Expressions</span></span>

<span data-ttu-id="4a4f9-113">如果要避免创建新的命名类型所需的额外代码和开销，请使用对象表达式。</span><span class="sxs-lookup"><span data-stu-id="4a4f9-113">You use object expressions when you want to avoid the extra code and overhead that is required to create a new, named type.</span></span> <span data-ttu-id="4a4f9-114">如果使用对象表达式来最大程度地减少在程序中创建的类型的数目，则可以减少代码的行数，并防止不必要的类型激增。</span><span class="sxs-lookup"><span data-stu-id="4a4f9-114">If you use object expressions to minimize the number of types created in a program, you can reduce the number of lines of code and prevent the unnecessary proliferation of types.</span></span> <span data-ttu-id="4a4f9-115">您可以使用对象表达式自定义现有类型，也可以为手头的特定事例提供适当的接口实现，而不是仅创建用于处理特定情况的许多类型。</span><span class="sxs-lookup"><span data-stu-id="4a4f9-115">Instead of creating many types just to handle specific situations, you can use an object expression that customizes an existing type or provides an appropriate implementation of an interface for the specific case at hand.</span></span>

## <a name="see-also"></a><span data-ttu-id="4a4f9-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a4f9-116">See also</span></span>

- [<span data-ttu-id="4a4f9-117">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="4a4f9-117">F# Language Reference</span></span>](index.md)
