---
title: 'Visual Studio for Mac 中的 F # 入门'
description: '了解如何在 Visual Studio for Mac 中使用 F #。'
ms.date: 07/03/2018
ms.openlocfilehash: d2ad24ad18bb31419b39508f2cf555c82fbe2e0b
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2020
ms.locfileid: "96437992"
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a><span data-ttu-id="9b3fc-103">Visual Studio for Mac 中的 F # 入门</span><span class="sxs-lookup"><span data-stu-id="9b3fc-103">Get started with F# in Visual Studio for Mac</span></span>

<span data-ttu-id="9b3fc-104">Visual Studio for Mac IDE 支持 F # 和 Visual F# 工具。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-104">F# and the Visual F# tooling are supported in the Visual Studio for Mac IDE.</span></span> <span data-ttu-id="9b3fc-105">确保已 [安装 Visual Studio for Mac](install-fsharp.md#install-f-with-visual-studio-for-mac)。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-105">Ensure that you have [Visual Studio for Mac installed](install-fsharp.md#install-f-with-visual-studio-for-mac).</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="9b3fc-106">创建控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="9b3fc-106">Creating a console application</span></span>

<span data-ttu-id="9b3fc-107">Visual Studio for Mac 中最基本的项目之一是控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-107">One of the most basic projects in Visual Studio for Mac is the Console Application.</span></span>  <span data-ttu-id="9b3fc-108">下面介绍如何执行该操作。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-108">Here's how to do it.</span></span>  <span data-ttu-id="9b3fc-109">打开 Visual Studio for Mac 后：</span><span class="sxs-lookup"><span data-stu-id="9b3fc-109">Once Visual Studio for Mac is open:</span></span>

1. <span data-ttu-id="9b3fc-110">在 " **文件** " 菜单上，指向 " **新建解决方案**"。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-110">On the **File** menu, point to **New Solution**.</span></span>

2. <span data-ttu-id="9b3fc-111">在 "新建项目" 对话框中，控制台应用程序有两个不同的模板。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-111">In the New Project dialog, there are 2 different templates for Console Application.</span></span>  <span data-ttu-id="9b3fc-112">在其他 > 的 .NET 中有一个面向 .NET Framework 的。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-112">There is one under Other -> .NET which targets the .NET Framework.</span></span>  <span data-ttu-id="9b3fc-113">另一个模板位于 .NET Core 下，即面向 .NET Core > 应用。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-113">The other template is under .NET Core -> App which targets .NET Core.</span></span>  <span data-ttu-id="9b3fc-114">这两个模板都适用于本文的目的。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-114">Either template should work for the purpose of this article.</span></span>

3. <span data-ttu-id="9b3fc-115">如果需要，在 "控制台应用" 下，将 c # 改为 F #。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-115">Under console app, change C# to F# if needed.</span></span>  <span data-ttu-id="9b3fc-116">选择 " **下一步** " 按钮继续！</span><span class="sxs-lookup"><span data-stu-id="9b3fc-116">Choose the **Next** button to move forward!</span></span>  

4. <span data-ttu-id="9b3fc-117">为项目命名，并为应用选择所需的选项。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-117">Give your project a name, and choose the options you want for the app.</span></span>  <span data-ttu-id="9b3fc-118">请注意，屏幕右侧的预览窗格将显示将根据所选选项创建的目录结构。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-118">Notice, the preview pane to the side of the screen that will show the directory structure that will be created based on the options selected.</span></span>  

5. <span data-ttu-id="9b3fc-119">单击“创建”。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-119">Click **Create**.</span></span>  <span data-ttu-id="9b3fc-120">现在应会在解决方案资源管理器中看到一个 F # 项目。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-120">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="9b3fc-121">编写代码</span><span class="sxs-lookup"><span data-stu-id="9b3fc-121">Writing your code</span></span>

<span data-ttu-id="9b3fc-122">让我们首先编写一些代码。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-122">Let's get started by writing some code first.</span></span>  <span data-ttu-id="9b3fc-123">确保该 `Program.fs` 文件已打开，然后将其内容替换为以下内容：</span><span class="sxs-lookup"><span data-stu-id="9b3fc-123">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="9b3fc-124">在上面的代码示例中，已定义了一个函数， `square` 该函数采用一个名为的输入 `x` ，并将其与自身相乘。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-124">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="9b3fc-125">由于 F # 使用 [类型推理](../language-reference/type-inference.md)，因此 `x` 不需要指定的类型。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-125">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="9b3fc-126">F # 编译器了解乘法的有效类型，并根据调用方式将类型分配给 `x` `square` 。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-126">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="9b3fc-127">如果将鼠标悬停在上方 `square` ，应会看到以下内容：</span><span class="sxs-lookup"><span data-stu-id="9b3fc-127">If you hover over `square`, you should see the following:</span></span>

