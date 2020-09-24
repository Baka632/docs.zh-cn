---
title: <cancelRequestedQueries> WCF 的
ms.date: 03/30/2017
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
ms.openlocfilehash: 205399330c1aa69b332c2149ee32d9b6098ccdbe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151163"
---
# <a name="cancelrequestedqueries-of-wcf"></a><span data-ttu-id="84431-102">\<cancelRequestedQueries> WCF 的</span><span class="sxs-lookup"><span data-stu-id="84431-102">\<cancelRequestedQueries> of WCF</span></span>

<span data-ttu-id="84431-103">表示一个查询集合，这些查询用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="84431-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="84431-104">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="84431-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="84431-105">有关跟踪配置文件查询的详细信息，请参阅 [跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="84431-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="84431-106">语法</span><span class="sxs-lookup"><span data-stu-id="84431-106">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestQueries>
          <cancelRequestQuery activityName="String"
                              childActivityName="String" />
        </cancelRequestQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="84431-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="84431-107">Attributes and elements</span></span>  

<span data-ttu-id="84431-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="84431-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="84431-109">特性</span><span class="sxs-lookup"><span data-stu-id="84431-109">Attributes</span></span>

<span data-ttu-id="84431-110">无。</span><span class="sxs-lookup"><span data-stu-id="84431-110">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="84431-111">子元素</span><span class="sxs-lookup"><span data-stu-id="84431-111">Child elements</span></span>
  
|<span data-ttu-id="84431-112">元素</span><span class="sxs-lookup"><span data-stu-id="84431-112">Element</span></span>|<span data-ttu-id="84431-113">描述</span><span class="sxs-lookup"><span data-stu-id="84431-113">Description</span></span>|  
|-------------|-----------------|  
|[\<cancelRequestedQuery>](cancelrequestedquery-of-wcf.md)|<span data-ttu-id="84431-114">一个查询，用于跟踪父活动取消子活动的请求</span><span class="sxs-lookup"><span data-stu-id="84431-114">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="84431-115">父元素</span><span class="sxs-lookup"><span data-stu-id="84431-115">Parent elements</span></span>  
  
|<span data-ttu-id="84431-116">元素</span><span class="sxs-lookup"><span data-stu-id="84431-116">Element</span></span>|<span data-ttu-id="84431-117">描述</span><span class="sxs-lookup"><span data-stu-id="84431-117">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="84431-118">一个配置元素，包含 <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> 属性所标识的特定工作流的所有查询。</span><span class="sxs-lookup"><span data-stu-id="84431-118">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="84431-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="84431-119">See also</span></span>

- <xref:System.Activities.Tracking.CancelRequestedQuery>
- [<span data-ttu-id="84431-120">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="84431-120">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="84431-121">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="84431-121">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
