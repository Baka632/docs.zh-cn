---
title: 1124 - InvokeMethodIsStatic
ms.date: 03/30/2017
ms.assetid: b9643641-fb52-4fa8-b354-4dd6617d68f6
ms.openlocfilehash: d7ad99131f9813c2102f52784fc33605bed37557
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242118"
---
# <a name="1124---invokemethodisstatic"></a><span data-ttu-id="2528d-102">1124 - InvokeMethodIsStatic</span><span class="sxs-lookup"><span data-stu-id="2528d-102">1124 - InvokeMethodIsStatic</span></span>

## <a name="properties"></a><span data-ttu-id="2528d-103">属性</span><span class="sxs-lookup"><span data-stu-id="2528d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2528d-104">ID</span><span class="sxs-lookup"><span data-stu-id="2528d-104">ID</span></span>|<span data-ttu-id="2528d-105">1124</span><span class="sxs-lookup"><span data-stu-id="2528d-105">1124</span></span>|  
|<span data-ttu-id="2528d-106">关键字</span><span class="sxs-lookup"><span data-stu-id="2528d-106">Keywords</span></span>|<span data-ttu-id="2528d-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2528d-107">WFRuntime</span></span>|  
|<span data-ttu-id="2528d-108">Level</span><span class="sxs-lookup"><span data-stu-id="2528d-108">Level</span></span>|<span data-ttu-id="2528d-109">信息</span><span class="sxs-lookup"><span data-stu-id="2528d-109">Information</span></span>|  
|<span data-ttu-id="2528d-110">通道</span><span class="sxs-lookup"><span data-stu-id="2528d-110">Channel</span></span>|<span data-ttu-id="2528d-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="2528d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2528d-112">描述</span><span class="sxs-lookup"><span data-stu-id="2528d-112">Description</span></span>  

 <span data-ttu-id="2528d-113">在 CacheMetadata 步骤中，InvokeMethod 活动指示要调用的方法是静态的。</span><span class="sxs-lookup"><span data-stu-id="2528d-113">During CacheMetadata step, InvokeMethod activity indicates the method to be invoked is static.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2528d-114">消息</span><span class="sxs-lookup"><span data-stu-id="2528d-114">Message</span></span>  

 <span data-ttu-id="2528d-115">InvokeMethod“%1”- 方法为静态。</span><span class="sxs-lookup"><span data-stu-id="2528d-115">InvokeMethod '%1' - method is Static.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2528d-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="2528d-116">Details</span></span>  
  
|<span data-ttu-id="2528d-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="2528d-117">Data Item Name</span></span>|<span data-ttu-id="2528d-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="2528d-118">Data Item Type</span></span>|<span data-ttu-id="2528d-119">描述</span><span class="sxs-lookup"><span data-stu-id="2528d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2528d-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="2528d-120">InvokeMethod</span></span>|<span data-ttu-id="2528d-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="2528d-121">xs:string</span></span>|<span data-ttu-id="2528d-122">InvokeMethod 活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="2528d-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="2528d-123">应用程序域</span><span class="sxs-lookup"><span data-stu-id="2528d-123">AppDomain</span></span>|<span data-ttu-id="2528d-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="2528d-124">xs:string</span></span>|<span data-ttu-id="2528d-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="2528d-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
