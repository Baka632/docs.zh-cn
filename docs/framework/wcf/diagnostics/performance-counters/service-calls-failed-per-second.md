---
title: 服务：Calls Failed Per Second（每秒失败的调用次数）
ms.date: 03/30/2017
ms.assetid: 5a2c7939-107d-4f0c-b43c-e02e079e8a9d
ms.openlocfilehash: c97e4b0c6c2c71756a9bed7b1a2359ad0c118a98
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96252967"
---
# <a name="service-calls-failed-per-second"></a><span data-ttu-id="b4897-102">服务：Calls Failed Per Second（每秒失败的调用次数）</span><span class="sxs-lookup"><span data-stu-id="b4897-102">Service: Calls Failed Per Second</span></span>

<span data-ttu-id="b4897-103">计数器名称：Calls Failed Per Second（每秒失败的调用次数）。</span><span class="sxs-lookup"><span data-stu-id="b4897-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b4897-104">描述</span><span class="sxs-lookup"><span data-stu-id="b4897-104">Description</span></span>  

 <span data-ttu-id="b4897-105">一秒钟内由此服务收到且具有未处理异常的调用次数。</span><span class="sxs-lookup"><span data-stu-id="b4897-105">Number of calls that have unhandled exceptions, and are received by this service in a second.</span></span>  
  
 <span data-ttu-id="b4897-106">此计数器的性能计数器类型 [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))，其值使用以下公式进行计算。</span><span class="sxs-lookup"><span data-stu-id="b4897-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="b4897-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="b4897-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="b4897-108">在托管代码中，出现错误条件时引发异常。</span><span class="sxs-lookup"><span data-stu-id="b4897-108">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="b4897-109">在托管代码中，出现错误条件时引发异常。</span><span class="sxs-lookup"><span data-stu-id="b4897-109">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="b4897-110">此服务中每出现一个未处理异常，此计数器就会递增。</span><span class="sxs-lookup"><span data-stu-id="b4897-110">This counter is incremented every time there is an unhandled exception in this service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4897-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b4897-111">See also</span></span>

- [<span data-ttu-id="b4897-112">在协定和服务中指定和处理错误</span><span class="sxs-lookup"><span data-stu-id="b4897-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
