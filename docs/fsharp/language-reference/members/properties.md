---
title: 属性
description: '了解 F # 属性，这些属性是表示与对象关联的值的成员。'
ms.date: 05/16/2016
ms.openlocfilehash: a2a4fbfc88831dcb5cad7a2da701969b2e98b2e3
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740193"
---
# <a name="properties"></a><span data-ttu-id="e306c-103">属性</span><span class="sxs-lookup"><span data-stu-id="e306c-103">Properties</span></span>

<span data-ttu-id="e306c-104">*属性* 是表示与对象关联的值的成员。</span><span class="sxs-lookup"><span data-stu-id="e306c-104">*Properties* are members that represent values associated with an object.</span></span>

## <a name="syntax"></a><span data-ttu-id="e306c-105">语法</span><span class="sxs-lookup"><span data-stu-id="e306c-105">Syntax</span></span>

```fsharp
// Property that has both get and set defined.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with [accessibility-modifier] get() =
    get-function-body
and [accessibility-modifier] set parameter =
    set-function-body

// Alternative syntax for a property that has get and set.
[ attributes-for-get ]
[ static ] member [accessibility-modifier-for-get] [self-identifier.]PropertyName =
    get-function-body
[ attributes-for-set ]
[ static ] member [accessibility-modifier-for-set] [self-identifier.]PropertyName
with set parameter =
    set-function-body

// Property that has get only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName =
    get-function-body

// Alternative syntax for property that has get only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with get() =
    get-function-body

// Property that has set only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with set parameter =
    set-function-body

// Automatically implemented properties.
[ attributes ]
[ static ] member val [accessibility-modifier] PropertyName = initialization-expression [ with get, set ]
```

## <a name="remarks"></a><span data-ttu-id="e306c-106">备注</span><span class="sxs-lookup"><span data-stu-id="e306c-106">Remarks</span></span>

<span data-ttu-id="e306c-107">属性表示在面向对象的编程中的 "具有" 关系，它表示与对象实例相关联的数据，对于静态属性，则表示与类型相关联的数据。</span><span class="sxs-lookup"><span data-stu-id="e306c-107">Properties represent the "has a" relationship in object-oriented programming, representing data that is associated with object instances or, for static properties, with the type.</span></span>

<span data-ttu-id="e306c-108">可以通过两种方式声明属性，具体取决于是否要显式指定基础值 (也称为属性的后备存储) ，或者是否允许编译器自动生成后备存储。</span><span class="sxs-lookup"><span data-stu-id="e306c-108">You can declare properties in two ways, depending on whether you want to explicitly specify the underlying value (also called the backing store) for the property, or if you want to allow the compiler to automatically generate the backing store for you.</span></span> <span data-ttu-id="e306c-109">通常，如果属性具有非普通实现并且属性只是值或变量的简单包装，则应使用更明确的方式。</span><span class="sxs-lookup"><span data-stu-id="e306c-109">Generally, you should use the more explicit way if the property has a non-trivial implementation and the automatic way when the property is just a simple wrapper for a value or variable.</span></span> <span data-ttu-id="e306c-110">若要显式声明属性，请使用 `member` 关键字。</span><span class="sxs-lookup"><span data-stu-id="e306c-110">To declare a property explicitly, use the `member` keyword.</span></span> <span data-ttu-id="e306c-111">此声明性语法后跟指定 `get` 和 `set` 方法（也称为 " *访问器*"）的语法。</span><span class="sxs-lookup"><span data-stu-id="e306c-111">This declarative syntax is followed by the syntax that specifies the `get` and `set` methods, also named *accessors*.</span></span> <span data-ttu-id="e306c-112">"语法" 部分中显示的显式语法的各种形式用于读/写、只读和只写属性。</span><span class="sxs-lookup"><span data-stu-id="e306c-112">The various forms of the explicit syntax shown in the syntax section are used for read/write, read-only, and write-only properties.</span></span> <span data-ttu-id="e306c-113">对于只读属性，只定义一个 `get` 方法; 对于只写属性，只定义一个 `set` 方法。</span><span class="sxs-lookup"><span data-stu-id="e306c-113">For read-only properties, you define only a `get` method; for write-only properties, define only a `set` method.</span></span> <span data-ttu-id="e306c-114">请注意，当属性具有 `get` 和 `set` 访问器时，可以使用替代语法来指定每个访问器不同的属性和可访问性修饰符，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="e306c-114">Note that when a property has both `get` and `set` accessors, the alternative syntax enables you to specify attributes and accessibility modifiers that are different for each accessor, as is shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3201.fs)]

