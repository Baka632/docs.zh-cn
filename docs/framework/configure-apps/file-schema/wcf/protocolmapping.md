---
title: <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 5076644b-1f33-4f26-9488-87de9fcda04c
ms.openlocfilehash: 0a79aa18c74ddb8ec47f02620d16d391b4a36b68
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162291"
---
# \<protocolMapping>

<span data-ttu-id="b1857-101">表示一个配置节，用于定义传输协议方案（如 http、net.tcp、net.pipe 等）和 WCF 绑定之间的一组默认协议映射。</span><span class="sxs-lookup"><span data-stu-id="b1857-101">Represents a configuration section for defining a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span> <span data-ttu-id="b1857-102">在运行时创建默认终结点时，Windows Communication Foundation (WCF) 会查看已配置的映射，并决定要将哪个绑定用于特定的地址。</span><span class="sxs-lookup"><span data-stu-id="b1857-102">When creating default endpoints at runtime, Windows Communication Foundation (WCF) looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<protocolMapping>**  
  
## <a name="syntax"></a><span data-ttu-id="b1857-103">语法</span><span class="sxs-lookup"><span data-stu-id="b1857-103">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b1857-104">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b1857-104">Attributes and Elements</span></span>  

 <span data-ttu-id="b1857-105">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b1857-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b1857-106">特性</span><span class="sxs-lookup"><span data-stu-id="b1857-106">Attributes</span></span>  

 <span data-ttu-id="b1857-107">无。</span><span class="sxs-lookup"><span data-stu-id="b1857-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b1857-108">子元素</span><span class="sxs-lookup"><span data-stu-id="b1857-108">Child Elements</span></span>  
  
|<span data-ttu-id="b1857-109">元素</span><span class="sxs-lookup"><span data-stu-id="b1857-109">Element</span></span>|<span data-ttu-id="b1857-110">描述</span><span class="sxs-lookup"><span data-stu-id="b1857-110">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="b1857-111">包含传输协议方案（如 http、net.tcp、net.pipe 等）和 WCF 绑定之间的默认协议映射。</span><span class="sxs-lookup"><span data-stu-id="b1857-111">Contains a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a WCF binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b1857-112">父元素</span><span class="sxs-lookup"><span data-stu-id="b1857-112">Parent Elements</span></span>  
  
|<span data-ttu-id="b1857-113">元素</span><span class="sxs-lookup"><span data-stu-id="b1857-113">Element</span></span>|<span data-ttu-id="b1857-114">描述</span><span class="sxs-lookup"><span data-stu-id="b1857-114">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](system-servicemodel.md)|<span data-ttu-id="b1857-115">所有 WCF 配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="b1857-115">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b1857-116">示例</span><span class="sxs-lookup"><span data-stu-id="b1857-116">Example</span></span>  

 <span data-ttu-id="b1857-117">下面的配置示例演示 machine.config 文件中的默认协议映射。</span><span class="sxs-lookup"><span data-stu-id="b1857-117">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="b1857-118">您可以通过修改 machine.config 文件在计算机级别重写此默认映射。</span><span class="sxs-lookup"><span data-stu-id="b1857-118">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="b1857-119">或者，如果您只希望在应用程序范围内重写此映射，则可以在应用程序配置文件中重写此节，并为单独的协议方案更改映射。</span><span class="sxs-lookup"><span data-stu-id="b1857-119">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
```xml  
<protocolMapping>
  <add scheme="http"
       binding="basicHttpBinding" />
  <add scheme="net.tcp"
       binding="netTcpBinding" />
  <add scheme="net.pipe"
       binding="netNamedPipeBinding" />
  <add scheme="net.msmq"
       binding="netMsmqBinding" />
</protocolMapping>
```  
  
## <a name="see-also"></a><span data-ttu-id="b1857-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="b1857-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>
