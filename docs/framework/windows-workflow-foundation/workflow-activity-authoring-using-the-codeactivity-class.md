---
title: 使用 CodeActivity 类的工作流活动创作
ms.date: 03/30/2017
ms.assetid: cfe315c1-f86d-43ec-b9ce-2f8c469b1106
ms.openlocfilehash: 714e0971a006db20d002b0f3a486533b1357fba7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293814"
---
# <a name="workflow-activity-authoring-using-the-codeactivity-class"></a><span data-ttu-id="247f5-102">使用 CodeActivity 类的工作流活动创作</span><span class="sxs-lookup"><span data-stu-id="247f5-102">Workflow Activity Authoring Using the CodeActivity Class</span></span>

<span data-ttu-id="247f5-103">从 <xref:System.Activities.CodeActivity> 继承而创建的活动可以通过重写 <xref:System.Activities.CodeActivity.Execute%2A> 方法来实现基本的命令性行为。</span><span class="sxs-lookup"><span data-stu-id="247f5-103">Activities created by inheriting from <xref:System.Activities.CodeActivity> can implement basic imperative behavior by overriding the <xref:System.Activities.CodeActivity.Execute%2A> method.</span></span>

## <a name="using-codeactivitycontext"></a><span data-ttu-id="247f5-104">使用 CodeActivityContext</span><span class="sxs-lookup"><span data-stu-id="247f5-104">Using CodeActivityContext</span></span>

 <span data-ttu-id="247f5-105">通过使用类型为 <xref:System.Activities.CodeActivity.Execute%2A> 的 `context` 参数的成员，可从 <xref:System.Activities.CodeActivityContext> 方法中访问工作流运行时的功能。</span><span class="sxs-lookup"><span data-stu-id="247f5-105">Features of the workflow runtime can be accessed from within the <xref:System.Activities.CodeActivity.Execute%2A> method by using members of the `context` parameter, of type <xref:System.Activities.CodeActivityContext>.</span></span> <span data-ttu-id="247f5-106">可通过 <xref:System.Activities.CodeActivityContext> 使用的功能如下：</span><span class="sxs-lookup"><span data-stu-id="247f5-106">The features available through <xref:System.Activities.CodeActivityContext> include the following:</span></span>

- <span data-ttu-id="247f5-107">获取并设置变量和自变量的值。</span><span class="sxs-lookup"><span data-stu-id="247f5-107">Getting and setting the values of variables and arguments.</span></span>

- <span data-ttu-id="247f5-108">使用 <xref:System.Activities.CodeActivityContext.Track%2A> 的自定义跟踪功能。</span><span class="sxs-lookup"><span data-stu-id="247f5-108">Custom tracking features using <xref:System.Activities.CodeActivityContext.Track%2A>.</span></span>

- <span data-ttu-id="247f5-109">使用 <xref:System.Activities.CodeActivityContext.GetProperty%2A> 访问活动的执行属性。</span><span class="sxs-lookup"><span data-stu-id="247f5-109">Access to the activity’s execution properties using <xref:System.Activities.CodeActivityContext.GetProperty%2A>.</span></span>

#### <a name="to-create-a-custom-activity-that-inherits-from-codeactivity"></a><span data-ttu-id="247f5-110">创建从 CodeActivity 继承的自定义活动</span><span class="sxs-lookup"><span data-stu-id="247f5-110">To create a custom activity that inherits from CodeActivity</span></span>

1. <span data-ttu-id="247f5-111">打开 Visual Studio 2010。</span><span class="sxs-lookup"><span data-stu-id="247f5-111">Open Visual Studio 2010.</span></span>

2. <span data-ttu-id="247f5-112">依次选择 " **文件**"、" **新建**" 和 " **项目**"。</span><span class="sxs-lookup"><span data-stu-id="247f5-112">Select **File**, **New**, and then **Project**.</span></span> <span data-ttu-id="247f5-113">在 "**项目类型**" 窗口中的 " **Visual c #** " 下选择 " **Workflow 4.0** "，然后选择 " **v2010** " 节点。</span><span class="sxs-lookup"><span data-stu-id="247f5-113">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="247f5-114">在 "**模板**" 窗口中选择 "**活动库**"。</span><span class="sxs-lookup"><span data-stu-id="247f5-114">Select **Activity Library** in the **Templates** window.</span></span> <span data-ttu-id="247f5-115">将新项目命名为 HelloActivity。</span><span class="sxs-lookup"><span data-stu-id="247f5-115">Name the new project HelloActivity.</span></span>

3. <span data-ttu-id="247f5-116">右键单击击 helloactivity 项目中的 Activity1，然后选择 " **删除**"。</span><span class="sxs-lookup"><span data-stu-id="247f5-116">Right-click Activity1.xaml in the HelloActivity project and select **Delete**.</span></span>

4. <span data-ttu-id="247f5-117">右键单击 "击 helloactivity" 项目，然后依次选择 " **添加** "、" **类**"。</span><span class="sxs-lookup"><span data-stu-id="247f5-117">Right-click the HelloActivity project and select **Add** , and then **Class**.</span></span> <span data-ttu-id="247f5-118">将新类命名为 HelloActivity.cs。</span><span class="sxs-lookup"><span data-stu-id="247f5-118">Name the new class HelloActivity.cs.</span></span>

5. <span data-ttu-id="247f5-119">在 HelloActivity.cs 文件中，添加以下 `using` 指令。</span><span class="sxs-lookup"><span data-stu-id="247f5-119">In the HelloActivity.cs file, add the following `using` directives.</span></span>

    ```csharp
    using System.Activities;
    using System.Activities.Statements;
    ```

6. <span data-ttu-id="247f5-120">通过向类声明中添加一个基类使新类从 <xref:System.Activities.CodeActivity> 继承。</span><span class="sxs-lookup"><span data-stu-id="247f5-120">Make the new class inherit from <xref:System.Activities.CodeActivity> by adding a base class to the class declaration.</span></span>

    ```csharp
    class HelloActivity : CodeActivity
    ```

7. <span data-ttu-id="247f5-121">通过添加 <xref:System.Activities.CodeActivity.Execute%2A> 方法来向类中添加功能。</span><span class="sxs-lookup"><span data-stu-id="247f5-121">Add functionality to the class by adding an <xref:System.Activities.CodeActivity.Execute%2A> method.</span></span>

    ```csharp
    protected override void Execute(CodeActivityContext context)
    {
        Console.WriteLine("Hello World!");
    }
    ```

8. <span data-ttu-id="247f5-122">使用 <xref:System.Activities.CodeActivityContext> 创建一个跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="247f5-122">Use the <xref:System.Activities.CodeActivityContext> to create a tracking record.</span></span>

    ```csharp
    protected override void Execute(CodeActivityContext context)
    {
        Console.WriteLine("Hello World!");
        CustomTrackingRecord record = new CustomTrackingRecord("MyRecord");
        record.Data.Add(new KeyValuePair<String, Object>("ExecutionTime", DateTime.Now));
        context.Track(record);
    }
    ```
