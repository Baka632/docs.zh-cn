---
title: 使用 Visual Studio Code 调试 .NET 控制台应用程序
description: 了解如何使用 Visual Studio Code 调试 .NET 控制台应用。
ms.date: 05/26/2020
ms.openlocfilehash: 7215ed4a93b31ebac313c04708734667148c4e02
ms.sourcegitcommit: 30fef5b0ed76e334377d28fa8e80159b29353e10
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2020
ms.locfileid: "96556104"
---
# <a name="tutorial-debug-a-net-console-application-using-visual-studio-code"></a><span data-ttu-id="4b3c7-103">教程：使用 Visual Studio Code 调试 .NET 控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="4b3c7-103">Tutorial: Debug a .NET console application using Visual Studio Code</span></span>

<span data-ttu-id="4b3c7-104">本教程介绍了 Visual Studio Code 中可用于处理 .NET 应用的调试工具。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-104">This tutorial introduces the debugging tools available in Visual Studio Code for working with .NET apps.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4b3c7-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="4b3c7-105">Prerequisites</span></span>

- <span data-ttu-id="4b3c7-106">本教程适用于在[使用 Visual Studio Code 创建 .NET 控制台应用程序](with-visual-studio-code.md)中创建的控制台应用。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-106">This tutorial works with the console app that you create in [Create a .NET console application using Visual Studio Code](with-visual-studio-code.md).</span></span>

## <a name="use-debug-build-configuration"></a><span data-ttu-id="4b3c7-107">使用“调试”生成配置</span><span class="sxs-lookup"><span data-stu-id="4b3c7-107">Use Debug build configuration</span></span>

<span data-ttu-id="4b3c7-108">“调试”和“发布”是 .NET Core 的内置生成配置 。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-108">*Debug* and *Release* are .NET Core's built-in build configurations.</span></span> <span data-ttu-id="4b3c7-109">可使用“调试”生成配置进行调试，使用“发布”配置进行最终版本分发。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-109">You use the Debug build configuration for debugging and the Release configuration for the final release distribution.</span></span>

<span data-ttu-id="4b3c7-110">在“调试”配置中，程序使用完整符号调试信息编译，且不进行优化。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-110">In the Debug configuration, a program compiles with full symbolic debug information and no optimization.</span></span> <span data-ttu-id="4b3c7-111">优化会使调试复杂化，因为源代码和生成的指令之间的关系更加复杂。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-111">Optimization complicates debugging, because the relationship between source code and generated instructions is more complex.</span></span> <span data-ttu-id="4b3c7-112">程序的发布配置进行了完全优化，且不包含任何符号调试信息。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-112">The release configuration of a program has no symbolic debug information and is fully optimized.</span></span>

<span data-ttu-id="4b3c7-113">默认情况下，Visual Studio Code 启动设置使用“调试”生成配置，因此不需要在调试之前对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-113">By default, Visual Studio Code launch settings use the Debug build configuration, so you don't need to change it before debugging.</span></span>

1. <span data-ttu-id="4b3c7-114">启动 Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-114">Start Visual Studio Code.</span></span>

1. <span data-ttu-id="4b3c7-115">打开在[使用 Visual Studio Code 中创建 .NET 控制台应用程序](with-visual-studio-code.md)中创建的项目的文件夹。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-115">Open the folder of the project that you created in [Create a .NET console application using Visual Studio Code](with-visual-studio-code.md).</span></span>

## <a name="set-a-breakpoint"></a><span data-ttu-id="4b3c7-116">设置断点</span><span class="sxs-lookup"><span data-stu-id="4b3c7-116">Set a breakpoint</span></span>

<span data-ttu-id="4b3c7-117">断点会在执行包含断点的代码行之前暂时中断执行应用程序。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-117">A *breakpoint* temporarily interrupts the execution of the application before the line with the breakpoint is executed.</span></span>

1. <span data-ttu-id="4b3c7-118">打开 *Program.cs* 文件。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-118">Open the *Program.cs* file.</span></span>

