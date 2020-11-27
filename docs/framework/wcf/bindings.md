---
title: Windows Communication Foundation 绑定
ms.date: 03/30/2017
helpviewer_keywords:
- bindings [WCF]
ms.assetid: 845df323-be53-4848-92ef-ba67a406484d
ms.openlocfilehash: 3ce861404e59d24c2b1e0b548026bc795157fffe
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272366"
---
# <a name="windows-communication-foundation-bindings"></a><span data-ttu-id="ff9a6-102">Windows Communication Foundation 绑定</span><span class="sxs-lookup"><span data-stu-id="ff9a6-102">Windows Communication Foundation Bindings</span></span>

<span data-ttu-id="ff9a6-103">绑定指定 Windows Communication Foundation (WCF) 服务终结点与其他终结点通信的方式。</span><span class="sxs-lookup"><span data-stu-id="ff9a6-103">Bindings specify how a Windows Communication Foundation (WCF) service endpoint communicates with other endpoints.</span></span> <span data-ttu-id="ff9a6-104">绑定最起码必须指定要使用的传输（如 HTTP 或 TCP）。</span><span class="sxs-lookup"><span data-stu-id="ff9a6-104">At its most basic, a binding must specify the transport (for example, HTTP or TCP) to use.</span></span> <span data-ttu-id="ff9a6-105">你还可以通过绑定来设置其他特征，如安全和事务支持。</span><span class="sxs-lookup"><span data-stu-id="ff9a6-105">You can also set other characteristics, such as security and transaction support, through bindings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ff9a6-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="ff9a6-106">In This Section</span></span>  

 [<span data-ttu-id="ff9a6-107">WCF 绑定概述</span><span class="sxs-lookup"><span data-stu-id="ff9a6-107">WCF Bindings Overview</span></span>](bindings-overview.md)  
 <span data-ttu-id="ff9a6-108">概述 WCF 绑定的功能、系统提供的绑定，以及如何定义或修改它们。</span><span class="sxs-lookup"><span data-stu-id="ff9a6-108">Overview of what WCF bindings do, what bindings the system provides, and how you can define or modify them.</span></span>  
  
 [<span data-ttu-id="ff9a6-109">系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="ff9a6-109">System-Provided Bindings</span></span>](system-provided-bindings.md)  
 <span data-ttu-id="ff9a6-110">WCF 附带的绑定列表。</span><span class="sxs-lookup"><span data-stu-id="ff9a6-110">A list of bindings included with WCF.</span></span> <span data-ttu-id="ff9a6-111">这些绑定包含大部分安全和消息模式需求。</span><span class="sxs-lookup"><span data-stu-id="ff9a6-111">These bindings cover the majority of security and message pattern requirements.</span></span>  
  
 [<span data-ttu-id="ff9a6-112">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="ff9a6-112">Using Bindings to Configure Services and Clients</span></span>](using-bindings-to-configure-services-and-clients.md)  
 <span data-ttu-id="ff9a6-113">WCF 绑定包含客户端必须用于连接到服务终结点的重要信息。</span><span class="sxs-lookup"><span data-stu-id="ff9a6-113">A WCF binding contains important information that clients must use to connect to service endpoints.</span></span>  
  
 [<span data-ttu-id="ff9a6-114">配置服务绑定</span><span class="sxs-lookup"><span data-stu-id="ff9a6-114">Configuring Bindings for Services</span></span>](configuring-bindings-for-wcf-services.md)  
 <span data-ttu-id="ff9a6-115">通过配置，管理员和安装者可以自定义服务终结点的绑定。</span><span class="sxs-lookup"><span data-stu-id="ff9a6-115">Configuration enables administrators and installers to customize the bindings for service endpoints.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ff9a6-116">参考</span><span class="sxs-lookup"><span data-stu-id="ff9a6-116">Reference</span></span>  

 <xref:System.ServiceModel.Channels>  
  
## <a name="related-sections"></a><span data-ttu-id="ff9a6-117">相关章节</span><span class="sxs-lookup"><span data-stu-id="ff9a6-117">Related Sections</span></span>  

 [<span data-ttu-id="ff9a6-118">终结点：地址、绑定和协定</span><span class="sxs-lookup"><span data-stu-id="ff9a6-118">Endpoints: Addresses, Bindings, and Contracts</span></span>](./feature-details/endpoints-addresses-bindings-and-contracts.md)  
  
 [<span data-ttu-id="ff9a6-119">绑定</span><span class="sxs-lookup"><span data-stu-id="ff9a6-119">Bindings</span></span>](./feature-details/bindings.md)  
  
## <a name="see-also"></a><span data-ttu-id="ff9a6-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff9a6-120">See also</span></span>

- [<span data-ttu-id="ff9a6-121">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="ff9a6-121">Custom Bindings</span></span>](./extending/custom-bindings.md)
