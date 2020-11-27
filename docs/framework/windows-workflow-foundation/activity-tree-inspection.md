---
title: 活动树检查
ms.date: 03/30/2017
ms.assetid: 100d00e4-8c1d-4233-8fbb-dd443a01155d
ms.openlocfilehash: 044dcbbe7f22b1026dbc4dc14ab87da4f5a9d0ee
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289147"
---
# <a name="activity-tree-inspection"></a><span data-ttu-id="e52b2-102">活动树检查</span><span class="sxs-lookup"><span data-stu-id="e52b2-102">Activity Tree Inspection</span></span>

<span data-ttu-id="e52b2-103">活动树检查由工作流应用程序作者用于检查由应用程序承载的工作流。</span><span class="sxs-lookup"><span data-stu-id="e52b2-103">Activity tree inspection is used by workflow application authors to inspect the workflows hosted by the application.</span></span> <span data-ttu-id="e52b2-104">使用 <xref:System.Activities.WorkflowInspectionServices>，可以在工作流中搜索特定子活动、单个活动并可以枚举其属性，还可以在特定时间缓存活动的运行时元数据。</span><span class="sxs-lookup"><span data-stu-id="e52b2-104">By using <xref:System.Activities.WorkflowInspectionServices>, workflows can be searched for specific child activities, individual activities and their properties can be enumerated, and runtime metadata of the activities can be cached at a specific time.</span></span> <span data-ttu-id="e52b2-105">此主题概述 <xref:System.Activities.WorkflowInspectionServices> 以及如何将其用于检查活动树。</span><span class="sxs-lookup"><span data-stu-id="e52b2-105">This topic provides an overview of <xref:System.Activities.WorkflowInspectionServices> and how to use it to inspect an activity tree.</span></span>  
  
