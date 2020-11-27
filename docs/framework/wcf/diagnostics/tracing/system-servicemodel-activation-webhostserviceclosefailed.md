---
title: System.ServiceModel.Activation.WebHostServiceCloseFailed
ms.date: 03/30/2017
ms.assetid: 3cab9856-a5cf-4f0e-a0cb-89425e368f8e
ms.openlocfilehash: e39ca97bdefafee840206036f89e8b165609516a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263004"
---
# <a name="systemservicemodelactivationwebhostserviceclosefailed"></a><span data-ttu-id="a08a2-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span><span class="sxs-lookup"><span data-stu-id="a08a2-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span></span>

<span data-ttu-id="a08a2-103">当服务无法正常关闭并中止时发生。</span><span class="sxs-lookup"><span data-stu-id="a08a2-103">Occurs when a service cannot be closed gracefully and is aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="a08a2-104">描述</span><span class="sxs-lookup"><span data-stu-id="a08a2-104">Description</span></span>  

 <span data-ttu-id="a08a2-105">此错误代码仅出现在日志文件中。</span><span class="sxs-lookup"><span data-stu-id="a08a2-105">This error code only appears in the log file.</span></span> <span data-ttu-id="a08a2-106">它通常指示编程错误，例如，在已经调用 Abort 之后尝试关闭服务的时候。</span><span class="sxs-lookup"><span data-stu-id="a08a2-106">It usually indicates a programming error, for example, when you try to close a service after Abort has already been called.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="a08a2-107">疑难解答</span><span class="sxs-lookup"><span data-stu-id="a08a2-107">Troubleshooting</span></span>  

 <span data-ttu-id="a08a2-108">请检查应用程序源代码。</span><span class="sxs-lookup"><span data-stu-id="a08a2-108">Check the application source code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a08a2-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a08a2-109">See also</span></span>

- [<span data-ttu-id="a08a2-110">跟踪</span><span class="sxs-lookup"><span data-stu-id="a08a2-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="a08a2-111">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="a08a2-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="a08a2-112">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="a08a2-112">Administration and Diagnostics</span></span>](../index.md)
