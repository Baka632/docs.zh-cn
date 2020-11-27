---
title: 定义和指定错误
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- handling faults [WCF], specifying
- handling faults [WCF], defining
ms.assetid: c00c84f1-962d-46a7-b07f-ebc4f80fbfc1
ms.openlocfilehash: 67096c4531d13bc66f584c09c458c0a5a2a41c6b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96260898"
---
# <a name="defining-and-specifying-faults"></a><span data-ttu-id="d8c9e-102">定义和指定错误</span><span class="sxs-lookup"><span data-stu-id="d8c9e-102">Defining and Specifying Faults</span></span>

<span data-ttu-id="d8c9e-103">SOAP 错误可将错误情况信息从服务传达到客户端，在双工情况下，还可以以互操作方式从客户端传达到服务。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-103">SOAP faults convey error condition information from a service to a client and, in the duplex case, from a client to a service in an interoperable way.</span></span> <span data-ttu-id="d8c9e-104">此主题讨论何时并且如何自定义错误内容并指定可以返回错误的操作。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-104">This topic discusses when and how to define custom fault content and specify which operations can return them.</span></span> <span data-ttu-id="d8c9e-105">有关服务或双工客户端如何发送这些错误以及客户端或服务应用程序如何处理这些错误的详细信息，请参阅 [发送和接收错误](sending-and-receiving-faults.md)。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-105">For more information about how a service, or duplex client, can send those faults and how a client or service application handles these faults, see [Sending and Receiving Faults](sending-and-receiving-faults.md).</span></span> <span data-ttu-id="d8c9e-106">有关 Windows Communication Foundation (WCF) 应用程序中的错误处理的概述，请参阅在 [协定和服务中指定和处理](specifying-and-handling-faults-in-contracts-and-services.md)错误。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-106">For an overview of error handling in Windows Communication Foundation (WCF) applications, see [Specifying and Handling Faults in Contracts and Services](specifying-and-handling-faults-in-contracts-and-services.md).</span></span>  
  
## <a name="overview"></a><span data-ttu-id="d8c9e-107">概述</span><span class="sxs-lookup"><span data-stu-id="d8c9e-107">Overview</span></span>  

 <span data-ttu-id="d8c9e-108">声明的 SOAP 错误是指其中的某个操作具有 <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType> 的错误，该属性指定自定义 SOAP 错误类型。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-108">Declared SOAP faults are those in which an operation has a <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType> that specifies a custom SOAP fault type.</span></span> <span data-ttu-id="d8c9e-109">未声明的 SOAP 错误是指那些未在相应操作的协定中指定的错误。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-109">Undeclared SOAP faults are those that are not specified in the contract for an operation.</span></span> <span data-ttu-id="d8c9e-110">本主题帮助您识别这些错误情况并为您的服务创建一个错误协定，当收到自定义 SOAP 错误时，客户端可以用它正确地处理这些错误情况。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-110">This topic helps you identify those error conditions and create a fault contract for your service that clients can use to properly handle those error conditions when notified by custom SOAP faults.</span></span> <span data-ttu-id="d8c9e-111">基本任务依次为：</span><span class="sxs-lookup"><span data-stu-id="d8c9e-111">The basic tasks are, in order:</span></span>  
  
1. <span data-ttu-id="d8c9e-112">定义服务的客户端应该知道的错误情况。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-112">Define the error conditions that a client of your service should know about.</span></span>  
  
2. <span data-ttu-id="d8c9e-113">为这些错误情况定义 SOAP 错误的自定义内容。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-113">Define the custom content of the SOAP faults for those error conditions.</span></span>  
  
3. <span data-ttu-id="d8c9e-114">标记您的操作，以便以 WSDL 向客户端公开这些操作引发的特定 SOAP 错误。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-114">Mark your operations so that the specific SOAP faults that they throw are exposed to clients in WSDL.</span></span>  
  
