---
title: 1036 - RuntimeTransactionCompletionRequested
ms.date: 03/30/2017
ms.assetid: d36b9f44-7c0f-4083-9d3a-9034dd2b98de
ms.openlocfilehash: 96ea253fd61652a3719eaf8b1a4d31aa88337eeb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294256"
---
# <a name="1036---runtimetransactioncompletionrequested"></a><span data-ttu-id="4e861-102">1036 - RuntimeTransactionCompletionRequested</span><span class="sxs-lookup"><span data-stu-id="4e861-102">1036 - RuntimeTransactionCompletionRequested</span></span>

## <a name="properties"></a><span data-ttu-id="4e861-103">属性</span><span class="sxs-lookup"><span data-stu-id="4e861-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4e861-104">ID</span><span class="sxs-lookup"><span data-stu-id="4e861-104">ID</span></span>|<span data-ttu-id="4e861-105">1036</span><span class="sxs-lookup"><span data-stu-id="4e861-105">1036</span></span>|  
|<span data-ttu-id="4e861-106">关键字</span><span class="sxs-lookup"><span data-stu-id="4e861-106">Keywords</span></span>|<span data-ttu-id="4e861-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="4e861-107">WFRuntime</span></span>|  
|<span data-ttu-id="4e861-108">级别</span><span class="sxs-lookup"><span data-stu-id="4e861-108">Level</span></span>|<span data-ttu-id="4e861-109">“详细”</span><span class="sxs-lookup"><span data-stu-id="4e861-109">Verbose</span></span>|  
|<span data-ttu-id="4e861-110">通道</span><span class="sxs-lookup"><span data-stu-id="4e861-110">Channel</span></span>|<span data-ttu-id="4e861-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="4e861-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4e861-112">描述</span><span class="sxs-lookup"><span data-stu-id="4e861-112">Description</span></span>  

 <span data-ttu-id="4e861-113">指示活动已安排了运行时事务的完成。</span><span class="sxs-lookup"><span data-stu-id="4e861-113">Indicates an activity has scheduled the completion of the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4e861-114">消息</span><span class="sxs-lookup"><span data-stu-id="4e861-114">Message</span></span>  

 <span data-ttu-id="4e861-115">Activity“%1”、DisplayName“%2”、InstanceId“%3”已安排了运行时事务的完成。</span><span class="sxs-lookup"><span data-stu-id="4e861-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has scheduled completion of the runtime transaction.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4e861-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="4e861-116">Details</span></span>  
  
|<span data-ttu-id="4e861-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="4e861-117">Data Item Name</span></span>|<span data-ttu-id="4e861-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="4e861-118">Data Item Type</span></span>|<span data-ttu-id="4e861-119">描述</span><span class="sxs-lookup"><span data-stu-id="4e861-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4e861-120">活动</span><span class="sxs-lookup"><span data-stu-id="4e861-120">Activity</span></span>|<span data-ttu-id="4e861-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="4e861-121">xs:string</span></span>|<span data-ttu-id="4e861-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="4e861-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="4e861-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="4e861-123">DisplayName</span></span>|<span data-ttu-id="4e861-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="4e861-124">xs:string</span></span>|<span data-ttu-id="4e861-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="4e861-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="4e861-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="4e861-126">InstanceId</span></span>|<span data-ttu-id="4e861-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="4e861-127">xs:string</span></span>|<span data-ttu-id="4e861-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="4e861-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="4e861-129">应用程序域</span><span class="sxs-lookup"><span data-stu-id="4e861-129">AppDomain</span></span>|<span data-ttu-id="4e861-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="4e861-130">xs:string</span></span>|<span data-ttu-id="4e861-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="4e861-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
