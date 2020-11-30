---
title: 如何：取消 PLINQ 查询
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to cancel
- cancellation, PLINQ
ms.assetid: 80b14640-edfa-4153-be1b-3e003d3e9c1a
ms.openlocfilehash: f8ca723ca3b9b9428c95651ebe2fa7d92e48ebbb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713283"
---
# <a name="how-to-cancel-a-plinq-query"></a><span data-ttu-id="ce035-102">如何：取消 PLINQ 查询</span><span class="sxs-lookup"><span data-stu-id="ce035-102">How to: Cancel a PLINQ Query</span></span>

<span data-ttu-id="ce035-103">下面的示例展示了取消 PLINQ 查询的两种方法。</span><span class="sxs-lookup"><span data-stu-id="ce035-103">The following examples show two ways to cancel a PLINQ query.</span></span> <span data-ttu-id="ce035-104">第一个示例展示了如何取消主要由数据遍历组成的查询。</span><span class="sxs-lookup"><span data-stu-id="ce035-104">The first example shows how to cancel a query that consists mostly of data traversal.</span></span> <span data-ttu-id="ce035-105">第二个示例展示了如何取消包含计算成本很高的用户函数的查询。</span><span class="sxs-lookup"><span data-stu-id="ce035-105">The second example shows how to cancel a query that contains a user function that is computationally expensive.</span></span>

> [!NOTE]
> <span data-ttu-id="ce035-106">选中“仅我的代码”后，Visual Studio 会在抛出异常的代码行处中断，并显示错误消息“用户代码未处理异常”。</span><span class="sxs-lookup"><span data-stu-id="ce035-106">When "Just My Code" is enabled, Visual Studio will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="ce035-107">此错误是良性的。</span><span class="sxs-lookup"><span data-stu-id="ce035-107">This error is benign.</span></span> <span data-ttu-id="ce035-108">可以按 F5 继续运行，并请参阅下面示例中所示的异常处理行为。</span><span class="sxs-lookup"><span data-stu-id="ce035-108">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="ce035-109">为了阻止 Visual Studio 在第一个错误出现时中断，只需依次转到“工具”、“选项”、“调试”、“常规”  下，取消选中“仅我的代码”复选框即可。</span><span class="sxs-lookup"><span data-stu-id="ce035-109">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>
>
> <span data-ttu-id="ce035-110">本示例旨在演示用法，运行速度可能不如等效的顺序 LINQ to Objects 查询快。</span><span class="sxs-lookup"><span data-stu-id="ce035-110">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="ce035-111">若要详细了解加速，请参阅[了解 PLINQ 中的加速](understanding-speedup-in-plinq.md)。</span><span class="sxs-lookup"><span data-stu-id="ce035-111">For more information about speedup, see [Understanding Speedup in PLINQ](understanding-speedup-in-plinq.md).</span></span>

## <a name="example"></a><span data-ttu-id="ce035-112">示例</span><span class="sxs-lookup"><span data-stu-id="ce035-112">Example</span></span>

