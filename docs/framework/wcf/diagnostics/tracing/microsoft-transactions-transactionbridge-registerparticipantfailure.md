---
title: Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure
ms.date: 03/30/2017
ms.assetid: 3a4ead79-8550-4037-84e3-fd70ff56e001
ms.openlocfilehash: 2f0198d3c288b4c3833cdac8e5f943ba822c22e9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96252018"
---
# <a name="microsofttransactionstransactionbridgeregisterparticipantfailure"></a><span data-ttu-id="50b6e-102">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span><span class="sxs-lookup"><span data-stu-id="50b6e-102">Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure</span></span>

<span data-ttu-id="50b6e-103">WS-AT 协议服务未能注册某个控制协议的参与者。</span><span class="sxs-lookup"><span data-stu-id="50b6e-103">The WS-AT protocol service failed to register a participant for a control protocol.</span></span>  
  
## <a name="description"></a><span data-ttu-id="50b6e-104">描述</span><span class="sxs-lookup"><span data-stu-id="50b6e-104">Description</span></span>  

 <span data-ttu-id="50b6e-105">跟踪 MSDTC 是否检测到无效的注册请求。</span><span class="sxs-lookup"><span data-stu-id="50b6e-105">Traced if MSDTC detects an invalid Registration request.</span></span> <span data-ttu-id="50b6e-106">这可能是由于多个完成注册请求和内部错误造成的。</span><span class="sxs-lookup"><span data-stu-id="50b6e-106">This can be caused by  multiple Completion registration requests and internal errors.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="50b6e-107">疑难解答</span><span class="sxs-lookup"><span data-stu-id="50b6e-107">Troubleshooting</span></span>  

 <span data-ttu-id="50b6e-108">不要尝试多次“为完成而注册”。</span><span class="sxs-lookup"><span data-stu-id="50b6e-108">Do not try to Register for Completion more than once.</span></span>  <span data-ttu-id="50b6e-109">此外，检查跟踪消息中的状态字符串以确定是否存在任何可操作的项。</span><span class="sxs-lookup"><span data-stu-id="50b6e-109">Also, inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50b6e-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50b6e-110">See also</span></span>

- [<span data-ttu-id="50b6e-111">跟踪</span><span class="sxs-lookup"><span data-stu-id="50b6e-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="50b6e-112">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="50b6e-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="50b6e-113">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="50b6e-113">Administration and Diagnostics</span></span>](../index.md)