### <a name="defining-error-conditions-that-clients-should-know-about"></a><span data-ttu-id="d8c9e-115">定义客户端应该知道的错误情况</span><span class="sxs-lookup"><span data-stu-id="d8c9e-115">Defining Error Conditions That Clients Should Know About</span></span>  

 <span data-ttu-id="d8c9e-116">SOAP 错误是公开描述的、传达特定操作的错误信息的消息。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-116">SOAP faults are publicly described messages that carry fault information for a particular operation.</span></span> <span data-ttu-id="d8c9e-117">由于它们是同其他操作消息一起以 WSDL 描述的，因此客户端应该知道它们且希望在调用某个操作时处理这样的错误。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-117">Because they are described along with other operation messages in WSDL, clients know and, therefore, expect to handle such faults when invoking an operation.</span></span> <span data-ttu-id="d8c9e-118">但是，因为 WCF 服务是用托管代码编写的，所以，决定将托管代码中的哪些错误条件转换为错误并返回给客户端，这样就可以将服务中的错误情况和 bug 与客户端的正式错误会话隔开。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-118">But because WCF services are written in managed code, deciding which error conditions in managed code are to be converted into faults and returned to the client provides you the opportunity to separate error conditions and bugs in your service from the formal error conversation you have with a client.</span></span>  
  
 <span data-ttu-id="d8c9e-119">例如，下面的代码示例演示一个采用两个整数并返回另一个整数的操作。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-119">For example, the following code example shows an operation that takes two integers and returns another integer.</span></span> <span data-ttu-id="d8c9e-120">这里可引发若干个异常，因此设计错误协定时，必须确定哪些是客户端最重要的错误情况。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-120">Several exceptions can be thrown here, so when designing the fault contract, you must determine which error conditions are important for your client.</span></span> <span data-ttu-id="d8c9e-121">在这种情况下，服务应该删除 <xref:System.DivideByZeroException?displayProperty=nameWithType> 异常。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-121">In this case, the service should detect the <xref:System.DivideByZeroException?displayProperty=nameWithType> exception.</span></span>  
  
```csharp  
[ServiceContract]  
public class CalculatorService  
{  
    [OperationContract]
    int Divide(int a, int b)  
    {  
      if (b==0) throw new Exception("Division by zero!");  
      return a/b;  
    }  
}  
```  
  
```vb
<ServiceContract> _
Public Class CalculatorService
    <OperationContract> _
    Public Function Divide(a As Integer, b As Integer) As Integer
        If b = 0 Then Throw New DivideByZeroException("Division by zero!")
        Return a / b
    End Function
End Class
```
  
 <span data-ttu-id="d8c9e-122">在上面的示例中，该操作可返回一个特定的除以零的自定义 SOAP 错误、可返回一个特定于数学运算但包含特定的除以零信息的自定义错误、可为若干个不同错误情况返回多个错误，或根本不返回 SOAP 错误。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-122">In the preceding example the operation can either return a custom SOAP fault that is specific to dividing by zero, a custom fault that is specific to math operations but that contains information specific to dividing by zero, multiple faults for several different error situations, or no SOAP fault at all.</span></span>  
  
