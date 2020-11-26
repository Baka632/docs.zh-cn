---
title: 1008 - WorkflowApplicationUnloaded
ms.date: 03/30/2017
ms.assetid: a605b780-4a7e-43ab-92e7-0a3b01d053b0
ms.openlocfilehash: 6ea121e7901d877d4f0d8f9f5bfd259c2f93696d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239816"
---
# <a name="1008---workflowapplicationunloaded"></a><span data-ttu-id="67b94-102">1008 - WorkflowApplicationUnloaded</span><span class="sxs-lookup"><span data-stu-id="67b94-102">1008 - WorkflowApplicationUnloaded</span></span>

## <a name="properties"></a><span data-ttu-id="67b94-103">属性</span><span class="sxs-lookup"><span data-stu-id="67b94-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="67b94-104">ID</span><span class="sxs-lookup"><span data-stu-id="67b94-104">ID</span></span>|<span data-ttu-id="67b94-105">1008</span><span class="sxs-lookup"><span data-stu-id="67b94-105">1008</span></span>|  
|<span data-ttu-id="67b94-106">关键字</span><span class="sxs-lookup"><span data-stu-id="67b94-106">Keywords</span></span>|<span data-ttu-id="67b94-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="67b94-107">WFRuntime</span></span>|  
|<span data-ttu-id="67b94-108">Level</span><span class="sxs-lookup"><span data-stu-id="67b94-108">Level</span></span>|<span data-ttu-id="67b94-109">信息</span><span class="sxs-lookup"><span data-stu-id="67b94-109">Information</span></span>|  
|<span data-ttu-id="67b94-110">通道</span><span class="sxs-lookup"><span data-stu-id="67b94-110">Channel</span></span>|<span data-ttu-id="67b94-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="67b94-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="67b94-112">描述</span><span class="sxs-lookup"><span data-stu-id="67b94-112">Description</span></span>  

 <span data-ttu-id="67b94-113">指示工作流应用程序已卸载。</span><span class="sxs-lookup"><span data-stu-id="67b94-113">Indicates a workflow application has unloaded.</span></span>  
  
## <a name="message"></a><span data-ttu-id="67b94-114">消息</span><span class="sxs-lookup"><span data-stu-id="67b94-114">Message</span></span>  

 <span data-ttu-id="67b94-115">WorkflowInstance Id“%1”已卸载。</span><span class="sxs-lookup"><span data-stu-id="67b94-115">WorkflowInstance Id: '%1' was Unloaded.</span></span>  
  
## <a name="details"></a><span data-ttu-id="67b94-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="67b94-116">Details</span></span>  
  
|<span data-ttu-id="67b94-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="67b94-117">Data Item Name</span></span>|<span data-ttu-id="67b94-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="67b94-118">Data Item Type</span></span>|<span data-ttu-id="67b94-119">描述</span><span class="sxs-lookup"><span data-stu-id="67b94-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="67b94-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="67b94-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="67b94-121">工作流的实例 ID</span><span class="sxs-lookup"><span data-stu-id="67b94-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="67b94-122">应用程序域</span><span class="sxs-lookup"><span data-stu-id="67b94-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="67b94-123">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="67b94-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