```console
val square: x:int -> int
```

<span data-ttu-id="9b3fc-128">这就是所谓函数的类型签名。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-128">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="9b3fc-129">可以按如下所示读取： "方形是一个函数，它采用名为 x 的整数并生成一个整数"。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-129">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="9b3fc-130">请注意，编译器 `square` 现在提供 `int` 类型，这是因为乘法在 *所有* 类型中都不是泛型的，而是在一组封闭类型中是通用的。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-130">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="9b3fc-131">此时将选取 F # 编译器 `int` ，但如果您 `square` 使用其他输入类型（如）调用，则会调整类型签名 `float` 。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-131">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="9b3fc-132">定义了另一个函数， `main` 该函数用特性修饰，用 `EntryPoint` 来告知 F # 编译器程序执行应在此开始。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-132">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="9b3fc-133">它遵循与其他 [C 样式编程语言](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B)相同的约定，可以将命令行参数传递给此函数，并 (通常) 返回整数代码 `0` 。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-133">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="9b3fc-134">在此函数中，我们使用的参数调用了 `square` 函数 `12` 。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-134">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="9b3fc-135">然后，F # 编译器将的类型分配为 `square` `int -> int` (即，使用 `int` 并生成) 的函数 `int` 。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-135">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="9b3fc-136">对的调用 `printfn` 是一个格式化的打印函数，它使用格式字符串（类似于 C 样式编程语言）、与在格式字符串中指定的参数相对应的参数，然后输出结果和新行。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-136">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="9b3fc-137">运行代码</span><span class="sxs-lookup"><span data-stu-id="9b3fc-137">Running your code</span></span>

<span data-ttu-id="9b3fc-138">可以通过单击顶级菜单中的 " **运行** " 来运行代码并查看结果，然后在 **不调试的情况下启动**。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-138">You can run the code and see results by clicking on **Run** from the top level menu and then **Start Without Debugging**.</span></span>  <span data-ttu-id="9b3fc-139">这将在不调试的情况下运行程序，并允许你查看结果。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-139">This will run the program without debugging and allows you to see the results.</span></span>

<span data-ttu-id="9b3fc-140">现在，应会看到以下输出到 Visual Studio for Mac 弹出的控制台窗口：</span><span class="sxs-lookup"><span data-stu-id="9b3fc-140">You should now see the following printed to the console window that Visual Studio for Mac popped up:</span></span>

```console
12 squared is 144!
```

<span data-ttu-id="9b3fc-141">祝贺你！</span><span class="sxs-lookup"><span data-stu-id="9b3fc-141">Congratulations!</span></span>  <span data-ttu-id="9b3fc-142">已在 Visual Studio for Mac 中创建了第一个 F # 项目，并编写了一个 F # 函数，该函数将调用该函数的结果输出，并运行该项目以查看一些结果。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-142">You've created your first F# project in Visual Studio for Mac, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="using-f-interactive"></a><span data-ttu-id="9b3fc-143">使用 F# 交互窗口</span><span class="sxs-lookup"><span data-stu-id="9b3fc-143">Using F# Interactive</span></span>

<span data-ttu-id="9b3fc-144">Visual Studio for Mac Visual F# 工具的最佳功能之一是 F# 交互窗口 "窗口。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-144">One of the best features of the Visual F# tooling in Visual Studio for Mac is the F# Interactive Window.</span></span>  <span data-ttu-id="9b3fc-145">它允许你将代码发送到可调用该代码并以交互方式查看结果的进程。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-145">It allows you to send code over to a process where you can call that code and see the result interactively.</span></span>

<span data-ttu-id="9b3fc-146">若要开始使用它，请突出显示 `square` 代码中定义的函数。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-146">To begin using it, highlight the `square` function defined in your code.</span></span>  <span data-ttu-id="9b3fc-147">接下来，单击顶部菜单中的 " **编辑** "。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-147">Next, click on **Edit** from the top level menu.</span></span>  <span data-ttu-id="9b3fc-148">接下来 **，选择 "发送所选内容" F# 交互窗口**。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-148">Next select **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="9b3fc-149">这会执行 "F# 交互窗口" 窗口中的代码。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-149">This executes the code in the F# Interactive Window.</span></span>  <span data-ttu-id="9b3fc-150">也可以右键单击所选内容，然后选择 " **将所选内容发送到 F# 交互窗口**"。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-150">Alternatively, you can right click on the selection and choose **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="9b3fc-151">应会看到 "F# 交互窗口" 窗口中显示以下内容：</span><span class="sxs-lookup"><span data-stu-id="9b3fc-151">You should see the F# Interactive Window appear with the following in it:</span></span>

```console
>

val square : x:int -> int

>
```

