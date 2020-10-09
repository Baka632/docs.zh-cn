---
title: 本地函数 - C# 编程指南
description: C# 中的本地函数是嵌套在另一成员中并且可以从其包含成员中调用的私有方法。
ms.date: 10/02/2020
helpviewer_keywords:
- local functions [C#]
ms.openlocfilehash: a91995757048c8c54253d7f4b923d5194f69bc7b
ms.sourcegitcommit: 4d45bda8cd9558ea8af4be591e3d5a29360c1ece
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2020
ms.locfileid: "91654915"
---
# <a name="local-functions-c-programming-guide"></a>本地函数（C# 编程指南）

从 C# 7.0 开始，C# *支持本地函数*。 本地函数是一种嵌套在另一成员中的类型的私有方法。 仅能从其包含成员中调用它们。 可以在以下位置中声明和调用本地函数：

- 方法（尤其是迭代器方法和异步方法）
- 构造函数
- 属性访问器
- 事件访问器
- 匿名方法
- Lambda 表达式
- 终结器
- 其他本地函数

但是，不能在 expression-bodied 成员中声明本地函数。

> [!NOTE]
> 在某些情况下，可以使用 lambda 表达式实现本地函数也支持的功能。 有关比较，请参阅[本地函数与 lambda 表达式](#local-functions-vs-lambda-expressions)。

本地函数可使代码意图明确。 任何读取代码的人都可以看到，此方法不可调用，包含方法除外。 对于团队项目，它们也使得其他开发人员无法直接从类或结构中的其他位置错误调用此方法。

## <a name="local-function-syntax"></a>本地函数语法

本地函数被定义为包含成员中的嵌套方法。 其定义具有以下语法：

```csharp
<modifiers> <return-type> <method-name> <parameter-list>
```

可以将以下修饰符用于本地函数：

- [`async`](../../language-reference/keywords/async.md)
- [`unsafe`](../../language-reference/keywords/unsafe.md)
- [`static`](../../language-reference/keywords/static.md)（在 C# 8.0 和更高版本中）。 静态本地函数无法捕获局部变量或实例状态。
- [`extern`](../../language-reference/keywords/extern.md)（在 C# 9.0 和更高版本中）。 外部本地函数必须为 `static`。

在包含成员中定义的所有本地变量（包括其方法参数）都可在非静态本地函数中访问。

与方法定义不同，本地函数定义不能包含成员访问修饰符。 因为所有本地函数都是私有的，包括访问修饰符（如 `private` 关键字）会生成编译器错误 CS0106“修饰符‘private’对于此项无效”。

此外，属性不能应用于本地函数或其参数和类型参数。

以下示例定义了一个名为 `AppendPathSeparator` 的本地函数，该函数对于名为 `GetText` 的方法是私有的：

[!code-csharp[LocalFunctionExample](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions1.cs)]  

## <a name="local-functions-and-exceptions"></a>本地函数和异常

本地函数的一个实用功能是可以允许立即显示异常。 对于方法迭代器，仅在枚举返回的序列时才显示异常，而非在检索迭代器时。 对于异步方法，在等待返回的任务时，将观察到异步方法中引发的任何异常。

以下示例定义 `OddSequence` 方法，用于枚举指定范围之间的奇数。 因为它会将一个大于 100 的数字传递到 `OddSequence` 迭代器方法，该方法将引发 <xref:System.ArgumentOutOfRangeException>。 如示例中的输出所示，仅当循环访问数字时才显示异常，而非检索迭代器时。

[!code-csharp[LocalFunctionIterator1](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-iterator1.cs)]

相反，可以在执行验证时和通过从本地函数返回迭代器检索迭代器之前引发异常，如以下示例所示。

[!code-csharp[LocalFunctionIterator2](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-iterator2.cs)]

可以通过类似的方式使用本地函数来处理异步操作之外的异常。 异步方法中引发的异常通常都需要检查 <xref:System.AggregateException> 的内部异常。 本地函数允许代码快速失败，并允许同步引发和观察异常。

以下示例使用名为 `GetMultipleAsync` 的异步方法暂停指定的秒数并返回一个值，该值是该秒数的任意倍数。 最大延迟为 5 秒；如果该值大于 5，则结果为 <xref:System.ArgumentOutOfRangeException>。 如以下示例所示，开始执行 `GetMultipleAsync` 方法后，将值 6 传递到 `GetMultipleAsync` 方法时引发的异常将在 <xref:System.AggregateException> 中进行包装。

[!code-csharp[LocalFunctionAsync](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-async1.cs)]

正如处理方法迭代器一样，可以在调用异步方法之前重构本示例中的代码以执行验证。 如以下示例中的输出所示，<xref:System.ArgumentOutOfRangeException> 不在 <xref:System.AggregateException> 中进行包装。

[!code-csharp[LocalFunctionAsync](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-async2.cs)]

## <a name="local-functions-vs-lambda-expressions"></a>本地函数与 Lambda 表达式

乍看之下，本地函数和 [lambda 表达式](../../language-reference/operators/lambda-expressions.md)非常相似。 在许多情况下，选择使用 Lambda 表达式还是本地函数是风格和个人偏好的问题。 但是，应该注意，从两者中选用一种的时机和条件其实是存在差别的。

让我们检查一下阶乘算法的本地函数实现和 lambda 表达式实现之间的差异。 首先使用本地函数的版本：

[!code-csharp[LocalFunctionFactorial](../../../../samples/snippets/csharp/new-in-7/MathUtilities.cs#37_LocalFunctionFactorial "Recursive factorial using local function")]

将该实现与使用 Lambda 表达式的版本对比：

[!code-csharp[26_LambdaFactorial](../../../../samples/snippets/csharp/new-in-7/MathUtilities.cs#38_LambdaFactorial "Recursive factorial using lambda expressions")]

本地函数具有名称。 Lambda 表达式是赋给 `Func` 或 `Action` 类型变量的匿名方法。 在声明本地函数时，参数类型和返回类型是函数声明的一部分。 参数类型和返回类型不是 Lambda 表达式主体的一部分，而是 Lambda 表达式变量类型声明的一部分。 这两种差别可以产生跟清楚的代码。

本地函数的明确赋值规则与 Lambda 表达式的不同。 从范围内的任意代码位置都可以引用本地函数声明。 在可以访问（或通过引用 Lambda 表达式的委托调用）Lambda 表达式之前，必须先将 Lambda 表达式赋给委托变量。 请注意，使用 lambda 表达式的版本必须先定义 lambda 表达式 `nthFactorial`，然后再对其进行声明并实例化。 否则，会导致分配前引用 `nthFactorial` 时出现编译时错误。 这些区别意味着使用本地函数创建递归算法会更轻松。 你可以声明和定义一个调用自身的本地函数。 必须声明 Lambda 表达式，赋给默认值，然后才能将其重新赋给引用相同 Lambda 表达式的主体。

明确分配规则也会影响本地函数或 Lambda 表达式捕获的任何变量。 本地函数和 Lambda 表达式规则都要求在将本地函数或 Lambda 表达式转换为委托时，明确分配任何捕获的变量。 区别在于 Lambda 表达式在声明时转换为委托。 只有在用作委托时，本地函数才转换为委托。 如果声明了本地函数，但只是通过像调用方法一样调用该函数来引用该函数，它将不会转换成委托。 使用该规则可在封闭范围内的任何方便的位置声明本地函数。 声明本地函数的位置常见于父方法的末尾和返回任何语句后方。

第三，编译器可以执行静态分析，因此本地函数能够在封闭范围内明确分配捕获的变量。 请看以下示例：

```csharp
int M()
{
    int y;
    LocalFunction();
    return y;

    void LocalFunction() => y = 0;
}
```

编译器可以确定 `LocalFunction` 在调用时明确分配 `y`。 因为在 `return` 语句之前调用了 `LocalFunction`，所以在 `return` 语句中明确分配了 `y`。

可实现示例分析的分析允许第四个差异。 根据它们的用途，本地函数可以避免 Lambda 表达式始终需要的堆分配。 如果本地函数永远不会转换为委托，并且本地函数捕获的变量都不会被其他转换为委托的 lambda 或本地函数捕获，则编译器可以避免堆分配。

请看以下异步示例：

[!code-csharp[TaskLambdaExample](../../../../samples/snippets/csharp/new-in-7/AsyncWork.cs#36_TaskLambdaExample "Task returning method with lambda expression")]

该 lambda 表达式的闭包包含 `address`、`index` 和 `name` 变量。 就本地函数而言，实现闭包的对象可能为 `struct` 类型。 该结构类型将通过引用传递给本地函数。 实现中的这个差异将保存在分配上。

Lambda 表达式所需的实例化意味着额外的内存分配，后者可能是时间关键代码路径中的性能因素。 本地函数不会产生这种开销。 在以上示例中，本地函数版本具有的分配比 lambda 表达式版本少 2 个。

> [!NOTE]
> 等效于此方法的本地函数还将类用于闭包。 实现详细信息包括本地函数的闭包是作为 `class` 还是 `struct` 实现。 本地函数可能使用 `struct`，而 lambda 将始终使用 `class`。

[!code-csharp[TaskLocalFunctionExample](../../../../samples/snippets/csharp/new-in-7/AsyncWork.cs#TaskExample "Task returning method with local function")]

在本示例中尚未演示的最后一个优点是，可将本地函数作为迭代器实现，使用 `yield return` 语法生成一系列值。 Lambda 表达式中不允许使用 `yield return` 语句。

虽然本地函数对 lambda 表达式可能有点冗余，但实际上它们的目的和用法都不一样。 如果想要编写仅从上下文或其他方法中调用的函数，则使用本地函数更高效。

## <a name="see-also"></a>请参阅

- [方法](methods.md)
