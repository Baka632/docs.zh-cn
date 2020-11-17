---
title: F# 代码格式设置准则
description: '了解设置 F # 代码格式的准则。'
ms.date: 08/31/2020
ms.openlocfilehash: af98be75f21cbc594ff9cf779561d49e4965845a
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688249"
---
# <a name="f-code-formatting-guidelines"></a><span data-ttu-id="504f1-103">F# 代码格式设置准则</span><span class="sxs-lookup"><span data-stu-id="504f1-103">F# code formatting guidelines</span></span>

<span data-ttu-id="504f1-104">本文提供了有关如何设置代码格式以使 F # 代码为：</span><span class="sxs-lookup"><span data-stu-id="504f1-104">This article offers guidelines for how to format your code so that your F# code is:</span></span>

* <span data-ttu-id="504f1-105">更清晰</span><span class="sxs-lookup"><span data-stu-id="504f1-105">More legible</span></span>
* <span data-ttu-id="504f1-106">按照 Visual Studio 和其他编辑器中的格式设置工具所应用的约定进行</span><span class="sxs-lookup"><span data-stu-id="504f1-106">In accordance with conventions applied by formatting tools in Visual Studio and other editors</span></span>
* <span data-ttu-id="504f1-107">类似于其他代码 online</span><span class="sxs-lookup"><span data-stu-id="504f1-107">Similar to other code online</span></span>

