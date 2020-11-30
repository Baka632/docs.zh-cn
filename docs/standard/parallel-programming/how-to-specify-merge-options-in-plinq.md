---
title: 如何：在 PLINQ 中指定合并选项
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to use merge options
ms.assetid: 0f33b527-e91a-4550-a39a-e63e396fd831
ms.openlocfilehash: 7c7979dc828f89435422b464b22710b3a052911b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722422"
---
# <a name="how-to-specify-merge-options-in-plinq"></a><span data-ttu-id="3d01a-102">如何：在 PLINQ 中指定合并选项</span><span class="sxs-lookup"><span data-stu-id="3d01a-102">How to: Specify Merge Options in PLINQ</span></span>

<span data-ttu-id="3d01a-103">此示例展示了如何指定应用于 PLINQ 查询中所有后续运算符的合并选项。</span><span class="sxs-lookup"><span data-stu-id="3d01a-103">This example shows how to specify the merge options that will apply to all subsequent operators in a PLINQ query.</span></span> <span data-ttu-id="3d01a-104">虽然无需显式设置合并选项，但这样做可以提升性能。</span><span class="sxs-lookup"><span data-stu-id="3d01a-104">You do not have to set merge options explicitly, but doing so may improve performance.</span></span> <span data-ttu-id="3d01a-105">若要详细了解合并选项，请参阅 [PLINQ 中的合并选项](merge-options-in-plinq.md)。</span><span class="sxs-lookup"><span data-stu-id="3d01a-105">For more information about merge options, see [Merge Options in PLINQ](merge-options-in-plinq.md).</span></span>  
  
> [!WARNING]
> <span data-ttu-id="3d01a-106">本示例旨在演示用法，运行速度可能不如等效的顺序 LINQ to Objects 查询快。</span><span class="sxs-lookup"><span data-stu-id="3d01a-106">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="3d01a-107">若要详细了解加速，请参阅[了解 PLINQ 中的加速](understanding-speedup-in-plinq.md)。</span><span class="sxs-lookup"><span data-stu-id="3d01a-107">For more information about speedup, see [Understanding Speedup in PLINQ](understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d01a-108">示例</span><span class="sxs-lookup"><span data-stu-id="3d01a-108">Example</span></span>  

 <span data-ttu-id="3d01a-109">下面的示例展示了合并选项在基本方案中的行为，此方案包含无序源，并将高成本函数应用于每个元素。</span><span class="sxs-lookup"><span data-stu-id="3d01a-109">The following example demonstrates the behavior of merge options in a basic scenario that has an unordered source and applies an expensive function to every element.</span></span>  
  
 [!code-csharp[PLINQ#23](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#23)]
 [!code-vb[PLINQ#23](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#23)]  
  
 <span data-ttu-id="3d01a-110">如果 <xref:System.Linq.ParallelMergeOptions.AutoBuffered> 选项在第一个元素生成前导致不利延迟发生，请尝试使用 <xref:System.Linq.ParallelMergeOptions.NotBuffered> 选项，更快更顺畅地生成结果元素。</span><span class="sxs-lookup"><span data-stu-id="3d01a-110">In cases where the <xref:System.Linq.ParallelMergeOptions.AutoBuffered> option incurs an undesirable latency before the first element is yielded, try the <xref:System.Linq.ParallelMergeOptions.NotBuffered> option to yield result elements faster and more smoothly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d01a-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3d01a-111">See also</span></span>

- <xref:System.Linq.ParallelMergeOptions>
- [<span data-ttu-id="3d01a-112">并行 LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="3d01a-112">Parallel LINQ (PLINQ)</span></span>](introduction-to-plinq.md)
