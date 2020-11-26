---
title: 端到端跟踪
ms.date: 03/30/2017
ms.assetid: f5ac7fc7-f97c-4313-b068-54e0c471b2aa
ms.openlocfilehash: a8c06b9e4f70321e6ef3756863390dc62c659557
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243945"
---
# <a name="end-to-end-tracing"></a><span data-ttu-id="b099c-102">端到端跟踪</span><span class="sxs-lookup"><span data-stu-id="b099c-102">End-to-End Tracing</span></span>

<span data-ttu-id="b099c-103">端到端 (e2e) 跟踪允许开发人员在 Windows Communication Foundation (WCF) 基础结构中执行代码的执行，从而调查代码路径失败的原因，或者提供详细的跟踪以进行容量规划和性能分析。</span><span class="sxs-lookup"><span data-stu-id="b099c-103">End to End (e2e) Tracing allows developers to follow the execution of code in the Windows Communication Foundation (WCF) infrastructure to investigate why a code path has failed, or to provide detailed tracing for capacity planning and performance analysis.</span></span> <span data-ttu-id="b099c-104">Windows Communication Foundation (WCF) 提供了三种相关机制来帮助诊断错误的原因：活动、传输和传播。</span><span class="sxs-lookup"><span data-stu-id="b099c-104">Windows Communication Foundation (WCF) provides three correlation mechanisms to help diagnose the cause of an error: activities, transfers, and propagation.</span></span>  
  
 <span data-ttu-id="b099c-105">有关端到端跟踪方案及其各自的活动和跟踪设计的列表，请参阅 [端到端跟踪方案](end-to-end-tracing-scenarios.md) 。</span><span class="sxs-lookup"><span data-stu-id="b099c-105">See [End-To-End Tracing Scenarios](end-to-end-tracing-scenarios.md) for a list of end-to-end tracing scenarios, and their respective activity and tracing design.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b099c-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="b099c-106">In This Section</span></span>  

 <span data-ttu-id="b099c-107">[活动](activity.md)：介绍 WINDOWS COMMUNICATION FOUNDATION (WCF) 跟踪模型中的活动跟踪。</span><span class="sxs-lookup"><span data-stu-id="b099c-107">[Activity](activity.md):  Describes activity traces in the Windows Communication Foundation (WCF) tracing model.</span></span>  
  
 <span data-ttu-id="b099c-108">[传输](transfer.md)：介绍 WINDOWS COMMUNICATION FOUNDATION (WCF) 跟踪模型中的传输，以及使用传输关联终结点内的活动。</span><span class="sxs-lookup"><span data-stu-id="b099c-108">[Transfer](transfer.md):  Describes transfer in the Windows Communication Foundation (WCF) tracing model, and using transfer to correlate activities within endpoints.</span></span>  
  
 <span data-ttu-id="b099c-109">[传播](propagation.md)：介绍 WINDOWS COMMUNICATION FOUNDATION (WCF) 跟踪模型中的活动传播，并使用传播跨终结点关联活动。</span><span class="sxs-lookup"><span data-stu-id="b099c-109">[Propagation](propagation.md):  Describes activity propagation in the Windows Communication Foundation (WCF) tracing model, and using propagation to correlate activities across endpoints.</span></span>  
  
 [<span data-ttu-id="b099c-110">跟踪类型摘要</span><span class="sxs-lookup"><span data-stu-id="b099c-110">Trace Type Summary</span></span>](trace-type-summary.md)  
  
 <span data-ttu-id="b099c-111">提供所有活动跟踪类型的摘要</span><span class="sxs-lookup"><span data-stu-id="b099c-111">Provides a summary of all activity trace types</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b099c-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b099c-112">See also</span></span>

- [<span data-ttu-id="b099c-113">配置跟踪</span><span class="sxs-lookup"><span data-stu-id="b099c-113">Configuring Tracing</span></span>](configuring-tracing.md)
- [<span data-ttu-id="b099c-114">使用服务跟踪查看器查看相关跟踪和进行故障诊断</span><span class="sxs-lookup"><span data-stu-id="b099c-114">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [<span data-ttu-id="b099c-115">端到端跟踪方案</span><span class="sxs-lookup"><span data-stu-id="b099c-115">End-To-End Tracing Scenarios</span></span>](end-to-end-tracing-scenarios.md)
- [<span data-ttu-id="b099c-116">服务跟踪查看器工具 (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="b099c-116">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../service-trace-viewer-tool-svctraceviewer-exe.md)
