---
description: :::no-loc text=interface:::（C#参考）
title: 接口 - C# 参考
ms.date: 01/17/2020
f1_keywords:
- interface_CSharpKeyword
helpviewer_keywords:
- interface keyword [C#]
ms.assetid: 7da38e81-4f99-4bc5-b07d-c986b687eeba
ms.openlocfilehash: 24f95e828522f467c519c0c8a7ba9410aa97af4e
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "89134583"
---
# <a name="no-loc-textinterface-c-reference"></a><span data-ttu-id="5d153-103">:::no-loc text="interface":::（C#参考）</span><span class="sxs-lookup"><span data-stu-id="5d153-103">:::no-loc text="interface"::: (C# Reference)</span></span>

<span data-ttu-id="5d153-104">接口定义协定。</span><span class="sxs-lookup"><span data-stu-id="5d153-104">An interface defines a contract.</span></span> <span data-ttu-id="5d153-105">实现该协定的任何 [`class`](class.md) 或 [`struct`](../builtin-types/struct.md) 必须提供接口中定义的成员的实现。</span><span class="sxs-lookup"><span data-stu-id="5d153-105">Any [`class`](class.md) or [`struct`](../builtin-types/struct.md) that implements that contract must provide an implementation of the members defined in the interface.</span></span> <span data-ttu-id="5d153-106">从 C# 8.0 开始，接口可为成员定义默认实现。</span><span class="sxs-lookup"><span data-stu-id="5d153-106">Beginning with C# 8.0, an interface may define a default implementation for members.</span></span> <span data-ttu-id="5d153-107">它还可以定义 [`static`](static.md) 成员，以便提供常见功能的单个实现。</span><span class="sxs-lookup"><span data-stu-id="5d153-107">It may also define [`static`](static.md) members in order to provide a single implementation for common functionality.</span></span>

<span data-ttu-id="5d153-108">在以下示例中，类 `ImplementationClass` 必须实现一个不含参数但返回 `void` 的名为 `SampleMethod` 的方法。</span><span class="sxs-lookup"><span data-stu-id="5d153-108">In the following example, class `ImplementationClass` must implement a method named `SampleMethod` that has no parameters and returns `void`.</span></span>

<span data-ttu-id="5d153-109">有关详细信息和示例，请参阅[接口](../../programming-guide/interfaces/index.md)。</span><span class="sxs-lookup"><span data-stu-id="5d153-109">For more information and examples, see [Interfaces](../../programming-guide/interfaces/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="5d153-110">示例</span><span class="sxs-lookup"><span data-stu-id="5d153-110">Example</span></span>

[!code-csharp[csrefKeywordsTypes#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#14)]

<span data-ttu-id="5d153-111">接口可以是命名空间或类的成员。</span><span class="sxs-lookup"><span data-stu-id="5d153-111">An interface can be a member of a namespace or a class.</span></span> <span data-ttu-id="5d153-112">接口声明可以包含以下成员的声明（没有任何实现的签名）：</span><span class="sxs-lookup"><span data-stu-id="5d153-112">An interface declaration can contain declarations (signatures without any implementation) of the following members:</span></span>

- [<span data-ttu-id="5d153-113">方法</span><span class="sxs-lookup"><span data-stu-id="5d153-113">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)
- [<span data-ttu-id="5d153-114">属性</span><span class="sxs-lookup"><span data-stu-id="5d153-114">Properties</span></span>](../../programming-guide/classes-and-structs/using-properties.md)
- [<span data-ttu-id="5d153-115">索引器</span><span class="sxs-lookup"><span data-stu-id="5d153-115">Indexers</span></span>](../../programming-guide/indexers/using-indexers.md)
- [<span data-ttu-id="5d153-116">事件</span><span class="sxs-lookup"><span data-stu-id="5d153-116">Events</span></span>](event.md)

<span data-ttu-id="5d153-117">上述成员声明通常不包含主体。</span><span class="sxs-lookup"><span data-stu-id="5d153-117">These preceding member declarations typically do not contain a body.</span></span> <span data-ttu-id="5d153-118">从 C# 8.0 开始，接口成员可以声明主体。</span><span class="sxs-lookup"><span data-stu-id="5d153-118">Beginning with C# 8.0, an interface member may declare a body.</span></span> <span data-ttu-id="5d153-119">这称为“默认实现”。</span><span class="sxs-lookup"><span data-stu-id="5d153-119">This is called a *default implementation*.</span></span> <span data-ttu-id="5d153-120">具有主体的成员允许接口为不提供重写实现的类和结构提供“默认”实现。</span><span class="sxs-lookup"><span data-stu-id="5d153-120">Members with bodies permit the interface to provide a "default" implementation for classes and structs that don't provide an overriding implementation.</span></span> <span data-ttu-id="5d153-121">此外，从 C# 8.0 开始，接口可以包括：</span><span class="sxs-lookup"><span data-stu-id="5d153-121">In addition, beginning with C# 8.0, an interface may include:</span></span>

- [<span data-ttu-id="5d153-122">常量</span><span class="sxs-lookup"><span data-stu-id="5d153-122">Constants</span></span>](const.md)
- [<span data-ttu-id="5d153-123">运算符</span><span class="sxs-lookup"><span data-stu-id="5d153-123">Operators</span></span>](../operators/operator-overloading.md)
- <span data-ttu-id="5d153-124">[静态构造函数](../../programming-guide/classes-and-structs/constructors.md#static-constructors)。</span><span class="sxs-lookup"><span data-stu-id="5d153-124">[Static constructor](../../programming-guide/classes-and-structs/constructors.md#static-constructors).</span></span>
- [<span data-ttu-id="5d153-125">嵌套类型</span><span class="sxs-lookup"><span data-stu-id="5d153-125">Nested types</span></span>](../../programming-guide/classes-and-structs/nested-types.md)
- [<span data-ttu-id="5d153-126">静态字段、方法、属性、索引和事件</span><span class="sxs-lookup"><span data-stu-id="5d153-126">Static fields, methods, properties, indexers, and events</span></span>](static.md)
- <span data-ttu-id="5d153-127">使用显式接口实现语法的成员声明。</span><span class="sxs-lookup"><span data-stu-id="5d153-127">Member declarations using the explicit interface implementation syntax.</span></span>
- <span data-ttu-id="5d153-128">显式访问修饰符（默认访问权限为 [`public`](access-modifiers.md)）。</span><span class="sxs-lookup"><span data-stu-id="5d153-128">Explicit access modifiers (the default access is [`public`](access-modifiers.md)).</span></span>

<span data-ttu-id="5d153-129">接口不能包含实例状态。</span><span class="sxs-lookup"><span data-stu-id="5d153-129">Interfaces may not contain instance state.</span></span> <span data-ttu-id="5d153-130">虽然现在允许使用静态字段，但接口中不允许使用实例字段。</span><span class="sxs-lookup"><span data-stu-id="5d153-130">While static fields are now permitted, instance fields are not permitted in interfaces.</span></span> <span data-ttu-id="5d153-131">接口中不支持[实例自动属性](../../programming-guide/classes-and-structs/auto-implemented-properties.md)，因为它们将隐式声明隐藏的字段。</span><span class="sxs-lookup"><span data-stu-id="5d153-131">[Instance auto-properties](../../programming-guide/classes-and-structs/auto-implemented-properties.md) are not supported in interfaces, as they would implicitly declare a hidden field.</span></span> <span data-ttu-id="5d153-132">此规则对属性声明有细微影响。</span><span class="sxs-lookup"><span data-stu-id="5d153-132">This rule has a subtle effect on property declarations.</span></span> <span data-ttu-id="5d153-133">在接口声明中，以下代码不会像在 `class` 或 `struct` 中一样声明自动实现的属性。</span><span class="sxs-lookup"><span data-stu-id="5d153-133">In an interface declaration, the following code does not declare an auto-implemented property as it does in a `class` or `struct`.</span></span> <span data-ttu-id="5d153-134">相反，它会声明一个属性，该属性没有默认实现，而必须在该实现接口的任何类型中实现它：</span><span class="sxs-lookup"><span data-stu-id="5d153-134">Instead, it declares a property that doesn't have a default implementation but must be implemented in any type that implements the interface:</span></span>

```csharp
public interface INamed
{
  public string Name {get; set;}
}
```

<span data-ttu-id="5d153-135">一个接口可从一个或多个基接口继承。</span><span class="sxs-lookup"><span data-stu-id="5d153-135">An interface can inherit from one or more base interfaces.</span></span> <span data-ttu-id="5d153-136">当接口 [重写基接口中的方法实现](override.md)时，必须使用[显式接口实现](../../programming-guide/interfaces/explicit-interface-implementation.md)语法。</span><span class="sxs-lookup"><span data-stu-id="5d153-136">When an interface [overrides a method](override.md) implemented in a base interface, it must use the [explicit interface implementation](../../programming-guide/interfaces/explicit-interface-implementation.md) syntax.</span></span>

<span data-ttu-id="5d153-137">基类型列表包含基类和接口时，基类必须是列表中的第 1 项。</span><span class="sxs-lookup"><span data-stu-id="5d153-137">When a base type list contains a base class and interfaces, the base class must come first in the list.</span></span>

<span data-ttu-id="5d153-138">实现接口的类可以显式实现该接口的成员。</span><span class="sxs-lookup"><span data-stu-id="5d153-138">A class that implements an interface can explicitly implement members of that interface.</span></span> <span data-ttu-id="5d153-139">显式实现的成员不能通过类实例访问，而只能通过接口实例访问。</span><span class="sxs-lookup"><span data-stu-id="5d153-139">An explicitly implemented member cannot be accessed through a class instance, but only through an instance of the interface.</span></span> <span data-ttu-id="5d153-140">此外，只能通过接口实例访问默认接口成员。</span><span class="sxs-lookup"><span data-stu-id="5d153-140">In addition, default interface members can only be accessed through an instance of the interface.</span></span>

<span data-ttu-id="5d153-141">有关显式接口实现的详细信息，请参阅[显式接口实现](../../programming-guide/interfaces/explicit-interface-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="5d153-141">For more information about explicit interface implementation, see [Explicit Interface Implementation](../../programming-guide/interfaces/explicit-interface-implementation.md).</span></span>

## <a name="example"></a><span data-ttu-id="5d153-142">示例</span><span class="sxs-lookup"><span data-stu-id="5d153-142">Example</span></span>

<span data-ttu-id="5d153-143">下例演示了接口实现。</span><span class="sxs-lookup"><span data-stu-id="5d153-143">The following example demonstrates interface implementation.</span></span> <span data-ttu-id="5d153-144">在此示例中，接口包含属性声明，类包含实现。</span><span class="sxs-lookup"><span data-stu-id="5d153-144">In this example, the interface contains the property declaration and the class contains the implementation.</span></span> <span data-ttu-id="5d153-145">实现 `IPoint` 的类的任何实例都具有整数属性 `x` 和 `y`。</span><span class="sxs-lookup"><span data-stu-id="5d153-145">Any instance of a class that implements `IPoint` has integer properties `x` and `y`.</span></span>

[!code-csharp[csrefKeywordsTypes#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#15)]

## <a name="c-language-specification"></a><span data-ttu-id="5d153-146">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="5d153-146">C# language specification</span></span>

<span data-ttu-id="5d153-147">有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的[接口](~/_csharplang/spec/interfaces.md)部分和 [默认接口成员 - C# 8.0](~/_csharplang/proposals/csharp-8.0/default-interface-methods.md) 的功能规范</span><span class="sxs-lookup"><span data-stu-id="5d153-147">For more information, see the [Interfaces](~/_csharplang/spec/interfaces.md) section of the [C# language specification](~/_csharplang/spec/introduction.md) and the feature specification for [Default interface members - C# 8.0](~/_csharplang/proposals/csharp-8.0/default-interface-methods.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="5d153-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d153-148">See also</span></span>

- [<span data-ttu-id="5d153-149">C# 参考</span><span class="sxs-lookup"><span data-stu-id="5d153-149">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5d153-150">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="5d153-150">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5d153-151">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="5d153-151">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="5d153-152">引用类型</span><span class="sxs-lookup"><span data-stu-id="5d153-152">Reference Types</span></span>](reference-types.md)
- [<span data-ttu-id="5d153-153">接口</span><span class="sxs-lookup"><span data-stu-id="5d153-153">Interfaces</span></span>](../../programming-guide/interfaces/index.md)
- [<span data-ttu-id="5d153-154">使用属性</span><span class="sxs-lookup"><span data-stu-id="5d153-154">Using Properties</span></span>](../../programming-guide/classes-and-structs/using-properties.md)
- [<span data-ttu-id="5d153-155">使用索引器</span><span class="sxs-lookup"><span data-stu-id="5d153-155">Using Indexers</span></span>](../../programming-guide/indexers/using-indexers.md)