[!code-csharp[PLINQ#16](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#16)]
[!code-vb[PLINQ#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#16)]

<span data-ttu-id="ce035-113">PLINQ 框架不会将一个 <xref:System.OperationCanceledException> 滚动到 <xref:System.AggregateException?displayProperty=nameWithType> 中；必须在单独的 catch 块中处理 <xref:System.OperationCanceledException>。</span><span class="sxs-lookup"><span data-stu-id="ce035-113">The PLINQ framework does not roll a single <xref:System.OperationCanceledException> into an <xref:System.AggregateException?displayProperty=nameWithType>; the <xref:System.OperationCanceledException> must be handled in a separate catch block.</span></span> <span data-ttu-id="ce035-114">如果一个或多个用户委托抛出 OperationCanceledException(externalCT)（通过使用外部 <xref:System.Threading.CancellationToken?displayProperty=nameWithType>），但没有其他任何异常，且查询被定义为 `AsParallel().WithCancellation(externalCT)`，那么 PLINQ 会抛出 <xref:System.OperationCanceledException> (externalCT)，而不是 <xref:System.AggregateException?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="ce035-114">If one or more user delegates throws an OperationCanceledException(externalCT) (by using an external <xref:System.Threading.CancellationToken?displayProperty=nameWithType>) but no other exception, and the query was defined as `AsParallel().WithCancellation(externalCT)`, then PLINQ will issue a single <xref:System.OperationCanceledException> (externalCT) rather than an <xref:System.AggregateException?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ce035-115">不过，如果一个用户委托抛出 <xref:System.OperationCanceledException>，另一个委托抛出另一种类型的异常，那么这两个异常都会滚动到 <xref:System.AggregateException> 中。</span><span class="sxs-lookup"><span data-stu-id="ce035-115">However, if one user delegate throws an <xref:System.OperationCanceledException>, and another delegate throws another exception type, then both exceptions will be rolled into an <xref:System.AggregateException>.</span></span>

<span data-ttu-id="ce035-116">关于取消的一般性指南如下：</span><span class="sxs-lookup"><span data-stu-id="ce035-116">The general guidance on cancellation is as follows:</span></span>

1. <span data-ttu-id="ce035-117">如果执行用户委托取消，应将外部 <xref:System.Threading.CancellationToken> 告知给 PLINQ，并引发 <xref:System.OperationCanceledException>(externalCT)。</span><span class="sxs-lookup"><span data-stu-id="ce035-117">If you perform user-delegate cancellation, you should inform PLINQ about the external <xref:System.Threading.CancellationToken> and throw an <xref:System.OperationCanceledException>(externalCT).</span></span>

2. <span data-ttu-id="ce035-118">如果发生取消且没有引发其他任何异常，则处理 <xref:System.OperationCanceledException>，而不是 <xref:System.AggregateException>。</span><span class="sxs-lookup"><span data-stu-id="ce035-118">If cancellation occurs and no other exceptions are thrown, then handle an <xref:System.OperationCanceledException> rather than an <xref:System.AggregateException>.</span></span>

## <a name="example"></a><span data-ttu-id="ce035-119">示例</span><span class="sxs-lookup"><span data-stu-id="ce035-119">Example</span></span>

<span data-ttu-id="ce035-120">下面的示例展示了如何在用户代码中使用计算成本高的函数时处理取消。</span><span class="sxs-lookup"><span data-stu-id="ce035-120">The following example shows how to handle cancellation when you have a computationally expensive function in user code.</span></span>

[!code-csharp[PLINQ#17](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#17)]
[!code-vb[PLINQ#17](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#17)]

<span data-ttu-id="ce035-121">在用户代码中处理取消时，无需在查询定义中使用 <xref:System.Linq.ParallelEnumerable.WithCancellation%2A>。</span><span class="sxs-lookup"><span data-stu-id="ce035-121">When you handle the cancellation in user code, you do not have to use <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> in the query definition.</span></span> <span data-ttu-id="ce035-122">不过，之所以建议使用 <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> 是因为，<xref:System.Linq.ParallelEnumerable.WithCancellation%2A> 对查询性能没有影响，并让取消由查询运算符和用户代码进行处理。</span><span class="sxs-lookup"><span data-stu-id="ce035-122">However, we recommended that you do use <xref:System.Linq.ParallelEnumerable.WithCancellation%2A>, because <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> has no effect on query performance and it enables the cancellation to be handled by query operators and your user code.</span></span>

<span data-ttu-id="ce035-123">为了确保系统响应速度，建议每毫秒检查一次取消；不过，只要不超过每 10 毫秒一次，任何频率都认为是可接受的。</span><span class="sxs-lookup"><span data-stu-id="ce035-123">In order to ensure system responsiveness, we recommend that you check for cancellation around once per millisecond; however, any period up to 10 milliseconds is considered acceptable.</span></span> <span data-ttu-id="ce035-124">此频率不得对代码性能产生不利影响。</span><span class="sxs-lookup"><span data-stu-id="ce035-124">This frequency should not have a negative impact on your code's performance.</span></span>

<span data-ttu-id="ce035-125">如果枚举器已遭清理（例如，当代码跳出循环访问查询结果的 foreach（Visual Basic 中的 For Each）循环时），查询就会被取消，但不会引发异常。</span><span class="sxs-lookup"><span data-stu-id="ce035-125">When an enumerator is disposed, for example when code breaks out of a foreach (For Each in Visual Basic) loop that is iterating over query results, then the query is canceled, but no exception is thrown.</span></span>

## <a name="see-also"></a><span data-ttu-id="ce035-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="ce035-126">See also</span></span>

- <xref:System.Linq.ParallelEnumerable>
- [<span data-ttu-id="ce035-127">并行 LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="ce035-127">Parallel LINQ (PLINQ)</span></span>](introduction-to-plinq.md)
- [<span data-ttu-id="ce035-128">托管线程中的取消</span><span class="sxs-lookup"><span data-stu-id="ce035-128">Cancellation in Managed Threads</span></span>](../threading/cancellation-in-managed-threads.md)
