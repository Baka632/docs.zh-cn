---
title: 117 - WorkflowInstanceTerminatedRecordWithId
ms.date: 03/30/2017
ms.assetid: e68539d0-5338-468a-9f75-7e5b09d39a3c
ms.openlocfilehash: 5e16eff8e8ce9815cac604be110e899a29b4af3d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281724"
---
# <a name="117---workflowinstanceterminatedrecordwithid"></a><span data-ttu-id="be8fe-102">117 - WorkflowInstanceTerminatedRecordWithId</span><span class="sxs-lookup"><span data-stu-id="be8fe-102">117 - WorkflowInstanceTerminatedRecordWithId</span></span>

## <a name="properties"></a><span data-ttu-id="be8fe-103">属性</span><span class="sxs-lookup"><span data-stu-id="be8fe-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="be8fe-104">ID</span><span class="sxs-lookup"><span data-stu-id="be8fe-104">ID</span></span>|<span data-ttu-id="be8fe-105">117</span><span class="sxs-lookup"><span data-stu-id="be8fe-105">117</span></span>|  
|<span data-ttu-id="be8fe-106">关键字</span><span class="sxs-lookup"><span data-stu-id="be8fe-106">Keywords</span></span>|<span data-ttu-id="be8fe-107">HealthMonitoring、WFTracking</span><span class="sxs-lookup"><span data-stu-id="be8fe-107">HealthMonitoring, WFTracking</span></span>|  
|<span data-ttu-id="be8fe-108">Level</span><span class="sxs-lookup"><span data-stu-id="be8fe-108">Level</span></span>|<span data-ttu-id="be8fe-109">错误</span><span class="sxs-lookup"><span data-stu-id="be8fe-109">Error</span></span>|  
|<span data-ttu-id="be8fe-110">通道</span><span class="sxs-lookup"><span data-stu-id="be8fe-110">Channel</span></span>|<span data-ttu-id="be8fe-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="be8fe-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="be8fe-112">描述</span><span class="sxs-lookup"><span data-stu-id="be8fe-112">Description</span></span>  

 <span data-ttu-id="be8fe-113">当工作流实例发出 WorkflowInstanceTerminatedRecord 时，ETW 跟踪参与者将发出此事件。</span><span class="sxs-lookup"><span data-stu-id="be8fe-113">This event is emitted by the ETW tracking participant when a workflow instance emits WorkflowInstanceTerminatedRecord.</span></span>  
  
## <a name="message"></a><span data-ttu-id="be8fe-114">消息</span><span class="sxs-lookup"><span data-stu-id="be8fe-114">Message</span></span>  

 <span data-ttu-id="be8fe-115">TrackRecord = WorkflowInstanceTerminatedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span><span class="sxs-lookup"><span data-stu-id="be8fe-115">TrackRecord = WorkflowInstanceTerminatedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5,  Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span></span>  
  
## <a name="details"></a><span data-ttu-id="be8fe-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="be8fe-116">Details</span></span>  
  
