---
title: 通道扩展性
ms.date: 03/30/2017
ms.assetid: 4cc3b20b-778a-4ae8-b58c-a3822fb13065
ms.openlocfilehash: 1a734c305e2a6f2fc759647ab5bdf380f7c7eeee
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253827"
---
# <a name="channels-extensibility"></a><span data-ttu-id="073b0-102">通道扩展性</span><span class="sxs-lookup"><span data-stu-id="073b0-102">Channels Extensibility</span></span>

<span data-ttu-id="073b0-103">本节包含演示自定义通道的示例。</span><span class="sxs-lookup"><span data-stu-id="073b0-103">This section contains samples that demonstrate custom channels.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="073b0-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="073b0-104">In This Section</span></span>  

 [<span data-ttu-id="073b0-105">本地通道</span><span class="sxs-lookup"><span data-stu-id="073b0-105">Local Channel</span></span>](local-channel.md)  
 <span data-ttu-id="073b0-106">演示本地通道，它是用于在同一个应用程序域内进行通信的 WCF 传输通道。</span><span class="sxs-lookup"><span data-stu-id="073b0-106">Demonstrates the local channel, a WCF transport channel that is used for communication within the same application domain.</span></span>  
  
 [<span data-ttu-id="073b0-107">可靠安全配置文件</span><span class="sxs-lookup"><span data-stu-id="073b0-107">Reliable Secure Profile</span></span>](reliable-secure-profile.md)  
 <span data-ttu-id="073b0-108">演示如何将 WCF 和可靠安全配置文件 (RSP) 组合在一起。</span><span class="sxs-lookup"><span data-stu-id="073b0-108">Demonstrates how to compose WCF and Reliable Secure Profile (RSP).</span></span>  
  
 [<span data-ttu-id="073b0-109">自定义通道调度程序</span><span class="sxs-lookup"><span data-stu-id="073b0-109">Custom Channel Dispatcher</span></span>](custom-channel-dispatcher.md)  
 <span data-ttu-id="073b0-110">演示如何通过直接实现 <xref:System.ServiceModel.ServiceHostBase> 以自定义方式生成通道堆栈，以及如何在 Web 主机环境中创建自定义通道调度程序。</span><span class="sxs-lookup"><span data-stu-id="073b0-110">Demonstrates how to build the channel stack in a custom way by implementing <xref:System.ServiceModel.ServiceHostBase> directly and how to create a custom channel dispatcher in Web host environment.</span></span>  
  
 [<span data-ttu-id="073b0-111">通道分块</span><span class="sxs-lookup"><span data-stu-id="073b0-111">Chunking Channel</span></span>](chunking-channel.md)  
 <span data-ttu-id="073b0-112">演示如何限制用于缓冲使用 WCF 发送的大型消息的内存量。</span><span class="sxs-lookup"><span data-stu-id="073b0-112">Demonstrates how to limit the amount of memory used to buffer large messages sent using WCF.</span></span>
  
 [<span data-ttu-id="073b0-113">HttpCookieSession</span><span class="sxs-lookup"><span data-stu-id="073b0-113">HttpCookieSession</span></span>](httpcookiesession.md)  
 <span data-ttu-id="073b0-114">演示如何生成自定义协议通道，以便使用 HTTP Cookie 进行会话管理。</span><span class="sxs-lookup"><span data-stu-id="073b0-114">Demonstrates how to build a custom protocol channel to use HTTP cookies for session management.</span></span>  
  
 [<span data-ttu-id="073b0-115">自定义消息拦截器</span><span class="sxs-lookup"><span data-stu-id="073b0-115">Custom Message Interceptor</span></span>](custom-message-interceptor.md)  
 <span data-ttu-id="073b0-116">演示如何实现可创建通道工厂和通道侦听器的自定义绑定元素，以便在运行时堆栈的特定点截获所有传入和传出消息。</span><span class="sxs-lookup"><span data-stu-id="073b0-116">Demonstrates how to implement a custom binding element that creates channel factories and channel listeners to intercept all incoming and outgoing messages at a particular point in the run-time stack.</span></span>
