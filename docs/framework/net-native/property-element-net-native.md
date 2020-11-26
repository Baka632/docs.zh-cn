---
title: <Property>元素 (.NET Native)
ms.date: 03/30/2017
ms.assetid: ad4ba56d-3bcb-4c10-ba90-1cc66e2175a1
ms.openlocfilehash: a0bdf95a1d1cadf7423f8c6595add13eda4d0d9a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250848"
---
# <a name="property-element-net-native"></a><span data-ttu-id="d0e5b-102">\<Property>元素 (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="d0e5b-102">\<Property> Element (.NET Native)</span></span>

<span data-ttu-id="d0e5b-103">将运行时反射策略应用到一个属性。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-103">Applies runtime reflection policy to a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0e5b-104">语法</span><span class="sxs-lookup"><span data-stu-id="d0e5b-104">Syntax</span></span>  
  
```xml  
<Property Name="property_name"  
          Browse="policy_type"  
          Dynamic="policy_type"  
          Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d0e5b-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d0e5b-105">Attributes and Elements</span></span>  

 <span data-ttu-id="d0e5b-106">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d0e5b-107">特性</span><span class="sxs-lookup"><span data-stu-id="d0e5b-107">Attributes</span></span>  
  
|<span data-ttu-id="d0e5b-108">属性</span><span class="sxs-lookup"><span data-stu-id="d0e5b-108">Attribute</span></span>|<span data-ttu-id="d0e5b-109">属性类型</span><span class="sxs-lookup"><span data-stu-id="d0e5b-109">Attribute type</span></span>|<span data-ttu-id="d0e5b-110">描述</span><span class="sxs-lookup"><span data-stu-id="d0e5b-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="d0e5b-111">常规</span><span class="sxs-lookup"><span data-stu-id="d0e5b-111">General</span></span>|<span data-ttu-id="d0e5b-112">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-112">Required attribute.</span></span> <span data-ttu-id="d0e5b-113">指定属性名称。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-113">Specifies the property name.</span></span>|  
|`Browse`|<span data-ttu-id="d0e5b-114">反射</span><span class="sxs-lookup"><span data-stu-id="d0e5b-114">Reflection</span></span>|<span data-ttu-id="d0e5b-115">可选特性。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-115">Optional attribute.</span></span> <span data-ttu-id="d0e5b-116">制对该属性信息的查询或列举该属性，但并不在运行时间启用任何动态访问。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-116">Controls querying for information about or enumerating the property but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="d0e5b-117">反射</span><span class="sxs-lookup"><span data-stu-id="d0e5b-117">Reflection</span></span>|<span data-ttu-id="d0e5b-118">可选特性。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-118">Optional attribute.</span></span> <span data-ttu-id="d0e5b-119">控制运行时对该属性的访问，以启用动态编程。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-119">Controls runtime access to the property to enable dynamic programming.</span></span> <span data-ttu-id="d0e5b-120">该策略确保一个属性可在运行时间内得到设置或动态检索。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-120">This policy ensures that a property can be set or retrieved dynamically at run time.</span></span>|  
|`Serialize`|<span data-ttu-id="d0e5b-121">序列化</span><span class="sxs-lookup"><span data-stu-id="d0e5b-121">Serialization</span></span>|<span data-ttu-id="d0e5b-122">可选特性。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-122">Optional attribute.</span></span> <span data-ttu-id="d0e5b-123">控制运行时对一个属性的访问以启用类型实例，使其通过程序库得到序列化，例如通过 Newtonsoft JSON 序列化程序，或被用于绑定数据。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-123">Controls runtime access to a property to enable type instances to be serialized by libraries such as the Newtonsoft JSON serializer or to be used for data binding.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="d0e5b-124">Name 特性</span><span class="sxs-lookup"><span data-stu-id="d0e5b-124">Name attribute</span></span>  
  
|<span data-ttu-id="d0e5b-125">值</span><span class="sxs-lookup"><span data-stu-id="d0e5b-125">Value</span></span>|<span data-ttu-id="d0e5b-126">描述</span><span class="sxs-lookup"><span data-stu-id="d0e5b-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d0e5b-127">method_name</span><span class="sxs-lookup"><span data-stu-id="d0e5b-127">*method_name*</span></span>|<span data-ttu-id="d0e5b-128">属性名称。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-128">The property name.</span></span> <span data-ttu-id="d0e5b-129">属性的类型由父级 [\<Type>](type-element-net-native.md) 或 [\<TypeInstantiation>](typeinstantiation-element-net-native.md) 元素定义。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-129">The type of the property is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="d0e5b-130">所有其他特性</span><span class="sxs-lookup"><span data-stu-id="d0e5b-130">All other attributes</span></span>  
  
|<span data-ttu-id="d0e5b-131">值</span><span class="sxs-lookup"><span data-stu-id="d0e5b-131">Value</span></span>|<span data-ttu-id="d0e5b-132">描述</span><span class="sxs-lookup"><span data-stu-id="d0e5b-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d0e5b-133">*策略_设置*</span><span class="sxs-lookup"><span data-stu-id="d0e5b-133">*policy_setting*</span></span>|<span data-ttu-id="d0e5b-134">该设置将应用到这个属性的策略类型。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-134">The setting to apply to this policy type for the property.</span></span> <span data-ttu-id="d0e5b-135">可能值为 `Auto`、`Excluded`、`Included` 和 `Required`。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-135">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="d0e5b-136">有关详细信息，请参阅[运行时指令策略设置](runtime-directive-policy-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-136">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d0e5b-137">子元素</span><span class="sxs-lookup"><span data-stu-id="d0e5b-137">Child Elements</span></span>  

 <span data-ttu-id="d0e5b-138">无。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d0e5b-139">父元素</span><span class="sxs-lookup"><span data-stu-id="d0e5b-139">Parent Elements</span></span>  
  
|<span data-ttu-id="d0e5b-140">元素</span><span class="sxs-lookup"><span data-stu-id="d0e5b-140">Element</span></span>|<span data-ttu-id="d0e5b-141">描述</span><span class="sxs-lookup"><span data-stu-id="d0e5b-141">Description</span></span>|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|<span data-ttu-id="d0e5b-142">将反射策略应用到一种类型及其所有成员。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-142">Applies reflection policy to a type and all its members.</span></span>|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|<span data-ttu-id="d0e5b-143">将反射策略应用到一种构造泛型类型及其所有成员。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-143">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0e5b-144">备注</span><span class="sxs-lookup"><span data-stu-id="d0e5b-144">Remarks</span></span>  

 <span data-ttu-id="d0e5b-145">如果一个属性的策略没有得到显式定义，它将继承其父元素的运行时间策略。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-145">If a property's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0e5b-146">示例</span><span class="sxs-lookup"><span data-stu-id="d0e5b-146">Example</span></span>  

 <span data-ttu-id="d0e5b-147">以下实例使用反射实例化了一个 `Book` 对象并显示了其属性值。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-147">The following example uses reflection to instantiate a `Book` object and display its property values.</span></span> <span data-ttu-id="d0e5b-148">该项目的原始 default.rd.xml 文件显示如下：</span><span class="sxs-lookup"><span data-stu-id="d0e5b-148">The original default.rd.xml file for the project appears as follows:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Namespace Name="LibraryApplications"  Browse="Required Public" >  
         <Type Name="Book"   Activate="All" />  
      </Namespace>  
   </Application>  
</Directives>  
```  
  
 <span data-ttu-id="d0e5b-149">该文件将 `All` 值应用到允许通过反射访问类构造函数的 `Activate` 的类的 `Book` 策略。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-149">The file applies the `All` value to the `Activate` policy for the `Book` class, which allows access to class constructors through reflection.</span></span> <span data-ttu-id="d0e5b-150">`Browse` 类的 `Book` 策略是从其父命名空间继承的。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-150">The `Browse` policy for the `Book` class is inherited from its parent namespace.</span></span> <span data-ttu-id="d0e5b-151">这已设置为 `Required Public`，这使得元数据在运行时可用。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-151">This is set to `Required Public`, which makes metadata available at runtime.</span></span>  
  
 <span data-ttu-id="d0e5b-152">以下是该实例的源代码。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-152">The following is the source code for the example.</span></span> <span data-ttu-id="d0e5b-153">`outputBlock`变量表示一个 <xref:Windows.UI.Xaml.Controls.TextBlock> 控件。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-153">The `outputBlock` variable represents a <xref:Windows.UI.Xaml.Controls.TextBlock> control.</span></span>  
  
 [!code-csharp[ProjectN_Reflection#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/property1.cs#6)]  
  
 <span data-ttu-id="d0e5b-154">然而，编译和执行此示例将引发 [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) 异常。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-154">However, compiling and executing this example throws a [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) exception.</span></span> <span data-ttu-id="d0e5b-155">尽管我们已经使 `Book` 类型的元数据变得可用，我们却未使属性获取者的实施变得动态可用。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-155">Although we've made metadata for the `Book` type available, we've failed to make the implementations of the property getters available dynamically.</span></span> <span data-ttu-id="d0e5b-156">我们可通过以下方法之一纠正这个错误：</span><span class="sxs-lookup"><span data-stu-id="d0e5b-156">We can correct this error by either in one of two ways:</span></span>  
  
- <span data-ttu-id="d0e5b-157">通过 `Dynamic` `Book` 在其元素中定义类型的策略 [\<Type>](type-element-net-native.md) 。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-157">by defining the `Dynamic` policy for the `Book` type in its [\<Type>](type-element-net-native.md) element.</span></span>  
  
- <span data-ttu-id="d0e5b-158">通过为要 [\<Property>](property-element-net-native.md) 调用其 getter 的每个属性添加一个嵌套元素，如下 default.rd.xml 文件所示。</span><span class="sxs-lookup"><span data-stu-id="d0e5b-158">By adding a nested [\<Property>](property-element-net-native.md) element for each property whose getter we'd like to invoke, as the following default.rd.xml file does.</span></span>  
  
    ```xml  
    <Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
       <Application>  
          <Namespace Name="LibraryApplications"  Browse="Required Public" >  
             <Type Name="Book"   Activate="All" >  
                <Property Name="Title" Dynamic="Required" />  
                <Property Name="Author" Dynamic="Required" />  
                  <Property Name="ISBN" Dynamic="Required" />  
             </Type>  
          </Namespace>  
       </Application>  
    </Directives>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d0e5b-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d0e5b-159">See also</span></span>

- [<span data-ttu-id="d0e5b-160">运行时指令 (rd.xml) 配置文件引用</span><span class="sxs-lookup"><span data-stu-id="d0e5b-160">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="d0e5b-161">运行时指令元素</span><span class="sxs-lookup"><span data-stu-id="d0e5b-161">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="d0e5b-162">运行时指令策略设置</span><span class="sxs-lookup"><span data-stu-id="d0e5b-162">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