### <a name="define-the-content-of-error-conditions"></a><span data-ttu-id="d8c9e-123">定义错误情况的内容</span><span class="sxs-lookup"><span data-stu-id="d8c9e-123">Define the Content of Error Conditions</span></span>  

 <span data-ttu-id="d8c9e-124">将某个错误情况标识为可有效地返回一个自定义 SOAP 错误后，下一步是定义该错误的内容并确保内容结构可以被序列化。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-124">Once an error condition has been identified as one that can usefully return a custom SOAP fault, the next step is to define the contents of that fault and ensure that the content structure can be serialized.</span></span> <span data-ttu-id="d8c9e-125">上面的代码示例演示的是特定于 `Divide` 运算的一个错误，如果 `Calculator` 服务上还存在其他运算，则单个自定义 SOAP 错误可通知客户端所有计算器错误情况，包括 `Divide`。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-125">The code example in the preceding section shows an error specific to a `Divide` operation, but if there are other operations on the `Calculator` service, then a single custom SOAP fault can inform the client of all calculator error conditions, `Divide` included.</span></span> <span data-ttu-id="d8c9e-126">下面的代码示例演示如何创建一个自定义 SOAP 错误 `MathFault`，它可以报告使用所有数学运算（包括 `Divide`）时产生的错误。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-126">The following code example shows the creation of a custom SOAP fault, `MathFault`, which can report errors made using all math operations, including `Divide`.</span></span> <span data-ttu-id="d8c9e-127">当该类可以指定一个操作（`Operation` 属性）和一个描述问题的值（`ProblemType` 属性）时，该类和这些属性必须被序列化以便以自定义 SOAP 错误的形式传输到客户端。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-127">While the class can specify an operation (the `Operation` property) and a value that describes the problem (the `ProblemType` property), the class and these properties must be serializable to be transferred to the client in a custom SOAP fault.</span></span> <span data-ttu-id="d8c9e-128">因此，使用 <xref:System.Runtime.Serialization.DataContractAttribute?displayProperty=nameWithType> 和 <xref:System.Runtime.Serialization.DataMemberAttribute?displayProperty=nameWithType> 属性 (Attribute)，以使该类型及其属性 (Property) 可序列化和尽可能可互操作。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-128">Therefore, the <xref:System.Runtime.Serialization.DataContractAttribute?displayProperty=nameWithType> and <xref:System.Runtime.Serialization.DataMemberAttribute?displayProperty=nameWithType> attributes are used to make the type and its properties serializable and as interoperable as possible.</span></span>  
  
 [!code-csharp[Faults#2](../../../samples/snippets/csharp/VS_Snippets_CFX/faults/cs/service.cs#2)]
 [!code-vb[Faults#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faults/vb/service.vb#2)]  
  
 <span data-ttu-id="d8c9e-129">有关如何确保数据可序列化的详细信息，请参阅 [在服务协定中指定数据传输](./feature-details/specifying-data-transfer-in-service-contracts.md)。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-129">For more information about how to ensure your data is serializable, see [Specifying Data Transfer in Service Contracts](./feature-details/specifying-data-transfer-in-service-contracts.md).</span></span> <span data-ttu-id="d8c9e-130">有关提供的序列化支持的列表 <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> ，请参阅 [数据协定序列化程序支持的类型](./feature-details/types-supported-by-the-data-contract-serializer.md)。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-130">For a list of the serialization support that <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> provides, see [Types Supported by the Data Contract Serializer](./feature-details/types-supported-by-the-data-contract-serializer.md).</span></span>  
  
### <a name="mark-operations-to-establish-the-fault-contract"></a><span data-ttu-id="d8c9e-131">标记操作以建立错误协定</span><span class="sxs-lookup"><span data-stu-id="d8c9e-131">Mark Operations to Establish the Fault Contract</span></span>  

 <span data-ttu-id="d8c9e-132">定义了一个将作为自定义 SOAP 错误的一部分返回的可序列化数据结构后，最后一步是将操作协定标记为引发该类型的一个 SOAP 错误。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-132">Once a serializable data structure that is returned as part of a custom SOAP fault is defined, the last step is to mark your operation contract as throwing a SOAP fault of that type.</span></span> <span data-ttu-id="d8c9e-133">为此，可以使用 <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType> 属性并传递构造的自定义数据类型的类型。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-133">To do this, use the <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType> attribute and pass the type of the custom data type that you have constructed.</span></span> <span data-ttu-id="d8c9e-134">下面的代码示例演示如何使用 <xref:System.ServiceModel.FaultContractAttribute> 属性将 `Divide` 运算指定为可以返回一个 `MathFault` 类型的 SOAP 错误。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-134">The following code example shows how to use the <xref:System.ServiceModel.FaultContractAttribute> attribute to specify that the `Divide` operation can return a SOAP fault of type `MathFault`.</span></span> <span data-ttu-id="d8c9e-135">现在也可以将其他基于数学的运算指定为可以返回 `MathFault`。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-135">Other math-based operations can now also specify that they can return a `MathFault`.</span></span>  
  
 [!code-csharp[Faults#1](../../../samples/snippets/csharp/VS_Snippets_CFX/faults/cs/service.cs#1)]
 [!code-vb[Faults#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faults/vb/service.vb#1)]  
  
 <span data-ttu-id="d8c9e-136">可以将某个操作指定为返回一个以上的自定义错误，方法为使用一个以上的 <xref:System.ServiceModel.FaultContractAttribute> 属性标记该操作。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-136">An operation can specify that it returns more than one custom fault by marking that operation with more than one <xref:System.ServiceModel.FaultContractAttribute> attribute.</span></span>  
  
 <span data-ttu-id="d8c9e-137">下一步是在操作实现中实现错误协定，如 [发送和接收故障](sending-and-receiving-faults.md)主题中所述。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-137">The next step, to implement the fault contract in your operation implementation, is described in the topic [Sending and Receiving Faults](sending-and-receiving-faults.md).</span></span>  
  
#### <a name="soap-wsdl-and-interoperability-considerations"></a><span data-ttu-id="d8c9e-138">SOAP、WSDL 和互操作性的注意事项</span><span class="sxs-lookup"><span data-stu-id="d8c9e-138">SOAP, WSDL, and Interoperability Considerations</span></span>  

 <span data-ttu-id="d8c9e-139">在某些情况下，特别是与其他平台进行互操作时，控制错误在 SOAP 消息中的显示方式或在 WSDL 元数据中对它的描述方式可能会十分重要。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-139">In some circumstances, especially when interoperating with other platforms, it may be important to control the way a fault appears in a SOAP message or the way it is described in the WSDL metadata.</span></span>  
  
 <span data-ttu-id="d8c9e-140"><xref:System.ServiceModel.FaultContractAttribute> 属性 (Attribute) 有一个 <xref:System.ServiceModel.FaultContractAttribute.Name%2A> 属性 (Property)，可以控制在元数据中为该错误生成的 WSDL 错误元素名称。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-140">The <xref:System.ServiceModel.FaultContractAttribute> attribute has a <xref:System.ServiceModel.FaultContractAttribute.Name%2A> property that allows control of the WSDL fault element name that is generated in the metadata for that fault.</span></span>  
  
 <span data-ttu-id="d8c9e-141">根据 SOAP 标准，一个错误可有一个 `Action`、一个 `Code`，以及一个 `Reason`。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-141">According to the SOAP standard, a fault can have an `Action`, a `Code`, and a `Reason`.</span></span> <span data-ttu-id="d8c9e-142">`Action` 受 <xref:System.ServiceModel.FaultContractAttribute.Action%2A> 属性控制。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-142">The `Action` is controlled by the <xref:System.ServiceModel.FaultContractAttribute.Action%2A> property.</span></span> <span data-ttu-id="d8c9e-143"><xref:System.ServiceModel.FaultException.Code%2A> 属性和 <xref:System.ServiceModel.FaultException.Reason%2A> 属性是 <xref:System.ServiceModel.FaultException?displayProperty=nameWithType> 类的两个属性，该类是泛型 <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> 的父类。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-143">The <xref:System.ServiceModel.FaultException.Code%2A> property and <xref:System.ServiceModel.FaultException.Reason%2A> property are both properties of the <xref:System.ServiceModel.FaultException?displayProperty=nameWithType> class, which is the parent class of the generic <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d8c9e-144">`Code` 属性包含一个 <xref:System.ServiceModel.FaultCode.SubCode%2A> 成员。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-144">The `Code` property includes a <xref:System.ServiceModel.FaultCode.SubCode%2A> member.</span></span>  
  
 <span data-ttu-id="d8c9e-145">在访问生成错误的非服务时，存在某些限制。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-145">When accessing non-services that generate faults, certain limitations exist.</span></span> <span data-ttu-id="d8c9e-146">WCF 仅支持架构描述并且与数据协定兼容的详细信息类型的错误。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-146">WCF supports only faults with detail types that the schema describes and that are compatible with data contracts.</span></span> <span data-ttu-id="d8c9e-147">例如，如上所述，WCF 不支持在其详细信息类型中使用 XML 属性的错误，或在详细信息部分中具有多个顶级元素的错误。</span><span class="sxs-lookup"><span data-stu-id="d8c9e-147">For example, as mentioned above, WCF does not support faults that use XML attributes in their detail types, or faults with more than one top-level element in the detail section.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8c9e-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d8c9e-148">See also</span></span>

- <xref:System.ServiceModel.FaultContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- [<span data-ttu-id="d8c9e-149">在协定和服务中指定和处理错误</span><span class="sxs-lookup"><span data-stu-id="d8c9e-149">Specifying and Handling Faults in Contracts and Services</span></span>](specifying-and-handling-faults-in-contracts-and-services.md)
- [<span data-ttu-id="d8c9e-150">发送和接收错误</span><span class="sxs-lookup"><span data-stu-id="d8c9e-150">Sending and Receiving Faults</span></span>](sending-and-receiving-faults.md)
- [<span data-ttu-id="d8c9e-151">如何：在服务协定中声明错误</span><span class="sxs-lookup"><span data-stu-id="d8c9e-151">How to: Declare Faults in Service Contracts</span></span>](how-to-declare-faults-in-service-contracts.md)
- [<span data-ttu-id="d8c9e-152">了解保护级别</span><span class="sxs-lookup"><span data-stu-id="d8c9e-152">Understanding Protection Level</span></span>](understanding-protection-level.md)
- [<span data-ttu-id="d8c9e-153">如何：设置 ProtectionLevel 属性</span><span class="sxs-lookup"><span data-stu-id="d8c9e-153">How to: Set the ProtectionLevel Property</span></span>](how-to-set-the-protectionlevel-property.md)
- [<span data-ttu-id="d8c9e-154">在服务协定中指定数据传输</span><span class="sxs-lookup"><span data-stu-id="d8c9e-154">Specifying Data Transfer in Service Contracts</span></span>](./feature-details/specifying-data-transfer-in-service-contracts.md)
