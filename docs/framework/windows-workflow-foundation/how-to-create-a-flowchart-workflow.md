---
title: 如何：创建 Flowchart 工作流
description: 本文介绍如何创建一个工作流，该工作流使用内置活动和前一篇文章中的自定义活动。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 185d7aea-68a6-4bd8-adde-45050f33170a
ms.openlocfilehash: f8e0703591629a72e0a8f6eeb05dd9d19c8c4c91
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275822"
---
# <a name="how-to-create-a-flowchart-workflow"></a><span data-ttu-id="6286a-103">如何：创建 Flowchart 工作流</span><span class="sxs-lookup"><span data-stu-id="6286a-103">How to: Create a Flowchart Workflow</span></span>

<span data-ttu-id="6286a-104">工作流可基于内置活动以及自定义活动来构造。</span><span class="sxs-lookup"><span data-stu-id="6286a-104">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="6286a-105">本主题介绍如何创建一个工作流，该工作流使用内置活动（如 <xref:System.Activities.Statements.Flowchart> 活动）和前面的 [如何：创建活动](how-to-create-an-activity.md) 主题中的自定义活动。</span><span class="sxs-lookup"><span data-stu-id="6286a-105">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Flowchart> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="6286a-106">该工作流模拟猜数游戏。</span><span class="sxs-lookup"><span data-stu-id="6286a-106">The workflow models a number guessing game.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6286a-107">入门教程中的每个主题都依赖于前面的主题。</span><span class="sxs-lookup"><span data-stu-id="6286a-107">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="6286a-108">若要完成本主题，必须先完成 [操作方法：创建活动](how-to-create-an-activity.md)。</span><span class="sxs-lookup"><span data-stu-id="6286a-108">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6286a-109">若要下载完整版教程，请参阅 [Windows Workflow Foundation (WF45) — 入门教程](https://go.microsoft.com/fwlink/?LinkID=248976)。</span><span class="sxs-lookup"><span data-stu-id="6286a-109">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-workflow"></a><span data-ttu-id="6286a-110">创建工作流</span><span class="sxs-lookup"><span data-stu-id="6286a-110">To create the workflow</span></span>  
  
1. <span data-ttu-id="6286a-111">在 **解决方案资源管理器** 中右键单击 " **NumberGuessWorkflowActivities** "，然后选择 "**添加**"、"**新建项**"。</span><span class="sxs-lookup"><span data-stu-id="6286a-111">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>  
  
2. <span data-ttu-id="6286a-112">在 " **已安装** 的 **公共项** " 节点中，选择 " **工作流**"。</span><span class="sxs-lookup"><span data-stu-id="6286a-112">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="6286a-113">从 **“工作流”** 列表中选择 **“活动”**。</span><span class="sxs-lookup"><span data-stu-id="6286a-113">Select **Activity** from the **Workflow** list.</span></span>  
  
3. <span data-ttu-id="6286a-114">`FlowchartNumberGuessWorkflow`在 "**名称**" 框中键入，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="6286a-114">Type `FlowchartNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>  
  
4. <span data-ttu-id="6286a-115">将 "**流程图**" 活动从 "**工具箱**" 的 "**流程图**" 部分拖放到工作流设计图面上的 "在 **此处放置活动**" 标签上。</span><span class="sxs-lookup"><span data-stu-id="6286a-115">Drag a **Flowchart** activity from the **Flowchart** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="6286a-116">创建工作流变量和自变量</span><span class="sxs-lookup"><span data-stu-id="6286a-116">To create the workflow variables and arguments</span></span>  
  
1. <span data-ttu-id="6286a-117">在 **解决方案资源管理器** 中双击 " **flowchartnumberguessworkflow.xaml** " 以在设计器中显示工作流（如果尚未显示）。</span><span class="sxs-lookup"><span data-stu-id="6286a-117">Double-click **FlowchartNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>  
  
2. <span data-ttu-id="6286a-118">单击工作流设计器左下方的 " **参数** " 以显示 " **参数** " 窗格。</span><span class="sxs-lookup"><span data-stu-id="6286a-118">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
3. <span data-ttu-id="6286a-119">单击 **“创建参数”**。</span><span class="sxs-lookup"><span data-stu-id="6286a-119">Click **Create Argument**.</span></span>  
  
4. <span data-ttu-id="6286a-120">在 `MaxNumber` "**名称**" 框中键入，从 "**方向**" 下拉列表 **中** 选择 "输入"，从 "**参数类型**" 下拉列表中选择 " **Int32** "，然后按 enter 保存该参数。</span><span class="sxs-lookup"><span data-stu-id="6286a-120">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
5. <span data-ttu-id="6286a-121">单击 **“创建参数”**。</span><span class="sxs-lookup"><span data-stu-id="6286a-121">Click **Create Argument**.</span></span>  
  
6. <span data-ttu-id="6286a-122">在 `Turns` 新添加的参数下方的 "**名称**" 框中键入 `MaxNumber` ，从 "**方向**" 下拉列表中选择 "向 **外**"，从 "**参数类型**" 下拉列表中选择 " **Int32** "，然后按 enter。</span><span class="sxs-lookup"><span data-stu-id="6286a-122">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
7. <span data-ttu-id="6286a-123">单击活动设计器左下角的 **“参数”**，关闭 **“参数”** 窗格。</span><span class="sxs-lookup"><span data-stu-id="6286a-123">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
8. <span data-ttu-id="6286a-124">单击工作流设计器左下方的 " **变量** "，以显示 " **变量** " 窗格。</span><span class="sxs-lookup"><span data-stu-id="6286a-124">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>  
  
9. <span data-ttu-id="6286a-125">单击 **“创建变量”**。</span><span class="sxs-lookup"><span data-stu-id="6286a-125">Click **Create Variable**.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="6286a-126">如果未显示 " **创建变量** " 框，请单击 <xref:System.Activities.Statements.Flowchart> 工作流设计器图面上的活动以选择它。</span><span class="sxs-lookup"><span data-stu-id="6286a-126">If no **Create Variable** box is displayed, click the <xref:System.Activities.Statements.Flowchart> activity on the workflow designer surface to select it.</span></span>  
  
10. <span data-ttu-id="6286a-127">在 `Guess` "**名称**" 框中键入，从 "**变量类型**" 下拉列表中选择 " **Int32** "，然后按 enter 保存变量。</span><span class="sxs-lookup"><span data-stu-id="6286a-127">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
11. <span data-ttu-id="6286a-128">单击 **“创建变量”**。</span><span class="sxs-lookup"><span data-stu-id="6286a-128">Click **Create Variable**.</span></span>  
  
12. <span data-ttu-id="6286a-129">在 `Target` "**名称**" 框中键入，从 "**变量类型**" 下拉列表中选择 " **Int32** "，然后按 enter 保存变量。</span><span class="sxs-lookup"><span data-stu-id="6286a-129">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
13. <span data-ttu-id="6286a-130">单击活动设计器左下角的 **“变量”**，关闭 **“变量”** 窗格。</span><span class="sxs-lookup"><span data-stu-id="6286a-130">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>  
  
### <a name="to-add-the-workflow-activities"></a><span data-ttu-id="6286a-131">添加工作流活动</span><span class="sxs-lookup"><span data-stu-id="6286a-131">To add the workflow activities</span></span>  
  
1. <span data-ttu-id="6286a-132">将 " **Assign** " 活动从 "**工具箱**" 的 "**基元**" 部分拖放到 "**开始**" 节点上，该节点位于流程图的顶部。</span><span class="sxs-lookup"><span data-stu-id="6286a-132">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and hover it over the **Start** node, which is at the top of the flowchart.</span></span> <span data-ttu-id="6286a-133">当 **Assign** 活动位于 **开始** 节点上时， **开始** 节点附近会出现三个三角形。</span><span class="sxs-lookup"><span data-stu-id="6286a-133">When the **Assign** activity is over the **Start** node, three triangles will appear around the **Start** node.</span></span> <span data-ttu-id="6286a-134">删除位于 **开始** 节点正下方的三角形上的 "**分配**" 活动。</span><span class="sxs-lookup"><span data-stu-id="6286a-134">Drop the **Assign** activity on the triangle that is directly below the **Start** node.</span></span> <span data-ttu-id="6286a-135">这会将这两个项链接在一起，并将 **分配** 活动指定为流程图中的第一个活动。</span><span class="sxs-lookup"><span data-stu-id="6286a-135">This will link the two items together and designates the **Assign** activity as the first activity in the flowchart.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="6286a-136">也还可以通过手动将活动链接到开始节点而将活动指示为流程图中的起始活动。</span><span class="sxs-lookup"><span data-stu-id="6286a-136">Activities can also be indicated as the starting activity in the workflow by manually linking them activity to the start node.</span></span> <span data-ttu-id="6286a-137">为此，请将鼠标悬停在 " **开始** " 节点上，单击在鼠标位于 " **开始** " 节点上时出现的矩形之一，然后将连接线向下拖至所需的活动，并将其放置在出现的某个矩形上。</span><span class="sxs-lookup"><span data-stu-id="6286a-137">To do this, hover the mouse over the **Start** node, click one of the rectangles that appear when the mouse is over the **Start** node, and drag the connecting line down to the desired activity and drop it on one of the rectangles that appear.</span></span> <span data-ttu-id="6286a-138">还可以通过右键单击某一活动，并选择 " **设为开始节点**"，将该活动指定为启动活动。</span><span class="sxs-lookup"><span data-stu-id="6286a-138">You can also designate an activity as the starting activity by right-clicking the it and choosing **Set as Start Node**.</span></span>  
  
2. <span data-ttu-id="6286a-139">在 " `Target` **到** " 框中键入，然后在 " **输入 c # 表达式** " 或 " **输入 VB 表达式** " 框中键入以下表达式。</span><span class="sxs-lookup"><span data-stu-id="6286a-139">Type `Target` into the **To** box and the following expression into the **Enter a C# Expression** or **Enter a VB expression** box.</span></span>  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    > <span data-ttu-id="6286a-140">如果未显示 **“工具箱”** 窗口，请从 **“视图”** 菜单中选择 **“工具箱”**。</span><span class="sxs-lookup"><span data-stu-id="6286a-140">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
3. <span data-ttu-id="6286a-141">从 "**工具箱**" 的 " **NumberGuessWorkflowActivities** " 部分拖动 " **prompt** " 活动，将其拖放到上一步骤中的 " **Assign** " 活动下面，并将 " **prompt** " 活动连接到 " **assign** " 活动。</span><span class="sxs-lookup"><span data-stu-id="6286a-141">Drag a **Prompt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox**, drop it below the **Assign** activity from the previous step, and connect the **Prompt** activity to the **Assign** activity.</span></span> <span data-ttu-id="6286a-142">可通过三种方法来连接这两个活动。</span><span class="sxs-lookup"><span data-stu-id="6286a-142">There are three ways to connect the two activities.</span></span> <span data-ttu-id="6286a-143">第一种方法是在将 **Prompt** 活动放置在工作流上时连接它们。</span><span class="sxs-lookup"><span data-stu-id="6286a-143">The first way is to connect them as you drop the **Prompt** activity on the workflow.</span></span> <span data-ttu-id="6286a-144">将 " **提示** " 活动拖到工作流中时，将其悬停在 " **assign** " 活动上，并将其放置到 " **提示** " 活动超过 " **assign** " 活动时显示的四个三角形之一。</span><span class="sxs-lookup"><span data-stu-id="6286a-144">As you are dragging the **Prompt** activity to the workflow, hover it over the **Assign** activity and drop it onto one of the four triangles that appear when the **Prompt** activity is over the **Assign** activity.</span></span> <span data-ttu-id="6286a-145">第二种方法是将 **提示** 活动放到工作流上所需的位置。</span><span class="sxs-lookup"><span data-stu-id="6286a-145">The second way is to drop the **Prompt** activity onto the workflow at the desired location.</span></span> <span data-ttu-id="6286a-146">然后，将鼠标悬停在 " **Assign** " 活动上，然后将出现的一个矩形拖到 " **Prompt** " 活动。</span><span class="sxs-lookup"><span data-stu-id="6286a-146">Then, hover the mouse over the **Assign** activity and drag one of the rectangles that appears down to the **Prompt** activity.</span></span> <span data-ttu-id="6286a-147">拖动鼠标，使 " **Assign** " 活动中的连接线连接到 **Prompt** 活动的一个矩形，然后松开鼠标按钮。</span><span class="sxs-lookup"><span data-stu-id="6286a-147">Drag the mouse so that the connecting line from the **Assign** activity connects to one of the rectangles of the **Prompt** activity, and then release the mouse button.</span></span> <span data-ttu-id="6286a-148">第三种方法与第一种方法非常相似，不同之处在于，它不是从 "**工具箱**" 拖动 " **Prompt** " 活动，而是将其从 "工作流" 设计图面上的位置拖动，将其悬停在 " **Assign** " 活动上，然后将其放到显示的某个三角形上。</span><span class="sxs-lookup"><span data-stu-id="6286a-148">The third way is very similar to the first way, except that instead of dragging the **Prompt** activity from the **Toolbox**, you drag it from its location on the workflow design surface, hover it over the **Assign** activity, and drop it onto one of the triangles that appears.</span></span>  
  
4. <span data-ttu-id="6286a-149">在 **Prompt** 活动的 "**属性" 窗口** 中，在 `"EnterGuess"` " **BookmarkName** " 属性值框中键入包括引号。</span><span class="sxs-lookup"><span data-stu-id="6286a-149">In the **Properties Window** for the **Prompt** activity, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box.</span></span> <span data-ttu-id="6286a-150">`Guess`在 "**结果** 属性值" 框中键入，然后在 "**文本**" 属性框中键入以下表达式。</span><span class="sxs-lookup"><span data-stu-id="6286a-150">Type `Guess` into the **Result** property value box, and type the following expression into the **Text** property box.</span></span>  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    > <span data-ttu-id="6286a-151">如果未显示 "**属性" 窗口**，请从 "**视图**" 菜单中选择 "**属性窗口**"。</span><span class="sxs-lookup"><span data-stu-id="6286a-151">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
5. <span data-ttu-id="6286a-152">从 **工具箱** 的 "**基元**" 部分拖动 " **Assign** " 活动，并使用上一步骤中所述的方法之一来连接该活动，使其位于 **Prompt** 活动下面。</span><span class="sxs-lookup"><span data-stu-id="6286a-152">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and connect it using one of the methods described in the previous step so that it is below the **Prompt** activity.</span></span>  
  
6. <span data-ttu-id="6286a-153">在 `Turns` " **到** " 框中键入，然后 `Turns + 1` 在 " **输入 c # 表达式**  " 或 " **输入 VB 表达式** " 框中键入。</span><span class="sxs-lookup"><span data-stu-id="6286a-153">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression**  or **Enter a VB expression** box.</span></span>  
  
7. <span data-ttu-id="6286a-154">拖动 "**工具箱**" 的 "**流程图**" 部分中的 **FlowDecision** ，并将其连接到 " **Assign** " 活动下。</span><span class="sxs-lookup"><span data-stu-id="6286a-154">Drag a **FlowDecision** from the **Flowchart** section of the **Toolbox** and connect it below the **Assign** activity.</span></span> <span data-ttu-id="6286a-155">在 " **属性" 窗口** 中，在 " **Condition** " 属性值框中键入以下表达式。</span><span class="sxs-lookup"><span data-stu-id="6286a-155">In the **Properties Window**, type the following expression into the **Condition** property value box.</span></span>  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
8. <span data-ttu-id="6286a-156">将另一个 " **FlowDecision** " 活动从 " **工具箱** " 拖放到第一个活动下。</span><span class="sxs-lookup"><span data-stu-id="6286a-156">Drag another **FlowDecision** activity from the **Toolbox** and drop it below the first one.</span></span> <span data-ttu-id="6286a-157">通过将顶部 **FlowDecision** 活动中标记 **为 "False** " 的矩形拖到第二个 **FlowDecision** 活动顶部的矩形来连接这两个活动。</span><span class="sxs-lookup"><span data-stu-id="6286a-157">Connect the two activities by dragging from the rectangle that is labeled **False** on the top **FlowDecision** activity to the rectangle at the top of the second **FlowDecision** activity.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="6286a-158">如果在 **FlowDecision** 上看不到 " **True** " 和 " **False** " 标签，则将鼠标悬停在 **FlowDecision** 上。</span><span class="sxs-lookup"><span data-stu-id="6286a-158">If you do not see the **True** and **False** labels on the **FlowDecision**, hover the mouse over the **FlowDecision**.</span></span>  
  
9. <span data-ttu-id="6286a-159">单击第二个 " **FlowDecision** " 活动将其选中。</span><span class="sxs-lookup"><span data-stu-id="6286a-159">Click the second **FlowDecision** activity to select it.</span></span> <span data-ttu-id="6286a-160">在 " **属性" 窗口** 中，在 " **Condition** " 属性值框中键入以下表达式。</span><span class="sxs-lookup"><span data-stu-id="6286a-160">In the **Properties Window**, type the following expression into the **Condition** property value box.</span></span>  
  
    ```text
    Guess < Target
    ```  
  
10. <span data-ttu-id="6286a-161">将两个 " **WriteLine** " 活动从 "**工具箱**" 的 "**基元**" 部分拖放到两个 **FlowDecision** 活动下。</span><span class="sxs-lookup"><span data-stu-id="6286a-161">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that they are side by side below the two **FlowDecision** activities.</span></span> <span data-ttu-id="6286a-162">将底部 **FlowDecision** 活动的 **真正** 操作连接到最左端的 **Writeline** 活动，并将 **False** 操作连接到最右侧的 **writeline** 活动。</span><span class="sxs-lookup"><span data-stu-id="6286a-162">Connect the **True** action of the bottom **FlowDecision** activity to the leftmost **WriteLine** activity, and the **False** action to the rightmost **WriteLine** activity.</span></span>  
  
11. <span data-ttu-id="6286a-163">单击最左边的 " **WriteLine** " 活动将其选中，然后在 "**属性" 窗口** 的 " **Text** " 属性值框中键入以下表达式。</span><span class="sxs-lookup"><span data-stu-id="6286a-163">Click the leftmost **WriteLine** activity to select it, and type the following expression into the **Text** property value box in the **Properties Window**.</span></span>  
  
    ```text
    "Your guess is too low."  
    ```  
  
12. <span data-ttu-id="6286a-164">将 **WriteLine** 连接到它上面的 **Prompt** 活动的左侧。</span><span class="sxs-lookup"><span data-stu-id="6286a-164">Connect the **WriteLine** to the left side of the **Prompt** activity that is above it.</span></span>  
  
13. <span data-ttu-id="6286a-165">单击最右边的 " **WriteLine** " 活动将其选中，然后在 "**属性" 窗口** 的 " **Text** " 属性值框中键入以下表达式。</span><span class="sxs-lookup"><span data-stu-id="6286a-165">Click the rightmost **WriteLine** activity to select it, and type the following expression into the **Text** property value box in the **Properties Window**.</span></span>  
  
    ```text
    "Your guess is too high."  
    ```  
  
14. <span data-ttu-id="6286a-166">将 **WriteLine** 活动连接到其上面的 **Prompt** 活动的右侧。</span><span class="sxs-lookup"><span data-stu-id="6286a-166">Connect the **WriteLine** activity to the right side of the **Prompt** activity above it.</span></span>  
  
     <span data-ttu-id="6286a-167">下面的示例阐释已完成的工作流。</span><span class="sxs-lookup"><span data-stu-id="6286a-167">The following example illustrates the completed workflow.</span></span>  
  
     ![显示已完成的 Windows Workflow Foundation 流程图的关系图。](./media/how-to-create-a-flowchart-workflow/completed-windows-workflow-flowchart.png)  
  
### <a name="to-build-the-workflow"></a><span data-ttu-id="6286a-169">生成工作流</span><span class="sxs-lookup"><span data-stu-id="6286a-169">To build the workflow</span></span>  
  
1. <span data-ttu-id="6286a-170">按 CTRL+SHIFT+B 生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="6286a-170">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="6286a-171">有关如何运行工作流的说明，请参阅下一主题 [如何：运行工作流](how-to-run-a-workflow.md)。</span><span class="sxs-lookup"><span data-stu-id="6286a-171">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span> <span data-ttu-id="6286a-172">如果你已经完成了如何：使用不同的工作流样式[运行工作流](how-to-run-a-workflow.md)步骤，并希望使用此步骤中的流程图工作流运行它，请跳到[如何：运行工作流](how-to-run-a-workflow.md)中的 "[生成并运行应用程序](how-to-run-a-workflow.md#BKMK_ToRunTheApplication)" 部分。</span><span class="sxs-lookup"><span data-stu-id="6286a-172">If you have already completed the [How to: Run a Workflow](how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the flowchart workflow from this step, skip ahead to the [To build and run the application](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6286a-173">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6286a-173">See also</span></span>

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [<span data-ttu-id="6286a-174">Windows Workflow Foundation 编程</span><span class="sxs-lookup"><span data-stu-id="6286a-174">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="6286a-175">设计工作流</span><span class="sxs-lookup"><span data-stu-id="6286a-175">Designing Workflows</span></span>](designing-workflows.md)
- [<span data-ttu-id="6286a-176">入门教程</span><span class="sxs-lookup"><span data-stu-id="6286a-176">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="6286a-177">如何：创建活动</span><span class="sxs-lookup"><span data-stu-id="6286a-177">How to: Create an Activity</span></span>](how-to-create-an-activity.md)
- [<span data-ttu-id="6286a-178">如何：运行工作流</span><span class="sxs-lookup"><span data-stu-id="6286a-178">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)
