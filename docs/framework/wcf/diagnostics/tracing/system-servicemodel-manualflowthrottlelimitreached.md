---
title: System.ServiceModel.ManualFlowThrottleLimitReached
ms.date: 03/30/2017
ms.assetid: 9aba851f-1830-493b-8e3e-60f454eb923e
ms.openlocfilehash: 180a06efc94acba40806e1f5d661553127549596
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96248482"
---
# <a name="systemservicemodelmanualflowthrottlelimitreached"></a><span data-ttu-id="c9082-102">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="c9082-102">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>

<span data-ttu-id="c9082-103">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="c9082-103">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>  
  
## <a name="description"></a><span data-ttu-id="c9082-104">描述</span><span class="sxs-lookup"><span data-stu-id="c9082-104">Description</span></span>  

 <span data-ttu-id="c9082-105">系统已达到为 ManualFlowControlLimit throttle 阈值设置的限制。</span><span class="sxs-lookup"><span data-stu-id="c9082-105">The system reached the limit set for the ManualFlowControlLimit throttle.</span></span> <span data-ttu-id="c9082-106">通过对 ServiceHost 或 InstanceContext 上的 ManualFlowControlLimit 属性进行适当修改，可以更改该阈值。</span><span class="sxs-lookup"><span data-stu-id="c9082-106">The throttle value can be changed by modifying the ManualFlowControlLimit property on either the ServiceHost or InstanceContext, as applicable.</span></span>  
  
 <span data-ttu-id="c9082-107">在手动流控制限制最初减少为 0 时发出此跟踪。</span><span class="sxs-lookup"><span data-stu-id="c9082-107">This trace is emitted when the manual flow control limit is initially reduced to 0.</span></span> <span data-ttu-id="c9082-108">不跟踪后续更改为 0 的情况。</span><span class="sxs-lookup"><span data-stu-id="c9082-108">Subsequent changes to 0 are not traced.</span></span> <span data-ttu-id="c9082-109">对于每个上下文只跟踪一次实例上下文上的流控制限制。</span><span class="sxs-lookup"><span data-stu-id="c9082-109">Flow control limit on the instance context is traced once for each context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9082-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c9082-110">See also</span></span>

- [<span data-ttu-id="c9082-111">跟踪</span><span class="sxs-lookup"><span data-stu-id="c9082-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="c9082-112">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="c9082-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="c9082-113">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="c9082-113">Administration and Diagnostics</span></span>](../index.md)
