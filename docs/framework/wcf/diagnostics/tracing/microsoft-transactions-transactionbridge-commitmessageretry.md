---
title: Microsoft.Transactions.TransactionBridge.CommitMessageRetry
ms.date: 03/30/2017
ms.assetid: 4abe01f0-6398-4fba-b2f3-c054b7f7e971
ms.openlocfilehash: 28b83b293570adf3b1cfdc15c77afd0f0cf768eb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96259020"
---
# <a name="microsofttransactionstransactionbridgecommitmessageretry"></a><span data-ttu-id="3ea37-102">Microsoft.Transactions.TransactionBridge.CommitMessageRetry</span><span class="sxs-lookup"><span data-stu-id="3ea37-102">Microsoft.Transactions.TransactionBridge.CommitMessageRetry</span></span>

<span data-ttu-id="3ea37-103">已向无反应参与者发送提交消息重试。</span><span class="sxs-lookup"><span data-stu-id="3ea37-103">A commit message retry was sent to an unresponsive participant.</span></span>  
  
## <a name="description"></a><span data-ttu-id="3ea37-104">描述</span><span class="sxs-lookup"><span data-stu-id="3ea37-104">Description</span></span>  

 <span data-ttu-id="3ea37-105">如果本地事务管理器在给定时间内未收到响应，因而需要向从属参与者重新发送“提交”消息，则进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="3ea37-105">Traced if the local Transaction Manager needed to resend a Commit message to a subordinate participant because it did not receive a response in a given amount of time.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="3ea37-106">疑难解答</span><span class="sxs-lookup"><span data-stu-id="3ea37-106">Troubleshooting</span></span>  

 <span data-ttu-id="3ea37-107">调查导致响应未及时传送的潜在网络或产品问题。</span><span class="sxs-lookup"><span data-stu-id="3ea37-107">Investigate potential network or product issues that prevent the response from being delivered on time.</span></span>  <span data-ttu-id="3ea37-108">如果看到很多这样的消息，可能表明基础结构有问题或响应时间异常长。</span><span class="sxs-lookup"><span data-stu-id="3ea37-108">If many of these messages are seen, it can indicate infrastructure problems or abnormally long response times.</span></span> <span data-ttu-id="3ea37-109">这两种问题都会明显降低系统中事务的吞吐量。</span><span class="sxs-lookup"><span data-stu-id="3ea37-109">Both issues will drastically reduce the throughput of transactions within the system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ea37-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3ea37-110">See also</span></span>

- [<span data-ttu-id="3ea37-111">跟踪</span><span class="sxs-lookup"><span data-stu-id="3ea37-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="3ea37-112">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="3ea37-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="3ea37-113">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="3ea37-113">Administration and Diagnostics</span></span>](../index.md)