1. <span data-ttu-id="4b3c7-119">单击代码窗口的左边缘，在显示名称、日期和时间的行上设置断点。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-119">Set a *breakpoint* on the line that displays the name, date, and time, by clicking in the left margin of the code window.</span></span> <span data-ttu-id="4b3c7-120">左边缘在行号的左侧。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-120">The left margin is to the left of the line numbers.</span></span> <span data-ttu-id="4b3c7-121">设置断点的其他方法是在选中代码行时按 <kbd>F9</kbd> 或从菜单中选择“运行” > “切换断点” 。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-121">Other ways to set a breakpoint are by pressing <kbd>F9</kbd> or choosing **Run** > **Toggle Breakpoint** from the menu while the line of code is selected.</span></span>

   <span data-ttu-id="4b3c7-122">Visual Studio Code 通过在左边缘显示红点来指示设置了断点的行。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-122">Visual Studio Code indicates the line on which the breakpoint is set by displaying a red dot in the left margin.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/breakpoint-set.png" alt-text="断点集":::

## <a name="set-up-for-terminal-input"></a><span data-ttu-id="4b3c7-124">设置终端输入</span><span class="sxs-lookup"><span data-stu-id="4b3c7-124">Set up for terminal input</span></span>

<span data-ttu-id="4b3c7-125">断点位于 `Console.ReadLine` 方法调用之后。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-125">The breakpoint is located after a `Console.ReadLine` method call.</span></span> <span data-ttu-id="4b3c7-126">调试控制台不接受正在运行的程序的终端输入。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-126">The **Debug Console** doesn't accept terminal input for a running program.</span></span> <span data-ttu-id="4b3c7-127">若要在调试时处理终端输入，可以使用集成终端（Visual Studio Code 窗口之一）或外部终端。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-127">To handle terminal input while debugging, you can use the integrated terminal (one of the Visual Studio Code windows) or an external terminal.</span></span> <span data-ttu-id="4b3c7-128">本教程中使用集成终端。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-128">For this tutorial, you use the integrated terminal.</span></span>

1. <span data-ttu-id="4b3c7-129">打开 .vscode/launch.json。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-129">Open *.vscode/launch.json*.</span></span>

1. <span data-ttu-id="4b3c7-130">将 `console` 设置从 `internalConsole` 更改为 `integratedTerminal`：</span><span class="sxs-lookup"><span data-stu-id="4b3c7-130">Change the `console` setting from `internalConsole` to `integratedTerminal`:</span></span>

   ```json
   "console": "integratedTerminal",
   ```

1. <span data-ttu-id="4b3c7-131">保存更改。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-131">Save your changes.</span></span>

## <a name="start-debugging"></a><span data-ttu-id="4b3c7-132">“启动调试”</span><span class="sxs-lookup"><span data-stu-id="4b3c7-132">Start debugging</span></span>

1. <span data-ttu-id="4b3c7-133">选择左侧菜单上的“调试”图标，打开“调试”视图。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-133">Open the Debug view by selecting the Debugging icon on the left side menu.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/select-debug-pane.png" alt-text="在 Visual Studio Code 中打开“调试”选项卡":::

1. <span data-ttu-id="4b3c7-135">选择窗格顶部 .NET Core Launch（控制台）旁边的绿色箭头。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-135">Select the green arrow at the top of the pane, next to **.NET Core Launch (console)**.</span></span> <span data-ttu-id="4b3c7-136">在调试模式下启动程序的其他方法是，按 <kbd>F5</kbd> 或从菜单中选择“运行” > “启动调试” 。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-136">Other ways to start the program in debugging mode are by pressing <kbd>F5</kbd> or choosing **Run** > **Start Debugging** from the menu.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/start-debugging.png" alt-text="开始调试":::

1. <span data-ttu-id="4b3c7-138">选择“终端”选项卡以查看程序在等待响应之前</span><span class="sxs-lookup"><span data-stu-id="4b3c7-138">Select the **Terminal** tab to see the "What is your name?"</span></span> <span data-ttu-id="4b3c7-139">显示的“What is your name?”提示。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-139">prompt that the program displays before waiting for a response.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/select-terminal.png" alt-text="选择“终端”选项卡":::

1. <span data-ttu-id="4b3c7-141">在“终端”窗口中输入字符串以响应输入姓名提示，然后按 <kbd>Enter</kbd>。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-141">Enter a string in the **Terminal** window in response to the prompt for a name, and then press <kbd>Enter</kbd>.</span></span>

   <span data-ttu-id="4b3c7-142">到达断点时，程序停止执行，然后执行 `Console.WriteLine` 方法。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-142">Program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span> <span data-ttu-id="4b3c7-143">“变量”窗口的“局部变量”部分显示当前正在执行的方法中定义的变量值 。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-143">The **Locals** section of the **Variables** window displays the values of variables that are defined in the currently executing method.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/breakpoint-hit.png" alt-text="命中断点，显示局部变量":::

