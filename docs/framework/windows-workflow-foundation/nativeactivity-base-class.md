---
title: NativeActivity 基类
ms.date: 03/30/2017
ms.assetid: 254a4c50-425b-426d-a32f-0f7234925bac
ms.openlocfilehash: d875f62dacadb2baf6b5d7e93ddb2933aed9cdb0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274954"
---
# <a name="nativeactivity-base-class"></a><span data-ttu-id="d100f-102">NativeActivity 基类</span><span class="sxs-lookup"><span data-stu-id="d100f-102">NativeActivity Base Class</span></span>

<span data-ttu-id="d100f-103"><xref:System.Activities.NativeActivity> 是一个带有受保护的构造函数的抽象类。</span><span class="sxs-lookup"><span data-stu-id="d100f-103"><xref:System.Activities.NativeActivity> is an abstract class with a protected constructor.</span></span> <span data-ttu-id="d100f-104">与 <xref:System.Activities.CodeActivity> 一样，<xref:System.Activities.NativeActivity> 用于通过实现 <xref:System.Activities.NativeActivity.Execute%2A> 方法来编写命令性行为。</span><span class="sxs-lookup"><span data-stu-id="d100f-104">Like <xref:System.Activities.CodeActivity>, <xref:System.Activities.NativeActivity> is used for writing imperative behavior by implementing an <xref:System.Activities.NativeActivity.Execute%2A> method.</span></span> <span data-ttu-id="d100f-105">与 <xref:System.Activities.CodeActivity> 不同的是，通过传递给 <xref:System.Activities.NativeActivity> 方法的 <xref:System.Activities.NativeActivityContext> 对象，<xref:System.Activities.NativeActivity.Execute%2A> 有权访问工作流运行时的所有公开的功能。</span><span class="sxs-lookup"><span data-stu-id="d100f-105">Unlike <xref:System.Activities.CodeActivity>, <xref:System.Activities.NativeActivity> has access to all of the exposed features of the workflow runtime through the <xref:System.Activities.NativeActivityContext> object passed to the <xref:System.Activities.NativeActivity.Execute%2A> method.</span></span>

## <a name="using-nativeactivitycontext"></a><span data-ttu-id="d100f-106">使用 NativeActivityContext</span><span class="sxs-lookup"><span data-stu-id="d100f-106">Using NativeActivityContext</span></span>

 <span data-ttu-id="d100f-107">通过使用类型为 <xref:System.Activities.NativeActivity.Execute%2A> 的 `context` 参数的成员，可从 <xref:System.Activities.NativeActivityContext> 方法中访问工作流运行时的功能。</span><span class="sxs-lookup"><span data-stu-id="d100f-107">Features of the workflow runtime can be accessed from within the <xref:System.Activities.NativeActivity.Execute%2A> method by using members of the `context` parameter, of type <xref:System.Activities.NativeActivityContext>.</span></span> <span data-ttu-id="d100f-108">可通过 <xref:System.Activities.NativeActivityContext> 使用的功能如下：</span><span class="sxs-lookup"><span data-stu-id="d100f-108">The features available through <xref:System.Activities.NativeActivityContext> include the following:</span></span>

- <span data-ttu-id="d100f-109">获取并设置自变量和变量。</span><span class="sxs-lookup"><span data-stu-id="d100f-109">Getting and setting of arguments and variables.</span></span>

- <span data-ttu-id="d100f-110">使用 <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A> 安排子活动。</span><span class="sxs-lookup"><span data-stu-id="d100f-110">Scheduling child activities with <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A></span></span>

- <span data-ttu-id="d100f-111">使用 <xref:System.Activities.NativeActivityContext.Abort%2A> 中止活动执行。</span><span class="sxs-lookup"><span data-stu-id="d100f-111">Aborting activity execution using <xref:System.Activities.NativeActivityContext.Abort%2A>.</span></span>

- <span data-ttu-id="d100f-112">使用 <xref:System.Activities.NativeActivityContext.CancelChild%2A> 和 <xref:System.Activities.NativeActivityContext.CancelChildren%2A> 取消子级执行。</span><span class="sxs-lookup"><span data-stu-id="d100f-112">Canceling child execution using <xref:System.Activities.NativeActivityContext.CancelChild%2A> and <xref:System.Activities.NativeActivityContext.CancelChildren%2A>.</span></span>

- <span data-ttu-id="d100f-113">使用 <xref:System.Activities.NativeActivityContext.CreateBookmark%2A>、<xref:System.Activities.NativeActivityContext.RemoveBookmark%2A> 和 <xref:System.Activities.NativeActivityContext.ResumeBookmark%2A> 等方法访问活动书签。</span><span class="sxs-lookup"><span data-stu-id="d100f-113">Access to activity bookmarks using such methods as <xref:System.Activities.NativeActivityContext.CreateBookmark%2A>, <xref:System.Activities.NativeActivityContext.RemoveBookmark%2A>, and <xref:System.Activities.NativeActivityContext.ResumeBookmark%2A>.</span></span>

- <span data-ttu-id="d100f-114">使用 <xref:System.Activities.CodeActivityContext.Track%2A> 的自定义跟踪功能。</span><span class="sxs-lookup"><span data-stu-id="d100f-114">Custom tracking features using <xref:System.Activities.CodeActivityContext.Track%2A>.</span></span>

- <span data-ttu-id="d100f-115">使用 <xref:System.Activities.CodeActivityContext.GetProperty%2A> 和 <xref:System.Activities.NativeActivityContext.GetValue%2A> 访问活动的执行属性和值属性。</span><span class="sxs-lookup"><span data-stu-id="d100f-115">Access to the activity’s execution properties and value properties using <xref:System.Activities.CodeActivityContext.GetProperty%2A> and <xref:System.Activities.NativeActivityContext.GetValue%2A>.</span></span>

