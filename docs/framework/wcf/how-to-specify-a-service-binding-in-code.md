---
title: 如何：在代码中指定服务绑定
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 67ab5dd8-79c1-4e62-aa75-828ea918a53a
ms.openlocfilehash: 7cf54754661182dca1e91c75b158d9b0a34a1f5e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236476"
---
# <a name="how-to-specify-a-service-binding-in-code"></a><span data-ttu-id="5d27e-102">如何：在代码中指定服务绑定</span><span class="sxs-lookup"><span data-stu-id="5d27e-102">How to: Specify a Service Binding in Code</span></span>

<span data-ttu-id="5d27e-103">在本示例中，将为计算器服务定义一个 `ICalculator` 协定，在 `CalculatorService` 类中实现该服务，然后在代码中定义其终结点（在这段代码中还指定该服务必须使用 <xref:System.ServiceModel.BasicHttpBinding> 类）。</span><span class="sxs-lookup"><span data-stu-id="5d27e-103">In this example, an `ICalculator` contract is defined for a calculator service, the service is implemented in the `CalculatorService` class, and then its endpoint is defined in code, where it is specified that the service must use the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span>  
  
 <span data-ttu-id="5d27e-104">通常，最佳做法是以声明方式在配置中指定绑定和地址信息，而不是在代码中强制指定。</span><span class="sxs-lookup"><span data-stu-id="5d27e-104">It is usually the best practice to specify the binding and address information declaratively in configuration rather than imperatively in code.</span></span> <span data-ttu-id="5d27e-105">在代码中定义终结点通常是不可行的，因为已部署服务的绑定和地址通常与在部署服务时所用的绑定和地址不同。</span><span class="sxs-lookup"><span data-stu-id="5d27e-105">Defining endpoints in code is usually not practical because the bindings and addresses for a deployed service are typically different from those used while the service is being developed.</span></span> <span data-ttu-id="5d27e-106">一般说来，通过将绑定和寻址信息放置在代码之外，无需重新编译或重新部署应用程序即可更改这些信息。</span><span class="sxs-lookup"><span data-stu-id="5d27e-106">More generally, keeping the binding and addressing information out of the code allows them to change without having to recompile or redeploy the application.</span></span>  
  
 <span data-ttu-id="5d27e-107">有关如何使用配置元素而不是代码来配置此服务的说明，请参阅 [如何：在配置中指定服务绑定](how-to-specify-a-service-binding-in-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="5d27e-107">For a description of how to configure this service using configuration elements instead of code, see [How to: Specify a Service Binding in Configuration](how-to-specify-a-service-binding-in-configuration.md).</span></span>  
  
### <a name="to-specify-in-code-to-use-the-basichttpbinding-for-the-service"></a><span data-ttu-id="5d27e-108">在代码中指定将 BasicHttpBinding 用于服务</span><span class="sxs-lookup"><span data-stu-id="5d27e-108">To specify in code to use the BasicHttpBinding for the service</span></span>  
  
1. <span data-ttu-id="5d27e-109">为该类型的服务定义服务协定。</span><span class="sxs-lookup"><span data-stu-id="5d27e-109">Define a service contract for the type of service.</span></span>  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#1)]
     [!code-vb[C_HowTo_CodeServiceBinding#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#1)]  
  
2. <span data-ttu-id="5d27e-110">在服务类中实现该服务协定。</span><span class="sxs-lookup"><span data-stu-id="5d27e-110">Implement the service contract in a service class.</span></span>  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#2)]
     [!code-vb[C_HowTo_CodeServiceBinding#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#2)]  
  
3. <span data-ttu-id="5d27e-111">在主机应用程序中，创建该服务的基址以及要用于该服务的绑定。</span><span class="sxs-lookup"><span data-stu-id="5d27e-111">In the hosting application, create the base address for the service and the binding to use with the service.</span></span>  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#3)]
     [!code-vb[C_HowTo_CodeServiceBinding#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#3)]  
  
4. <span data-ttu-id="5d27e-112">创建该服务的宿主，添加终结点，然后打开该宿主。</span><span class="sxs-lookup"><span data-stu-id="5d27e-112">Create the host for the service, add the endpoint, and then open the host.</span></span>  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#4)]
     [!code-vb[C_HowTo_CodeServiceBinding#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#4)]  
  
### <a name="to-modify-the-default-values-of-the-binding-properties"></a><span data-ttu-id="5d27e-113">修改绑定属性的默认值</span><span class="sxs-lookup"><span data-stu-id="5d27e-113">To modify the default values of the binding properties</span></span>  
  
1. <span data-ttu-id="5d27e-114">若要修改 <xref:System.ServiceModel.BasicHttpBinding> 类的默认属性值之一，请在创建宿主之前将绑定上的该属性值设置为新值。</span><span class="sxs-lookup"><span data-stu-id="5d27e-114">To modify one of the default property values of the <xref:System.ServiceModel.BasicHttpBinding> class, set the property value on the binding to the new value before creating the host.</span></span> <span data-ttu-id="5d27e-115">例如，若要将默认打开和关闭超时值从 1 分钟更改为 2 分钟，请使用下面的代码。</span><span class="sxs-lookup"><span data-stu-id="5d27e-115">For example, to change the default open and close timeout values of 1 minute to 2 minutes, use the following.</span></span>  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#5)]
     [!code-vb[C_HowTo_CodeServiceBinding#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="5d27e-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5d27e-116">See also</span></span>

- [<span data-ttu-id="5d27e-117">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="5d27e-117">Using Bindings to Configure Services and Clients</span></span>](using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="5d27e-118">指定终结点地址</span><span class="sxs-lookup"><span data-stu-id="5d27e-118">Specifying an Endpoint Address</span></span>](specifying-an-endpoint-address.md)
