---
title: 篡改
ms.date: 03/30/2017
ms.assetid: 3bad93be-60bb-4f89-96ab-a1c3dc7c0fad
ms.openlocfilehash: c2b0cae1dc57fac486122ca17fc8109ffe62f77d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249795"
---
# <a name="tampering"></a><span data-ttu-id="a677f-102">篡改</span><span class="sxs-lookup"><span data-stu-id="a677f-102">Tampering</span></span>

<span data-ttu-id="a677f-103">*篡改* 是指更改消息或消息传递，并使用已更改的消息，而不是它的用途。</span><span class="sxs-lookup"><span data-stu-id="a677f-103">*Tampering* is the act of altering a message, or the delivery of a message, and using the altered message for a purpose other than what it was intended for.</span></span>  
  
## <a name="do-not-disable-ws-addressing"></a><span data-ttu-id="a677f-104">不要禁用 WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="a677f-104">Do Not Disable WS-Addressing</span></span>  

 <span data-ttu-id="a677f-105">WS-Addressing 规范在每条消息中提供了地址标头，从而允许消息接收方验证消息的发送方。</span><span class="sxs-lookup"><span data-stu-id="a677f-105">The WS-Addressing specification provides address headers on each message, allowing a message recipient to verify the sender of the message.</span></span> <span data-ttu-id="a677f-106">将 <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> 属性设置为 <xref:System.ServiceModel.Channels.AddressingVersion.None%2A> 可禁用此功能。</span><span class="sxs-lookup"><span data-stu-id="a677f-106">You can disable this feature by setting the <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> property to <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.</span></span>  
  
 <span data-ttu-id="a677f-107">当安全模式设置为“消息”并且禁用了 WS-Addressing 时，攻击者就能获取来自客户端的请求，并将其发送到另一个服务，而第二个服务无法检测该消息是否来自于原客户端。</span><span class="sxs-lookup"><span data-stu-id="a677f-107">When the security mode is set to Message, and if WS-Addressing is disabled, an attacker could take a request from a client and send it to another service, and the second service has no way of detecting that the message came from the original client.</span></span> <span data-ttu-id="a677f-108">实际上，第一个服务在与第二个服务通信时，可假装它是一个客户端。</span><span class="sxs-lookup"><span data-stu-id="a677f-108">In effect, the first service can pretend that it is a client when talking to the second service.</span></span>  
  
 <span data-ttu-id="a677f-109">为了避免这个问题，请不要将 <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> 属性设置为 <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>，并避免使用 <xref:System.ServiceModel.Channels.MessageVersion>，如静态 <xref:System.ServiceModel.Channels.MessageVersion.Soap12%2A> 属性，它会将 <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> 属性设置为 <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>。</span><span class="sxs-lookup"><span data-stu-id="a677f-109">To mitigate this, never set the <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> property to <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>, and avoid the use of <xref:System.ServiceModel.Channels.MessageVersion>, such as the static <xref:System.ServiceModel.Channels.MessageVersion.Soap12%2A> property, which sets the <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> property to <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a677f-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a677f-110">See also</span></span>

- [<span data-ttu-id="a677f-111">安全注意事项</span><span class="sxs-lookup"><span data-stu-id="a677f-111">Security Considerations</span></span>](security-considerations-in-wcf.md)
- [<span data-ttu-id="a677f-112">信息泄露</span><span class="sxs-lookup"><span data-stu-id="a677f-112">Information Disclosure</span></span>](information-disclosure.md)
- [<span data-ttu-id="a677f-113">权限提升</span><span class="sxs-lookup"><span data-stu-id="a677f-113">Elevation of Privilege</span></span>](elevation-of-privilege.md)
- [<span data-ttu-id="a677f-114">拒绝服务</span><span class="sxs-lookup"><span data-stu-id="a677f-114">Denial of Service</span></span>](denial-of-service.md)
- [<span data-ttu-id="a677f-115">不支持的方案</span><span class="sxs-lookup"><span data-stu-id="a677f-115">Unsupported Scenarios</span></span>](unsupported-scenarios.md)
- [<span data-ttu-id="a677f-116">重播攻击</span><span class="sxs-lookup"><span data-stu-id="a677f-116">Replay Attacks</span></span>](replay-attacks.md)
