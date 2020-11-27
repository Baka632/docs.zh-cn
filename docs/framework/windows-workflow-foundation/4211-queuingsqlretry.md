---
title: 4211 - QueuingSqlRetry
ms.date: 03/30/2017
ms.assetid: df569f88-c86b-4503-840d-1399b67f4df7
ms.openlocfilehash: ff8a1e099934f5bf71fef0afbb7e54c0d1851fae
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267177"
---
# <a name="4211---queuingsqlretry"></a><span data-ttu-id="e337a-102">4211 - QueuingSqlRetry</span><span class="sxs-lookup"><span data-stu-id="e337a-102">4211 - QueuingSqlRetry</span></span>

## <a name="properties"></a><span data-ttu-id="e337a-103">属性</span><span class="sxs-lookup"><span data-stu-id="e337a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e337a-104">ID</span><span class="sxs-lookup"><span data-stu-id="e337a-104">ID</span></span>|<span data-ttu-id="e337a-105">4211</span><span class="sxs-lookup"><span data-stu-id="e337a-105">4211</span></span>|  
|<span data-ttu-id="e337a-106">关键字</span><span class="sxs-lookup"><span data-stu-id="e337a-106">Keywords</span></span>|<span data-ttu-id="e337a-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="e337a-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="e337a-108">Level</span><span class="sxs-lookup"><span data-stu-id="e337a-108">Level</span></span>|<span data-ttu-id="e337a-109">警告</span><span class="sxs-lookup"><span data-stu-id="e337a-109">Warning</span></span>|  
|<span data-ttu-id="e337a-110">通道</span><span class="sxs-lookup"><span data-stu-id="e337a-110">Channel</span></span>|<span data-ttu-id="e337a-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="e337a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e337a-112">描述</span><span class="sxs-lookup"><span data-stu-id="e337a-112">Description</span></span>  

 <span data-ttu-id="e337a-113">指示将 SQL 重试排队。</span><span class="sxs-lookup"><span data-stu-id="e337a-113">Indicates queuing SQL retry.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e337a-114">消息</span><span class="sxs-lookup"><span data-stu-id="e337a-114">Message</span></span>  

 <span data-ttu-id="e337a-115">正在将 SQL 重试排队，延迟 %1 毫秒。</span><span class="sxs-lookup"><span data-stu-id="e337a-115">Queuing SQL retry with delay %1 milliseconds.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e337a-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="e337a-116">Details</span></span>  
  
|<span data-ttu-id="e337a-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="e337a-117">Data Item Name</span></span>|<span data-ttu-id="e337a-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="e337a-118">Data Item Type</span></span>|<span data-ttu-id="e337a-119">描述</span><span class="sxs-lookup"><span data-stu-id="e337a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e337a-120">延迟</span><span class="sxs-lookup"><span data-stu-id="e337a-120">Delay</span></span>|<span data-ttu-id="e337a-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="e337a-121">xs:string</span></span>|<span data-ttu-id="e337a-122">重试之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="e337a-122">The delay between retries.</span></span>|  
|<span data-ttu-id="e337a-123">应用程序域</span><span class="sxs-lookup"><span data-stu-id="e337a-123">AppDomain</span></span>|<span data-ttu-id="e337a-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="e337a-124">xs:string</span></span>|<span data-ttu-id="e337a-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="e337a-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
