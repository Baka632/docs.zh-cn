---
title: <proxy> 元素（网络设置）
description: <proxy>网络设置元素定义 .NET Framework 中的代理服务器选项。 本文包含一个示例。
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
ms.openlocfilehash: 54b324dcd27d5827159bc2d773365e388a367d26
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190210"
---
# <a name="proxy-element-network-settings"></a><span data-ttu-id="2786c-104">\<proxy> 元素（网络设置）</span><span class="sxs-lookup"><span data-stu-id="2786c-104">\<proxy> Element (Network Settings)</span></span>

<span data-ttu-id="2786c-105">定义代理服务器。</span><span class="sxs-lookup"><span data-stu-id="2786c-105">Defines a proxy server.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<proxy>**

## <a name="syntax"></a><span data-ttu-id="2786c-106">语法</span><span class="sxs-lookup"><span data-stu-id="2786c-106">Syntax</span></span>  
  
```xml  
<proxy
  autoDetect="True|False|Unspecified"
  bypassonlocal="True|False|Unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="True|False|Unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2786c-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2786c-107">Attributes and Elements</span></span>  

 <span data-ttu-id="2786c-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2786c-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2786c-109">特性</span><span class="sxs-lookup"><span data-stu-id="2786c-109">Attributes</span></span>  
  
|<span data-ttu-id="2786c-110">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="2786c-110">**Attribute**</span></span>|<span data-ttu-id="2786c-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="2786c-111">**Description**</span></span>|  
|-------------------|---------------------|  
|`autoDetect`|<span data-ttu-id="2786c-112">指定是否自动检测代理。</span><span class="sxs-lookup"><span data-stu-id="2786c-112">Specifies whether the proxy is automatically detected.</span></span> <span data-ttu-id="2786c-113">默认值是 `Unspecified`。</span><span class="sxs-lookup"><span data-stu-id="2786c-113">The default value is `Unspecified`.</span></span>|  
|`bypassonlocal`|<span data-ttu-id="2786c-114">指定对于本地资源是否跳过代理。</span><span class="sxs-lookup"><span data-stu-id="2786c-114">Specifies whether the proxy is bypassed for local resources.</span></span> <span data-ttu-id="2786c-115">本地资源包括本地服务器 (`http://localhost` 、 `http://loopback` 或 `http://127.0.0.1`) 以及不带句点的 URI (`http://webserver`) 。</span><span class="sxs-lookup"><span data-stu-id="2786c-115">Local resources include the local server (`http://localhost`, `http://loopback`, or `http://127.0.0.1`) and a URI without a period (`http://webserver`).</span></span> <span data-ttu-id="2786c-116">默认值是 `Unspecified`。</span><span class="sxs-lookup"><span data-stu-id="2786c-116">The default value is `Unspecified`.</span></span>|  
|`proxyaddress`|<span data-ttu-id="2786c-117">指定要使用的代理 URI。</span><span class="sxs-lookup"><span data-stu-id="2786c-117">Specifies the proxy URI to use.</span></span>|  
|`scriptLocation`|<span data-ttu-id="2786c-118">指定配置脚本的位置。</span><span class="sxs-lookup"><span data-stu-id="2786c-118">Specifies the location of the configuration script.</span></span> <span data-ttu-id="2786c-119">不要将 `bypassonlocal` 属性与此属性一起使用。</span><span class="sxs-lookup"><span data-stu-id="2786c-119">Do not use the `bypassonlocal` attribute with this attribute.</span></span> |  
|`usesystemdefault`|<span data-ttu-id="2786c-120">指定是否使用 Internet Explorer 代理设置。</span><span class="sxs-lookup"><span data-stu-id="2786c-120">Specifies whether to use Internet Explorer proxy settings.</span></span> <span data-ttu-id="2786c-121">如果设置为 `True` ，则后续特性将重写 Internet Explorer 代理设置。</span><span class="sxs-lookup"><span data-stu-id="2786c-121">If set to `True`, subsequent attributes will override Internet Explorer proxy settings.</span></span> <span data-ttu-id="2786c-122">默认值是 `Unspecified`。</span><span class="sxs-lookup"><span data-stu-id="2786c-122">The default value is `Unspecified`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2786c-123">子元素</span><span class="sxs-lookup"><span data-stu-id="2786c-123">Child Elements</span></span>  

 <span data-ttu-id="2786c-124">无。</span><span class="sxs-lookup"><span data-stu-id="2786c-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2786c-125">父元素</span><span class="sxs-lookup"><span data-stu-id="2786c-125">Parent Elements</span></span>  
  