<span data-ttu-id="9b3fc-152">这会显示函数的相同函数签名 `square` ，在您前面悬停该函数时，您会看到此函数签名。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-152">This shows the same function signature for the `square` function, which you saw earlier when you hovered over the function.</span></span>  <span data-ttu-id="9b3fc-153">由于 `square` 现在是在 F# 交互窗口进程中定义的，因此可以通过不同的值调用它：</span><span class="sxs-lookup"><span data-stu-id="9b3fc-153">Because `square` is now defined in the F# Interactive process, you can call it with different values:</span></span>

```console
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

<span data-ttu-id="9b3fc-154">这会执行函数，将结果绑定到新名称 `it` ，并显示的类型和值 `it` 。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-154">This executes the function, binds the result to a new name `it`, and displays the type and value of `it`.</span></span>  <span data-ttu-id="9b3fc-155">请注意，必须用终止每行 `;;` 。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-155">Note that you must terminate each line with `;;`.</span></span>  <span data-ttu-id="9b3fc-156">这是 F# 交互窗口知道函数调用完成的时间。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-156">This is how F# Interactive knows when your function call is finished.</span></span>  <span data-ttu-id="9b3fc-157">您还可以在 F# 交互窗口中定义新函数：</span><span class="sxs-lookup"><span data-stu-id="9b3fc-157">You can also define new functions in F# Interactive:</span></span>

```console
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

<span data-ttu-id="9b3fc-158">上面定义了一个新函数， `isOdd` 该函数采用 `int` 并检查它是否为奇数！</span><span class="sxs-lookup"><span data-stu-id="9b3fc-158">The above defines a new function, `isOdd`, which takes an `int` and checks to see if it's odd!</span></span>  <span data-ttu-id="9b3fc-159">您可以调用此函数，以查看它如何返回不同的输入。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-159">You can call this function to see what it returns with different inputs.</span></span>  <span data-ttu-id="9b3fc-160">可以在函数调用中调用函数：</span><span class="sxs-lookup"><span data-stu-id="9b3fc-160">You can call functions within function calls:</span></span>

```console
> isOdd (square 15);;
val it : bool = true
```

<span data-ttu-id="9b3fc-161">还可以使用 [管道转发运算符](../language-reference/symbol-and-operator-reference/index.md) 将值传递给两个函数：</span><span class="sxs-lookup"><span data-stu-id="9b3fc-161">You can also use the [pipe-forward operator](../language-reference/symbol-and-operator-reference/index.md) to pipeline the value into the two functions:</span></span>

```console
> 15 |> square |> isOdd;;
val it : bool = true
```

<span data-ttu-id="9b3fc-162">后面的教程中介绍了管道转发运算符等。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-162">The pipe-forward operator, and more, are covered in later tutorials.</span></span>

<span data-ttu-id="9b3fc-163">这只是了解到 F# 交互窗口可以执行的操作。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-163">This is only a glimpse into what you can do with F# Interactive.</span></span>  <span data-ttu-id="9b3fc-164">若要了解详细信息，请参阅 [F # 的交互式编程](../tools/fsharp-interactive/index.md)。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-164">To learn more, check out [Interactive Programming with F#](../tools/fsharp-interactive/index.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="9b3fc-165">后续步骤</span><span class="sxs-lookup"><span data-stu-id="9b3fc-165">Next steps</span></span>

<span data-ttu-id="9b3fc-166">如果你尚未阅读，请查看 [f # 教程](../tour.md)，其中介绍了 f # 语言的一些核心功能。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-166">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="9b3fc-167">它将概述 F # 的某些功能，并提供可复制到 Visual Studio for Mac 并运行的丰富代码示例。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-167">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio for Mac and run.</span></span>  <span data-ttu-id="9b3fc-168">在 [F # 指南](../index.yml)中，还可以使用一些很好的外部资源，展示。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-168">There are also some great external resources you can use, showcased in the [F# Guide](../index.yml).</span></span>

## <a name="see-also"></a><span data-ttu-id="9b3fc-169">请参阅</span><span class="sxs-lookup"><span data-stu-id="9b3fc-169">See also</span></span>

- [<span data-ttu-id="9b3fc-170">F# 指南</span><span class="sxs-lookup"><span data-stu-id="9b3fc-170">F# guide</span></span>](../index.yml)
- [<span data-ttu-id="9b3fc-171">F# 教程</span><span class="sxs-lookup"><span data-stu-id="9b3fc-171">Tour of F#</span></span>](../tour.md)
- [<span data-ttu-id="9b3fc-172">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="9b3fc-172">F# language reference</span></span>](../language-reference/index.md)
- [<span data-ttu-id="9b3fc-173">类型推理</span><span class="sxs-lookup"><span data-stu-id="9b3fc-173">Type inference</span></span>](../language-reference/type-inference.md)
- [<span data-ttu-id="9b3fc-174">符号和运算符引用</span><span class="sxs-lookup"><span data-stu-id="9b3fc-174">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)