<span data-ttu-id="e306c-115">对于具有和方法的读/写属性， `get` `set` 和的顺序 `get` `set` 可以反转。</span><span class="sxs-lookup"><span data-stu-id="e306c-115">For read/write properties, which have both a `get` and `set` method, the order of `get` and `set` can be reversed.</span></span> <span data-ttu-id="e306c-116">或者，你可以提供仅为提供的语法 `get` 和仅显示的语法， `set` 而不是使用组合语法。</span><span class="sxs-lookup"><span data-stu-id="e306c-116">Alternatively, you can provide the syntax shown for `get` only and the syntax shown for `set` only instead of using the combined syntax.</span></span> <span data-ttu-id="e306c-117">这样做可以更轻松地注释单个 `get` 或 `set` 方法，前提是您可能需要执行此操作。</span><span class="sxs-lookup"><span data-stu-id="e306c-117">Doing this makes it easier to comment out the individual `get` or `set` method, if that is something you might need to do.</span></span> <span data-ttu-id="e306c-118">下面的代码演示了使用组合语法的替代方法。</span><span class="sxs-lookup"><span data-stu-id="e306c-118">This alternative to using the combined syntax is shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3203.fs)]

<span data-ttu-id="e306c-119">保存属性的数据的私有值称为 " *后备存储*"。</span><span class="sxs-lookup"><span data-stu-id="e306c-119">Private values that hold the data for properties are called *backing stores*.</span></span> <span data-ttu-id="e306c-120">若要让编译器自动创建后备存储，请使用关键字 `member val` ，省略自标识符，然后提供一个表达式来初始化属性。</span><span class="sxs-lookup"><span data-stu-id="e306c-120">To have the compiler create the backing store automatically, use the keywords `member val`, omit the self-identifier, then provide an expression to initialize the property.</span></span> <span data-ttu-id="e306c-121">如果该属性是可变的，则包括 `with get, set` 。</span><span class="sxs-lookup"><span data-stu-id="e306c-121">If the property is to be mutable, include `with get, set`.</span></span> <span data-ttu-id="e306c-122">例如，下面的类类型包括两个自动实现的属性。</span><span class="sxs-lookup"><span data-stu-id="e306c-122">For example, the following class type includes two automatically implemented properties.</span></span> <span data-ttu-id="e306c-123">`Property1` 为只读，并初始化为提供给主构造函数的自变量，并且 `Property2` 是一个初始化为空字符串的可设置属性：</span><span class="sxs-lookup"><span data-stu-id="e306c-123">`Property1` is read-only and is initialized to the argument provided to the primary constructor, and `Property2` is a settable property initialized to an empty string:</span></span>

```fsharp
type MyClass(property1 : int) =
member val Property1 = property1
member val Property2 = "" with get, set
```

<span data-ttu-id="e306c-124">自动实现的属性是类型初始化的一部分，因此必须在任何其他成员定义之前包含它们，就像 `let` `do` 类型定义中的绑定和绑定一样。</span><span class="sxs-lookup"><span data-stu-id="e306c-124">Automatically implemented properties are part of the initialization of a type, so they must be included before any other member definitions, just like `let` bindings and `do` bindings in a type definition.</span></span> <span data-ttu-id="e306c-125">请注意，仅在初始化时计算初始化自动实现的属性的表达式，而不会在每次访问该属性时进行计算。</span><span class="sxs-lookup"><span data-stu-id="e306c-125">Note that the expression that initializes an automatically implemented property is only evaluated upon initialization, and not every time the property is accessed.</span></span> <span data-ttu-id="e306c-126">此行为与显式实现的属性的行为相反。</span><span class="sxs-lookup"><span data-stu-id="e306c-126">This behavior is in contrast to the behavior of an explicitly implemented property.</span></span> <span data-ttu-id="e306c-127">这实际上意味着将用于初始化这些属性的代码添加到类的构造函数中。</span><span class="sxs-lookup"><span data-stu-id="e306c-127">What this effectively means is that the code to initialize these properties is added to the constructor of a class.</span></span> <span data-ttu-id="e306c-128">请考虑以下显示这种差异的代码：</span><span class="sxs-lookup"><span data-stu-id="e306c-128">Consider the following code that shows this difference:</span></span>

```fsharp
type MyClass() =
    let random  = new System.Random()
    member val AutoProperty = random.Next() with get, set
    member this.ExplicitProperty = random.Next()

let class1 = new MyClass()

printfn $"class1.AutoProperty = %d{class1.AutoProperty}"
printfn $"class1.ExplicitProperty = %d{class1.ExplicitProperty}"
```

<span data-ttu-id="e306c-129">**输出**</span><span class="sxs-lookup"><span data-stu-id="e306c-129">**Output**</span></span>

```console
class1.AutoProperty = 1853799794
class1.AutoProperty = 1853799794
class1.ExplicitProperty = 978922705
class1.ExplicitProperty = 1131210765
```

