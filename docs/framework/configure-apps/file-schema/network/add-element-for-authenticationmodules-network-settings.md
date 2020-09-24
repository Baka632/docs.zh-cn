---
title: authenticationModules 的 <add> 元素（网络设置）
description: <add>ConnectionManagement 的网络设置元素将 IP 地址或 DNS 名称添加到 .NET Framework 中的连接管理列表。
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/add
helpviewer_keywords:
- authenticationModules, add element
- add element, authenticationModules
- <authenticationModules>, add element
- <add> element, authenticationModules
ms.assetid: 333c5fb0-a2ab-4db8-8531-a7fe37bb9b5b
ms.openlocfilehash: f679a43ed1851e9681a2a57ca1639f8aa75aa8b3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149499"
---
# <a name="add-element-for-authenticationmodules-network-settings"></a><span data-ttu-id="b41ea-103">authenticationModules 的 \<add> 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="b41ea-103">\<add> Element for authenticationModules (Network Settings)</span></span>

<span data-ttu-id="b41ea-104">向应用程序添加身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="b41ea-104">Adds an authentication module to the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<authenticationModules>**](authenticationmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="b41ea-105">语法</span><span class="sxs-lookup"><span data-stu-id="b41ea-105">Syntax</span></span>  
  
```xml  
<add
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b41ea-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b41ea-106">Attributes and Elements</span></span>  

 <span data-ttu-id="b41ea-107">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b41ea-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b41ea-108">特性</span><span class="sxs-lookup"><span data-stu-id="b41ea-108">Attributes</span></span>  
  
|<span data-ttu-id="b41ea-109">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="b41ea-109">**Attribute**</span></span>|<span data-ttu-id="b41ea-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="b41ea-110">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="b41ea-111">完全限定的类型名称 (由) 的 <xref:System.Type.FullName%2A> 属性和程序集名称指示， (由 <xref:System.Reflection.Assembly.FullName%2A> 逗号分隔的属性) 。</span><span class="sxs-lookup"><span data-stu-id="b41ea-111">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b41ea-112">子元素</span><span class="sxs-lookup"><span data-stu-id="b41ea-112">Child Elements</span></span>  

 <span data-ttu-id="b41ea-113">无。</span><span class="sxs-lookup"><span data-stu-id="b41ea-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b41ea-114">父元素</span><span class="sxs-lookup"><span data-stu-id="b41ea-114">Parent Elements</span></span>  
  
|<span data-ttu-id="b41ea-115">**元素**</span><span class="sxs-lookup"><span data-stu-id="b41ea-115">**Element**</span></span>|<span data-ttu-id="b41ea-116">**说明**</span><span class="sxs-lookup"><span data-stu-id="b41ea-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b41ea-117">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="b41ea-117">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="b41ea-118">指定用于对网络请求进行身份验证的模块。</span><span class="sxs-lookup"><span data-stu-id="b41ea-118">Specifies modules used to authenticate network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b41ea-119">备注</span><span class="sxs-lookup"><span data-stu-id="b41ea-119">Remarks</span></span>  

 <span data-ttu-id="b41ea-120">`add` 元素会在已注册的身份验证模块列表末尾添加一个身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="b41ea-120">The `add` element adds an authentication module to the end of the list of registered authentication modules.</span></span> <span data-ttu-id="b41ea-121">身份验证模块按照它们添加到列表中的顺序进行调用。</span><span class="sxs-lookup"><span data-stu-id="b41ea-121">Authentication modules are called in the order in which they were added to the list.</span></span>  
  
 <span data-ttu-id="b41ea-122">特性的值 `type` 应为有效的类型名称和相应的程序集名称，用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="b41ea-122">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="b41ea-123">配置文件</span><span class="sxs-lookup"><span data-stu-id="b41ea-123">Configuration Files</span></span>  

 <span data-ttu-id="b41ea-124">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="b41ea-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b41ea-125">示例</span><span class="sxs-lookup"><span data-stu-id="b41ea-125">Example</span></span>  

 <span data-ttu-id="b41ea-126">下面的示例启用了默认的身份验证模块。</span><span class="sxs-lookup"><span data-stu-id="b41ea-126">The following example enables the default authentication modules.</span></span> <span data-ttu-id="b41ea-127">应将版本和 PublicKeyToken 的值替换为指定模块的正确值。</span><span class="sxs-lookup"><span data-stu-id="b41ea-127">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
        <authenticationModules>  
            <add type="System.Net.DigestClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.NegotiateClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.KerberosClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.NtlmClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
            <add type="System.Net.BasicClient, System, Version=2.0.3600.0,  
                 Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
        </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b41ea-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="b41ea-128">See also</span></span>

- <xref:System.Net.IAuthenticationModule>
- <xref:System.Net.AuthenticationManager>
- [<span data-ttu-id="b41ea-129">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="b41ea-129">Network Settings Schema</span></span>](index.md)
