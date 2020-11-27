---
title: ConnectionOrientedTransportBindingElement
ms.date: 03/30/2017
ms.assetid: c1308313-f0e2-49e6-977d-6b4ce9ad35d1
ms.openlocfilehash: 3c69b73cc05a56a7556630de0f83675590442293
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274148"
---
# <a name="connectionorientedtransportbindingelement"></a><span data-ttu-id="b0ecd-102">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="b0ecd-102">ConnectionOrientedTransportBindingElement</span></span>

<span data-ttu-id="b0ecd-103">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="b0ecd-103">ConnectionOrientedTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0ecd-104">语法</span><span class="sxs-lookup"><span data-stu-id="b0ecd-104">Syntax</span></span>  
  
```csharp
class ConnectionOrientedTransportBindingElement : TransportBindingElement  
{  
  datetime ChannelInitializationTimeout;  
  sint32 ConnectionBufferSize;  
  string HostNameComparisonMode;  
  sint32 MaxBufferSize;  
  datetime MaxOutputDelay;  
  sint32 MaxPendingAccepts;  
  sint32 MaxPendingConnections;  
  string TransferMode;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b0ecd-105">方法</span><span class="sxs-lookup"><span data-stu-id="b0ecd-105">Methods</span></span>  

 <span data-ttu-id="b0ecd-106">ConnectionOrientedTransportBindingElement 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="b0ecd-106">The ConnectionOrientedTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b0ecd-107">属性</span><span class="sxs-lookup"><span data-stu-id="b0ecd-107">Properties</span></span>  

 <span data-ttu-id="b0ecd-108">ConnectionOrientedTransportBindingElement 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="b0ecd-108">The ConnectionOrientedTransportBindingElement class has the following properties:</span></span>  
  
### <a name="channelinitializationtimeout"></a><span data-ttu-id="b0ecd-109">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="b0ecd-109">ChannelInitializationTimeout</span></span>  

 <span data-ttu-id="b0ecd-110">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="b0ecd-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="b0ecd-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b0ecd-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b0ecd-112">指定在超时前可用于完成通道初始化的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="b0ecd-112">The timespan that specifies how long the channel initialization has to complete before timing out.</span></span>  
  
### <a name="connectionbuffersize"></a><span data-ttu-id="b0ecd-113">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="b0ecd-113">ConnectionBufferSize</span></span>  

 <span data-ttu-id="b0ecd-114">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="b0ecd-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="b0ecd-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b0ecd-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b0ecd-116">用于从客户端或服务传输网络上的序列化消息块的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="b0ecd-116">The size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>  
  
### <a name="hostnamecomparisonmode"></a><span data-ttu-id="b0ecd-117">HostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="b0ecd-117">HostNameComparisonMode</span></span>  

 <span data-ttu-id="b0ecd-118">数据类型：字符串</span><span class="sxs-lookup"><span data-stu-id="b0ecd-118">Data type: string</span></span>  
  
 <span data-ttu-id="b0ecd-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b0ecd-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b0ecd-120">一个值，指示在对 URI 进行匹配时，是否使用主机名来访问服务。</span><span class="sxs-lookup"><span data-stu-id="b0ecd-120">A value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>  
  
### <a name="maxbuffersize"></a><span data-ttu-id="b0ecd-121">MaxBufferSize</span><span class="sxs-lookup"><span data-stu-id="b0ecd-121">MaxBufferSize</span></span>  

 <span data-ttu-id="b0ecd-122">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="b0ecd-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="b0ecd-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b0ecd-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b0ecd-124">要使用的缓冲区最大大小。</span><span class="sxs-lookup"><span data-stu-id="b0ecd-124">The maximum size of the buffer to use.</span></span>  
  
### <a name="maxoutputdelay"></a><span data-ttu-id="b0ecd-125">MaxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="b0ecd-125">MaxOutputDelay</span></span>  

 <span data-ttu-id="b0ecd-126">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="b0ecd-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="b0ecd-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b0ecd-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b0ecd-128">消息块或完整消息在发出之前可以在内存中保持缓冲的最大时间间隔。</span><span class="sxs-lookup"><span data-stu-id="b0ecd-128">The maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>  
  
### <a name="maxpendingaccepts"></a><span data-ttu-id="b0ecd-129">MaxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="b0ecd-129">MaxPendingAccepts</span></span>  

 <span data-ttu-id="b0ecd-130">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="b0ecd-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="b0ecd-131">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b0ecd-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b0ecd-132">可用于处理服务上的传入连接的最大挂起异步接受线程数。</span><span class="sxs-lookup"><span data-stu-id="b0ecd-132">The maximum number of pending asynchronous accept threads that are available for processing incoming connections on the service.</span></span>  
  
### <a name="maxpendingconnections"></a><span data-ttu-id="b0ecd-133">MaxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="b0ecd-133">MaxPendingConnections</span></span>  

 <span data-ttu-id="b0ecd-134">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="b0ecd-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="b0ecd-135">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b0ecd-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b0ecd-136">最大挂起连接数。</span><span class="sxs-lookup"><span data-stu-id="b0ecd-136">The maximum number of pending connections.</span></span>  
  
### <a name="transfermode"></a><span data-ttu-id="b0ecd-137">TransferMode</span><span class="sxs-lookup"><span data-stu-id="b0ecd-137">TransferMode</span></span>  

 <span data-ttu-id="b0ecd-138">数据类型：字符串</span><span class="sxs-lookup"><span data-stu-id="b0ecd-138">Data type: string</span></span>  
  
 <span data-ttu-id="b0ecd-139">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b0ecd-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b0ecd-140">一个值，指定通过面向连接的传输对消息进行缓冲还是流处理。</span><span class="sxs-lookup"><span data-stu-id="b0ecd-140">A value that specifies whether the messages are buffered or streamed with the connection-oriented transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0ecd-141">要求</span><span class="sxs-lookup"><span data-stu-id="b0ecd-141">Requirements</span></span>  
  
|<span data-ttu-id="b0ecd-142">MOF</span><span class="sxs-lookup"><span data-stu-id="b0ecd-142">MOF</span></span>|<span data-ttu-id="b0ecd-143">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="b0ecd-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b0ecd-144">命名空间</span><span class="sxs-lookup"><span data-stu-id="b0ecd-144">Namespace</span></span>|<span data-ttu-id="b0ecd-145">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="b0ecd-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b0ecd-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b0ecd-146">See also</span></span>

- <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>