## <a name="use-the-debug-console"></a><span data-ttu-id="4b3c7-145">使用“调试控制台”</span><span class="sxs-lookup"><span data-stu-id="4b3c7-145">Use the Debug Console</span></span>

<span data-ttu-id="4b3c7-146">在“调试控制台”窗口中，可以与正在调试的应用程序进行交互。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-146">The **Debug Console** window lets you interact with the application you're debugging.</span></span> <span data-ttu-id="4b3c7-147">可更改变量值，看看这样会对程序产生哪些影响。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-147">You can change the value of variables to see how it affects your program.</span></span>

1. <span data-ttu-id="4b3c7-148">选择“调试控制台”选项卡。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-148">Select the **Debug Console** tab.</span></span>

1. <span data-ttu-id="4b3c7-149">在“调试控制台”窗口底部的提示符处输入 `name = "Gracie"`，然后按 <kbd>Enter</kbd>。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-149">Enter `name = "Gracie"` at the prompt at the bottom of the **Debug Console** window and press the <kbd>Enter</kbd> key.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/change-variable-values.png" alt-text="更改变量值":::

1. <span data-ttu-id="4b3c7-151">在“调试控制台”窗口底部输入 `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()`，然后按 <kbd>Enter</kbd>。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-151">Enter `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()` at the bottom of the **Debug Console** window and press the <kbd>Enter</kbd> key.</span></span>

   <span data-ttu-id="4b3c7-152">“变量”窗口显示 `name` 和 `date` 变量的新值。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-152">The **Variables** window displays the new values of the `name` and `date` variables.</span></span>

1. <span data-ttu-id="4b3c7-153">选择工具栏中的“继续”按钮继续执行程序。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-153">Continue program execution by selecting the **Continue** button in the toolbar.</span></span> <span data-ttu-id="4b3c7-154">继续操作的另一种方法是按 <kbd>F5</kbd>。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-154">Another way to continue is by pressing <kbd>F5</kbd>.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/continue-debugging.png" alt-text="继续调试":::

1. <span data-ttu-id="4b3c7-156">再次选择“终端”选项卡。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-156">Select the **Terminal** tab again.</span></span>

   <span data-ttu-id="4b3c7-157">控制台窗口中显示的值对应于在“调试控制台”窗口中所做的更改。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-157">The values displayed in the console window correspond to the changes you made in the **Debug Console**.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/changed-variable-values.png" alt-text="显示输入值的终端":::

1. <span data-ttu-id="4b3c7-159">按任意键，退出应用程序并停止调试。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-159">Press any key to exit the application and stop debugging.</span></span>

## <a name="set-a-conditional-breakpoint"></a><span data-ttu-id="4b3c7-160">设置条件断点</span><span class="sxs-lookup"><span data-stu-id="4b3c7-160">Set a conditional breakpoint</span></span>

<span data-ttu-id="4b3c7-161">程序显示用户输入的字符串。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-161">The program displays the string that the user enters.</span></span> <span data-ttu-id="4b3c7-162">如果用户没有输入任何内容，情况又如何呢？</span><span class="sxs-lookup"><span data-stu-id="4b3c7-162">What happens if the user doesn't enter anything?</span></span> <span data-ttu-id="4b3c7-163">可以使用名为“条件断点”的有用调试功能对此进行测试。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-163">You can test this with a useful debugging feature called a *conditional breakpoint*.</span></span>

1. <span data-ttu-id="4b3c7-164">右键单击（在 macOS 上按住 <kbd>Ctrl</kbd> 并单击）表示断点的红点。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-164">Right-click (<kbd>Ctrl</kbd>-click on macOS) on the red dot that represents the breakpoint.</span></span> <span data-ttu-id="4b3c7-165">在上下文菜单中，选择“编辑断点”，打开可输入条件表达式的对话框。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-165">In the context menu, select **Edit Breakpoint** to open a dialog that lets you enter a conditional expression.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/breakpoint-context-menu.png" alt-text="断点上下文菜单":::

