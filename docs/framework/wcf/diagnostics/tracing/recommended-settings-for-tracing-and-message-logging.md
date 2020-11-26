---
title: 跟踪和消息日志记录的推荐设置
description: 了解 WCF 中不同操作环境的推荐跟踪和消息日志记录设置。
ms.date: 03/30/2017
ms.assetid: c6aca6e8-704e-4779-a9ef-50c46850249e
ms.openlocfilehash: b23298b8ee95b3bcd61a3712e9ff91acf6a6a3e9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96240090"
---
# <a name="recommended-settings-for-tracing-and-message-logging"></a><span data-ttu-id="e9c3e-103">跟踪和消息日志记录的推荐设置</span><span class="sxs-lookup"><span data-stu-id="e9c3e-103">Recommended Settings for Tracing and Message Logging</span></span>

<span data-ttu-id="e9c3e-104">本主题描述用于不同操作环境的跟踪和消息日志记录的推荐设置。</span><span class="sxs-lookup"><span data-stu-id="e9c3e-104">This topic describes recommended tracing and message logging settings for different operating environments.</span></span>  
  
## <a name="recommended-settings-for-a-production-environment"></a><span data-ttu-id="e9c3e-105">生产环境中的推荐设置</span><span class="sxs-lookup"><span data-stu-id="e9c3e-105">Recommended Settings for a Production Environment</span></span>  

 <span data-ttu-id="e9c3e-106">对于生产环境，如果您使用的是 WCF 跟踪源，请将 `switchValue` 设置为“警告”。</span><span class="sxs-lookup"><span data-stu-id="e9c3e-106">For a production environment, if you are using WCF trace sources, set the `switchValue` to Warning.</span></span> <span data-ttu-id="e9c3e-107">如果您使用的是 WCF `System.ServiceModel` 跟踪源，请将 `switchValue` 属性设置为 `Warning`，并将 `propagateActivity` 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="e9c3e-107">If you are using the WCF `System.ServiceModel` trace source, set the `switchValue` attribute to `Warning` and the `propagateActivity` attribute to `true`.</span></span> <span data-ttu-id="e9c3e-108">如果您使用的是用户定义的跟踪源，请将 `switchValue` 属性设置为 `Warning, ActivityTracing`。</span><span class="sxs-lookup"><span data-stu-id="e9c3e-108">If you are using a user-defined trace source, set the `switchValue` attribute to `Warning, ActivityTracing`.</span></span> <span data-ttu-id="e9c3e-109">这可以使用 [配置编辑器工具 ( # A0) ](../../configuration-editor-tool-svcconfigeditor-exe.md)手动完成。</span><span class="sxs-lookup"><span data-stu-id="e9c3e-109">This can be done manually using the [Configuration Editor Tool (SvcConfigEditor.exe)](../../configuration-editor-tool-svcconfigeditor-exe.md).</span></span> <span data-ttu-id="e9c3e-110">如果你没有预测性能情况，则可以在上述所有情况中，将 `switchValue` 属性设置为 `Information`，这将生成大量的跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="e9c3e-110">If you do not anticipate a hit in performance, you can set the `switchValue` attribute to `Information` in all the previously mentioned cases, which generates a fairly large amount of trace data.</span></span> <span data-ttu-id="e9c3e-111">下面的示例演示这些推荐的设置。</span><span class="sxs-lookup"><span data-stu-id="e9c3e-111">The following example demonstrates these recommended settings.</span></span>  
  
```xml  
<configuration>  
 <system.diagnostics>  
  <sources>  
    <source name="System.ServiceModel"  
            switchValue="Warning"  
            propagateActivity="true" >  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="myUserTraceSource"  
            switchValue="Warning, ActivityTracing">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add name="xml"  
         type="System.Diagnostics.XmlWriterTraceListener"  
               initializeData="C:\logs\Traces.svclog" />  
  </sharedListeners>  
 </system.diagnostics>  
  
<system.serviceModel>  
  <diagnostics wmiProviderEnabled="true">  
  </diagnostics>  
 </system.serviceModel>  
</configuration>  
```  
  
## <a name="recommended-settings-for-deployment-or-debugging"></a><span data-ttu-id="e9c3e-112">用于部署或调试的推荐设置</span><span class="sxs-lookup"><span data-stu-id="e9c3e-112">Recommended Settings for Deployment or Debugging</span></span>  

 <span data-ttu-id="e9c3e-113">对于部署或调试环境，请为用户定义的或 `Information` 跟踪源选择 `Verbose` 或 `ActivityTracing`，以及 `System.ServiceModel`。</span><span class="sxs-lookup"><span data-stu-id="e9c3e-113">For deployment or debugging environment, choose `Information` or `Verbose`, along with `ActivityTracing` for either a user-defined or `System.ServiceModel` trace source.</span></span> <span data-ttu-id="e9c3e-114">若要增强调试功能，也应将其他跟踪源 (`System.ServiceModel.MessageLogging`) 添加到配置中以启用消息日志记录。</span><span class="sxs-lookup"><span data-stu-id="e9c3e-114">To enhance debugging, you should also add an additional trace source (`System.ServiceModel.MessageLogging`) to the configuration to enable message logging.</span></span> <span data-ttu-id="e9c3e-115">请注意，`switchValue` 属性对此跟踪源没有任何影响。</span><span class="sxs-lookup"><span data-stu-id="e9c3e-115">Notice that the `switchValue` attribute has no impact on this trace source.</span></span>  
  
 <span data-ttu-id="e9c3e-116">下面的示例通过使用利用了 `XmlWriterTraceListener` 的共享侦听器来演示推荐的设置。</span><span class="sxs-lookup"><span data-stu-id="e9c3e-116">The following example demonstrates the recommended settings, using a shared listener that utilizes the `XmlWriterTraceListener`.</span></span>  
  
```xml  
<configuration>  
 <system.diagnostics>  
  <sources>  
    <source name="System.ServiceModel"  
            switchValue="Information, ActivityTracing"  
            propagateActivity="true" >  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="System.ServiceModel.MessageLogging">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="myUserTraceSource"  
            switchValue="Information, ActivityTracing">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add name="xml"  
         type="System.Diagnostics.XmlWriterTraceListener"  
               initializeData="C:\logs\Traces.svclog" />  
  </sharedListeners>  
 </system.diagnostics>  
  
 <system.serviceModel>  
  <diagnostics wmiProviderEnabled="true">  
      <messageLogging
           logEntireMessage="true"
           logMalformedMessages="true"  
           logMessagesAtServiceLevel="true"
           logMessagesAtTransportLevel="true"  
           maxMessagesToLog="3000"
       />  
  </diagnostics>  
 </system.serviceModel>  
</configuration>  
```  
  
## <a name="using-wmi-to-modify-settings"></a><span data-ttu-id="e9c3e-117">使用 WMI 修改设置</span><span class="sxs-lookup"><span data-stu-id="e9c3e-117">Using WMI to Modify Settings</span></span>  

 <span data-ttu-id="e9c3e-118">可以使用 WMI 更改运行时的配置设置（通过按照上述配置示例，启用配置中的 `wmiProviderEnabled` 属性）。</span><span class="sxs-lookup"><span data-stu-id="e9c3e-118">You can use WMI to change configuration settings at runtime (by enabling the `wmiProviderEnabled` attribute in the configuration, as demonstrated in the previously configuration example).</span></span> <span data-ttu-id="e9c3e-119">例如，可以在运行时使用 CIM Studio 中的 WMI 将跟踪源级别从“警告”更改为“信息”。</span><span class="sxs-lookup"><span data-stu-id="e9c3e-119">For example, you can use WMI within the CIM Studio to change the trace source levels from Warning to Information at runtime.</span></span> <span data-ttu-id="e9c3e-120">应该注意，这种方式的即时调试的性能开销可能非常高。</span><span class="sxs-lookup"><span data-stu-id="e9c3e-120">You should be aware that the performance cost of live debugging in this way can be very high.</span></span> <span data-ttu-id="e9c3e-121">有关使用 WMI 的详细信息，请参阅 [使用诊断 Windows Management Instrumentation](../wmi/index.md) 主题。</span><span class="sxs-lookup"><span data-stu-id="e9c3e-121">For more information about using WMI, see the [Using Windows Management Instrumentation for Diagnostics](../wmi/index.md) topic.</span></span>  
  
## <a name="enable-correlated-events-in-aspnet-tracing"></a><span data-ttu-id="e9c3e-122">在 ASP.NET 跟踪中启用相关事件</span><span class="sxs-lookup"><span data-stu-id="e9c3e-122">Enable Correlated Events in ASP.NET Tracing</span></span>  

 <span data-ttu-id="e9c3e-123">除非启用了 ASP.NET 事件跟踪，否则 ASP.NET 事件不会设置关联 ID (ActivityID)。</span><span class="sxs-lookup"><span data-stu-id="e9c3e-123">ASP.NET events do not set the correlation ID (ActivityID) unless ASP.NET event tracing is turned on.</span></span> <span data-ttu-id="e9c3e-124">若要正确查看相关事件，必须使用命令控制台中的以下命令打开 ASP.NET 事件跟踪，可通过转到 " **启动**"、" **运行** " 并键入 **cmd** 来调用它。</span><span class="sxs-lookup"><span data-stu-id="e9c3e-124">To see correlated events properly, you have to turn on ASP.NET events tracing using the following command in the command console, which can be invoked by going to **Start**, **Run** and type **cmd**,</span></span>  
  
```console  
logman start mytrace -pf logman.providers -o test.etl –ets  
```  
  
 <span data-ttu-id="e9c3e-125">若要关闭 ASP.NET 事件跟踪，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="e9c3e-125">To turn off tracing of ASP.NET events, use the following command,</span></span>  
  
```console
logman stop mytrace -ets  
```  
  
## <a name="see-also"></a><span data-ttu-id="e9c3e-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e9c3e-126">See also</span></span>

- [<span data-ttu-id="e9c3e-127">使用 Windows Management Instrumentation 诊断</span><span class="sxs-lookup"><span data-stu-id="e9c3e-127">Using Windows Management Instrumentation for Diagnostics</span></span>](../wmi/index.md)