## <a name="using-workflowinspectionservices"></a><span data-ttu-id="e52b2-106">使用 WorkflowInspectionServices</span><span class="sxs-lookup"><span data-stu-id="e52b2-106">Using WorkflowInspectionServices</span></span>  

 <span data-ttu-id="e52b2-107"><xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> 方法用于枚举指定活动树中的所有活动。</span><span class="sxs-lookup"><span data-stu-id="e52b2-107">The <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> method is used to enumerate all of the activities in the specified activity tree.</span></span> <span data-ttu-id="e52b2-108"><xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> 返回一个可枚举对象，该对象涉及树中包括子活动在内的所有活动、委托处理程序、变量默认值和参数表达式。</span><span class="sxs-lookup"><span data-stu-id="e52b2-108"><xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> returns an enumerable that touches all activities within the tree including children, delegate handlers, variable defaults, and argument expressions.</span></span> <span data-ttu-id="e52b2-109">在下面的示例中，使用 <xref:System.Activities.Statements.Sequence>、<xref:System.Activities.Statements.While>、<xref:System.Activities.Statements.ForEach%601>、<xref:System.Activities.Statements.WriteLine> 和表达式创建一个工作流定义。</span><span class="sxs-lookup"><span data-stu-id="e52b2-109">In the following example, a workflow definition is created by using a <xref:System.Activities.Statements.Sequence>, <xref:System.Activities.Statements.While>, <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.WriteLine>, and expressions.</span></span> <span data-ttu-id="e52b2-110">在创建工作流定义后，将调用此定义，然后再调用 `InspectActivity` 方法。</span><span class="sxs-lookup"><span data-stu-id="e52b2-110">After the workflow definition is created, it is invoked and then the `InspectActivity` method is called.</span></span>  
  
 [!code-csharp[CFX_WorkflowApplicationExample#45](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#45)]  
  
 <span data-ttu-id="e52b2-111">为了枚举活动，在根活动上调用了 <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A>，并在返回的每个活动上重新递归调用。</span><span class="sxs-lookup"><span data-stu-id="e52b2-111">To enumerate the activities, the <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> is called on the root activity, and again recursively on each returned activity.</span></span> <span data-ttu-id="e52b2-112">在下面的示例中，将活动树中每个活动和表达式的 <xref:System.Activities.Activity.DisplayName%2A> 写入控制台。</span><span class="sxs-lookup"><span data-stu-id="e52b2-112">In the following example, the <xref:System.Activities.Activity.DisplayName%2A> of each activity and expression in the activity tree is written to the console.</span></span>  
  
 [!code-csharp[CFX_WorkflowApplicationExample#46](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#46)]  
  
 <span data-ttu-id="e52b2-113">此示例代码提供以下输出。</span><span class="sxs-lookup"><span data-stu-id="e52b2-113">This sample code provides the following output.</span></span>  
  
 <span data-ttu-id="e52b2-114">**List Item 1**</span><span class="sxs-lookup"><span data-stu-id="e52b2-114">**List Item 1**</span></span>  
<span data-ttu-id="e52b2-115">**列表项 2** 
**列表项 3** 
**列表项 4** 
**列表项 5** 
**添加到集合的项。** 
**序列\*\*\*\*文本<列表 \<String> >**</span><span class="sxs-lookup"><span data-stu-id="e52b2-115">**List Item 2**
**List Item 3**
**List Item 4**
**List Item 5**
**Items added to collection.**
**Sequence** **Literal<List\<String>>**</span></span>  
 <span data-ttu-id="e52b2-116">**While**</span><span class="sxs-lookup"><span data-stu-id="e52b2-116">**While**</span></span>  
 <span data-ttu-id="e52b2-117">**AddToCollection\<String>**</span><span class="sxs-lookup"><span data-stu-id="e52b2-117">**AddToCollection\<String>**</span></span>  
 <span data-ttu-id="e52b2-118">**VariableValue<ICollection\<String>>**</span><span class="sxs-lookup"><span data-stu-id="e52b2-118">**VariableValue<ICollection\<String>>**</span></span>  
 <span data-ttu-id="e52b2-119">**LambdaValue\<String>**</span><span class="sxs-lookup"><span data-stu-id="e52b2-119">**LambdaValue\<String>**</span></span>  
 <span data-ttu-id="e52b2-120">**LocationReferenceValue<列表\<String>>**</span><span class="sxs-lookup"><span data-stu-id="e52b2-120">**LocationReferenceValue<List\<String>>**</span></span>  
 <span data-ttu-id="e52b2-121">**LambdaValue\<Boolean>**</span><span class="sxs-lookup"><span data-stu-id="e52b2-121">**LambdaValue\<Boolean>**</span></span>  
 <span data-ttu-id="e52b2-122">**LocationReferenceValue<列表\<String>>**</span><span class="sxs-lookup"><span data-stu-id="e52b2-122">**LocationReferenceValue<List\<String>>**</span></span>  
 <span data-ttu-id="e52b2-123">**ForEach\<String>**</span><span class="sxs-lookup"><span data-stu-id="e52b2-123">**ForEach\<String>**</span></span>  
 <span data-ttu-id="e52b2-124">**VariableValue<IEnumerable\<String>>**</span><span class="sxs-lookup"><span data-stu-id="e52b2-124">**VariableValue<IEnumerable\<String>>**</span></span>  
 <span data-ttu-id="e52b2-125">**WriteLine**</span><span class="sxs-lookup"><span data-stu-id="e52b2-125">**WriteLine**</span></span>  
 <span data-ttu-id="e52b2-126">**DelegateArgumentValue\<String>**</span><span class="sxs-lookup"><span data-stu-id="e52b2-126">**DelegateArgumentValue\<String>**</span></span>  
 <span data-ttu-id="e52b2-127">**序列**</span><span class="sxs-lookup"><span data-stu-id="e52b2-127">**Sequence**</span></span>  
 <span data-ttu-id="e52b2-128">**WriteLine**</span><span class="sxs-lookup"><span data-stu-id="e52b2-128">**WriteLine**</span></span>  
 <span data-ttu-id="e52b2-129">**文本 \<String>** 若要检索特定活动，而不是枚举所有活动， <xref:System.Activities.WorkflowInspectionServices.Resolve%2A> 则使用。</span><span class="sxs-lookup"><span data-stu-id="e52b2-129">**Literal\<String>**  To retrieve a specific activity instead of enumerating all of the activities, <xref:System.Activities.WorkflowInspectionServices.Resolve%2A> is used.</span></span> <span data-ttu-id="e52b2-130">如果以前没有调用过 <xref:System.Activities.WorkflowInspectionServices.Resolve%2A>，则 <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> 和 `WorkflowInspectionServices.CacheMetadata` 均会执行元数据缓存。</span><span class="sxs-lookup"><span data-stu-id="e52b2-130">Both <xref:System.Activities.WorkflowInspectionServices.Resolve%2A> and <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> perform metadata caching if `WorkflowInspectionServices.CacheMetadata` has not been previously called.</span></span> <span data-ttu-id="e52b2-131">如果已调用过 <xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A>，则 <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> 基于现有元数据。</span><span class="sxs-lookup"><span data-stu-id="e52b2-131">If <xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A> has been called then <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> is based on the existing metadata.</span></span> <span data-ttu-id="e52b2-132">因此，如果自上次调用 <xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A> 以来对树进行了更改，则 <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> 可能会产生意外的结果。</span><span class="sxs-lookup"><span data-stu-id="e52b2-132">Therefore, if tree changes have been made since the last call to <xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A>, <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> might give unexpected results.</span></span> <span data-ttu-id="e52b2-133">如果在调用后对工作流进行了更改 <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> ，则可以通过调用方法来重新缓存元数据 <xref:System.Activities.Validation.ActivityValidationServices> <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> 。</span><span class="sxs-lookup"><span data-stu-id="e52b2-133">If changes have been made to the workflow after calling <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A>, metadata can be re-cached by calling the <xref:System.Activities.Validation.ActivityValidationServices> <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> method.</span></span> <span data-ttu-id="e52b2-134">缓存元数据在下一节中讨论。</span><span class="sxs-lookup"><span data-stu-id="e52b2-134">Caching metadata is discussed in the next section.</span></span>  
  
### <a name="caching-metadata"></a><span data-ttu-id="e52b2-135">缓存元数据</span><span class="sxs-lookup"><span data-stu-id="e52b2-135">Caching Metadata</span></span>  

 <span data-ttu-id="e52b2-136">缓存某个活动的元数据将生成并验证活动的自变量、变量、子活动和活动委托的描述。</span><span class="sxs-lookup"><span data-stu-id="e52b2-136">Caching the metadata for an activity builds and validates a description of the activity’s arguments, variables, child activities, and activity delegates.</span></span> <span data-ttu-id="e52b2-137">默认情况下，元数据在准备执行某个活动时由运行时缓存。</span><span class="sxs-lookup"><span data-stu-id="e52b2-137">Metadata, by default, is cached by the runtime when an activity is prepared for execution.</span></span> <span data-ttu-id="e52b2-138">例如，如果工作流主机作者希望在此之前缓存某个活动或活动树的元数据，以便提前使用所有开销，则可使用 <xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A> 在需要时缓存元数据。</span><span class="sxs-lookup"><span data-stu-id="e52b2-138">If a workflow host author wants to cache the metadata for an activity or activity tree before this, for example to take all of the cost upfront, then <xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A> can be used to cache the metadata at the desired time.</span></span>