1. <span data-ttu-id="4b3c7-167">在下拉菜单中选择 `Expression`，输入以下条件表达式，并按 <kbd>Enter</kbd>。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-167">Select `Expression` in the drop-down, enter the following conditional expression, and press <kbd>Enter</kbd>.</span></span>

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   :::image type="content" source="media/debugging-with-visual-studio-code/conditional-expression.png" alt-text="输入条件表达式":::

   <span data-ttu-id="4b3c7-169">每次命中断点时，调试器都会调用 `String.IsNullOrEmpty(name)` 方法，仅当该方法调用返回 `true` 时，它才会在此行上中断。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-169">Each time the breakpoint is hit, the debugger calls the `String.IsNullOrEmpty(name)` method, and it breaks on this line only if the method call returns `true`.</span></span>

   <span data-ttu-id="4b3c7-170">可以指定命中次数（而不是条件表达式），这样程序就会在语句的执行次数达到指定值时中断执行。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-170">Instead of a conditional expression, you can specify a *hit count*, which interrupts program execution before a statement is executed a specified number of times.</span></span> <span data-ttu-id="4b3c7-171">另一种方法是指定筛选条件，这样就可以根据诸如线程标识符、进程名称或线程名称之类的特性来中断程序执行。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-171">Another option is to specify a *filter condition*, which interrupts program execution based on such attributes as a thread identifier, process name, or thread name.</span></span>

1. <span data-ttu-id="4b3c7-172">通过按 F5<kbd></kbd> 调试来启动程序。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-172">Start the program with debugging by pressing <kbd>F5</kbd>.</span></span>

1. <span data-ttu-id="4b3c7-173">在“终端”选项卡中，在系统提示输入姓名时按 <kbd>Enter</kbd>。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-173">In the **Terminal** tab, press the <kbd>Enter</kbd> key when prompted to enter your name.</span></span>

   <span data-ttu-id="4b3c7-174">由于符合指定的条件（`name` 为 `null` 或 <xref:System.String.Empty?displayProperty=nameWithType>），因此程序会在到达断点时以及在 `Console.WriteLine` 方法执行之前停止执行。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-174">Because the condition you specified (`name` is either `null` or <xref:System.String.Empty?displayProperty=nameWithType>) has been satisfied, program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span>

   <span data-ttu-id="4b3c7-175">“变量”窗口显示 `name` 变量的值为 `""` 或 <xref:System.String.Empty?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-175">The **Variables** window shows that the value of the `name` variable is `""`, or <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>

1. <span data-ttu-id="4b3c7-176">在“调试控制台”提示符中输入下面的语句并按 <kbd>Enter</kbd>，确认值为空字符串。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-176">Confirm the value is an empty string by entering the following statement at the **Debug Console** prompt and pressing <kbd>Enter</kbd>.</span></span> <span data-ttu-id="4b3c7-177">结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-177">The result is `true`.</span></span>

   ```csharp
   name == String.Empty
   ```

   :::image type="content" source="media/debugging-with-visual-studio-code/expression-in-debug-console.png" alt-text="在执行语句后返回 true 值的调试控制台":::

1. <span data-ttu-id="4b3c7-179">选择工具栏上的“继续”按钮，继续执行程序。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-179">Select the **Continue** button on the toolbar to continue program execution.</span></span>

1. <span data-ttu-id="4b3c7-180">选择“终端”选项卡，然后按任意键退出程序，停止调试。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-180">Select the **Terminal** tab, and press any key to exit the program and stop debugging.</span></span>

1. <span data-ttu-id="4b3c7-181">单击代码窗口左边缘上的点，清除断点。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-181">Clear the breakpoint by clicking on the dot in the left margin of the code window.</span></span> <span data-ttu-id="4b3c7-182">清除断点的其他方法是在选中代码行时按 <kbd>F9</kbd> 或从菜单中选择“运行”>“切换断点”。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-182">Other ways to clear a breakpoint are by pressing <kbd>F9</kbd> or choosing **Run > Toggle Breakpoint** from the menu while the line of code is selected.</span></span>

1. <span data-ttu-id="4b3c7-183">如果收到断点条件将丢失的警告，请选择“删除断点”。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-183">If you get a warning that the breakpoint condition will be lost, select **Remove Breakpoint**.</span></span>

## <a name="step-through-a-program"></a><span data-ttu-id="4b3c7-184">单步执行程序</span><span class="sxs-lookup"><span data-stu-id="4b3c7-184">Step through a program</span></span>

