---
title: 209 - MessageInspectorBeforeSendInvoked
ms.date: 03/30/2017
ms.assetid: 7d710875-fb77-4463-978b-bc86d59d84cd
ms.openlocfilehash: 50a9424f445781cac70d7d7fde58beea10231cfa
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267749"
---
# <a name="209---messageinspectorbeforesendinvoked"></a><span data-ttu-id="0d0dc-102">209 - MessageInspectorBeforeSendInvoked</span><span class="sxs-lookup"><span data-stu-id="0d0dc-102">209 - MessageInspectorBeforeSendInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="0d0dc-103">属性</span><span class="sxs-lookup"><span data-stu-id="0d0dc-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0d0dc-104">ID</span><span class="sxs-lookup"><span data-stu-id="0d0dc-104">ID</span></span>|<span data-ttu-id="0d0dc-105">209</span><span class="sxs-lookup"><span data-stu-id="0d0dc-105">209</span></span>|  
|<span data-ttu-id="0d0dc-106">关键字</span><span class="sxs-lookup"><span data-stu-id="0d0dc-106">Keywords</span></span>|<span data-ttu-id="0d0dc-107">疑难解答，ServiceModel</span><span class="sxs-lookup"><span data-stu-id="0d0dc-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="0d0dc-108">Level</span><span class="sxs-lookup"><span data-stu-id="0d0dc-108">Level</span></span>|<span data-ttu-id="0d0dc-109">信息</span><span class="sxs-lookup"><span data-stu-id="0d0dc-109">Information</span></span>|  
|<span data-ttu-id="0d0dc-110">通道</span><span class="sxs-lookup"><span data-stu-id="0d0dc-110">Channel</span></span>|<span data-ttu-id="0d0dc-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="0d0dc-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0d0dc-112">描述</span><span class="sxs-lookup"><span data-stu-id="0d0dc-112">Description</span></span>  

 <span data-ttu-id="0d0dc-113">服务模型对消息检查器调用 `BeforeSend` 方法之后，将发出此事件。</span><span class="sxs-lookup"><span data-stu-id="0d0dc-113">This event is emitted after the Service Model has invoked the `BeforeSend` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0d0dc-114">消息</span><span class="sxs-lookup"><span data-stu-id="0d0dc-114">Message</span></span>  

 <span data-ttu-id="0d0dc-115">调度程序对“%1”类型的 MessageInspector 调用了“BeforeSendRequest”。</span><span class="sxs-lookup"><span data-stu-id="0d0dc-115">The Dispatcher invoked 'BeforeSendRequest' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0d0dc-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="0d0dc-116">Details</span></span>  
  
|<span data-ttu-id="0d0dc-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="0d0dc-117">Data Item Name</span></span>|<span data-ttu-id="0d0dc-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="0d0dc-118">Data Item Type</span></span>|<span data-ttu-id="0d0dc-119">描述</span><span class="sxs-lookup"><span data-stu-id="0d0dc-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0d0dc-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="0d0dc-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="0d0dc-121">所调用 `MessageInspector` 的类型的 CLR FullName。</span><span class="sxs-lookup"><span data-stu-id="0d0dc-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="0d0dc-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="0d0dc-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="0d0dc-123">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="0d0dc-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="0d0dc-124">其格式定义为 "网站名称应用程序虚拟路径&#124;服务虚拟路径&#124;ServiceName"。</span><span class="sxs-lookup"><span data-stu-id="0d0dc-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="0d0dc-125">示例： "Default Web Site//Calculatorapplication&#124;/CalculatorService.svc&#124;CalculatorService"。</span><span class="sxs-lookup"><span data-stu-id="0d0dc-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="0d0dc-126">应用程序域</span><span class="sxs-lookup"><span data-stu-id="0d0dc-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="0d0dc-127">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="0d0dc-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