<span data-ttu-id="504f1-108">这些准则基于通过[Anh-Dung Phan](https://github.com/dungpa)提供的[F # 格式设置约定的综合性指南](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md)。</span><span class="sxs-lookup"><span data-stu-id="504f1-108">These guidelines are based on [A comprehensive guide to F# Formatting Conventions](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) by [Anh-Dung Phan](https://github.com/dungpa).</span></span>

## <a name="general-rules-for-indentation"></a><span data-ttu-id="504f1-109">缩进的一般规则</span><span class="sxs-lookup"><span data-stu-id="504f1-109">General rules for indentation</span></span>

<span data-ttu-id="504f1-110">F # 默认使用有效空白。</span><span class="sxs-lookup"><span data-stu-id="504f1-110">F# uses significant white space by default.</span></span> <span data-ttu-id="504f1-111">以下准则旨在提供有关如何调整一些可能会带来的挑战的指导。</span><span class="sxs-lookup"><span data-stu-id="504f1-111">The following guidelines are intended to provide guidance as to how to juggle some challenges this can impose.</span></span>

### <a name="using-spaces"></a><span data-ttu-id="504f1-112">使用空格</span><span class="sxs-lookup"><span data-stu-id="504f1-112">Using spaces</span></span>

<span data-ttu-id="504f1-113">需要缩进时，必须使用空格，而不是制表符。</span><span class="sxs-lookup"><span data-stu-id="504f1-113">When indentation is required, you must use spaces, not tabs.</span></span> <span data-ttu-id="504f1-114">至少需要一个空格。</span><span class="sxs-lookup"><span data-stu-id="504f1-114">At least one space is required.</span></span> <span data-ttu-id="504f1-115">你的组织可以创建编码标准来指定要用于缩进的空格数;典型情况下，每个级别都有两个、三个或四个空格的缩进。</span><span class="sxs-lookup"><span data-stu-id="504f1-115">Your organization can create coding standards to specify the number of spaces to use for indentation; two, three, or four spaces of indentation at each level where indentation occurs is typical.</span></span>

<span data-ttu-id="504f1-116">**建议每个缩进包含四个空格。**</span><span class="sxs-lookup"><span data-stu-id="504f1-116">**We recommend four spaces per indentation.**</span></span>

<span data-ttu-id="504f1-117">也就是说，程序的缩进是一种主观上的事。</span><span class="sxs-lookup"><span data-stu-id="504f1-117">That said, indentation of programs is a subjective matter.</span></span> <span data-ttu-id="504f1-118">变体正常，但应遵循的第一条规则是 *缩进的一致性*。</span><span class="sxs-lookup"><span data-stu-id="504f1-118">Variations are OK, but the first rule you should follow is *consistency of indentation*.</span></span> <span data-ttu-id="504f1-119">选择一种普遍接受的缩进样式，并在代码库中系统地使用它。</span><span class="sxs-lookup"><span data-stu-id="504f1-119">Choose a generally accepted style of indentation and use it systematically throughout your codebase.</span></span>

## <a name="formatting-white-space"></a><span data-ttu-id="504f1-120">设置空格的格式</span><span class="sxs-lookup"><span data-stu-id="504f1-120">Formatting white space</span></span>

<span data-ttu-id="504f1-121">F # 区分空格。</span><span class="sxs-lookup"><span data-stu-id="504f1-121">F# is white space sensitive.</span></span> <span data-ttu-id="504f1-122">尽管通过适当的缩进涵盖了空白中的大多数语义，但还有其他一些事项需要注意。</span><span class="sxs-lookup"><span data-stu-id="504f1-122">Although most semantics from white space are covered by proper indentation, there are some other things to consider.</span></span>

### <a name="formatting-operators-in-arithmetic-expressions"></a><span data-ttu-id="504f1-123">在算术表达式中设置运算符的格式</span><span class="sxs-lookup"><span data-stu-id="504f1-123">Formatting operators in arithmetic expressions</span></span>

<span data-ttu-id="504f1-124">在二进制算术表达式周围始终使用空格：</span><span class="sxs-lookup"><span data-stu-id="504f1-124">Always use white space around binary arithmetic expressions:</span></span>

```fsharp
let subtractThenAdd x = x - 1 + 3
```

<span data-ttu-id="504f1-125">一元 `-` 运算符的后面应始终紧跟它们所取消的值：</span><span class="sxs-lookup"><span data-stu-id="504f1-125">Unary `-` operators should always be immediately followed by the value they are negating:</span></span>

```fsharp
// OK
let negate x = -x

// Bad
let negateBad x = - x
```

<span data-ttu-id="504f1-126">在运算符后面添加空白字符可能会对 `-` 其他人造成混淆。</span><span class="sxs-lookup"><span data-stu-id="504f1-126">Adding a white-space character after the `-` operator can lead to confusion for others.</span></span>

<span data-ttu-id="504f1-127">总而言之，始终必须：</span><span class="sxs-lookup"><span data-stu-id="504f1-127">In summary, it's important to always:</span></span>

* <span data-ttu-id="504f1-128">围绕空格环绕二元运算符</span><span class="sxs-lookup"><span data-stu-id="504f1-128">Surround binary operators with white space</span></span>
* <span data-ttu-id="504f1-129">一元运算符后面永远没有尾随空格</span><span class="sxs-lookup"><span data-stu-id="504f1-129">Never have trailing white space after a unary operator</span></span>

<span data-ttu-id="504f1-130">二进制算术运算符的准则尤其重要。</span><span class="sxs-lookup"><span data-stu-id="504f1-130">The binary arithmetic operator guideline is especially important.</span></span> <span data-ttu-id="504f1-131">如果无法将二元运算符括起来 `-` ，则在与某些格式设置选项结合使用时，可能会将其解释为一元运算 `-` 。</span><span class="sxs-lookup"><span data-stu-id="504f1-131">Failing to surround a binary `-` operator, when combined with certain formatting choices, could lead to interpreting it as a unary `-`.</span></span>

### <a name="surround-a-custom-operator-definition-with-white-space"></a><span data-ttu-id="504f1-132">使用空格将自定义运算符定义括起来</span><span class="sxs-lookup"><span data-stu-id="504f1-132">Surround a custom operator definition with white space</span></span>

<span data-ttu-id="504f1-133">始终使用空格括起运算符定义：</span><span class="sxs-lookup"><span data-stu-id="504f1-133">Always use white space to surround an operator definition:</span></span>

```fsharp
// OK
let ( !> ) x f = f x

// Bad
let (!>) x f = f x
```

<span data-ttu-id="504f1-134">对于以开头并且包含多个字符的任何自定义运算符 `*` ，需要在定义的开头添加一个空格，以避免编译器歧义。</span><span class="sxs-lookup"><span data-stu-id="504f1-134">For any custom operator that starts with `*` and that has more than one character, you need to add a white space to the beginning of the definition to avoid a compiler ambiguity.</span></span> <span data-ttu-id="504f1-135">出于此原因，我们建议你只需将所有运算符的定义括起来，只包含一个空白字符。</span><span class="sxs-lookup"><span data-stu-id="504f1-135">Because of this, we recommend that you simply surround the definitions of all operators with a single white-space character.</span></span>

### <a name="surround-function-parameter-arrows-with-white-space"></a><span data-ttu-id="504f1-136">用空格将函数参数箭头括起来</span><span class="sxs-lookup"><span data-stu-id="504f1-136">Surround function parameter arrows with white space</span></span>

<span data-ttu-id="504f1-137">定义函数的签名时，使用符号周围的空格 `->` ：</span><span class="sxs-lookup"><span data-stu-id="504f1-137">When defining the signature of a function, use white space around the `->` symbol:</span></span>

```fsharp
// OK
type MyFun = int -> int -> string

// Bad
type MyFunBad = int->int->string
```

### <a name="surround-function-arguments-with-white-space"></a><span data-ttu-id="504f1-138">用空格将函数参数括起来</span><span class="sxs-lookup"><span data-stu-id="504f1-138">Surround function arguments with white space</span></span>

<span data-ttu-id="504f1-139">定义函数时，请在每个参数周围使用空白。</span><span class="sxs-lookup"><span data-stu-id="504f1-139">When defining a function, use white space around each argument.</span></span>

```fsharp
// OK
let myFun (a: decimal) b c = a + b + c

// Bad
let myFunBad (a:decimal)(b)c = a + b + c
```

### <a name="place-parameters-on-a-new-line-for-long-definitions"></a><span data-ttu-id="504f1-140">为长定义将参数放在新行上</span><span class="sxs-lookup"><span data-stu-id="504f1-140">Place parameters on a new line for long definitions</span></span>

<span data-ttu-id="504f1-141">如果函数定义非常长，请将参数放在新行上，并缩进这些参数以匹配后续参数的缩进级别。</span><span class="sxs-lookup"><span data-stu-id="504f1-141">If you have a very long function definition, place the parameters on new lines and indent them to match the indentation level of the subsequent parameter.</span></span>

```fsharp
module M =
    let LongFunctionWithLotsOfParameters(aVeryLongParam: AVeryLongTypeThatYouNeedToUse)
                                        (aSecondVeryLongParam: AVeryLongTypeThatYouNeedToUse)
                                        (aThirdVeryLongParam: AVeryLongTypeThatYouNeedToUse)
                                        =
        // ... the body of the method follows
```

<span data-ttu-id="504f1-142">这同样适用于使用元组的成员、构造函数和参数：</span><span class="sxs-lookup"><span data-stu-id="504f1-142">This also applies to members, constructors, and parameters using tuples:</span></span>

```fsharp
type TM() =
    member _.LongMethodWithLotsOfParameters(aVeryLongParam: AVeryLongTypeThatYouNeedToUse,
                                            aSecondVeryLongParam: AVeryLongTypeThatYouNeedToUse,
                                            aThirdVeryLongParam: AVeryLongTypeThatYouNeedToUse) =
        // ... the body of the method

type TC(aVeryLongCtorParam: AVeryLongTypeThatYouNeedToUse,
        aSecondVeryLongCtorParam: AVeryLongTypeThatYouNeedToUse,
        aThirdVeryLongCtorParam: AVeryLongTypeThatYouNeedToUse) =
    // ... the body of the class follows
```

<span data-ttu-id="504f1-143">如果参数为 currified 或有显式返回类型批注，则最好将该 `=` 字符放在新行上：</span><span class="sxs-lookup"><span data-stu-id="504f1-143">If the parameters are currified or there's an explicit return type annotation, it is preferable to place the `=` character on a new line:</span></span>

```fsharp
type C() =
    member _.LongMethodWithLotsOfParameters(aVeryLongParam: AVeryLongTypeThatYouNeedToUse,
                                            aSecondVeryLongParam: AVeryLongTypeThatYouNeedToUse,
                                            aThirdVeryLongParam: AVeryLongTypeThatYouNeedToUse)
                                            : AReturnType =
        // ... the body of the method
    member _.LongMethodWithLotsOfCurrifiedParams(aVeryLongParam: AVeryLongTypeThatYouNeedToUse)
                                                (aSecondVeryLongParam: AVeryLongTypeThatYouNeedToUse)
                                                (aThirdVeryLongParam: AVeryLongTypeThatYouNeedToUse)
                                                =
        // ... the body of the method
```

<span data-ttu-id="504f1-144">这是一种避免太长的行 (的方法，如果返回类型可能有长的名称) 并且在添加参数时具有更少的行损坏。</span><span class="sxs-lookup"><span data-stu-id="504f1-144">This is a way to avoid too long lines (in case return type might have long name) and have less line-damage when adding parameters.</span></span>

### <a name="type-annotations"></a><span data-ttu-id="504f1-145">类型批注</span><span class="sxs-lookup"><span data-stu-id="504f1-145">Type annotations</span></span>

#### <a name="right-pad-function-argument-type-annotations"></a><span data-ttu-id="504f1-146">右填充函数参数类型批注</span><span class="sxs-lookup"><span data-stu-id="504f1-146">Right-pad function argument type annotations</span></span>

<span data-ttu-id="504f1-147">定义具有类型批注的参数时，请使用符号后面的空格 `:` ：</span><span class="sxs-lookup"><span data-stu-id="504f1-147">When defining arguments with type annotations, use white space after the `:` symbol:</span></span>

```fsharp
// OK
let complexFunction (a: int) (b: int) c = a + b + c

// Bad
let complexFunctionBad (a :int) (b :int) (c:int) = a + b + c
```

#### <a name="surround-return-type-annotations-with-white-space"></a><span data-ttu-id="504f1-148">带有空格的环绕返回类型批注</span><span class="sxs-lookup"><span data-stu-id="504f1-148">Surround return type annotations with white space</span></span>

<span data-ttu-id="504f1-149">在允许绑定函数或值类型批注中 (在函数) 情况下返回类型时，请使用符号前后的空格 `:` ：</span><span class="sxs-lookup"><span data-stu-id="504f1-149">In a let-bound function or value type annotation (return type in the case of a function), use white space before and after the `:` symbol:</span></span>

```fsharp
// OK
let expensiveToCompute : int = 0 // Type annotation for let-bound value
let myFun (a: decimal) b c : decimal = a + b + c // Type annotation for the return type of a function
// Bad
let expensiveToComputeBad1:int = 1
let expensiveToComputeBad2 :int = 2
let myFunBad (a: decimal) b c:decimal = a + b + c
```

## <a name="formatting-blank-lines"></a><span data-ttu-id="504f1-150">设置空行的格式</span><span class="sxs-lookup"><span data-stu-id="504f1-150">Formatting blank lines</span></span>

* <span data-ttu-id="504f1-151">用两个空行分隔顶级函数和类定义。</span><span class="sxs-lookup"><span data-stu-id="504f1-151">Separate top-level function and class definitions with two blank lines.</span></span>
* <span data-ttu-id="504f1-152">类中的方法定义由一个空行分隔。</span><span class="sxs-lookup"><span data-stu-id="504f1-152">Method definitions inside a class are separated by a single blank line.</span></span>
* <span data-ttu-id="504f1-153">可以 (慎用额外的空白行) 分离相关函数组。</span><span class="sxs-lookup"><span data-stu-id="504f1-153">Extra blank lines may be used (sparingly) to separate groups of related functions.</span></span> <span data-ttu-id="504f1-154">可能会在一组相关的 liners (（例如，一组虚拟实现) ）之间省略空行。</span><span class="sxs-lookup"><span data-stu-id="504f1-154">Blank lines may be omitted between a bunch of related one-liners (for example, a set of dummy implementations).</span></span>
* <span data-ttu-id="504f1-155">在函数中，应慎用空白行以指示逻辑部分。</span><span class="sxs-lookup"><span data-stu-id="504f1-155">Use blank lines in functions, sparingly, to indicate logical sections.</span></span>

## <a name="formatting-comments"></a><span data-ttu-id="504f1-156">设置注释格式</span><span class="sxs-lookup"><span data-stu-id="504f1-156">Formatting comments</span></span>

<span data-ttu-id="504f1-157">通常，对于 ML 样式的块注释，使用多个双斜杠注释。</span><span class="sxs-lookup"><span data-stu-id="504f1-157">Generally prefer multiple double-slash comments over ML-style block comments.</span></span>

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

<span data-ttu-id="504f1-158">内联注释应为首字母大写。</span><span class="sxs-lookup"><span data-stu-id="504f1-158">Inline comments should capitalize the first letter.</span></span>

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a><span data-ttu-id="504f1-159">命名约定</span><span class="sxs-lookup"><span data-stu-id="504f1-159">Naming conventions</span></span>

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a><span data-ttu-id="504f1-160">将 camelCase 用于类绑定、表达式绑定以及模式绑定值和函数</span><span class="sxs-lookup"><span data-stu-id="504f1-160">Use camelCase for class-bound, expression-bound, and pattern-bound values and functions</span></span>

<span data-ttu-id="504f1-161">常见和接受的 F # 样式使用 camelCase 作为局部变量或模式匹配和函数定义中的所有名称。</span><span class="sxs-lookup"><span data-stu-id="504f1-161">It is common and accepted F# style to use camelCase for all names bound as local variables or in pattern matches and function definitions.</span></span>

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

<span data-ttu-id="504f1-162">类中的本地绑定函数还应使用 camelCase。</span><span class="sxs-lookup"><span data-stu-id="504f1-162">Locally bound functions in classes should also use camelCase.</span></span>

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a><span data-ttu-id="504f1-163">对模块绑定公共函数使用 camelCase</span><span class="sxs-lookup"><span data-stu-id="504f1-163">Use camelCase for module-bound public functions</span></span>

<span data-ttu-id="504f1-164">当模块绑定函数是公共 API 的一部分时，它应使用 camelCase：</span><span class="sxs-lookup"><span data-stu-id="504f1-164">When a module-bound function is part of a public API, it should use camelCase:</span></span>

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a><span data-ttu-id="504f1-165">将 camelCase 用于内部和私有模块绑定值和函数</span><span class="sxs-lookup"><span data-stu-id="504f1-165">Use camelCase for internal and private module-bound values and functions</span></span>

<span data-ttu-id="504f1-166">将 camelCase 用于专用模块绑定值，包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="504f1-166">Use camelCase for private module-bound values, including the following:</span></span>

* <span data-ttu-id="504f1-167">脚本中的即席函数</span><span class="sxs-lookup"><span data-stu-id="504f1-167">Ad hoc functions in scripts</span></span>

* <span data-ttu-id="504f1-168">构成模块或类型的内部实现的值</span><span class="sxs-lookup"><span data-stu-id="504f1-168">Values making up the internal implementation of a module or type</span></span>

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a><span data-ttu-id="504f1-169">将 camelCase 用于参数</span><span class="sxs-lookup"><span data-stu-id="504f1-169">Use camelCase for parameters</span></span>

<span data-ttu-id="504f1-170">所有参数应根据 .NET 命名约定使用 camelCase。</span><span class="sxs-lookup"><span data-stu-id="504f1-170">All parameters should use camelCase in accordance with .NET naming conventions.</span></span>

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a><span data-ttu-id="504f1-171">将 PascalCase 用于模块</span><span class="sxs-lookup"><span data-stu-id="504f1-171">Use PascalCase for modules</span></span>

<span data-ttu-id="504f1-172">所有模块 (顶级、内部、私有、嵌套) 应使用 PascalCase。</span><span class="sxs-lookup"><span data-stu-id="504f1-172">All modules (top-level, internal, private, nested) should use PascalCase.</span></span>

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a><span data-ttu-id="504f1-173">对类型声明、成员和标签使用 PascalCase</span><span class="sxs-lookup"><span data-stu-id="504f1-173">Use PascalCase for type declarations, members, and labels</span></span>

<span data-ttu-id="504f1-174">类、接口、结构、枚举、委托、记录和可区分联合都应以 PascalCase 命名。</span><span class="sxs-lookup"><span data-stu-id="504f1-174">Classes, interfaces, structs, enumerations, delegates, records, and discriminated unions should all be named with PascalCase.</span></span> <span data-ttu-id="504f1-175">记录和可区分联合的类型和标签内的成员还应使用 PascalCase。</span><span class="sxs-lookup"><span data-stu-id="504f1-175">Members within types and labels for records and discriminated unions should also use PascalCase.</span></span>

```fsharp
type IMyInterface =
    abstract Something: int

type MyClass() =
    member this.MyMethod(x, y) = x + y

type MyRecord = { IntVal: int; StringVal: string }

type SchoolPerson =
    | Professor
    | Student
    | Advisor
    | Administrator
```

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a><span data-ttu-id="504f1-176">将 PascalCase 用于 .NET 内部构造</span><span class="sxs-lookup"><span data-stu-id="504f1-176">Use PascalCase for constructs intrinsic to .NET</span></span>

<span data-ttu-id="504f1-177">命名空间、异常、事件和项目/ `.dll` 名称还应使用 PascalCase。</span><span class="sxs-lookup"><span data-stu-id="504f1-177">Namespaces, exceptions, events, and project/`.dll` names should also use PascalCase.</span></span> <span data-ttu-id="504f1-178">这不仅会使其他 .NET 语言的使用变得对使用者更自然，还与你可能会遇到的 .NET 命名约定一致。</span><span class="sxs-lookup"><span data-stu-id="504f1-178">Not only does this make consumption from other .NET languages feel more natural to consumers, it's also consistent with .NET naming conventions that you are likely to encounter.</span></span>

### <a name="avoid-underscores-in-names"></a><span data-ttu-id="504f1-179">避免名称中有下划线</span><span class="sxs-lookup"><span data-stu-id="504f1-179">Avoid underscores in names</span></span>

<span data-ttu-id="504f1-180">从历史上看，某些 F # 库在名称中使用了下划线。</span><span class="sxs-lookup"><span data-stu-id="504f1-180">Historically, some F# libraries have used underscores in names.</span></span> <span data-ttu-id="504f1-181">但是，这并不能再被广泛接受，因为它与 .NET 命名约定冲突。</span><span class="sxs-lookup"><span data-stu-id="504f1-181">However, this is no longer widely accepted, partly because it clashes with .NET naming conventions.</span></span> <span data-ttu-id="504f1-182">也就是说，某些 F # 程序员在很大程度上使用下划线，其中部分原因是出于历史原因，而容差和尊重非常重要。</span><span class="sxs-lookup"><span data-stu-id="504f1-182">That said, some F# programmers use underscores heavily, partly for historical reasons, and tolerance and respect is important.</span></span> <span data-ttu-id="504f1-183">但是，请注意，样式通常不喜欢有权选择是否使用的其他人。</span><span class="sxs-lookup"><span data-stu-id="504f1-183">However, be aware that the style is often disliked by others who have a choice about whether to use it.</span></span>

<span data-ttu-id="504f1-184">一个例外包括与本机组件互操作，其中有下划线。</span><span class="sxs-lookup"><span data-stu-id="504f1-184">One exception includes interoperating with native components, where underscores are common.</span></span>

### <a name="use-standard-f-operators"></a><span data-ttu-id="504f1-185">使用标准 F # 运算符</span><span class="sxs-lookup"><span data-stu-id="504f1-185">Use standard F# operators</span></span>

<span data-ttu-id="504f1-186">以下运算符是在 F # 标准库中定义的，应使用而不是定义等效运算符。</span><span class="sxs-lookup"><span data-stu-id="504f1-186">The following operators are defined in the F# standard library and should be used instead of defining equivalents.</span></span> <span data-ttu-id="504f1-187">建议使用这些运算符，因为这往往会使代码更具可读性和惯用。</span><span class="sxs-lookup"><span data-stu-id="504f1-187">Using these operators is recommended as it tends to make code more readable and idiomatic.</span></span> <span data-ttu-id="504f1-188">具有 OCaml 或其他功能编程语言的开发人员可能习惯于不同的惯例。</span><span class="sxs-lookup"><span data-stu-id="504f1-188">Developers with a background in OCaml or other functional programming language may be accustomed to different idioms.</span></span> <span data-ttu-id="504f1-189">以下列表汇总了建议的 F # 运算符。</span><span class="sxs-lookup"><span data-stu-id="504f1-189">The following list summarizes the recommended F# operators.</span></span>

```fsharp
x |> f // Forward pipeline
f >> g // Forward composition
x |> ignore // Discard away a value
x + y // Overloaded addition (including string concatenation)
x - y // Overloaded subtraction
x * y // Overloaded multiplication
x / y // Overloaded division
x % y // Overloaded modulus
x && y // Lazy/short-cut "and"
x || y // Lazy/short-cut "or"
x <<< y // Bitwise left shift
x >>> y // Bitwise right shift
x ||| y // Bitwise or, also for working with “flags” enumeration
x &&& y // Bitwise and, also for working with “flags” enumeration
x ^^^ y // Bitwise xor, also for working with “flags” enumeration
```

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a><span data-ttu-id="504f1-190">对泛型 (使用前缀语法 `Foo<T>`) 优先使用后缀语法 (`T Foo`) </span><span class="sxs-lookup"><span data-stu-id="504f1-190">Use prefix syntax for generics (`Foo<T>`) in preference to postfix syntax (`T Foo`)</span></span>

<span data-ttu-id="504f1-191">F # 同时继承命名泛型类型的后缀 ML 形式 (例如， `int list`) 以及前缀 .net 样式 (例如 `list<int>`) 。</span><span class="sxs-lookup"><span data-stu-id="504f1-191">F# inherits both the postfix ML style of naming generic types (for example, `int list`) as well as the prefix .NET style (for example, `list<int>`).</span></span> <span data-ttu-id="504f1-192">除了五个特定类型外，更喜欢 .NET 样式：</span><span class="sxs-lookup"><span data-stu-id="504f1-192">Prefer the .NET style, except for five specific types:</span></span>

1. <span data-ttu-id="504f1-193">对于 F # 列表，请使用后缀形式： `int list` 而不是 `list<int>` 。</span><span class="sxs-lookup"><span data-stu-id="504f1-193">For F# Lists, use the postfix form: `int list` rather than `list<int>`.</span></span>
2. <span data-ttu-id="504f1-194">对于 F # 选项，请使用后缀形式： `int option` 而不是 `option<int>` 。</span><span class="sxs-lookup"><span data-stu-id="504f1-194">For F# Options, use the postfix form: `int option` rather than `option<int>`.</span></span>
3. <span data-ttu-id="504f1-195">对于 F # 值选项，请使用后缀形式： `int voption` 而不是 `voption<int>` 。</span><span class="sxs-lookup"><span data-stu-id="504f1-195">For F# Value Options, use the postfix form: `int voption` rather than `voption<int>`.</span></span>
4. <span data-ttu-id="504f1-196">对于 F # 数组，请使用句法名称， `int[]` 而不是 `int array` 或 `array<int>` 。</span><span class="sxs-lookup"><span data-stu-id="504f1-196">For F# arrays, use the syntactic name `int[]` rather than `int array` or `array<int>`.</span></span>
5. <span data-ttu-id="504f1-197">对于引用单元格，请使用 `int ref` 而不是 `ref<int>` 或 `Ref<int>` 。</span><span class="sxs-lookup"><span data-stu-id="504f1-197">For Reference Cells, use `int ref` rather than `ref<int>` or `Ref<int>`.</span></span>

<span data-ttu-id="504f1-198">对于所有其他类型，请使用前缀形式。</span><span class="sxs-lookup"><span data-stu-id="504f1-198">For all other types, use the prefix form.</span></span>

## <a name="formatting-tuples"></a><span data-ttu-id="504f1-199">格式化元组</span><span class="sxs-lookup"><span data-stu-id="504f1-199">Formatting tuples</span></span>

<span data-ttu-id="504f1-200">元组实例化应带有括号，其中的分隔逗号后面应跟一个空格，例如： `(1, 2)` 、 `(x, y, z)` 。</span><span class="sxs-lookup"><span data-stu-id="504f1-200">A tuple instantiation should be parenthesized, and the delimiting commas within it should be followed by a single space, for example: `(1, 2)`, `(x, y, z)`.</span></span>

<span data-ttu-id="504f1-201">通常会接受在元组的模式匹配中省略括号：</span><span class="sxs-lookup"><span data-stu-id="504f1-201">It is commonly accepted to omit parentheses in pattern matching of tuples:</span></span>

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

<span data-ttu-id="504f1-202">如果元组是函数的返回值，则通常也可以接受省略括号：</span><span class="sxs-lookup"><span data-stu-id="504f1-202">It is also commonly accepted to omit parentheses if the tuple is the return value of a function:</span></span>

```fsharp
// OK
let update model msg =
    match msg with
    | 1 -> model + 1, []
    | _ -> model, [ msg ]
```

<span data-ttu-id="504f1-203">总而言之，使用带括号的元组实例化，但使用元组进行模式匹配或返回值时，可以将其视为非常好的以避免使用括号。</span><span class="sxs-lookup"><span data-stu-id="504f1-203">In summary, prefer parenthesized tuple instantiations, but when using tuples for pattern matching or a return value, it is considered fine to avoid parentheses.</span></span>

## <a name="formatting-discriminated-union-declarations"></a><span data-ttu-id="504f1-204">设置可区分联合声明的格式</span><span class="sxs-lookup"><span data-stu-id="504f1-204">Formatting discriminated union declarations</span></span>

<span data-ttu-id="504f1-205">`|`在类型定义中按四个空格缩进：</span><span class="sxs-lookup"><span data-stu-id="504f1-205">Indent `|` in type definition by four spaces:</span></span>

```fsharp
// OK
type Volume =
    | Liter of float
    | FluidOunce of float
    | ImperialPint of float

// Not OK
type Volume =
| Liter of float
| USPint of float
| ImperialPint of float
```

## <a name="formatting-discriminated-unions"></a><span data-ttu-id="504f1-206">设置可区分联合的格式</span><span class="sxs-lookup"><span data-stu-id="504f1-206">Formatting discriminated unions</span></span>

<span data-ttu-id="504f1-207">跨多个行拆分的实例化的可区分联合应为包含的数据提供具有缩进的新范围：</span><span class="sxs-lookup"><span data-stu-id="504f1-207">Instantiated Discriminated Unions that split across multiple lines should give contained data a new scope with indentation:</span></span>

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

<span data-ttu-id="504f1-208">右括号还可以位于新行上：</span><span class="sxs-lookup"><span data-stu-id="504f1-208">The closing parenthesis can also be on a new line:</span></span>

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a><span data-ttu-id="504f1-209">设置记录声明格式</span><span class="sxs-lookup"><span data-stu-id="504f1-209">Formatting record declarations</span></span>

<span data-ttu-id="504f1-210">`{`在类型定义中按四个空格缩进，并在同一行中启动字段列表：</span><span class="sxs-lookup"><span data-stu-id="504f1-210">Indent `{` in type definition by four spaces and start the field list on the same line:</span></span>

```fsharp
// OK
type PostalAddress =
    { Address: string
      City: string
      Zip: string }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

// Not OK
type PostalAddress =
  { Address: string
    City: string
    Zip: string }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

// Unusual in F#
type PostalAddress =
    {
        Address: string
        City: string
        Zip: string
    }
```

<span data-ttu-id="504f1-211">如果要在记录上声明接口实现或成员，则在新行上放置打开标记，并在新行上放置结束标记更可取：</span><span class="sxs-lookup"><span data-stu-id="504f1-211">Placing the opening token on a new line and the closing token on a new line is preferable if you are declaring interface implementations or members on the record:</span></span>

```fsharp
// Declaring additional members on PostalAddress
type PostalAddress =
    {
        Address: string
        City: string
        Zip: string
    }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

type MyRecord =
    {
        SomeField: int
    }
    interface IMyInterface
```

## <a name="formatting-records"></a><span data-ttu-id="504f1-212">设置记录格式</span><span class="sxs-lookup"><span data-stu-id="504f1-212">Formatting records</span></span>

<span data-ttu-id="504f1-213">可以在一行中写入短记录：</span><span class="sxs-lookup"><span data-stu-id="504f1-213">Short records can be written in one line:</span></span>

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

<span data-ttu-id="504f1-214">更长时间的记录应使用标签的新行：</span><span class="sxs-lookup"><span data-stu-id="504f1-214">Records that are longer should use new lines for labels:</span></span>

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="504f1-215">如果要执行以下操作，请在新行上放置打开标记，将 "内容" 选项卡在一个范围内，将结束标记放在新行上：</span><span class="sxs-lookup"><span data-stu-id="504f1-215">Placing the opening token on a new line, the contents tabbed over one scope, and the closing token on a new line is preferable if you are:</span></span>

* <span data-ttu-id="504f1-216">在具有不同缩进范围的代码中移动记录</span><span class="sxs-lookup"><span data-stu-id="504f1-216">Moving records around in code with different indentation scopes</span></span>
* <span data-ttu-id="504f1-217">将它们传递给函数</span><span class="sxs-lookup"><span data-stu-id="504f1-217">Piping them into a function</span></span>

```fsharp
let rainbow =
    {
        Boss1 = "Jeffrey"
        Boss2 = "Jeffrey"
        Boss3 = "Jeffrey"
        Boss4 = "Jeffrey"
        Boss5 = "Jeffrey"
        Boss6 = "Jeffrey"
        Boss7 = "Jeffrey"
        Boss8 = "Jeffrey"
        Lackeys = ["Zippy"; "George"; "Bungle"]
    }

type MyRecord =
    {
        SomeField: int
    }
    interface IMyInterface

let foo a =
    a
    |> Option.map (fun x ->
        {
            MyField = x
        })
```

<span data-ttu-id="504f1-218">相同的规则适用于列表和数组元素。</span><span class="sxs-lookup"><span data-stu-id="504f1-218">The same rules apply for list and array elements.</span></span>

## <a name="formatting-copy-and-update-record-expressions"></a><span data-ttu-id="504f1-219">设置复制和更新记录表达式的格式</span><span class="sxs-lookup"><span data-stu-id="504f1-219">Formatting copy-and-update record expressions</span></span>

<span data-ttu-id="504f1-220">复制和更新记录表达式仍是一条记录，因此应用类似的准则。</span><span class="sxs-lookup"><span data-stu-id="504f1-220">A copy-and-update record expression is still a record, so similar guidelines apply.</span></span>

<span data-ttu-id="504f1-221">短表达式可以放在一行上：</span><span class="sxs-lookup"><span data-stu-id="504f1-221">Short expressions can fit on one line:</span></span>

```fsharp
let point2 = { point with X = 1; Y = 2 }
```

<span data-ttu-id="504f1-222">更长的表达式应使用新行：</span><span class="sxs-lookup"><span data-stu-id="504f1-222">Longer expressions should use new lines:</span></span>

```fsharp
let rainbow2 =
    { rainbow with
        Boss = "Jeffrey"
        Lackeys = [ "Zippy"; "George"; "Bungle" ] }
```

<span data-ttu-id="504f1-223">与记录指南一样，你可能想要将多个单独的行专用于大括号，并将一个范围向右缩进到表达式。</span><span class="sxs-lookup"><span data-stu-id="504f1-223">And as with the record guidance, you may want to dedicate separate lines for the braces and indent one scope to the right with the expression.</span></span> <span data-ttu-id="504f1-224">在某些特殊情况下，例如，使用不带括号的可选值包装值时，可能需要在一行上保留大括号：</span><span class="sxs-lookup"><span data-stu-id="504f1-224">In some special cases, such as wrapping a value with an optional without parentheses, you may need to keep a brace on one line:</span></span>

```fsharp
type S = { F1: int; F2: string }
type State = { F:  S option }

let state = { F = Some { F1 = 1; F2 = "Hello" } }
let newState =
    {
        state with
            F = Some {
                    F1 = 0
                    F2 = ""
                }
    }
```

## <a name="formatting-lists-and-arrays"></a><span data-ttu-id="504f1-225">设置列表和数组的格式</span><span class="sxs-lookup"><span data-stu-id="504f1-225">Formatting lists and arrays</span></span>

<span data-ttu-id="504f1-226">`x :: l`运算符周围的空格写入 `::` (`::` 是内缀运算符，因此由空格括起来) 。</span><span class="sxs-lookup"><span data-stu-id="504f1-226">Write `x :: l` with spaces around the `::` operator (`::` is an infix operator, hence surrounded by spaces).</span></span>

<span data-ttu-id="504f1-227">在单个行中声明的列表和数组应该在左方括号后面和右括号之前有一个空格：</span><span class="sxs-lookup"><span data-stu-id="504f1-227">List and arrays declared on a single line should have a space after the opening bracket and before the closing bracket:</span></span>

```fsharp
let xs = [ 1; 2; 3 ]
let ys = [| 1; 2; 3; |]
```

<span data-ttu-id="504f1-228">请始终在两个不同的大括号运算符之间至少使用一个空格。</span><span class="sxs-lookup"><span data-stu-id="504f1-228">Always use at least one space between two distinct brace-like operators.</span></span> <span data-ttu-id="504f1-229">例如，在和之间留一个空格 `[` `{` 。</span><span class="sxs-lookup"><span data-stu-id="504f1-229">For example, leave a space between a `[` and a `{`.</span></span>

```fsharp
// OK
[ { IngredientName = "Green beans"; Quantity = 250 }
  { IngredientName = "Pine nuts"; Quantity = 250 }
  { IngredientName = "Feta cheese"; Quantity = 250 }
  { IngredientName = "Olive oil"; Quantity = 10 }
  { IngredientName = "Lemon"; Quantity = 1 } ]

// Not OK
[{ IngredientName = "Green beans"; Quantity = 250 }
 { IngredientName = "Pine nuts"; Quantity = 250 }
 { IngredientName = "Feta cheese"; Quantity = 250 }
 { IngredientName = "Olive oil"; Quantity = 10 }
 { IngredientName = "Lemon"; Quantity = 1 }]
```

<span data-ttu-id="504f1-230">相同的指导原则适用于元组的列表或数组。</span><span class="sxs-lookup"><span data-stu-id="504f1-230">The same guideline applies for lists or arrays of tuples.</span></span>

<span data-ttu-id="504f1-231">跨多个行拆分的列表和数组将遵循类似的规则作为记录：</span><span class="sxs-lookup"><span data-stu-id="504f1-231">Lists and arrays that split across multiple lines follow a similar rule as records do:</span></span>

```fsharp
let pascalsTriangle =
    [|
        [| 1 |]
        [| 1; 1 |]
        [| 1; 2; 1 |]
        [| 1; 3; 3; 1 |]
        [| 1; 4; 6; 4; 1 |]
        [| 1; 5; 10; 10; 5; 1 |]
        [| 1; 6; 15; 20; 15; 6; 1 |]
        [| 1; 7; 21; 35; 35; 21; 7; 1 |]
        [| 1; 8; 28; 56; 70; 56; 28; 8; 1 |]
    |]
```

<span data-ttu-id="504f1-232">与记录一样，将左括号和右括号声明到其自己的行上，可以更轻松地移动代码和管道转换为函数。</span><span class="sxs-lookup"><span data-stu-id="504f1-232">And as with records, declaring the opening and closing brackets on their own line will make moving code around and piping into functions easier.</span></span>

<span data-ttu-id="504f1-233">以编程方式生成数组和列表时，优先 `->` 于 `do ... yield` 始终生成值的时间：</span><span class="sxs-lookup"><span data-stu-id="504f1-233">When generating arrays and lists programmatically, prefer `->` over `do ... yield` when a value is always generated:</span></span>

```fsharp
// Preferred
let squares = [ for x in 1..10 -> x * x ]

// Not preferred
let squares' = [ for x in 1..10 do yield x * x ]
```

<span data-ttu-id="504f1-234">旧版本的 F # 语言需要 `yield` 在可能有条件地生成数据的情况下指定，或者可能存在连续的表达式进行计算。</span><span class="sxs-lookup"><span data-stu-id="504f1-234">Older versions of the F# language required specifying `yield` in situations where data may be generated conditionally, or there may be consecutive expressions to be evaluated.</span></span> <span data-ttu-id="504f1-235">`yield`如果你必须使用较旧的 F # 语言版本进行编译，则优先于忽略这些关键字：</span><span class="sxs-lookup"><span data-stu-id="504f1-235">Prefer omitting these `yield` keywords unless you must compile with an older F# language version:</span></span>

```fsharp
// Preferred
let daysOfWeek includeWeekend =
    [
        "Monday"
        "Tuesday"
        "Wednesday"
        "Thursday"
        "Friday"
        if includeWeekend then
            "Saturday"
            "Sunday"
    ]

// Not preferred
let daysOfWeek' includeWeekend =
    [
        yield "Monday"
        yield "Tuesday"
        yield "Wednesday"
        yield "Thursday"
        yield "Friday"
        if includeWeekend then
            yield "Saturday"
            yield "Sunday"
    ]
```

<span data-ttu-id="504f1-236">在某些情况下， `do...yield` 可能有助于提高可读性。</span><span class="sxs-lookup"><span data-stu-id="504f1-236">In some cases, `do...yield` may aid in readability.</span></span> <span data-ttu-id="504f1-237">尽管应考虑主观，但应考虑到这些情况。</span><span class="sxs-lookup"><span data-stu-id="504f1-237">These cases, though subjective, should be taken into consideration.</span></span>

## <a name="formatting-if-expressions"></a><span data-ttu-id="504f1-238">设置表达式的格式</span><span class="sxs-lookup"><span data-stu-id="504f1-238">Formatting if expressions</span></span>

<span data-ttu-id="504f1-239">条件的缩进取决于使其变得的表达式的大小和复杂程度。</span><span class="sxs-lookup"><span data-stu-id="504f1-239">Indentation of conditionals depends on the size and complexity of the expressions that make them up.</span></span>
<span data-ttu-id="504f1-240">仅在以下情况时将它们写入一行：</span><span class="sxs-lookup"><span data-stu-id="504f1-240">Simply write them on one line when:</span></span>

- <span data-ttu-id="504f1-241">`cond`、 `e1` 和 `e2` 为 short</span><span class="sxs-lookup"><span data-stu-id="504f1-241">`cond`, `e1` and `e2` are short</span></span>
- <span data-ttu-id="504f1-242">`e1` 和 `e2` 不是 `if/then/else` 表达式本身。</span><span class="sxs-lookup"><span data-stu-id="504f1-242">`e1` and `e2` are not `if/then/else` expressions themselves.</span></span>

```fsharp
if cond then e1 else e2
```

<span data-ttu-id="504f1-243">如果任何表达式为多行或表达式，则为 `if/then/else` 。</span><span class="sxs-lookup"><span data-stu-id="504f1-243">If any of the expressions are multi-line or `if/then/else` expressions.</span></span>

```fsharp
if cond then
    e1
else
    e2
```

<span data-ttu-id="504f1-244">带有和的多个条件在 `elif` `else` `if` 遵循一个行表达式的规则时，将在与相同的范围内缩进 `if/then/else` 。</span><span class="sxs-lookup"><span data-stu-id="504f1-244">Multiple conditionals with `elif` and `else` are indented at the same scope as the `if` when they follow the rules of the one line `if/then/else` expressions.</span></span>

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

<span data-ttu-id="504f1-245">如果有任何条件或表达式为多行，则整个 `if/then/else` 表达式为多行：</span><span class="sxs-lookup"><span data-stu-id="504f1-245">If any of the conditions or expressions is multi-line, the entire `if/then/else` expression is multi-line:</span></span>

```fsharp
if cond1 then
    e1
elif cond2 then
    e2
elif cond3 then
    e3
else
    e4
```

### <a name="pattern-matching-constructs"></a><span data-ttu-id="504f1-246">模式匹配构造</span><span class="sxs-lookup"><span data-stu-id="504f1-246">Pattern matching constructs</span></span>

<span data-ttu-id="504f1-247">`|`对匹配的每个子句使用，无缩进。</span><span class="sxs-lookup"><span data-stu-id="504f1-247">Use a `|` for each clause of a match with no indentation.</span></span> <span data-ttu-id="504f1-248">如果表达式较短，则如果每个子表达式也简单，则可以考虑使用单个行。</span><span class="sxs-lookup"><span data-stu-id="504f1-248">If the expression is short, you can consider using a single line if each subexpression is also simple.</span></span>

```fsharp
// OK
match l with
| { him = x; her = "Posh" } :: tail -> x
| _ :: tail -> findDavid tail
| [] -> failwith "Couldn't find David"

// Not OK
match l with
    | { him = x; her = "Posh" } :: tail -> x
    | _ :: tail -> findDavid tail
    | [] -> failwith "Couldn't find David"
```

<span data-ttu-id="504f1-249">如果模式匹配箭头右侧的表达式太大，则将其移动到下面的行，并从中缩进一个步骤 `match` / `|` 。</span><span class="sxs-lookup"><span data-stu-id="504f1-249">If the expression on the right of the pattern matching arrow is too large, move it to the following line, indented one step from the `match`/`|`.</span></span>

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

<span data-ttu-id="504f1-250">从开始，从开始，对匿名函数进行的模式匹配 `function` 通常不应缩进太远。</span><span class="sxs-lookup"><span data-stu-id="504f1-250">Pattern matching of anonymous functions, starting by `function`, should generally not indent too far.</span></span> <span data-ttu-id="504f1-251">例如，将一个作用域缩进如下所示：</span><span class="sxs-lookup"><span data-stu-id="504f1-251">For example, indenting one scope as follows is fine:</span></span>

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

<span data-ttu-id="504f1-252">即使使用关键字，使用定义的函数中的模式匹配 `let` 也 `let rec` 应缩进四个空格 `let` `function` ：</span><span class="sxs-lookup"><span data-stu-id="504f1-252">Pattern matching in functions defined by `let` or `let rec` should be indented four spaces after starting of `let`, even if `function` keyword is used:</span></span>

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

<span data-ttu-id="504f1-253">建议不要对齐箭头。</span><span class="sxs-lookup"><span data-stu-id="504f1-253">We do not recommend aligning arrows.</span></span>

## <a name="formatting-trywith-expressions"></a><span data-ttu-id="504f1-254">格式 try/with 表达式</span><span class="sxs-lookup"><span data-stu-id="504f1-254">Formatting try/with expressions</span></span>

<span data-ttu-id="504f1-255">应将异常类型的模式匹配缩进到与相同的级别 `with` 。</span><span class="sxs-lookup"><span data-stu-id="504f1-255">Pattern matching on the exception type should be indented at the same level as `with`.</span></span>

```fsharp
try
    if System.DateTime.Now.Second % 3 = 0 then
        raise (new System.Exception())
    else
        raise (new System.ApplicationException())
with
| :? System.ApplicationException ->
    printfn "A second that was not a multiple of 3"
| _ ->
    printfn "A second that was a multiple of 3"
```

## <a name="formatting-function-parameter-application"></a><span data-ttu-id="504f1-256">格式化函数参数应用程序</span><span class="sxs-lookup"><span data-stu-id="504f1-256">Formatting function parameter application</span></span>

<span data-ttu-id="504f1-257">通常，大多数函数参数应用程序都在同一行中完成。</span><span class="sxs-lookup"><span data-stu-id="504f1-257">In general, most function parameter application is done on the same line.</span></span>

<span data-ttu-id="504f1-258">如果希望将参数应用于新行中的函数，请按一个范围将它们缩进。</span><span class="sxs-lookup"><span data-stu-id="504f1-258">If you wish to apply parameters to a function on a new line, indent them by one scope.</span></span>

```fsharp
// OK
sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity

// OK
sprintf
     "\t%s - %i\n\r"
     x.IngredientName x.Quantity

// OK
let printVolumes x =
    printf "Volume in liters = %f, in us pints = %f, in imperial = %f"
        (convertVolumeToLiter x)
        (convertVolumeUSPint x)
        (convertVolumeImperialPint x)
```

<span data-ttu-id="504f1-259">Lambda 表达式同样适用于函数参数。</span><span class="sxs-lookup"><span data-stu-id="504f1-259">The same guidelines apply for lambda expressions as function arguments.</span></span> <span data-ttu-id="504f1-260">如果 lambda 表达式的主体，则正文可以有另一行，并按一个作用域缩进</span><span class="sxs-lookup"><span data-stu-id="504f1-260">If the body of a lambda expression, the body can have another line, indented by one scope</span></span>

```fsharp
let printListWithOffset a list1 =
    List.iter
        (fun elem -> printfn "%d" (a + elem))
        list1

// OK if lambda body is long enough
let printListWithOffset a list1 =
    List.iter
        (fun elem ->
            printfn "%d" (a + elem))
        list1
```

<span data-ttu-id="504f1-261">但是，如果 lambda 表达式的主体为多行，请考虑将其分解为单独的函数，而不是将多行构造作为单个参数应用于函数。</span><span class="sxs-lookup"><span data-stu-id="504f1-261">However, if the body of a lambda expression is more than one line, consider factoring it out into a separate function rather than have a multi-line construct applied as a single argument to a function.</span></span>

### <a name="formatting-infix-operators"></a><span data-ttu-id="504f1-262">格式化中缀运算符</span><span class="sxs-lookup"><span data-stu-id="504f1-262">Formatting infix operators</span></span>

<span data-ttu-id="504f1-263">用空格分隔运算符。</span><span class="sxs-lookup"><span data-stu-id="504f1-263">Separate operators by spaces.</span></span> <span data-ttu-id="504f1-264">此规则的明显例外是 `!` 和 `.` 运算符。</span><span class="sxs-lookup"><span data-stu-id="504f1-264">Obvious exceptions to this rule are the `!` and `.` operators.</span></span>

<span data-ttu-id="504f1-265">中缀表达式可在同一列上进行阵容：</span><span class="sxs-lookup"><span data-stu-id="504f1-265">Infix expressions are OK to lineup on same column:</span></span>

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a><span data-ttu-id="504f1-266">格式化管道运算符</span><span class="sxs-lookup"><span data-stu-id="504f1-266">Formatting pipeline operators</span></span>

<span data-ttu-id="504f1-267">管道 `|>` 运算符应位于它们所操作的表达式的下面。</span><span class="sxs-lookup"><span data-stu-id="504f1-267">Pipeline `|>` operators should go underneath the expressions they operate on.</span></span>

```fsharp
// Preferred approach
let methods2 =
    System.AppDomain.CurrentDomain.GetAssemblies()
    |> List.ofArray
    |> List.map (fun assm -> assm.GetTypes())
    |> Array.concat
    |> List.ofArray
    |> List.map (fun t -> t.GetMethods())
    |> Array.concat

// Not OK
let methods2 = System.AppDomain.CurrentDomain.GetAssemblies()
            |> List.ofArray
            |> List.map (fun assm -> assm.GetTypes())
            |> Array.concat
            |> List.ofArray
            |> List.map (fun t -> t.GetMethods())
            |> Array.concat
```

### <a name="formatting-modules"></a><span data-ttu-id="504f1-268">格式化模块</span><span class="sxs-lookup"><span data-stu-id="504f1-268">Formatting modules</span></span>

<span data-ttu-id="504f1-269">本地模块中的代码必须相对于模块缩进，但不应缩进顶级模块中的代码。</span><span class="sxs-lookup"><span data-stu-id="504f1-269">Code in a local module must be indented relative to the module, but code in a top-level module should not be indented.</span></span> <span data-ttu-id="504f1-270">命名空间元素不必缩进。</span><span class="sxs-lookup"><span data-stu-id="504f1-270">Namespace elements do not have to be indented.</span></span>

```fsharp
// A is a top-level module.
module A

let function1 a b = a - b * b
```

```fsharp
// A1 and A2 are local modules.
module A1 =
    let function1 a b = a * a + b * b

module A2 =
    let function2 a b = a * a - b * b
```

### <a name="formatting-object-expressions-and-interfaces"></a><span data-ttu-id="504f1-271">设置对象表达式和接口的格式</span><span class="sxs-lookup"><span data-stu-id="504f1-271">Formatting object expressions and interfaces</span></span>

<span data-ttu-id="504f1-272">对象表达式和接口的对齐方式应与在 `member` 四个空格后缩进的方式相同。</span><span class="sxs-lookup"><span data-stu-id="504f1-272">Object expressions and interfaces should be aligned in the same way with `member` being indented after four spaces.</span></span>

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s: String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-white-space-in-expressions"></a><span data-ttu-id="504f1-273">格式化表达式中的空白区域</span><span class="sxs-lookup"><span data-stu-id="504f1-273">Formatting white space in expressions</span></span>

<span data-ttu-id="504f1-274">避免 F # 表达式中有多余的空格。</span><span class="sxs-lookup"><span data-stu-id="504f1-274">Avoid extraneous white space in F# expressions.</span></span>

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

<span data-ttu-id="504f1-275">命名参数的周围还不应包含间距 `=` ：</span><span class="sxs-lookup"><span data-stu-id="504f1-275">Named arguments should also not have space surrounding the `=`:</span></span>

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```

### <a name="formatting-constructors-static-members-and-member-invocations"></a><span data-ttu-id="504f1-276">格式化构造函数、静态成员和成员调用</span><span class="sxs-lookup"><span data-stu-id="504f1-276">Formatting constructors, static members and member invocations</span></span>

<span data-ttu-id="504f1-277">如果表达式为 short，则用空格分隔参数，并将其保留在一行中。</span><span class="sxs-lookup"><span data-stu-id="504f1-277">If the expression is short, separate arguments with spaces and keep it in one line.</span></span>

```fsharp
let person = new Person(a1, a2)

let myRegexMatch = Regex.Match(input, regex)

let untypedRes = checker.ParseFile(file, source, opts)
```

<span data-ttu-id="504f1-278">如果表达式过长，则使用换行符并缩进一个作用域，而不是缩进到方括号。</span><span class="sxs-lookup"><span data-stu-id="504f1-278">If the expression is long, use newlines and indent one scope, rather than indenting to the bracket.</span></span>

```fsharp
let person =
    new Person(
        argument1,
        argument2
    )

let myRegexMatch =
    Regex.Match(
        "my longer input string with some interesting content in it",
        "myRegexPattern"
    )

let untypedRes =
    checker.ParseFile(
        fileName,
        sourceText,
        parsingOptionsWithDefines
    )
```

## <a name="formatting-attributes"></a><span data-ttu-id="504f1-279">格式设置特性</span><span class="sxs-lookup"><span data-stu-id="504f1-279">Formatting attributes</span></span>

<span data-ttu-id="504f1-280">[特性](../language-reference/attributes.md) 位于构造之上：</span><span class="sxs-lookup"><span data-stu-id="504f1-280">[Attributes](../language-reference/attributes.md) are placed above a construct:</span></span>

```fsharp
[<SomeAttribute>]
type MyClass() = ...

[<RequireQualifiedAccess>]
module M =
    let f x = x

[<Struct>]
type MyRecord =
    { Label1: int
      Label2: string }
```

<span data-ttu-id="504f1-281">它们应该在任何 XML 文档之后：</span><span class="sxs-lookup"><span data-stu-id="504f1-281">They should go after any XML documentation:</span></span>

```fsharp
/// Module with some things in it.
[<RequireQualifiedAccess>]
module M =
    let f x = x
```

### <a name="formatting-attributes-on-parameters"></a><span data-ttu-id="504f1-282">格式化参数上的特性</span><span class="sxs-lookup"><span data-stu-id="504f1-282">Formatting attributes on parameters</span></span>

<span data-ttu-id="504f1-283">还可以将属性放置在参数上。</span><span class="sxs-lookup"><span data-stu-id="504f1-283">Attributes can also be placed on parameters.</span></span> <span data-ttu-id="504f1-284">在这种情况下，请将其放在与参数相同的行上，并在名称之前：</span><span class="sxs-lookup"><span data-stu-id="504f1-284">In this case, place then on the same line as the parameter and before the name:</span></span>

```fsharp
// Defines a class that takes an optional value as input defaulting to false.
type C() =
    member _.M([<Optional; DefaultParameterValue(false)>] doSomething: bool)
```

### <a name="formatting-multiple-attributes"></a><span data-ttu-id="504f1-285">设置多个属性的格式</span><span class="sxs-lookup"><span data-stu-id="504f1-285">Formatting multiple attributes</span></span>

<span data-ttu-id="504f1-286">如果将多个特性应用于不是参数的构造，则应将它们放在每行中都有一个属性：</span><span class="sxs-lookup"><span data-stu-id="504f1-286">When multiple attributes are applied to a construct that is not a parameter, they should be placed such that there is one attribute per line:</span></span>

```fsharp
[<Struct>]
[<IsByRefLike>]
type MyRecord =
    { Label1: int
      Label2: string }
```

<span data-ttu-id="504f1-287">当应用于参数时，它们必须位于同一行上并由 `;` 分隔符分隔。</span><span class="sxs-lookup"><span data-stu-id="504f1-287">When applied to a parameter, they must be on the same line and separated by a `;` separator.</span></span>

## <a name="formatting-literals"></a><span data-ttu-id="504f1-288">设置文本格式</span><span class="sxs-lookup"><span data-stu-id="504f1-288">Formatting literals</span></span>

<span data-ttu-id="504f1-289">使用特性的[F # 文本](../language-reference/literals.md) `Literal` 应将属性置于其自己的行上，并使用 PascalCase 命名：</span><span class="sxs-lookup"><span data-stu-id="504f1-289">[F# literals](../language-reference/literals.md) using the `Literal` attribute should place the attribute on its own line and use PascalCase naming:</span></span>

```fsharp
[<Literal>]
let Path = __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let MyUrl = "www.mywebsitethatiamworkingwith.com"
```

<span data-ttu-id="504f1-290">避免将属性放置在与值相同的行上。</span><span class="sxs-lookup"><span data-stu-id="504f1-290">Avoid placing the attribute on the same line as the value.</span></span>

## <a name="formatting-computation-expression-operations"></a><span data-ttu-id="504f1-291">格式化计算表达式操作</span><span class="sxs-lookup"><span data-stu-id="504f1-291">Formatting computation expression operations</span></span>

<span data-ttu-id="504f1-292">为 [计算表达式](../language-reference/computation-expressions.md) 创建自定义操作时，建议使用 camelCase 命名：</span><span class="sxs-lookup"><span data-stu-id="504f1-292">When creating custom operations for [computation expressions](../language-reference/computation-expressions.md) it is recommended to use camelCase naming:</span></span>

```fsharp
type MathBuilder () =
    member _.Yield _ = 0

    [<CustomOperation("addOne")>]
    member _.AddOne (state: int) =
        state + 1

    [<CustomOperation("subtractOne")>]
    member _.SubtractOne (state: int) =
        state - 1

    [<CustomOperation("divideBy")>]
    member _.DivideBy (state: int, divisor: int) =
        state / divisor

    [<CustomOperation("multiplyBy")>]
    member _.MultiplyBy (state: int, factor: int) =
        state * factor

let math = MathBuilder()

// 10
let myNumber =
    math {
        addOne
        addOne
        addOne

        subtractOne

        divideBy 2

        multiplyBy 10
    }
```

<span data-ttu-id="504f1-293">所使用的命名约定最终应由要建模的域驱动。</span><span class="sxs-lookup"><span data-stu-id="504f1-293">The naming convention used should ultimately be driven by the domain being modeled.</span></span>
<span data-ttu-id="504f1-294">如果惯用使用不同的约定，应改为使用该约定。</span><span class="sxs-lookup"><span data-stu-id="504f1-294">If it is idiomatic to use a different convention, that convention should be used instead.</span></span>