<span data-ttu-id="e306c-130">上述代码的输出显示，AutoProperty 的值在被重复调用时不会更改，而 ExplicitProperty 会在每次调用时更改。</span><span class="sxs-lookup"><span data-stu-id="e306c-130">The output of the preceding code shows that the value of AutoProperty is unchanged when called repeatedly, whereas the ExplicitProperty changes each time it is called.</span></span> <span data-ttu-id="e306c-131">这说明，每次都不会计算自动实现属性的表达式，这与显式属性的 getter 方法相同。</span><span class="sxs-lookup"><span data-stu-id="e306c-131">This demonstrates that the expression for an automatically implemented property is not evaluated each time, as is the getter method for the explicit property.</span></span>

>[!WARNING]
><span data-ttu-id="e306c-132">某些库（如实体框架 (`System.Data.Entity`) 在基类构造函数中执行自定义操作，这些操作在初始化自动实现的属性时无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="e306c-132">There are some libraries, such as the Entity Framework (`System.Data.Entity`) that perform custom operations in base class constructors that don't work well with the initialization of automatically implemented properties.</span></span> <span data-ttu-id="e306c-133">在这些情况下，请尝试使用显式属性。</span><span class="sxs-lookup"><span data-stu-id="e306c-133">In those cases, try using explicit properties.</span></span>

<span data-ttu-id="e306c-134">属性可以是类、结构、可区分联合、记录、接口和类型扩展的成员，也可以在对象表达式中定义。</span><span class="sxs-lookup"><span data-stu-id="e306c-134">Properties can be members of classes, structures, discriminated unions, records, interfaces, and type extensions and can also be defined in object expressions.</span></span>

<span data-ttu-id="e306c-135">特性可应用到属性。</span><span class="sxs-lookup"><span data-stu-id="e306c-135">Attributes can be applied to properties.</span></span> <span data-ttu-id="e306c-136">若要将特性应用于属性，请在属性之前的单独行上写入特性。</span><span class="sxs-lookup"><span data-stu-id="e306c-136">To apply an attribute to a property, write the attribute on a separate line before the property.</span></span> <span data-ttu-id="e306c-137">有关更多信息，请参阅[特性](../attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="e306c-137">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="e306c-138">默认情况下，属性是公共的。</span><span class="sxs-lookup"><span data-stu-id="e306c-138">By default, properties are public.</span></span> <span data-ttu-id="e306c-139">辅助功能修饰符还可以应用于属性。</span><span class="sxs-lookup"><span data-stu-id="e306c-139">Accessibility modifiers can also be applied to properties.</span></span> <span data-ttu-id="e306c-140">若要应用可访问性修饰符，请在属性名称之前立即添加它（如果它要应用于 `get` 和方法） `set` ; `get` `set` 如果每个访问器需要不同的可访问性，请将其添加到和关键字之前。</span><span class="sxs-lookup"><span data-stu-id="e306c-140">To apply an accessibility modifier, add it immediately before the name of the property if it is meant to apply to both the `get` and `set` methods; add it before the `get` and `set` keywords if different accessibility is required for each accessor.</span></span> <span data-ttu-id="e306c-141">可 *访问性修饰符* 可以是下列其中一项： `public` 、 `private` 、 `internal` 。</span><span class="sxs-lookup"><span data-stu-id="e306c-141">The *accessibility-modifier* can be one of the following: `public`, `private`, `internal`.</span></span> <span data-ttu-id="e306c-142">有关详细信息，请参阅[访问控制](../access-control.md)。</span><span class="sxs-lookup"><span data-stu-id="e306c-142">For more information, see [Access Control](../access-control.md).</span></span>

<span data-ttu-id="e306c-143">每次访问属性时，都将执行属性实现。</span><span class="sxs-lookup"><span data-stu-id="e306c-143">Property implementations are executed each time a property is accessed.</span></span>

## <a name="static-and-instance-properties"></a><span data-ttu-id="e306c-144">静态属性和实例属性</span><span class="sxs-lookup"><span data-stu-id="e306c-144">Static and Instance Properties</span></span>

<span data-ttu-id="e306c-145">属性可以为静态或实例属性。</span><span class="sxs-lookup"><span data-stu-id="e306c-145">Properties can be static or instance properties.</span></span> <span data-ttu-id="e306c-146">可以在没有实例的情况下调用静态属性，并将其用于与类型相关联的值，而不是与单个对象一起使用。</span><span class="sxs-lookup"><span data-stu-id="e306c-146">Static properties can be invoked without an instance and are used for values associated with the type, not with individual objects.</span></span> <span data-ttu-id="e306c-147">对于静态属性，请省略自标识符。</span><span class="sxs-lookup"><span data-stu-id="e306c-147">For static properties, omit the self-identifier.</span></span> <span data-ttu-id="e306c-148">自标识符对于实例属性是必需的。</span><span class="sxs-lookup"><span data-stu-id="e306c-148">The self-identifier is required for instance properties.</span></span>

<span data-ttu-id="e306c-149">下面的静态属性定义基于某个方案，在此方案中，你有一个作为 `myStaticValue` 属性的后备存储的静态字段。</span><span class="sxs-lookup"><span data-stu-id="e306c-149">The following static property definition is based on a scenario in which you have a static field `myStaticValue` that is the backing store for the property.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3204.fs)]

