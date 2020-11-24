---
title: 使用 ConcurrentBag 创建目标池
ms.date: 05/01/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- object pool, in .NET Framework
ms.assetid: 0480e7ff-b6f9-480e-a889-2ed4264d8372
ms.openlocfilehash: c593c9b2011814c49563939f1094b62cd252879c
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "94822901"
---
# <a name="create-an-object-pool-by-using-a-concurrentbag"></a><span data-ttu-id="f7bce-102">使用 ConcurrentBag 创建目标池</span><span class="sxs-lookup"><span data-stu-id="f7bce-102">Create an object pool by using a ConcurrentBag</span></span>

<span data-ttu-id="f7bce-103">本示例演示如何使用 <xref:System.Collections.Concurrent.ConcurrentBag%601> 来实现对象池。</span><span class="sxs-lookup"><span data-stu-id="f7bce-103">This example shows how to use a <xref:System.Collections.Concurrent.ConcurrentBag%601> to implement an object pool.</span></span> <span data-ttu-id="f7bce-104">在需要某个类的多个实例并且创建或销毁该类的成本很高的情况下，对象池可以改进应用程序性能。</span><span class="sxs-lookup"><span data-stu-id="f7bce-104">Object pools can improve application performance in situations where you require multiple instances of a class and the class is expensive to create or destroy.</span></span> <span data-ttu-id="f7bce-105">客户端程序请求新对象时，对象池先尝试提供一个已创建并返回到该池的对象。</span><span class="sxs-lookup"><span data-stu-id="f7bce-105">When a client program requests a new object, the object pool first attempts to provide one that has already been created and returned to the pool.</span></span> <span data-ttu-id="f7bce-106">仅在没有可用对象时，才会创建一个新对象。</span><span class="sxs-lookup"><span data-stu-id="f7bce-106">If none is available, only then is a new object created.</span></span>

<span data-ttu-id="f7bce-107"><xref:System.Collections.Concurrent.ConcurrentBag%601> 用于存储对象，因为它支持快速插入和删除，特别是在同一线程既添加又删除项时。</span><span class="sxs-lookup"><span data-stu-id="f7bce-107">The <xref:System.Collections.Concurrent.ConcurrentBag%601> is used to store the objects because it supports fast insertion and removal, especially when the same thread is both adding and removing items.</span></span> <span data-ttu-id="f7bce-108">本示例可进一步扩充为以包数据结构实现的 <xref:System.Collections.Concurrent.IProducerConsumerCollection%601> 为依据生成，就像 <xref:System.Collections.Concurrent.ConcurrentQueue%601> 和 <xref:System.Collections.Concurrent.ConcurrentStack%601> 一样。</span><span class="sxs-lookup"><span data-stu-id="f7bce-108">This example could be further augmented to be built around a <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>, which the bag data structure implements, as do <xref:System.Collections.Concurrent.ConcurrentQueue%601> and <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span></span>

> [!TIP]
> <span data-ttu-id="f7bce-109">本文定义了如何使用底层并发类型编写你自己的对象池实现以存储要重用的对象。</span><span class="sxs-lookup"><span data-stu-id="f7bce-109">This article defines how to write your own implementation of an object pool with an underlying concurrent type to store objects for reuse.</span></span> <span data-ttu-id="f7bce-110">但是，<xref:Microsoft.Extensions.ObjectPool?displayProperty=fullName> 命名空间下已存在 <xref:Microsoft.Extensions.ObjectPool.ObjectPool%601?displayProperty=nameWithType> 类型。</span><span class="sxs-lookup"><span data-stu-id="f7bce-110">However, the <xref:Microsoft.Extensions.ObjectPool.ObjectPool%601?displayProperty=nameWithType> type already exists under the <xref:Microsoft.Extensions.ObjectPool?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="f7bce-111">在创建你自己的实现前，考虑使用可用类型，其中包括许多其他功能。</span><span class="sxs-lookup"><span data-stu-id="f7bce-111">Consider using the available type before creating your own implementation, which includes many additional features.</span></span>

## <a name="example"></a><span data-ttu-id="f7bce-112">示例</span><span class="sxs-lookup"><span data-stu-id="f7bce-112">Example</span></span>

[!code-csharp[CDS#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/objectpool.cs#04)]
[!code-vb[CDS#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/objectpool04.vb#04)]

## <a name="see-also"></a><span data-ttu-id="f7bce-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7bce-113">See also</span></span>

- [<span data-ttu-id="f7bce-114">线程安全集合</span><span class="sxs-lookup"><span data-stu-id="f7bce-114">Thread-Safe Collections</span></span>](index.md)
