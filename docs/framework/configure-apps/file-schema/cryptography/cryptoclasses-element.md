---
title: <cryptoClasses> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClasses
helpviewer_keywords:
- <cryptoClasses> element
- cryptoClasses element
ms.assetid: 290d5f96-946d-4f02-babb-1d31ec0b8295
ms.openlocfilehash: 89b96edcf1da20698cd203e78fa27e644fa69cc3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201819"
---
# <a name="cryptoclasses-element"></a><span data-ttu-id="10b49-102">\<cryptoClasses> 元素</span><span class="sxs-lookup"><span data-stu-id="10b49-102">\<cryptoClasses> Element</span></span>

<span data-ttu-id="10b49-103">包含加密类的列表，这些类具有到元素中的友好名称的映射 [\<nameEntry>](nameentry-element.md) 。</span><span class="sxs-lookup"><span data-stu-id="10b49-103">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoClasses>**  
  
## <a name="syntax"></a><span data-ttu-id="10b49-104">语法</span><span class="sxs-lookup"><span data-stu-id="10b49-104">Syntax</span></span>  
  
```xml  
<cryptoClasses>
</cryptoClasses>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="10b49-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="10b49-105">Attributes and Elements</span></span>  

 <span data-ttu-id="10b49-106">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="10b49-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="10b49-107">特性</span><span class="sxs-lookup"><span data-stu-id="10b49-107">Attributes</span></span>  

 <span data-ttu-id="10b49-108">无。</span><span class="sxs-lookup"><span data-stu-id="10b49-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="10b49-109">子元素</span><span class="sxs-lookup"><span data-stu-id="10b49-109">Child Elements</span></span>  
  
|<span data-ttu-id="10b49-110">元素</span><span class="sxs-lookup"><span data-stu-id="10b49-110">Element</span></span>|<span data-ttu-id="10b49-111">描述</span><span class="sxs-lookup"><span data-stu-id="10b49-111">Description</span></span>|  
|-------------|-----------------|  
|[\<cryptoClass>](cryptoclass-element.md)|<span data-ttu-id="10b49-112">包含一个加密类，该类具有到元素中的友好名称的映射 **\<nameEntry>** 。</span><span class="sxs-lookup"><span data-stu-id="10b49-112">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="10b49-113">父元素</span><span class="sxs-lookup"><span data-stu-id="10b49-113">Parent Elements</span></span>  
  
|<span data-ttu-id="10b49-114">元素</span><span class="sxs-lookup"><span data-stu-id="10b49-114">Element</span></span>|<span data-ttu-id="10b49-115">描述</span><span class="sxs-lookup"><span data-stu-id="10b49-115">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="10b49-116">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="10b49-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="10b49-117">包含加密设置。</span><span class="sxs-lookup"><span data-stu-id="10b49-117">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="10b49-118">包含类到友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="10b49-118">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="10b49-119">包含 `cryptographySettings` 元素。</span><span class="sxs-lookup"><span data-stu-id="10b49-119">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="10b49-120">示例</span><span class="sxs-lookup"><span data-stu-id="10b49-120">Example</span></span>  

 <span data-ttu-id="10b49-121">下面的示例演示如何使用 **\<cryptoClass>** 元素来引用加密类并配置运行时。</span><span class="sxs-lookup"><span data-stu-id="10b49-121">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="10b49-122">然后，你可以将字符串 "RSA" 传递给 <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> 方法，并使用 <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> 方法返回 `MyCryptoRSAClass` 对象。</span><span class="sxs-lookup"><span data-stu-id="10b49-122">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <!-- Other cryptography classes go here. -->  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
             <!-- Mappings to other cryptography classes go here. -->  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="10b49-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="10b49-123">See also</span></span>

- <xref:System.Security.Cryptography>
- [<span data-ttu-id="10b49-124">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="10b49-124">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="10b49-125">加密设置架构</span><span class="sxs-lookup"><span data-stu-id="10b49-125">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="10b49-126">加密服务</span><span class="sxs-lookup"><span data-stu-id="10b49-126">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="10b49-127">CryptoConfig. Cryptoconfig.createfromname。</span><span class="sxs-lookup"><span data-stu-id="10b49-127">System.Security.Cryptography.CryptoConfig.CreateFromName</span></span>](xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A)
- [<span data-ttu-id="10b49-128">配置加密类</span><span class="sxs-lookup"><span data-stu-id="10b49-128">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
