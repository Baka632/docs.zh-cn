---
title: 如何：实现动态分区
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to create a dynamic partitioner
ms.assetid: c875ad12-a161-43e6-ad1c-3d6927c536a7
ms.openlocfilehash: 1120d846743ac3b89d2d110b4d1abdd0083f9eab
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825736"
---
# <a name="how-to-implement-dynamic-partitions"></a><span data-ttu-id="35499-102">如何：实现动态分区</span><span class="sxs-lookup"><span data-stu-id="35499-102">How to: Implement Dynamic Partitions</span></span>

<span data-ttu-id="35499-103">下面的示例展示了如何实现自定义 <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType>，以实现动态分区，并可以通过特定重载 <xref:System.Threading.Tasks.Parallel.ForEach%2A> 和 PLINQ 进行使用。</span><span class="sxs-lookup"><span data-stu-id="35499-103">The following example shows how to implement a custom <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> that implements dynamic partitioning and can be used from certain overloads <xref:System.Threading.Tasks.Parallel.ForEach%2A> and from PLINQ.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35499-104">示例</span><span class="sxs-lookup"><span data-stu-id="35499-104">Example</span></span>

<span data-ttu-id="35499-105">每当分区对枚举器调用 <xref:System.Collections.IEnumerator.MoveNext%2A>，枚举器都会为此分区提供一个列表元素。</span><span class="sxs-lookup"><span data-stu-id="35499-105">Each time a partition calls <xref:System.Collections.IEnumerator.MoveNext%2A> on the enumerator, the enumerator provides the partition with one list element.</span></span> <span data-ttu-id="35499-106">如果是 PLINQ 和 <xref:System.Threading.Tasks.Parallel.ForEach%2A>，分区是 <xref:System.Threading.Tasks.Task> 实例。</span><span class="sxs-lookup"><span data-stu-id="35499-106">In the case of PLINQ and <xref:System.Threading.Tasks.Parallel.ForEach%2A>, the partition is a <xref:System.Threading.Tasks.Task> instance.</span></span> <span data-ttu-id="35499-107">由于请求在多个线程上并发，因此对当前索引的访问是同步的。</span><span class="sxs-lookup"><span data-stu-id="35499-107">Because requests are happening concurrently on multiple threads, access to the current index is synchronized.</span></span>  

[!code-csharp[TPL_Partitioners#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner02.cs#OrderableListPartitioner)]
[!code-vb[TPL_Partitioners#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/dynamicpartitioner.vb#04)]  

<span data-ttu-id="35499-108">例如，每个区块包含一个元素的区块分区。</span><span class="sxs-lookup"><span data-stu-id="35499-108">This is an example of chunk partitioning, with each chunk consisting of one element.</span></span> <span data-ttu-id="35499-109">通过一次提供更多元素，可以减少对锁的争用，并（从理论上说）实现更快的性能。</span><span class="sxs-lookup"><span data-stu-id="35499-109">By providing more elements at a time, you could reduce the contention over the lock and theoretically achieve faster performance.</span></span> <span data-ttu-id="35499-110">不过，在某个时间点，较大的区块可能需要额外的负载均衡逻辑，才能确保所有线程在全部工作完成前一直处于忙碌状态。</span><span class="sxs-lookup"><span data-stu-id="35499-110">However, at some point, larger chunks might require additional load-balancing logic in order to keep all threads busy until all the work is done.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35499-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="35499-111">See also</span></span>

* [<span data-ttu-id="35499-112">PLINQ 和 TPL 的自定义分区程序</span><span class="sxs-lookup"><span data-stu-id="35499-112">Custom Partitioners for PLINQ and TPL</span></span>](custom-partitioners-for-plinq-and-tpl.md)
* [<span data-ttu-id="35499-113">如何：实现静态分区程序</span><span class="sxs-lookup"><span data-stu-id="35499-113">How to: Implement a Partitioner for Static Partitioning</span></span>](how-to-implement-a-partitioner-for-static-partitioning.md)
