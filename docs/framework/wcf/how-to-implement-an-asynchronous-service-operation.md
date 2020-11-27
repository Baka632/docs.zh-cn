---
title: 如何：实现异步服务操作
description: 了解 WFC 中异步服务操作的结构。 服务操作可以异步或同步方式实现。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4e5d2ea5-d8f8-4712-bd18-ea3c5461702c
ms.openlocfilehash: 157311f29b203e0c26be21a89d2d5b560543094b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267827"
---
# <a name="how-to-implement-an-asynchronous-service-operation"></a><span data-ttu-id="206df-104">如何：实现异步服务操作</span><span class="sxs-lookup"><span data-stu-id="206df-104">How to: Implement an Asynchronous Service Operation</span></span>

<span data-ttu-id="206df-105">在 Windows Communication Foundation (WCF) 应用程序中，可以异步或同步实现服务操作，而无需向客户端进行调用。</span><span class="sxs-lookup"><span data-stu-id="206df-105">In Windows Communication Foundation (WCF) applications, a service operation can be implemented asynchronously or synchronously without dictating to the client how to call it.</span></span> <span data-ttu-id="206df-106">例如，可以同步调用异步服务操作，并且可以异步调用同步服务操作。</span><span class="sxs-lookup"><span data-stu-id="206df-106">For example, asynchronous service operations can be called synchronously, and synchronous service operations can be called asynchronously.</span></span> <span data-ttu-id="206df-107">有关演示如何在客户端应用程序中异步调用操作的示例，请参阅 [如何：异步调用服务操作](./feature-details/how-to-call-wcf-service-operations-asynchronously.md)。</span><span class="sxs-lookup"><span data-stu-id="206df-107">For an example that shows how to call an operation asynchronously in a client application, see [How to: Call Service Operations Asynchronously](./feature-details/how-to-call-wcf-service-operations-asynchronously.md).</span></span> <span data-ttu-id="206df-108">有关同步和异步操作的详细信息，请参阅 [设计服务协定](designing-service-contracts.md) 和 [同步和异步操作](synchronous-and-asynchronous-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="206df-108">For more information about synchronous and asynchronous operations, see [Designing Service Contracts](designing-service-contracts.md) and [Synchronous and Asynchronous Operations](synchronous-and-asynchronous-operations.md).</span></span> <span data-ttu-id="206df-109">本主题介绍异步服务操作的基本结构，代码并不完整。</span><span class="sxs-lookup"><span data-stu-id="206df-109">This topic describes the basic structure of an asynchronous service operation, the code is not complete.</span></span> <span data-ttu-id="206df-110">有关服务和客户端的完整示例，请参阅 [异步](/previous-versions/dotnet/netframework-4.0/ms751505(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="206df-110">For a complete example of both the service and client sides, see [Asynchronous](/previous-versions/dotnet/netframework-4.0/ms751505(v=vs.100)).</span></span>  
  
### <a name="implement-a-service-operation-asynchronously"></a><span data-ttu-id="206df-111">按异步方式实现服务操作</span><span class="sxs-lookup"><span data-stu-id="206df-111">Implement a service operation asynchronously</span></span>  
  
1. <span data-ttu-id="206df-112">在服务协定中，按照 .NET 异步设计准则声明一个异步方法对。</span><span class="sxs-lookup"><span data-stu-id="206df-112">In your service contract, declare an asynchronous method pair according to the .NET asynchronous design guidelines.</span></span> <span data-ttu-id="206df-113">`Begin` 方法采用一个参数、一个回调对象和一个状态对象作为参数，并且返回一个 <xref:System.IAsyncResult?displayProperty=nameWithType> 和一个匹配的 `End` 方法，该方法采用一个 <xref:System.IAsyncResult?displayProperty=nameWithType> 作为参数并将返回值返回。</span><span class="sxs-lookup"><span data-stu-id="206df-113">The `Begin` method takes a parameter, a callback object, and a state object, and returns a <xref:System.IAsyncResult?displayProperty=nameWithType> and a matching `End` method that takes a <xref:System.IAsyncResult?displayProperty=nameWithType> and returns the return value.</span></span> <span data-ttu-id="206df-114">有关异步调用的详细信息，请参阅 [异步编程设计模式](../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)。</span><span class="sxs-lookup"><span data-stu-id="206df-114">For more information about asynchronous calls, see [Asynchronous Programming Design Patterns](../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).</span></span>  
  
2. <span data-ttu-id="206df-115">使用 `Begin` 属性 (attribute) 标记该异步方法对的 <xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType> 方法，并将 <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A?displayProperty=nameWithType> 属性 (property) 设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="206df-115">Mark the `Begin` method of the asynchronous method pair with the <xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType> attribute and set the <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="206df-116">例如，下面的代码执行步骤 1 和 2。</span><span class="sxs-lookup"><span data-stu-id="206df-116">For example, the following code performs steps 1 and 2.</span></span>  
  
     [!code-csharp[C_SyncAsyncClient#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#6)]
     [!code-vb[C_SyncAsyncClient#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#6)]  
  
3. <span data-ttu-id="206df-117">按照异步设计准则在服务类中实现 `Begin/End` 方法对。</span><span class="sxs-lookup"><span data-stu-id="206df-117">Implement the `Begin/End` method pair in your service class according to the asynchronous design guidelines.</span></span> <span data-ttu-id="206df-118">例如，下面的代码示例演示一个实现，在此实现中，异步服务操作的 `Begin` 和 `End` 部分都向控制台写入一个字符串，并且将 `End` 操作的返回值返回到客户端。</span><span class="sxs-lookup"><span data-stu-id="206df-118">For example, the following code example shows an implementation in which a string is written to the console in both the `Begin` and `End` portions of the asynchronous service operation, and the return value of the `End` operation is returned to the client.</span></span> <span data-ttu-id="206df-119">有关完整的代码示例，请参见“示例”部分。</span><span class="sxs-lookup"><span data-stu-id="206df-119">For the complete code example, see the Example section.</span></span>  
  
     [!code-csharp[C_SyncAsyncClient#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#3)]
     [!code-vb[C_SyncAsyncClient#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="206df-120">示例</span><span class="sxs-lookup"><span data-stu-id="206df-120">Example</span></span>  

 <span data-ttu-id="206df-121">下面的代码示例演示以下各项：</span><span class="sxs-lookup"><span data-stu-id="206df-121">The following code examples show:</span></span>  
  
1. <span data-ttu-id="206df-122">与下列各项之间的服务协定接口：</span><span class="sxs-lookup"><span data-stu-id="206df-122">A service contract interface with:</span></span>  
  
    1. <span data-ttu-id="206df-123">同步 `SampleMethod` 操作。</span><span class="sxs-lookup"><span data-stu-id="206df-123">A synchronous `SampleMethod` operation.</span></span>  
  
    2. <span data-ttu-id="206df-124">异步 `BeginSampleMethod` 操作。</span><span class="sxs-lookup"><span data-stu-id="206df-124">An asynchronous `BeginSampleMethod` operation.</span></span>  
  
    3. <span data-ttu-id="206df-125">异步 `BeginServiceAsyncMethod` / `EndServiceAsyncMethod` 操作对。</span><span class="sxs-lookup"><span data-stu-id="206df-125">An asynchronous `BeginServiceAsyncMethod`/`EndServiceAsyncMethod` operation pair.</span></span>  
  
2. <span data-ttu-id="206df-126">使用 <xref:System.IAsyncResult?displayProperty=nameWithType> 对象的服务实现。</span><span class="sxs-lookup"><span data-stu-id="206df-126">A service implementation using a <xref:System.IAsyncResult?displayProperty=nameWithType> object.</span></span>  
  
 [!code-csharp[C_SyncAsyncClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#1)]
 [!code-vb[C_SyncAsyncClient#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="206df-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="206df-127">See also</span></span>

- [<span data-ttu-id="206df-128">设计服务协定</span><span class="sxs-lookup"><span data-stu-id="206df-128">Designing Service Contracts</span></span>](designing-service-contracts.md)
- [<span data-ttu-id="206df-129">同步和异步操作</span><span class="sxs-lookup"><span data-stu-id="206df-129">Synchronous and Asynchronous Operations</span></span>](synchronous-and-asynchronous-operations.md)