|<span data-ttu-id="2786c-126">**元素**</span><span class="sxs-lookup"><span data-stu-id="2786c-126">**Element**</span></span>|<span data-ttu-id="2786c-127">**说明**</span><span class="sxs-lookup"><span data-stu-id="2786c-127">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2786c-128">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="2786c-128">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="2786c-129">配置超文本传输协议 (HTTP) 代理服务器。</span><span class="sxs-lookup"><span data-stu-id="2786c-129">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="text-value"></a><span data-ttu-id="2786c-130">文本值</span><span class="sxs-lookup"><span data-stu-id="2786c-130">Text Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2786c-131">备注</span><span class="sxs-lookup"><span data-stu-id="2786c-131">Remarks</span></span>  

 <span data-ttu-id="2786c-132">`proxy`元素为应用程序定义代理服务器。</span><span class="sxs-lookup"><span data-stu-id="2786c-132">The `proxy` element defines a proxy server for an application.</span></span> <span data-ttu-id="2786c-133">如果配置文件中缺少此元素，则 .NET Framework 将使用 Internet Explorer 中的代理设置。</span><span class="sxs-lookup"><span data-stu-id="2786c-133">If this element is missing from the configuration file, then the .NET Framework will use the proxy settings in Internet Explorer.</span></span>  
  
 <span data-ttu-id="2786c-134">特性的值 `proxyaddress` 应为格式正确的统一资源标识符 (URI) 。</span><span class="sxs-lookup"><span data-stu-id="2786c-134">The value for the `proxyaddress` attribute should be a well-formed Uniform Resource Indicator (URI).</span></span>  
  
 <span data-ttu-id="2786c-135">`scriptLocation`属性指自动检测代理配置脚本。</span><span class="sxs-lookup"><span data-stu-id="2786c-135">The `scriptLocation` attribute refers to the automatic detection of proxy configuration scripts.</span></span> <span data-ttu-id="2786c-136"><xref:System.Net.WebProxy>如果在 Internet Explorer 中选择了 "**使用自动配置脚本**" 选项，则类将尝试查找通常名为 Wpad .dat) 的配置 (脚本。</span><span class="sxs-lookup"><span data-stu-id="2786c-136">The <xref:System.Net.WebProxy> class will attempt to locate a configuration script (usually named Wpad.dat) when the **Use automatic configuration script** option is selected in Internet Explorer.</span></span> <span data-ttu-id="2786c-137">如果 `bypassonlocal` 设置为任何值， `scriptLocation` 则将被忽略。</span><span class="sxs-lookup"><span data-stu-id="2786c-137">If `bypassonlocal` is set to any value, `scriptLocation` is ignored.</span></span>
  
 <span data-ttu-id="2786c-138">将 `usesystemdefault` .NET Framework 版本1.1 应用程序的属性迁移到版本2.0。</span><span class="sxs-lookup"><span data-stu-id="2786c-138">Use the `usesystemdefault` attribute for .NET Framework version 1.1 applications that are migrating to version 2.0.</span></span>  
  
 <span data-ttu-id="2786c-139">如果 `proxyaddress` 特性指定了无效的默认代理，则会引发异常。</span><span class="sxs-lookup"><span data-stu-id="2786c-139">An exception is thrown if the `proxyaddress` attribute specifies an invalid default proxy.</span></span> <span data-ttu-id="2786c-140">异常的 <xref:System.Exception.InnerException%2A> 属性应具有错误根本原因的详细信息。</span><span class="sxs-lookup"><span data-stu-id="2786c-140">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="2786c-141">配置文件</span><span class="sxs-lookup"><span data-stu-id="2786c-141">Configuration Files</span></span>  

 <span data-ttu-id="2786c-142">此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。</span><span class="sxs-lookup"><span data-stu-id="2786c-142">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2786c-143">示例</span><span class="sxs-lookup"><span data-stu-id="2786c-143">Example</span></span>  

 <span data-ttu-id="2786c-144">以下示例使用 Internet Explorer 代理中的默认值，指定代理地址，并绕过代理进行本地访问。</span><span class="sxs-lookup"><span data-stu-id="2786c-144">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="True"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="True"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2786c-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="2786c-145">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="2786c-146">网络设置架构</span><span class="sxs-lookup"><span data-stu-id="2786c-146">Network Settings Schema</span></span>](index.md)
