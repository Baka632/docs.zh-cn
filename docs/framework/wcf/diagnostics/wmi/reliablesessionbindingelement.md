---
title: ReliableSessionBindingElement
ms.date: 03/30/2017
ms.assetid: effda125-b8d3-4de6-8c0e-f59f5ea8f6eb
ms.openlocfilehash: f91e38ab88cd9f93e9bec0e3a6ca65254bc49570
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273316"
---
# <a name="reliablesessionbindingelement"></a><span data-ttu-id="33ab2-102">ReliableSessionBindingElement</span><span class="sxs-lookup"><span data-stu-id="33ab2-102">ReliableSessionBindingElement</span></span>

<span data-ttu-id="33ab2-103">ReliableSessionBindingElement</span><span class="sxs-lookup"><span data-stu-id="33ab2-103">ReliableSessionBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33ab2-104">语法</span><span class="sxs-lookup"><span data-stu-id="33ab2-104">Syntax</span></span>  
  
```csharp
class ReliableSessionBindingElement : BindingElement  
{  
  datetime AcknowledgementInterval;  
  boolean FlowControlEnabled;  
  datetime InactivityTimeout;  
  sint32 MaxPendingChannels;  
  sint32 MaxRetryCount;  
  sint32 MaxTransferWindowSize;  
  boolean Ordered;  
  integer ReliableMessagingVersion;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="33ab2-105">方法</span><span class="sxs-lookup"><span data-stu-id="33ab2-105">Methods</span></span>  

 <span data-ttu-id="33ab2-106">ReliableSessionBindingElement 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="33ab2-106">The ReliableSessionBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="33ab2-107">属性</span><span class="sxs-lookup"><span data-stu-id="33ab2-107">Properties</span></span>  

 <span data-ttu-id="33ab2-108">ReliableSessionBindingElement 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="33ab2-108">The ReliableSessionBindingElement class has the following properties:</span></span>  
  
### <a name="acknowledgementinterval"></a><span data-ttu-id="33ab2-109">AcknowledgementInterval</span><span class="sxs-lookup"><span data-stu-id="33ab2-109">AcknowledgementInterval</span></span>  

 <span data-ttu-id="33ab2-110">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="33ab2-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="33ab2-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="33ab2-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="33ab2-112">向工厂创建的可靠通道上的消息源发送确认之前目标等待的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="33ab2-112">The interval of time that a destination waits before sending an acknowledgement to the message source on reliable channels that are created by the factory.</span></span>  
  
### <a name="flowcontrolenabled"></a><span data-ttu-id="33ab2-113">FlowControlEnabled</span><span class="sxs-lookup"><span data-stu-id="33ab2-113">FlowControlEnabled</span></span>  

 <span data-ttu-id="33ab2-114">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="33ab2-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="33ab2-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="33ab2-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="33ab2-116">一个布尔值，指定是否启用流控制。</span><span class="sxs-lookup"><span data-stu-id="33ab2-116">A Boolean value that specifies whether flow control is enabled.</span></span>  
  
### <a name="inactivitytimeout"></a><span data-ttu-id="33ab2-117">InactivityTimeout</span><span class="sxs-lookup"><span data-stu-id="33ab2-117">InactivityTimeout</span></span>  

 <span data-ttu-id="33ab2-118">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="33ab2-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="33ab2-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="33ab2-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="33ab2-120">指定通道出错之前，通道允许其他通信方不发送任何消息的最长持续时间。</span><span class="sxs-lookup"><span data-stu-id="33ab2-120">Specifies the maximum duration the channel is going to allow the other communicating party not to send any messages before faulting the channel.</span></span>  
  
### <a name="maxpendingchannels"></a><span data-ttu-id="33ab2-121">MaxPendingChannels</span><span class="sxs-lookup"><span data-stu-id="33ab2-121">MaxPendingChannels</span></span>  

 <span data-ttu-id="33ab2-122">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="33ab2-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="33ab2-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="33ab2-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="33ab2-124">侦听器上可等待接受的最大通道数。</span><span class="sxs-lookup"><span data-stu-id="33ab2-124">The maximum number of channels that can wait to be accepted on the listener.</span></span>  
  
### <a name="maxretrycount"></a><span data-ttu-id="33ab2-125">MaxRetryCount</span><span class="sxs-lookup"><span data-stu-id="33ab2-125">MaxRetryCount</span></span>  

 <span data-ttu-id="33ab2-126">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="33ab2-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="33ab2-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="33ab2-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="33ab2-128">可靠通道未收到消息确认时，通过在其基础通道上调用 `Send` 尝试重新传输该消息的最多尝试次数。</span><span class="sxs-lookup"><span data-stu-id="33ab2-128">The maximum number of times a reliable channel attempts to retransmit a message it has not received an acknowledgement for, by calling `Send` on its underlying channel.</span></span>  
  
### <a name="maxtransferwindowsize"></a><span data-ttu-id="33ab2-129">MaxTransferWindowSize</span><span class="sxs-lookup"><span data-stu-id="33ab2-129">MaxTransferWindowSize</span></span>  

 <span data-ttu-id="33ab2-130">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="33ab2-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="33ab2-131">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="33ab2-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="33ab2-132">可靠会话的最大传输窗口大小。</span><span class="sxs-lookup"><span data-stu-id="33ab2-132">The maximum transfer window size for the reliable session.</span></span>  
  
### <a name="ordered"></a><span data-ttu-id="33ab2-133">已订购</span><span class="sxs-lookup"><span data-stu-id="33ab2-133">Ordered</span></span>  

 <span data-ttu-id="33ab2-134">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="33ab2-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="33ab2-135">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="33ab2-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="33ab2-136">一个布尔值，指定是否保证消息以其发送顺序抵达。</span><span class="sxs-lookup"><span data-stu-id="33ab2-136">A Boolean value that specifies whether messages are guaranteed to arrive in the order they were sent.</span></span>  
  
### <a name="reliablemessagingversion"></a><span data-ttu-id="33ab2-137">ReliableMessagingVersion</span><span class="sxs-lookup"><span data-stu-id="33ab2-137">ReliableMessagingVersion</span></span>  

 <span data-ttu-id="33ab2-138">数据类型：Integer</span><span class="sxs-lookup"><span data-stu-id="33ab2-138">Data type: integer</span></span>  
  
 <span data-ttu-id="33ab2-139">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="33ab2-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="33ab2-140">一个整数，指定可靠会话中使用的 WS-ReliableMessaging 协议版本。</span><span class="sxs-lookup"><span data-stu-id="33ab2-140">An integer that specifies the WS-ReliableMessaging protocol version used in the reliable session.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33ab2-141">要求</span><span class="sxs-lookup"><span data-stu-id="33ab2-141">Requirements</span></span>  
  
|<span data-ttu-id="33ab2-142">MOF</span><span class="sxs-lookup"><span data-stu-id="33ab2-142">MOF</span></span>|<span data-ttu-id="33ab2-143">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="33ab2-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="33ab2-144">命名空间</span><span class="sxs-lookup"><span data-stu-id="33ab2-144">Namespace</span></span>|<span data-ttu-id="33ab2-145">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="33ab2-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="33ab2-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33ab2-146">See also</span></span>

- <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>