<span data-ttu-id="4b3c7-185">使用 Visual Studio Code，还可以单步执行程序，并监视其执行情况。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-185">Visual Studio Code also allows you to step line by line through a program and monitor its execution.</span></span> <span data-ttu-id="4b3c7-186">通常可以设置断点，并通过程序代码的一小部分执行程序流。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-186">Ordinarily, you'd set a breakpoint and follow program flow through a small part of your program code.</span></span> <span data-ttu-id="4b3c7-187">由于此程序很小，因此可以单步执行整个程序。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-187">Since this program is small, you can step through the entire program.</span></span>

1. <span data-ttu-id="4b3c7-188">在 `Main` 方法的左大括号处设置一个断点。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-188">Set a breakpoint on the opening curly brace of the `Main` method.</span></span>

1. <span data-ttu-id="4b3c7-189">按 <kbd>F5</kbd> 启动调试。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-189">Press <kbd>F5</kbd> to start debugging.</span></span>

   <span data-ttu-id="4b3c7-190">Visual Studio Code 突出显示断点行。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-190">Visual Studio Code highlights the breakpoint line.</span></span>

   <span data-ttu-id="4b3c7-191">此时，“变量”窗口显示 `args` 数组为空，`name` 和 `date` 具有默认值。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-191">At this point, the **Variables** window shows that the `args` array is empty, and `name` and `date` have default values.</span></span>

1. <span data-ttu-id="4b3c7-192">选择“运行” > “单步执行”或按 <kbd>F11</kbd>。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-192">Select **Run** > **Step Into** or press <kbd>F11</kbd>.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/step-into.png" alt-text="“单步执行”按钮":::

   <span data-ttu-id="4b3c7-194">Visual Studio Code 突出显示下一行。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-194">Visual Studio Code highlights the next line.</span></span>

1. <span data-ttu-id="4b3c7-195">选择“运行” > “单步执行”或按 <kbd>F11</kbd>。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-195">Select **Run** > **Step Into** or press <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="4b3c7-196">Visual Studio Code 执行名称提示的 `Console.WriteLine` 并突出显示下一执行行。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-196">Visual Studio Code executes the `Console.WriteLine` for the name prompt and highlights the next line of execution.</span></span> <span data-ttu-id="4b3c7-197">下一行是 `name` 的 `Console.ReadLine`。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-197">The next line is the `Console.ReadLine` for the `name`.</span></span> <span data-ttu-id="4b3c7-198">“变量”窗口保持不变，“终端”选项卡显示“What is your name? ”</span><span class="sxs-lookup"><span data-stu-id="4b3c7-198">The **Variables** window is unchanged, and the **Terminal** tab shows the "What is your name?"</span></span> <span data-ttu-id="4b3c7-199">提示。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-199">prompt.</span></span>

1. <span data-ttu-id="4b3c7-200">选择“运行” > “单步执行”或按 <kbd>F11</kbd>。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-200">Select **Run** > **Step Into** or press <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="4b3c7-201">Visual Studio 突出显示 `name` 变量赋值。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-201">Visual Studio highlights the `name` variable assignment.</span></span> <span data-ttu-id="4b3c7-202">“变量”窗口显示 `name` 仍为 `null`。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-202">The **Variables** window shows that `name` is still `null`.</span></span>

1. <span data-ttu-id="4b3c7-203">在“终端”选项卡中输入字符串，然后按 <kbd>Enter</kbd>，响应提示。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-203">Respond to the prompt by entering a string in the Terminal tab and pressing <kbd>Enter</kbd>.</span></span>

   <span data-ttu-id="4b3c7-204">输入字符串时，“终端”选项卡可能无法显示输入的字符串，但 <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> 方法将捕获你的输入。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-204">The **Terminal** tab might not display the string you enter while you're entering it, but the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method will capture your input.</span></span>

1. <span data-ttu-id="4b3c7-205">选择“运行” > “单步执行”或按 <kbd>F11</kbd>。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-205">Select **Run** > **Step Into** or press <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="4b3c7-206">Visual Studio Code 突出显示 `date` 变量赋值。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-206">Visual Studio Code highlights the `date` variable assignment.</span></span> <span data-ttu-id="4b3c7-207">“变量”窗口显示 <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> 方法调用返回的值。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-207">The **Variables** window shows the value returned by the call to the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="4b3c7-208">“终端”选项卡显示在提示符处输入的字符串。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-208">The **Terminal** tab displays the string you entered at the prompt.</span></span>