<span data-ttu-id="e306c-150">属性也可以是类似数组，在这种情况下，它们被称为 *索引属性*。</span><span class="sxs-lookup"><span data-stu-id="e306c-150">Properties can also be array-like, in which case they are called *indexed properties*.</span></span> <span data-ttu-id="e306c-151">有关详细信息，请参阅 [索引属性](indexed-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="e306c-151">For more information, see [Indexed Properties](indexed-properties.md).</span></span>

## <a name="type-annotation-for-properties"></a><span data-ttu-id="e306c-152">属性的类型批注</span><span class="sxs-lookup"><span data-stu-id="e306c-152">Type Annotation for Properties</span></span>

<span data-ttu-id="e306c-153">在许多情况下，编译器提供的信息足以从后备存储的类型推断属性的类型，但您可以通过添加类型注释来显式设置类型。</span><span class="sxs-lookup"><span data-stu-id="e306c-153">In many cases, the compiler has enough information to infer the type of a property from the type of the backing store, but you can set the type explicitly by adding a type annotation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3205.fs)]

## <a name="using-property-set-accessors"></a><span data-ttu-id="e306c-154">使用属性集访问器</span><span class="sxs-lookup"><span data-stu-id="e306c-154">Using Property set Accessors</span></span>

<span data-ttu-id="e306c-155">您可以使用运算符设置提供 `set` 访问器的属性 `<-` 。</span><span class="sxs-lookup"><span data-stu-id="e306c-155">You can set properties that provide `set` accessors by using the `<-` operator.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3206.fs)]

<span data-ttu-id="e306c-156">输出为 **20**。</span><span class="sxs-lookup"><span data-stu-id="e306c-156">The output is **20**.</span></span>

## <a name="abstract-properties"></a><span data-ttu-id="e306c-157">抽象属性</span><span class="sxs-lookup"><span data-stu-id="e306c-157">Abstract Properties</span></span>

<span data-ttu-id="e306c-158">属性可以是抽象的。</span><span class="sxs-lookup"><span data-stu-id="e306c-158">Properties can be abstract.</span></span> <span data-ttu-id="e306c-159">与方法一样， `abstract` 只是表示存在与属性关联的虚拟调度。</span><span class="sxs-lookup"><span data-stu-id="e306c-159">As with methods, `abstract` just means that there is a virtual dispatch associated with the property.</span></span> <span data-ttu-id="e306c-160">抽象属性可以是真正抽象的，也就是说，在同一类中不使用定义。</span><span class="sxs-lookup"><span data-stu-id="e306c-160">Abstract properties can be truly abstract, that is, without a definition in the same class.</span></span> <span data-ttu-id="e306c-161">因此，包含此类属性的类是一个抽象类。</span><span class="sxs-lookup"><span data-stu-id="e306c-161">The class that contains such a property is therefore an abstract class.</span></span> <span data-ttu-id="e306c-162">另外，抽象可以只是表示属性是虚拟的，在这种情况下，定义必须存在于同一个类中。</span><span class="sxs-lookup"><span data-stu-id="e306c-162">Alternatively, abstract can just mean that a property is virtual, and in that case, a definition must be present in the same class.</span></span> <span data-ttu-id="e306c-163">请注意，抽象属性不能是私有的，如果一个访问器是抽象的，另一个访问器也必须是抽象的。</span><span class="sxs-lookup"><span data-stu-id="e306c-163">Note that abstract properties must not be private, and if one accessor is abstract, the other must also be abstract.</span></span> <span data-ttu-id="e306c-164">有关抽象类的详细信息，请参阅 [抽象类](../abstract-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="e306c-164">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3207.fs)]

## <a name="see-also"></a><span data-ttu-id="e306c-165">请参阅</span><span class="sxs-lookup"><span data-stu-id="e306c-165">See also</span></span>

- [<span data-ttu-id="e306c-166">成员</span><span class="sxs-lookup"><span data-stu-id="e306c-166">Members</span></span>](index.md)
- [<span data-ttu-id="e306c-167">方法</span><span class="sxs-lookup"><span data-stu-id="e306c-167">Methods</span></span>](methods.md)
