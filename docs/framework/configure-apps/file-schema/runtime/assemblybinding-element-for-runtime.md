---
title: <runtime> 的 <assemblyBinding> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding
helpviewer_keywords:
- <assemblyBinding> element
- assemblyBinding element
- container tags, <assemblyBinding> element
ms.assetid: 964cbb35-ab49-4498-8471-209689e5dada
ms.openlocfilehash: b6a39bcecfd2485481677496adcf026d986c283b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170241"
---
# <a name="assemblybinding-element-for-runtime"></a><span data-ttu-id="a129e-102">\<runtime> 的 \<assemblyBinding> 元素</span><span class="sxs-lookup"><span data-stu-id="a129e-102">\<assemblyBinding> Element for \<runtime></span></span>

<span data-ttu-id="a129e-103">包含有关程序集版本重定向和程序集位置的信息。</span><span class="sxs-lookup"><span data-stu-id="a129e-103">Contains information about assembly version redirection and the locations of assemblies.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<assemblyBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="a129e-104">语法</span><span class="sxs-lookup"><span data-stu-id="a129e-104">Syntax</span></span>  
  
```xml  
      <assemblyBinding
   xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
</assemblyBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a129e-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a129e-105">Attributes and Elements</span></span>  

 <span data-ttu-id="a129e-106">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a129e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a129e-107">特性</span><span class="sxs-lookup"><span data-stu-id="a129e-107">Attributes</span></span>  
  
|<span data-ttu-id="a129e-108">属性</span><span class="sxs-lookup"><span data-stu-id="a129e-108">Attribute</span></span>|<span data-ttu-id="a129e-109">描述</span><span class="sxs-lookup"><span data-stu-id="a129e-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a129e-110">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="a129e-110">**xmlns**</span></span>|<span data-ttu-id="a129e-111">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="a129e-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="a129e-112">指定程序集绑定所需的 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="a129e-112">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="a129e-113">使用字符串“urn: 架构-microsoft-com:asm.v1”作为值。</span><span class="sxs-lookup"><span data-stu-id="a129e-113">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span>|  
|<span data-ttu-id="a129e-114">**appliesTo**</span><span class="sxs-lookup"><span data-stu-id="a129e-114">**appliesTo**</span></span>|<span data-ttu-id="a129e-115">指定 .NET Framework 程序集重定向适用的运行时版本。</span><span class="sxs-lookup"><span data-stu-id="a129e-115">Specifies the runtime version the .NET Framework assembly redirection applies to.</span></span> <span data-ttu-id="a129e-116">此可选特性用 .NET Framework 版本号来指示其适用的版本。</span><span class="sxs-lookup"><span data-stu-id="a129e-116">This optional attribute uses a .NET Framework version number to indicate what version it applies to.</span></span> <span data-ttu-id="a129e-117">如果没有指定 appliesTo 特性，\<assemblyBinding> 元素将适用于 .NET Framework 的所有版本 。</span><span class="sxs-lookup"><span data-stu-id="a129e-117">If no **appliesTo** attribute is specified, the **\<assemblyBinding>** element applies to all versions of the .NET Framework.</span></span> <span data-ttu-id="a129e-118">.NET Framework 版本1.1 中引入了 **appliesTo** 特性;.NET Framework 版本1.0 将忽略它。</span><span class="sxs-lookup"><span data-stu-id="a129e-118">The **appliesTo** attribute was introduced in .NET Framework version 1.1; it is ignored by the .NET Framework version 1.0.</span></span> <span data-ttu-id="a129e-119">这意味着，即使指定了 appliesTo 特性，在使用 .NET Framework 版本 1.0 时所有的 \<assemblyBinding> 元素也都适用 。</span><span class="sxs-lookup"><span data-stu-id="a129e-119">This means that all **\<assemblyBinding>** elements are applied when using the .NET Framework version 1.0, even if an **appliesTo** attribute is specified.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a129e-120">子元素</span><span class="sxs-lookup"><span data-stu-id="a129e-120">Child Elements</span></span>  
  
|<span data-ttu-id="a129e-121">元素</span><span class="sxs-lookup"><span data-stu-id="a129e-121">Element</span></span>|<span data-ttu-id="a129e-122">描述</span><span class="sxs-lookup"><span data-stu-id="a129e-122">Description</span></span>|  
|-------------|-----------------|  
|[\<dependentAssembly>](dependentassembly-element.md)|<span data-ttu-id="a129e-123">封装程序集的绑定策略和程序集位置。</span><span class="sxs-lookup"><span data-stu-id="a129e-123">Encapsulates binding policy and assembly location for an assembly.</span></span> <span data-ttu-id="a129e-124">**\<dependentAssembly>** 为每个程序集使用一个标记。</span><span class="sxs-lookup"><span data-stu-id="a129e-124">Use one **\<dependentAssembly>** tag for each assembly.</span></span>|  
|[\<probing>](probing-element.md)|<span data-ttu-id="a129e-125">指定加载程序集时公共语言运行时搜索的子目录。</span><span class="sxs-lookup"><span data-stu-id="a129e-125">Specifies subdirectories the common language runtime searches when loading assemblies.</span></span>|  
|[\<publisherPolicy>](publisherpolicy-element.md)|<span data-ttu-id="a129e-126">指定运行时是否使用发布者策略。</span><span class="sxs-lookup"><span data-stu-id="a129e-126">Specifies whether the runtime applies publisher policy.</span></span>|  
|[\<qualifyAssembly>](qualifyassembly-element.md)|<span data-ttu-id="a129e-127">指定使用部分名称时应动态加载的程序集全名。</span><span class="sxs-lookup"><span data-stu-id="a129e-127">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a129e-128">父元素</span><span class="sxs-lookup"><span data-stu-id="a129e-128">Parent Elements</span></span>  
  
|<span data-ttu-id="a129e-129">元素</span><span class="sxs-lookup"><span data-stu-id="a129e-129">Element</span></span>|<span data-ttu-id="a129e-130">描述</span><span class="sxs-lookup"><span data-stu-id="a129e-130">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a129e-131">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="a129e-131">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a129e-132">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="a129e-132">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a129e-133">示例</span><span class="sxs-lookup"><span data-stu-id="a129e-133">Example</span></span>  

 <span data-ttu-id="a129e-134">下面的示例显示如何将一个程序集版本重定向到另一个版本并提供基本代码。</span><span class="sxs-lookup"><span data-stu-id="a129e-134">The following example shows how to redirect one assembly version to another and provide a codebase.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <bindingRedirect oldVersion="1.0.0.0"  
                             newVersion="2.0.0.0"/>  
            <codeBase version="2.0.0.0"  
                      href="http://www.litwareinc.com/myAssembly.dll"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="a129e-135">下面的示例演示如何使用 **appliesTo** 特性重定向 .NET Framework 程序集的绑定。</span><span class="sxs-lookup"><span data-stu-id="a129e-135">The following example shows how to use the **appliesTo** attribute to redirect binding of a .NET Framework assembly.</span></span>  
  
```xml  
<runtime>  
   <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
      <dependentAssembly>
         <assemblyIdentity name="mscorcfg" publicKeyToken="b03f5f7f11d50a3a" culture=""/>  
         <bindingRedirect oldVersion="0.0.0.0-65535.65535.65535.65535" newVersion="1.0.3300.0"/>  
      </dependentAssembly>  
   </assemblyBinding>  
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a129e-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="a129e-136">See also</span></span>

- [<span data-ttu-id="a129e-137">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="a129e-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a129e-138">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="a129e-138">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="a129e-139">重定向程序集版本</span><span class="sxs-lookup"><span data-stu-id="a129e-139">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
