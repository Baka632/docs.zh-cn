---
title: 查看类型信息
description: 使用 System.Type 查看类型信息，这是 .NET 中反射的中心。 查看 ConstructorInfo、MemberInfo、MethodInfo、FieldInfo 和 PropertyInfo。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- types, viewing type information
- Type object
- viewing type information
- reflection, viewing type information
ms.assetid: 7e7303a9-4064-4738-b4e7-b75974ed70d2
ms.openlocfilehash: 3baacbeca7f5cc50fbb720849aec273f996f86e7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96259136"
---
# <a name="viewing-type-information"></a><span data-ttu-id="3cc22-104">查看类型信息</span><span class="sxs-lookup"><span data-stu-id="3cc22-104">Viewing Type Information</span></span>

<span data-ttu-id="3cc22-105"><xref:System.Type?displayProperty=nameWithType> 类是反射的中心。</span><span class="sxs-lookup"><span data-stu-id="3cc22-105">The <xref:System.Type?displayProperty=nameWithType> class is central to reflection.</span></span> <span data-ttu-id="3cc22-106">当反射提出请求时，公共语言运行时为已加载的类型创建 Type  。</span><span class="sxs-lookup"><span data-stu-id="3cc22-106">The common language runtime creates the **Type** for a loaded type when reflection requests it.</span></span> <span data-ttu-id="3cc22-107">可使用 Type  对象的方法、字段、属性和嵌套类来查找该类型的任何信息。</span><span class="sxs-lookup"><span data-stu-id="3cc22-107">You can use a **Type** object's methods, fields, properties, and nested classes to find out everything about that type.</span></span>  
  
 <span data-ttu-id="3cc22-108">使用 <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> 或 <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType> 从尚未加载的程序集中获取 Type  对象，传入所需类型的名称。</span><span class="sxs-lookup"><span data-stu-id="3cc22-108">Use <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> or <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType> to obtain **Type** objects from assemblies that have not been loaded, passing in the name of the type or types you want.</span></span> <span data-ttu-id="3cc22-109">使用 <xref:System.Type.GetType%2A?displayProperty=nameWithType> 从已加载的程序集中获取 Type 对象  。</span><span class="sxs-lookup"><span data-stu-id="3cc22-109">Use <xref:System.Type.GetType%2A?displayProperty=nameWithType> to get the **Type** objects from an assembly that is already loaded.</span></span> <span data-ttu-id="3cc22-110">使用 <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType> 和 <xref:System.Reflection.Module.GetTypes%2A?displayProperty=nameWithType> 获取模块 Type 对象  。</span><span class="sxs-lookup"><span data-stu-id="3cc22-110">Use <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType> and <xref:System.Reflection.Module.GetTypes%2A?displayProperty=nameWithType> to obtain module **Type** objects.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3cc22-111">要检查和操纵泛型类型及方法，请参阅[反射类型和泛型类型](reflection-and-generic-types.md)和[如何：使用反射检查和实例化泛型类型](how-to-examine-and-instantiate-generic-types-with-reflection.md)中提供的其他信息。</span><span class="sxs-lookup"><span data-stu-id="3cc22-111">If you want to examine and manipulate generic types and methods, please see the additional information provided in [Reflection and Generic Types](reflection-and-generic-types.md) and [How to: Examine and Instantiate Generic Types with Reflection](how-to-examine-and-instantiate-generic-types-with-reflection.md).</span></span>  
  
 <span data-ttu-id="3cc22-112">下列示例演示获取程序集的 <xref:System.Reflection.Assembly> 对象和模块所必需的语法。</span><span class="sxs-lookup"><span data-stu-id="3cc22-112">The following example shows the syntax necessary to get the <xref:System.Reflection.Assembly> object and module for an assembly.</span></span>  
  
 [!code-cpp[Conceptual.Types.ViewInfo#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source5.cpp#6)]
 [!code-csharp[Conceptual.Types.ViewInfo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source5.cs#6)]
 [!code-vb[Conceptual.Types.ViewInfo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source5.vb#6)]  
  
 <span data-ttu-id="3cc22-113">下列示例演示如何从已加载的程序集获取 Type 对象  。</span><span class="sxs-lookup"><span data-stu-id="3cc22-113">The following example demonstrates getting **Type** objects from a loaded assembly.</span></span>  
  
 [!code-cpp[Conceptual.Types.ViewInfo#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source5.cpp#7)]
 [!code-csharp[Conceptual.Types.ViewInfo#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source5.cs#7)]
 [!code-vb[Conceptual.Types.ViewInfo#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source5.vb#7)]  
  
 <span data-ttu-id="3cc22-114">一旦获取 Type 对象，可通过多种方式来查看该类型成员的相关信息  。</span><span class="sxs-lookup"><span data-stu-id="3cc22-114">Once you obtain a **Type**, there are many ways you can discover information about the members of that type.</span></span> <span data-ttu-id="3cc22-115">例如，可调用 <xref:System.Type.GetMembers%2A?displayProperty=nameWithType> 方法查找所有类型的成员，获取一组描述当前类型各成员的 <xref:System.Reflection.MemberInfo> 对象。</span><span class="sxs-lookup"><span data-stu-id="3cc22-115">For example, you can find out about all the type's members by calling the <xref:System.Type.GetMembers%2A?displayProperty=nameWithType> method, which obtains an array of <xref:System.Reflection.MemberInfo> objects describing each of the members of the current type.</span></span>  
  
 <span data-ttu-id="3cc22-116">还可以使用 Type 类上的方法来检索按名称指定的一个或多个构造函数、方法、事件、字段或属性的相关信息  。</span><span class="sxs-lookup"><span data-stu-id="3cc22-116">You can also use methods on the **Type** class to retrieve information about one or more constructors, methods, events, fields, or properties that you specify by name.</span></span> <span data-ttu-id="3cc22-117">例如，<xref:System.Type.GetConstructor%2A?displayProperty=nameWithType> 封装当前类的特定构造函数。</span><span class="sxs-lookup"><span data-stu-id="3cc22-117">For example, <xref:System.Type.GetConstructor%2A?displayProperty=nameWithType> encapsulates a specific constructor of the current class.</span></span>  
  
 <span data-ttu-id="3cc22-118">如果有 Type，可使用 <xref:System.Type.Module%2A?displayProperty=nameWithType> 属性获取一个封装含该类型的模块的对象  。</span><span class="sxs-lookup"><span data-stu-id="3cc22-118">If you have a **Type**, you can use the <xref:System.Type.Module%2A?displayProperty=nameWithType> property to obtain an object that encapsulates the module containing that type.</span></span> <span data-ttu-id="3cc22-119">使用 <xref:System.Reflection.Module.Assembly%2A?displayProperty=nameWithType> 属性查找一个封装含该模块的程序集的对象。</span><span class="sxs-lookup"><span data-stu-id="3cc22-119">Use the <xref:System.Reflection.Module.Assembly%2A?displayProperty=nameWithType> property to locate an object that encapsulates the assembly containing the module.</span></span> <span data-ttu-id="3cc22-120">可以获取直接使用 <xref:System.Type.Assembly%2A?displayProperty=nameWithType> 属性封装类型的程序集。</span><span class="sxs-lookup"><span data-stu-id="3cc22-120">You can obtain the assembly that encapsulates the type directly by using the <xref:System.Type.Assembly%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="systemtype-and-constructorinfo"></a><span data-ttu-id="3cc22-121">System.Type 和 ConstructorInfo</span><span class="sxs-lookup"><span data-stu-id="3cc22-121">System.Type and ConstructorInfo</span></span>  

 <span data-ttu-id="3cc22-122">下列示例演示如何列出类的构造函数，在本例中即指 <xref:System.String> 类。</span><span class="sxs-lookup"><span data-stu-id="3cc22-122">The following example shows how to list the constructors for a class, in this case, the <xref:System.String> class.</span></span>  
  
 [!code-cpp[Conceptual.Types.ViewInfo#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Types.ViewInfo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source1.cs#1)]
 [!code-vb[Conceptual.Types.ViewInfo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source1.vb#1)]  
  
## <a name="memberinfo-methodinfo-fieldinfo-and-propertyinfo"></a><span data-ttu-id="3cc22-123">MemberInfo、MethodInfo、FieldInfo 和 PropertyInfo</span><span class="sxs-lookup"><span data-stu-id="3cc22-123">MemberInfo, MethodInfo, FieldInfo, and PropertyInfo</span></span>  

 <span data-ttu-id="3cc22-124">使用 <xref:System.Reflection.MemberInfo>、<xref:System.Reflection.MethodInfo>、<xref:System.Reflection.FieldInfo> 或 <xref:System.Reflection.PropertyInfo> 对象获取类型的方法、属性、事件和字段的相关信息。</span><span class="sxs-lookup"><span data-stu-id="3cc22-124">Obtain information about the type's methods, properties, events, and fields using <xref:System.Reflection.MemberInfo>, <xref:System.Reflection.MethodInfo>, <xref:System.Reflection.FieldInfo>, or <xref:System.Reflection.PropertyInfo> objects.</span></span>  
  
 <span data-ttu-id="3cc22-125">下列示例使用 MemberInfo 列出 System.IO.File 类中成员的数量，并使用 <xref:System.Type.IsPublic%2A> 属性确定类的可见性   。</span><span class="sxs-lookup"><span data-stu-id="3cc22-125">The following example uses **MemberInfo** to list the number of members in the **System.IO.File** class and uses the <xref:System.Type.IsPublic%2A> property to determine the visibility of the class.</span></span>  
  
 [!code-cpp[Conceptual.Types.ViewInfo#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Types.ViewInfo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source2.cs#2)]
 [!code-vb[Conceptual.Types.ViewInfo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source2.vb#2)]  
  
 <span data-ttu-id="3cc22-126">下列示例调查指定成员的类型。</span><span class="sxs-lookup"><span data-stu-id="3cc22-126">The following example investigates the type of the specified member.</span></span> <span data-ttu-id="3cc22-127">它在 MemberInfo 类的成员上执行反射，并列出该成员的类型  。</span><span class="sxs-lookup"><span data-stu-id="3cc22-127">It performs reflection on a member of the **MemberInfo** class, and lists its type.</span></span>  
  
 [!code-cpp[Conceptual.Types.ViewInfo#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source3.cpp#3)]
 [!code-csharp[Conceptual.Types.ViewInfo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source3.cs#3)]
 [!code-vb[Conceptual.Types.ViewInfo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source3.vb#3)]  
  
 <span data-ttu-id="3cc22-128">下列示例使用所有反射 \*Info 类和 <xref:System.Reflection.BindingFlags> 来列出指定类的全体成员（构造函数、字段、属性、事件和方法），并将成员区分为静态和实例类别  。</span><span class="sxs-lookup"><span data-stu-id="3cc22-128">The following example uses all the Reflection **\*Info** classes along with <xref:System.Reflection.BindingFlags> to list all the members (constructors, fields, properties, events, and methods) of the specified class, dividing the members into static and instance categories.</span></span>  
  
 [!code-cpp[Conceptual.Types.ViewInfo#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source4.cpp#4)]
 [!code-csharp[Conceptual.Types.ViewInfo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source4.cs#4)]
 [!code-vb[Conceptual.Types.ViewInfo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source4.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="3cc22-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="3cc22-129">See also</span></span>

- <xref:System.Reflection.BindingFlags>
- <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType>
- <xref:System.Type.GetType%2A?displayProperty=nameWithType>
- <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>
- <xref:System.Type.GetFields%2A?displayProperty=nameWithType>
- <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType>
- <xref:System.Reflection.Module.GetTypes%2A?displayProperty=nameWithType>
- <xref:System.Reflection.MemberInfo>
- <xref:System.Reflection.ConstructorInfo>
- <xref:System.Reflection.MethodInfo>
- <xref:System.Reflection.FieldInfo>
- <xref:System.Reflection.EventInfo>
- <xref:System.Reflection.ParameterInfo>
- [<span data-ttu-id="3cc22-130">反射类型和泛型类型</span><span class="sxs-lookup"><span data-stu-id="3cc22-130">Reflection and Generic Types</span></span>](reflection-and-generic-types.md)