1. <span data-ttu-id="4b3c7-209">选择“运行” > “单步执行”或按 <kbd>F11</kbd>。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-209">Select **Run** > **Step Into** or press <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="4b3c7-210">“变量”窗口显示通过 <xref:System.DateTime.Now?displayProperty=nameWithType> 属性赋值后的 `date` 变量值。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-210">The **Variables** window shows the value of the `date` variable after the assignment from the <xref:System.DateTime.Now?displayProperty=nameWithType> property.</span></span>

1. <span data-ttu-id="4b3c7-211">选择“运行” > “单步执行”或按 <kbd>F11</kbd>。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-211">Select **Run** > **Step Into** or press <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="4b3c7-212">Visual Studio Code 调用 <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-212">Visual Studio Code calls the <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="4b3c7-213">控制台窗口会显示格式化的字符串。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-213">The console window displays the formatted string.</span></span>

1. <span data-ttu-id="4b3c7-214">选择“运行” > “跳出”或按 <kbd>Shift</kbd>+<kbd>F11</kbd>。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-214">Select **Run** > **Step Out** or press <kbd>Shift</kbd>+<kbd>F11</kbd>.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/step-out.png" alt-text="“跳出”按钮":::

1. <span data-ttu-id="4b3c7-216">选择“终端”选项卡。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-216">Select the **Terminal** tab.</span></span>

   <span data-ttu-id="4b3c7-217">终端显示“按任意键退出…”</span><span class="sxs-lookup"><span data-stu-id="4b3c7-217">The terminal displays "Press any key to exit..."</span></span>

1. <span data-ttu-id="4b3c7-218">按任意键退出程序。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-218">Press any key to exit the program.</span></span>

## <a name="use-release-build-configuration"></a><span data-ttu-id="4b3c7-219">使用“发布”生成配置</span><span class="sxs-lookup"><span data-stu-id="4b3c7-219">Use Release build configuration</span></span>

<span data-ttu-id="4b3c7-220">测试应用程序的“调试”版本后，还应该编译并测试“发布”版本。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-220">Once you've tested the Debug version of your application, you should also compile and test the Release version.</span></span> <span data-ttu-id="4b3c7-221">发布版本包含编译器优化，这些优化可能会影响应用程序的行为。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-221">The Release version incorporates compiler optimizations that can affect the behavior of an application.</span></span> <span data-ttu-id="4b3c7-222">例如，旨在提升性能的编译器优化可能会在多线程应用程序中创建争用条件。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-222">For example, compiler optimizations that are designed to improve performance can create race conditions in multithreaded applications.</span></span>

<span data-ttu-id="4b3c7-223">若要构建和测试控制台应用程序的发布版本，请打开终端，并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="4b3c7-223">To build and test the Release version of your console application, open the **Terminal** and run the following command:</span></span>

```dotnetcli
dotnet run --configuration Release
```

## <a name="additional-resources"></a><span data-ttu-id="4b3c7-224">其他资源</span><span class="sxs-lookup"><span data-stu-id="4b3c7-224">Additional resources</span></span>

* [<span data-ttu-id="4b3c7-225">在 Visual Studio Code 中进行调试</span><span class="sxs-lookup"><span data-stu-id="4b3c7-225">Debugging in Visual Studio Code</span></span>](https://code.visualstudio.com/docs/editor/debugging)

## <a name="next-steps"></a><span data-ttu-id="4b3c7-226">后续步骤</span><span class="sxs-lookup"><span data-stu-id="4b3c7-226">Next steps</span></span>

<span data-ttu-id="4b3c7-227">在本教程中，使用了 Visual Studio Code 调试工具。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-227">In this tutorial, you used Visual Studio Code debugging tools.</span></span> <span data-ttu-id="4b3c7-228">在下一教程中，你将发布应用的可部署版本。</span><span class="sxs-lookup"><span data-stu-id="4b3c7-228">In the next tutorial, you publish a deployable version of the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4b3c7-229">使用 Visual Studio Code 发布 .NET 控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="4b3c7-229">Publish a .NET console application using Visual Studio Code</span></span>](publishing-with-visual-studio-code.md)