|<span data-ttu-id="be8fe-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="be8fe-117">Data Item Name</span></span>|<span data-ttu-id="be8fe-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="be8fe-118">Data Item Type</span></span>|<span data-ttu-id="be8fe-119">描述</span><span class="sxs-lookup"><span data-stu-id="be8fe-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="be8fe-120">InstanceId</span><span class="sxs-lookup"><span data-stu-id="be8fe-120">InstanceId</span></span>|<span data-ttu-id="be8fe-121">xs:GUID</span><span class="sxs-lookup"><span data-stu-id="be8fe-121">xs:GUID</span></span>|<span data-ttu-id="be8fe-122">工作流的实例 ID</span><span class="sxs-lookup"><span data-stu-id="be8fe-122">The instance id for the workflow</span></span>|  
|<span data-ttu-id="be8fe-123">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="be8fe-123">RecordNumber</span></span>|<span data-ttu-id="be8fe-124">xs:long</span><span class="sxs-lookup"><span data-stu-id="be8fe-124">xs:long</span></span>|<span data-ttu-id="be8fe-125">发出的记录的序列号</span><span class="sxs-lookup"><span data-stu-id="be8fe-125">The sequence number of the emitted record</span></span>|  
|<span data-ttu-id="be8fe-126">EventTime</span><span class="sxs-lookup"><span data-stu-id="be8fe-126">EventTime</span></span>|<span data-ttu-id="be8fe-127">xs:dateTime</span><span class="sxs-lookup"><span data-stu-id="be8fe-127">xs:dateTime</span></span>|<span data-ttu-id="be8fe-128">发出该事件时的 UTC 时间</span><span class="sxs-lookup"><span data-stu-id="be8fe-128">The time in UTC when the event was emitted</span></span>|  
|<span data-ttu-id="be8fe-129">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="be8fe-129">ActivityDefinitionId</span></span>|<span data-ttu-id="be8fe-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="be8fe-130">xs:string</span></span>|<span data-ttu-id="be8fe-131">工作流中根活动的名称</span><span class="sxs-lookup"><span data-stu-id="be8fe-131">The name of the root activity in the workflow</span></span>|  
|<span data-ttu-id="be8fe-132">状态</span><span class="sxs-lookup"><span data-stu-id="be8fe-132">State</span></span>|<span data-ttu-id="be8fe-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="be8fe-133">xs:string</span></span>|<span data-ttu-id="be8fe-134">工作流的当前状态。</span><span class="sxs-lookup"><span data-stu-id="be8fe-134">The current state of the Workflow.</span></span>|  
|<span data-ttu-id="be8fe-135">批注</span><span class="sxs-lookup"><span data-stu-id="be8fe-135">Annotations</span></span>|<span data-ttu-id="be8fe-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="be8fe-136">xs:string</span></span>|<span data-ttu-id="be8fe-137">已添加到此事件中的批注。</span><span class="sxs-lookup"><span data-stu-id="be8fe-137">The annotations that were added to this event.</span></span> <span data-ttu-id="be8fe-138">值存储在 xml 元素中，格式为 \<items> \< item name = "annotationName" type="System.String"> a \</item> \</items> 。</span><span class="sxs-lookup"><span data-stu-id="be8fe-138">The values are stored in an xml element in the format \<items>\< item name = "annotationName" type="System.String">annotationValue\</item>\</items>.</span></span> <span data-ttu-id="be8fe-139">如果未指定任何批注，则该字符串包含 \<items/> 。</span><span class="sxs-lookup"><span data-stu-id="be8fe-139">If no annotations are specified then the string contains \<items/>.</span></span> <span data-ttu-id="be8fe-140">ETW 事件大小受到 ETW 缓冲区大小或 ETW 事件最大负载的限制。</span><span class="sxs-lookup"><span data-stu-id="be8fe-140">The ETW event size is limited by the ETW buffer size or the max payload for an ETW event.</span></span> <span data-ttu-id="be8fe-141">如果事件的大小超过 ETW 限制，则通过删除批注并将批注值替换为 ... 来截断事件。 \<items> \</items></span><span class="sxs-lookup"><span data-stu-id="be8fe-141">If the size of the event exceeds the ETW limits, then the event is truncated by dropping the annotations and replacing the annotation value with \<items>...\</items>.</span></span>|  
|<span data-ttu-id="be8fe-142">ProfileName</span><span class="sxs-lookup"><span data-stu-id="be8fe-142">ProfileName</span></span>|<span data-ttu-id="be8fe-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="be8fe-143">xs:string</span></span>|<span data-ttu-id="be8fe-144">导致发出此事件的跟踪配置文件的名称</span><span class="sxs-lookup"><span data-stu-id="be8fe-144">The name or the tracking profile that resulted in this event being emitted</span></span>|  
|<span data-ttu-id="be8fe-145">WorkflowDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="be8fe-145">WorkflowDefinitionIdentity</span></span>|<span data-ttu-id="be8fe-146">xs:string</span><span class="sxs-lookup"><span data-stu-id="be8fe-146">xs:string</span></span>|<span data-ttu-id="be8fe-147">工作流定义 ID</span><span class="sxs-lookup"><span data-stu-id="be8fe-147">The workflow definition id</span></span>|  
|<span data-ttu-id="be8fe-148">应用程序域</span><span class="sxs-lookup"><span data-stu-id="be8fe-148">AppDomain</span></span>|<span data-ttu-id="be8fe-149">xs:string</span><span class="sxs-lookup"><span data-stu-id="be8fe-149">xs:string</span></span>|<span data-ttu-id="be8fe-150">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="be8fe-150">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