- <span data-ttu-id="d100f-116">使用 <xref:System.Activities.NativeActivityContext.ScheduleAction%2A> 和 <xref:System.Activities.NativeActivityContext.ScheduleFunc%2A> 安排活动操作和功能。</span><span class="sxs-lookup"><span data-stu-id="d100f-116">Scheduling activity actions and functions using <xref:System.Activities.NativeActivityContext.ScheduleAction%2A> and <xref:System.Activities.NativeActivityContext.ScheduleFunc%2A>.</span></span>

### <a name="to-create-a-custom-activity-that-inherits-from-nativeactivity"></a><span data-ttu-id="d100f-117">创建从 NativeActivity 继承的自定义活动</span><span class="sxs-lookup"><span data-stu-id="d100f-117">To create a custom activity that inherits from NativeActivity</span></span>

1. <span data-ttu-id="d100f-118">OpenVisual Studio 2010。</span><span class="sxs-lookup"><span data-stu-id="d100f-118">OpenVisual Studio 2010.</span></span>

2. <span data-ttu-id="d100f-119">依次选择 " **文件**"、" **新建**" 和 " **项目**"。</span><span class="sxs-lookup"><span data-stu-id="d100f-119">Select **File**, **New**, and then **Project**.</span></span> <span data-ttu-id="d100f-120">在 "**项目类型**" 窗口中的 " **Visual c #** " 下选择 " **Workflow 4.0** "，然后选择 " **v2010** " 节点。</span><span class="sxs-lookup"><span data-stu-id="d100f-120">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="d100f-121">在 "**模板**" 窗口中选择 "**活动库**"。</span><span class="sxs-lookup"><span data-stu-id="d100f-121">Select **Activity Library** in the **Templates** window.</span></span> <span data-ttu-id="d100f-122">将新项目命名为 HelloActivity。</span><span class="sxs-lookup"><span data-stu-id="d100f-122">Name the new project HelloActivity.</span></span>

3. <span data-ttu-id="d100f-123">右键单击击 helloactivity 项目中的 Activity1，然后选择 " **删除**"。</span><span class="sxs-lookup"><span data-stu-id="d100f-123">Right-click Activity1.xaml in the HelloActivity project and select **Delete**.</span></span>

4. <span data-ttu-id="d100f-124">右键单击 "击 helloactivity" 项目，然后依次选择 " **添加**"、" **类**"。</span><span class="sxs-lookup"><span data-stu-id="d100f-124">Right-click the HelloActivity project and select **Add**, and then **Class**.</span></span> <span data-ttu-id="d100f-125">将新类命名为 HelloActivity.cs。</span><span class="sxs-lookup"><span data-stu-id="d100f-125">Name the new class HelloActivity.cs.</span></span>

5. <span data-ttu-id="d100f-126">在 HelloActivity.cs 文件中，添加以下 `using` 指令。</span><span class="sxs-lookup"><span data-stu-id="d100f-126">In the HelloActivity.cs file, add the following `using` directives.</span></span>

    ```csharp
    using System.Activities;
    using System.Activities.Statements;
    ```

6. <span data-ttu-id="d100f-127">通过向类声明中添加一个基类使新类从 <xref:System.Activities.NativeActivity> 继承。</span><span class="sxs-lookup"><span data-stu-id="d100f-127">Make the new class inherit from <xref:System.Activities.NativeActivity> by adding a base class to the class declaration.</span></span>

    ```csharp
    class HelloActivity : NativeActivity
    ```

7. <span data-ttu-id="d100f-128">通过添加 <xref:System.Activities.NativeActivity.Execute%2A> 方法来向类中添加功能。</span><span class="sxs-lookup"><span data-stu-id="d100f-128">Add functionality to the class by adding an <xref:System.Activities.NativeActivity.Execute%2A> method.</span></span>

    ```csharp
    protected override void Execute(NativeActivityContext context)
    {
        Console.WriteLine("Hello World!");
    }
    ```

8. <span data-ttu-id="d100f-129">重写 <xref:System.Activities.NativeActivity.CacheMetadata%2A> 方法并且调用相应的 Add 方法，以便让工作流运行时了解自定义活动的变量、自变量、子级和委托。</span><span class="sxs-lookup"><span data-stu-id="d100f-129">Override the <xref:System.Activities.NativeActivity.CacheMetadata%2A> method and call the appropriate Add method to let the workflow runtime know about the custom activity’s variables, arguments, children, and delegates.</span></span> <span data-ttu-id="d100f-130">有关更多信息，请参见 <xref:System.Activities.NativeActivityMetadata> 类。</span><span class="sxs-lookup"><span data-stu-id="d100f-130">For more information see the <xref:System.Activities.NativeActivityMetadata> class.</span></span>

9. <span data-ttu-id="d100f-131">使用 <xref:System.Activities.NativeActivityContext> 对象来计划书签。</span><span class="sxs-lookup"><span data-stu-id="d100f-131">Use the <xref:System.Activities.NativeActivityContext> object to schedule a bookmark.</span></span> <span data-ttu-id="d100f-132">有关如何创建、计划和恢复书签的详细信息，请参见 <xref:System.Activities.WorkflowApplicationIdleEventArgs.Bookmarks%2A>。</span><span class="sxs-lookup"><span data-stu-id="d100f-132">See <xref:System.Activities.WorkflowApplicationIdleEventArgs.Bookmarks%2A> for details on how to create, schedule, and resume a bookmark.</span></span>

    ```csharp
    protected override void Execute(NativeActivityContext context)
        {
            // Create a Bookmark and wait for it to be resumed.
            context.CreateBookmark(BookmarkName.Get(context),
                new BookmarkCallback(OnResumeBookmark));
        }
    ```
