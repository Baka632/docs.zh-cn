---
title: 配置跟踪
description: 了解如何启用跟踪、配置跟踪源、设置活动跟踪和传播，以及如何设置跟踪侦听器以访问 WCF 中的跟踪。
ms.date: 03/30/2017
helpviewer_keywords:
- tracing [WCF]
ms.assetid: 82922010-e8b3-40eb-98c4-10fc05c6d65d
ms.openlocfilehash: 35ac2dded5b3c727391fcad3ca950c2de4dbea64
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254436"
---
# <a name="configuring-tracing"></a><span data-ttu-id="a9fde-103">配置跟踪</span><span class="sxs-lookup"><span data-stu-id="a9fde-103">Configuring Tracing</span></span>

<span data-ttu-id="a9fde-104">本主题描述您可以如何启用跟踪，配置要发出跟踪的跟踪源并设置跟踪级别，设置活动跟踪和传播以支持端对端的跟踪关联，以及设置要访问跟踪的跟踪侦听器。</span><span class="sxs-lookup"><span data-stu-id="a9fde-104">This topic describes how you can enable tracing, configure trace sources to emit traces and set trace levels, set activity tracing and propagation to support end-to-end trace correlation, and set trace listeners to access traces.</span></span>  
  
 <span data-ttu-id="a9fde-105">有关生产或调试环境中的跟踪设置建议，请参阅 [建议用于跟踪和消息日志记录的设置](recommended-settings-for-tracing-and-message-logging.md)。</span><span class="sxs-lookup"><span data-stu-id="a9fde-105">For tracing settings recommendations in production or debugging environment, refer to [Recommended Settings for Tracing and Message Logging](recommended-settings-for-tracing-and-message-logging.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a9fde-106">在 Windows 8 上，您必须以提升的权限（以管理员身份运行）运行应用程序，应用程序才能生成跟踪日志。</span><span class="sxs-lookup"><span data-stu-id="a9fde-106">On Windows 8 you must run your application elevated (Run as Administrator) in order for your application to generate trace logs.</span></span>  
  
## <a name="enabling-tracing"></a><span data-ttu-id="a9fde-107">启用跟踪</span><span class="sxs-lookup"><span data-stu-id="a9fde-107">Enabling Tracing</span></span>  

 <span data-ttu-id="a9fde-108">Windows Communication Foundation (WCF) 输出用于诊断跟踪的以下数据：</span><span class="sxs-lookup"><span data-stu-id="a9fde-108">Windows Communication Foundation (WCF) outputs the following data for diagnostic tracing:</span></span>  
  
- <span data-ttu-id="a9fde-109">跟踪跨应用程序的所有组件的进程里程碑，如操作调用、代码异常、警告和其他重要处理事件。</span><span class="sxs-lookup"><span data-stu-id="a9fde-109">Traces for process milestones across all components of the applications, such as operation calls, code exceptions, warnings, and other significant processing events.</span></span>  
  
- <span data-ttu-id="a9fde-110">跟踪功能出现故障时发生的 Windows 错误事件。</span><span class="sxs-lookup"><span data-stu-id="a9fde-110">Windows error events when the tracing feature malfunctions.</span></span> <span data-ttu-id="a9fde-111">请参阅 [事件日志记录](../event-logging/index.md)。</span><span class="sxs-lookup"><span data-stu-id="a9fde-111">See [Event Logging](../event-logging/index.md).</span></span>  
  
 <span data-ttu-id="a9fde-112">WCF 跟踪在上构建 <xref:System.Diagnostics> 。</span><span class="sxs-lookup"><span data-stu-id="a9fde-112">WCF tracing is built on top of <xref:System.Diagnostics>.</span></span> <span data-ttu-id="a9fde-113">若要使用跟踪，应在配置文件或代码中定义跟踪源。</span><span class="sxs-lookup"><span data-stu-id="a9fde-113">To use tracing, you should define trace sources in the configuration file or in code.</span></span> <span data-ttu-id="a9fde-114">WCF 为每个 WCF 程序集定义一个跟踪源。</span><span class="sxs-lookup"><span data-stu-id="a9fde-114">WCF defines a trace source for each WCF assembly.</span></span> <span data-ttu-id="a9fde-115">`System.ServiceModel`跟踪源是最常规的 wcf 跟踪源，用于在 wcf 通信堆栈中记录处理里程碑，从进入/离开传输到输入/离开用户代码。</span><span class="sxs-lookup"><span data-stu-id="a9fde-115">The `System.ServiceModel` trace source is the most general WCF trace source, and records processing milestones across the WCF communication stack, from entering/leaving transport to entering/leaving user code.</span></span> <span data-ttu-id="a9fde-116">`System.ServiceModel.MessageLogging` 跟踪源记录流过系统的所有消息。</span><span class="sxs-lookup"><span data-stu-id="a9fde-116">The `System.ServiceModel.MessageLogging` trace source records all messages that flow through the system.</span></span>  
  
 <span data-ttu-id="a9fde-117">默认情况下不启用跟踪。</span><span class="sxs-lookup"><span data-stu-id="a9fde-117">Tracing is not enabled by default.</span></span> <span data-ttu-id="a9fde-118">若要激活跟踪，必须在配置中创建跟踪侦听器并为所选跟踪源设置除 "Off" 之外的跟踪级别;否则，WCF 不会生成任何跟踪。</span><span class="sxs-lookup"><span data-stu-id="a9fde-118">To activate tracing, you must create a trace listener and set a trace level other than "Off" for the selected trace source in configuration; otherwise, WCF does not generate any traces.</span></span> <span data-ttu-id="a9fde-119">如果不指定侦听器，则会自动禁用跟踪。</span><span class="sxs-lookup"><span data-stu-id="a9fde-119">If you do not specify a listener, tracing is automatically disabled.</span></span> <span data-ttu-id="a9fde-120">如果定义侦听器，但不指定级别，则默认情况下级别将设置为“Off”，这意味着不会发出任何跟踪。</span><span class="sxs-lookup"><span data-stu-id="a9fde-120">If a listener is defined, but no level is specified, the level is set to "Off" by default, which means that no trace is emitted.</span></span>  
  
 <span data-ttu-id="a9fde-121">如果使用 WCF 扩展点（如自定义操作调用程序），则应发出自己的跟踪。</span><span class="sxs-lookup"><span data-stu-id="a9fde-121">If you use WCF extensibility points such as custom operation invokers, you should emit your own traces.</span></span> <span data-ttu-id="a9fde-122">这是因为，如果实现扩展点，WCF 就不能再在默认路径中发出标准跟踪。</span><span class="sxs-lookup"><span data-stu-id="a9fde-122">This is because if you implement an extensibility point, WCF can no longer emit the standard traces in the default path.</span></span> <span data-ttu-id="a9fde-123">如果未通过发出跟踪实现手动跟踪支持，则可能看不到预期跟踪。</span><span class="sxs-lookup"><span data-stu-id="a9fde-123">If you do not implement manual tracing support by emitting traces, you may not see the traces you expect.</span></span>  
  
 <span data-ttu-id="a9fde-124">你可以通过编辑应用程序的配置文件来配置跟踪，Web.config 用于 Web 承载的应用程序，或者 Appname.exe.config 用于自承载应用程序。</span><span class="sxs-lookup"><span data-stu-id="a9fde-124">You can configure tracing by editing the application's configuration file—either Web.config for Web-hosted applications, or Appname.exe.config for self-hosted applications.</span></span> <span data-ttu-id="a9fde-125">下面的示例演示如何进行这样的编辑。</span><span class="sxs-lookup"><span data-stu-id="a9fde-125">The following is an example of such edit.</span></span> <span data-ttu-id="a9fde-126">有关这些设置的详细信息，请参阅 "将跟踪侦听器配置为使用跟踪" 部分。</span><span class="sxs-lookup"><span data-stu-id="a9fde-126">For more information on these settings, see the "Configuring Trace Listeners to Consume Traces" section.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <sources>  
         <source name="System.ServiceModel"
                    switchValue="Information, ActivityTracing"  
                    propagateActivity="true">  
            <listeners>  
               <add name="traceListener"
                   type="System.Diagnostics.XmlWriterTraceListener"
                   initializeData= "c:\log\Traces.svclog" />  
            </listeners>  
         </source>  
      </sources>  
   </system.diagnostics>  
</configuration>  
```  
  
> [!NOTE]
> <span data-ttu-id="a9fde-127">若要在 Visual Studio 中编辑 WCF 服务项目的配置文件，请右键单击该应用程序的配置文件（对于 Web 承载的应用程序为 Web.config）或 **解决方案资源管理器** 中自承载的应用程序的 Appname.exe.config。</span><span class="sxs-lookup"><span data-stu-id="a9fde-127">To edit the configuration file of a WCF service project in Visual Studio, right click the application's configuration file—either Web.config for Web-hosted applications, or Appname.exe.config for self-hosted application in **Solution Explorer**.</span></span> <span data-ttu-id="a9fde-128">然后选择 " **编辑 WCF 配置** " 上下文菜单项。</span><span class="sxs-lookup"><span data-stu-id="a9fde-128">Then choose the **Edit WCF Configuration** context menu item.</span></span> <span data-ttu-id="a9fde-129">这将启动 [ ( # A0) 的配置编辑器工具 ](../../configuration-editor-tool-svcconfigeditor-exe.md)，该工具使你能够使用图形用户界面修改 WCF 服务的配置设置。</span><span class="sxs-lookup"><span data-stu-id="a9fde-129">This launches the [Configuration Editor Tool (SvcConfigEditor.exe)](../../configuration-editor-tool-svcconfigeditor-exe.md), which enables you to modify configuration settings for WCF services using a graphical user interface.</span></span>  
  
## <a name="configuring-trace-sources-to-emit-traces"></a><span data-ttu-id="a9fde-130">配置要发出跟踪的跟踪源</span><span class="sxs-lookup"><span data-stu-id="a9fde-130">Configuring Trace Sources to Emit Traces</span></span>  

 <span data-ttu-id="a9fde-131">WCF 为每个程序集定义一个跟踪源。</span><span class="sxs-lookup"><span data-stu-id="a9fde-131">WCF defines a trace source for each assembly.</span></span> <span data-ttu-id="a9fde-132">在程序集中生成的跟踪由为该跟踪源定义的侦听器访问。</span><span class="sxs-lookup"><span data-stu-id="a9fde-132">Traces generated within an assembly are accessed by the listeners defined for that source.</span></span> <span data-ttu-id="a9fde-133">定义下列跟踪源：</span><span class="sxs-lookup"><span data-stu-id="a9fde-133">The following trace sources are defined:</span></span>  
  
- <span data-ttu-id="a9fde-134">System.servicemodel：记录 WCF 处理的所有阶段，只要读取配置，就会在传输中处理消息，安全处理，在用户代码中调度消息，等等。</span><span class="sxs-lookup"><span data-stu-id="a9fde-134">System.ServiceModel: Logs all stages of WCF processing, whenever configuration is read, a message is processed in transport, security processing, a message is dispatched in user code, and so on.</span></span>  
  
- <span data-ttu-id="a9fde-135">System.ServiceModel.MessageLogging：记录流过系统的所有消息。</span><span class="sxs-lookup"><span data-stu-id="a9fde-135">System.ServiceModel.MessageLogging: Logs all messages that flow through the system.</span></span>  
  
- <span data-ttu-id="a9fde-136">System.IdentityModel。</span><span class="sxs-lookup"><span data-stu-id="a9fde-136">System.IdentityModel.</span></span>  
  
- <span data-ttu-id="a9fde-137">System.ServiceModel.Activation。</span><span class="sxs-lookup"><span data-stu-id="a9fde-137">System.ServiceModel.Activation.</span></span>  
  
- <span data-ttu-id="a9fde-138">System.IO.Log：记录公用日志文件系统 (CLFS) 的 .NET Framework 接口。</span><span class="sxs-lookup"><span data-stu-id="a9fde-138">System.IO.Log: Logging for the .NET Framework interface to the Common Log File System (CLFS).</span></span>  
  
- <span data-ttu-id="a9fde-139">System.Runtime.Serialization：在读/写对象时进行记录。</span><span class="sxs-lookup"><span data-stu-id="a9fde-139">System.Runtime.Serialization: Logs when objects are read or written.</span></span>  
  
- <span data-ttu-id="a9fde-140">CardSpace。</span><span class="sxs-lookup"><span data-stu-id="a9fde-140">CardSpace.</span></span>  
  
 <span data-ttu-id="a9fde-141">可以将每个跟踪源配置为使用相同（共享）的侦听器，如下面的配置示例中所示。</span><span class="sxs-lookup"><span data-stu-id="a9fde-141">You can configure each trace source to use the same (shared) listener, as indicated in the following configuration example.</span></span>  
  
```xml  
<configuration>  
    <system.diagnostics>  
        <sources>  
            <source name="System.ServiceModel"
                    switchValue="Information, ActivityTracing"  
                    propagateActivity="true">  
                <listeners>  
                    <add name="xml" />  
                </listeners>  
            </source>  
            <source name="CardSpace">  
                <listeners>  
                    <add name="xml" />  
                </listeners>  
            </source>  
            <source name="System.IO.Log">  
                <listeners>  
                    <add name="xml" />  
                </listeners>  
            </source>  
            <source name="System.Runtime.Serialization">  
                <listeners>  
                    <add name="xml" />  
                </listeners>  
            </source>  
            <source name="System.IdentityModel">  
                <listeners>  
                    <add name="xml" />  
                </listeners>  
            </source>  
        </sources>  
  
        <sharedListeners>  
            <add name="xml"  
                 type="System.Diagnostics.XmlWriterTraceListener"  
                 initializeData="c:\log\Traces.svclog" />  
        </sharedListeners>  
    </system.diagnostics>  
</configuration>  
```  
  
 <span data-ttu-id="a9fde-142">另外，还可以添加用户定义的跟踪源来发出用户代码跟踪，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="a9fde-142">In addition, you can add user-defined trace sources, as demonstrated by the following example, to emit user code traces.</span></span>  
  
```xml  
<system.diagnostics>  
   <sources>  
       <source name="UserTraceSource" switchValue="Warning, ActivityTracing" >  
          <listeners>  
              <add name="xml"  
                 type="System.Diagnostics.XmlWriterTraceListener"  
                 initializeData="C:\logs\UserTraces.svclog" />  
          </listeners>  
       </source>  
   </sources>  
   <trace autoflush="true" />
</system.diagnostics>  
```  
  
 <span data-ttu-id="a9fde-143">有关创建用户定义的跟踪源的详细信息，请参阅 [扩展跟踪](../../samples/extending-tracing.md)。</span><span class="sxs-lookup"><span data-stu-id="a9fde-143">For more information about creating user-defined trace sources, see [Extending Tracing](../../samples/extending-tracing.md).</span></span>  
  
## <a name="configuring-trace-listeners-to-consume-traces"></a><span data-ttu-id="a9fde-144">配置要使用跟踪的跟踪侦听器</span><span class="sxs-lookup"><span data-stu-id="a9fde-144">Configuring Trace Listeners to Consume Traces</span></span>  

 <span data-ttu-id="a9fde-145">在运行时，WCF 将跟踪数据到侦听器，这些侦听器用于处理数据。</span><span class="sxs-lookup"><span data-stu-id="a9fde-145">At runtime, WCF feeds trace data to the listeners, which process the data.</span></span> <span data-ttu-id="a9fde-146">WCF 为提供了多个预定义的侦听器 <xref:System.Diagnostics> ，这些侦听器在输出时使用的格式不同。</span><span class="sxs-lookup"><span data-stu-id="a9fde-146">WCF provides several predefined listeners for <xref:System.Diagnostics>, which differ in the format they use for output.</span></span> <span data-ttu-id="a9fde-147">您也可以添加自定义侦听器类型。</span><span class="sxs-lookup"><span data-stu-id="a9fde-147">You can also add custom listener types.</span></span>  
  
 <span data-ttu-id="a9fde-148">可以使用 `add` 指定要使用的跟踪侦听器的名称和类型。</span><span class="sxs-lookup"><span data-stu-id="a9fde-148">You can use `add` to specify the name and type of the trace listener you want to use.</span></span> <span data-ttu-id="a9fde-149">在示例配置中，将侦听器命名为 `traceListener` 并添加了标准 .NET Framework 跟踪侦听器 (`System.Diagnostics.XmlWriterTraceListener`) 作为要使用的类型。</span><span class="sxs-lookup"><span data-stu-id="a9fde-149">In our example configuration, we named the Listener `traceListener` and added the standard .NET Framework trace listener (`System.Diagnostics.XmlWriterTraceListener`) as the type we want to use.</span></span> <span data-ttu-id="a9fde-150">可以为每个源添加任意数目的跟踪侦听器。</span><span class="sxs-lookup"><span data-stu-id="a9fde-150">You can add any number of trace listeners for each source.</span></span> <span data-ttu-id="a9fde-151">如果跟踪侦听器发出对文件的跟踪，则您必须在配置文件中指定输出文件的位置和名称。</span><span class="sxs-lookup"><span data-stu-id="a9fde-151">If the trace listener emits the trace to a file, you must specify the output file location and name in the configuration file.</span></span> <span data-ttu-id="a9fde-152">通过将 `initializeData` 设置为该侦听器的文件名称来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="a9fde-152">This is done by setting `initializeData` to the name of the file for that listener.</span></span> <span data-ttu-id="a9fde-153">如果不指定文件名，则会基于所用的侦听器类型生成一个随机文件名。</span><span class="sxs-lookup"><span data-stu-id="a9fde-153">If you do not specify a file name, a random file name is generated based on the listener type used.</span></span> <span data-ttu-id="a9fde-154">如果使用 <xref:System.Diagnostics.XmlWriterTraceListener>，则会生成不带扩展名的文件名。</span><span class="sxs-lookup"><span data-stu-id="a9fde-154">If <xref:System.Diagnostics.XmlWriterTraceListener> is used, a file name with no extension is generated.</span></span> <span data-ttu-id="a9fde-155">如果实现自定义侦听器，则也可以使用此属性来接收除文件名以外的初始化数据。</span><span class="sxs-lookup"><span data-stu-id="a9fde-155">If you implement a custom listener, you can also use this attribute to receive initialization data other than a filename.</span></span> <span data-ttu-id="a9fde-156">例如，可以为此属性指定数据库标识符。</span><span class="sxs-lookup"><span data-stu-id="a9fde-156">For example, you can specify a database identifier for this attribute.</span></span>  
  
 <span data-ttu-id="a9fde-157">可以将自定义跟踪侦听器配置为在网络上发送跟踪，例如，发送到远程数据库。</span><span class="sxs-lookup"><span data-stu-id="a9fde-157">You can configure a custom trace listener to send traces on the wire, for example, to a remote database.</span></span> <span data-ttu-id="a9fde-158">作为应用程序部署人员，您应对远程计算机上的跟踪日志施加适当的访问控制。</span><span class="sxs-lookup"><span data-stu-id="a9fde-158">As an application deployer, you should enforce proper access control on the trace logs in the remote machine.</span></span>  
  
 <span data-ttu-id="a9fde-159">您也可以通过编程方式配置跟踪侦听器。</span><span class="sxs-lookup"><span data-stu-id="a9fde-159">You can also configure a trace listener programmatically.</span></span> <span data-ttu-id="a9fde-160">有关详细信息，请参阅 [如何：创建和初始化跟踪侦听器](../../../debug-trace-profile/how-to-create-and-initialize-trace-listeners.md) 以及 [创建自定义 TraceListener](/archive/msdn-magazine/2006/april/clr-inside-out-extending-system-diagnostics)。</span><span class="sxs-lookup"><span data-stu-id="a9fde-160">For more information, see [How to: Create and Initialize Trace Listeners](../../../debug-trace-profile/how-to-create-and-initialize-trace-listeners.md) and [Creating a Custom TraceListener](/archive/msdn-magazine/2006/april/clr-inside-out-extending-system-diagnostics).</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="a9fde-161">由于 `System.Diagnostics.XmlWriterTraceListener` 不是线程安全的，因此，跟踪源可能会在输出跟踪时以独占方式锁定资源。</span><span class="sxs-lookup"><span data-stu-id="a9fde-161">Because `System.Diagnostics.XmlWriterTraceListener` is not thread-safe, the trace source may lock resources exclusively when outputting traces.</span></span> <span data-ttu-id="a9fde-162">当多个线程输出对配置为使用此侦听器的跟踪源的跟踪时，可能会出现资源争用，这会致使重大的性能问题。</span><span class="sxs-lookup"><span data-stu-id="a9fde-162">When many threads output traces to a trace source configured to use this listener, resource contention may occur, which results in a significant performance issue.</span></span> <span data-ttu-id="a9fde-163">若要解决此问题，应实现一个线程安全的自定义侦听器。</span><span class="sxs-lookup"><span data-stu-id="a9fde-163">To resolve this problem, you should implement a custom listener that is thread-safe.</span></span>  
  
## <a name="trace-level"></a><span data-ttu-id="a9fde-164">跟踪级别</span><span class="sxs-lookup"><span data-stu-id="a9fde-164">Trace Level</span></span>  

 <span data-ttu-id="a9fde-165">跟踪级别由跟踪源的 `switchValue` 设置控制。</span><span class="sxs-lookup"><span data-stu-id="a9fde-165">The tracing level is controlled by the `switchValue` setting of the trace source.</span></span> <span data-ttu-id="a9fde-166">下表中描述了可用的跟踪级别。</span><span class="sxs-lookup"><span data-stu-id="a9fde-166">The available tracing levels are described in the following table.</span></span>  
  
|<span data-ttu-id="a9fde-167">跟踪级别</span><span class="sxs-lookup"><span data-stu-id="a9fde-167">Trace Level</span></span>|<span data-ttu-id="a9fde-168">被跟踪事件的特性</span><span class="sxs-lookup"><span data-stu-id="a9fde-168">Nature of the Tracked Events</span></span>|<span data-ttu-id="a9fde-169">被跟踪事件的内容</span><span class="sxs-lookup"><span data-stu-id="a9fde-169">Content of the Tracked Events</span></span>|<span data-ttu-id="a9fde-170">被跟踪事件</span><span class="sxs-lookup"><span data-stu-id="a9fde-170">Tracked Events</span></span>|<span data-ttu-id="a9fde-171">用户目标</span><span class="sxs-lookup"><span data-stu-id="a9fde-171">User Target</span></span>|  
|-----------------|----------------------------------|-----------------------------------|--------------------|-----------------|  
|<span data-ttu-id="a9fde-172">关</span><span class="sxs-lookup"><span data-stu-id="a9fde-172">Off</span></span>|<span data-ttu-id="a9fde-173">不适用</span><span class="sxs-lookup"><span data-stu-id="a9fde-173">N/A</span></span>|<span data-ttu-id="a9fde-174">不适用</span><span class="sxs-lookup"><span data-stu-id="a9fde-174">N/A</span></span>|<span data-ttu-id="a9fde-175">不发出任何跟踪。</span><span class="sxs-lookup"><span data-stu-id="a9fde-175">No traces are emitted.</span></span>|<span data-ttu-id="a9fde-176">不适用</span><span class="sxs-lookup"><span data-stu-id="a9fde-176">N/A</span></span>|  
|<span data-ttu-id="a9fde-177">关键</span><span class="sxs-lookup"><span data-stu-id="a9fde-177">Critical</span></span>|<span data-ttu-id="a9fde-178">"负面" 事件：指示意外处理或错误情况的事件。</span><span class="sxs-lookup"><span data-stu-id="a9fde-178">"Negative" events: events that indicate an unexpected processing or an error condition.</span></span>||<span data-ttu-id="a9fde-179">将记录包括下列各项的未经处理的异常：</span><span class="sxs-lookup"><span data-stu-id="a9fde-179">Unhandled exceptions including the following are logged:</span></span><br /><br /> <span data-ttu-id="a9fde-180">-OutOfMemoryException</span><span class="sxs-lookup"><span data-stu-id="a9fde-180">-   OutOfMemoryException</span></span><br /><span data-ttu-id="a9fde-181">-ThreadAbortException (CLR 调用任何 ThreadAbortExceptionHandler) </span><span class="sxs-lookup"><span data-stu-id="a9fde-181">-   ThreadAbortException (the CLR invokes any ThreadAbortExceptionHandler)</span></span><br /><span data-ttu-id="a9fde-182">-无法捕获 StackOverflowException () </span><span class="sxs-lookup"><span data-stu-id="a9fde-182">-   StackOverflowException (cannot be caught)</span></span><br /><span data-ttu-id="a9fde-183">-System.configuration.configurationerrorsexception</span><span class="sxs-lookup"><span data-stu-id="a9fde-183">-   ConfigurationErrorsException</span></span><br /><span data-ttu-id="a9fde-184">-SEHException</span><span class="sxs-lookup"><span data-stu-id="a9fde-184">-   SEHException</span></span><br /><span data-ttu-id="a9fde-185">-应用程序启动错误</span><span class="sxs-lookup"><span data-stu-id="a9fde-185">-   Application start errors</span></span><br /><span data-ttu-id="a9fde-186">-Failfast 事件</span><span class="sxs-lookup"><span data-stu-id="a9fde-186">-   Failfast events</span></span><br /><span data-ttu-id="a9fde-187">-系统挂起</span><span class="sxs-lookup"><span data-stu-id="a9fde-187">-   System hangs</span></span><br /><span data-ttu-id="a9fde-188">-有害消息：导致应用程序失败的消息跟踪。</span><span class="sxs-lookup"><span data-stu-id="a9fde-188">-   Poison messages: message traces that cause the application to fail.</span></span>|<span data-ttu-id="a9fde-189">Administrators</span><span class="sxs-lookup"><span data-stu-id="a9fde-189">Administrators</span></span><br /><br /> <span data-ttu-id="a9fde-190">应用程序开发人员</span><span class="sxs-lookup"><span data-stu-id="a9fde-190">Application developers</span></span>|  
|<span data-ttu-id="a9fde-191">错误</span><span class="sxs-lookup"><span data-stu-id="a9fde-191">Error</span></span>|<span data-ttu-id="a9fde-192">"负面" 事件：指示意外处理或错误情况的事件。</span><span class="sxs-lookup"><span data-stu-id="a9fde-192">"Negative" events: events that indicate an unexpected processing or an error condition.</span></span>|<span data-ttu-id="a9fde-193">已发生意外处理。</span><span class="sxs-lookup"><span data-stu-id="a9fde-193">Unexpected processing has happened.</span></span> <span data-ttu-id="a9fde-194">应用程序未能执行预期的任务。</span><span class="sxs-lookup"><span data-stu-id="a9fde-194">The application was not able to perform a task as expected.</span></span> <span data-ttu-id="a9fde-195">然而，应用程序仍处于开启状态并在运行。</span><span class="sxs-lookup"><span data-stu-id="a9fde-195">However, the application is still up and running.</span></span>|<span data-ttu-id="a9fde-196">记录所有异常。</span><span class="sxs-lookup"><span data-stu-id="a9fde-196">All exceptions are logged.</span></span>|<span data-ttu-id="a9fde-197">Administrators</span><span class="sxs-lookup"><span data-stu-id="a9fde-197">Administrators</span></span><br /><br /> <span data-ttu-id="a9fde-198">应用程序开发人员</span><span class="sxs-lookup"><span data-stu-id="a9fde-198">Application developers</span></span>|  
|<span data-ttu-id="a9fde-199">警告</span><span class="sxs-lookup"><span data-stu-id="a9fde-199">Warning</span></span>|<span data-ttu-id="a9fde-200">"负面" 事件：指示意外处理或错误情况的事件。</span><span class="sxs-lookup"><span data-stu-id="a9fde-200">"Negative" events: events that indicate an unexpected processing or an error condition.</span></span>|<span data-ttu-id="a9fde-201">可能的问题已经出现或可能出现，但是，应用程序仍在正常工作。</span><span class="sxs-lookup"><span data-stu-id="a9fde-201">A possible problem has occurred or may occur, but the application still functions correctly.</span></span> <span data-ttu-id="a9fde-202">不过，该应用程序可能不会继续正常工作。</span><span class="sxs-lookup"><span data-stu-id="a9fde-202">However, it may not continue to work properly.</span></span>|<span data-ttu-id="a9fde-203">-应用程序收到的请求数超过了限制设置允许的数目。</span><span class="sxs-lookup"><span data-stu-id="a9fde-203">-   The application is receiving more requests than its throttling settings allow.</span></span><br /><span data-ttu-id="a9fde-204">-接收队列接近配置的最大容量。</span><span class="sxs-lookup"><span data-stu-id="a9fde-204">-   The receiving queue is near its maximum configured capacity.</span></span><br /><span data-ttu-id="a9fde-205">-已超过超时。</span><span class="sxs-lookup"><span data-stu-id="a9fde-205">-   Timeout has exceeded.</span></span><br /><span data-ttu-id="a9fde-206">-拒绝凭据。</span><span class="sxs-lookup"><span data-stu-id="a9fde-206">-   Credentials are rejected.</span></span>|<span data-ttu-id="a9fde-207">Administrators</span><span class="sxs-lookup"><span data-stu-id="a9fde-207">Administrators</span></span><br /><br /> <span data-ttu-id="a9fde-208">应用程序开发人员</span><span class="sxs-lookup"><span data-stu-id="a9fde-208">Application developers</span></span>|  
|<span data-ttu-id="a9fde-209">信息</span><span class="sxs-lookup"><span data-stu-id="a9fde-209">Information</span></span>|<span data-ttu-id="a9fde-210">"正" 事件：标记成功里程碑的事件</span><span class="sxs-lookup"><span data-stu-id="a9fde-210">"Positive" events: events that mark successful milestones</span></span>|<span data-ttu-id="a9fde-211">应用程序执行的重要和成功里程碑，而不考虑该应用程序是否工作正常。</span><span class="sxs-lookup"><span data-stu-id="a9fde-211">Important and successful milestones of application execution, regardless of whether the application is working properly or not.</span></span>|<span data-ttu-id="a9fde-212">通常，生成对监视和诊断系统状态、测量性能或执行分析十分有用的消息。</span><span class="sxs-lookup"><span data-stu-id="a9fde-212">In general, messages helpful for monitoring and diagnosing system status, measuring performance or profiling are generated.</span></span> <span data-ttu-id="a9fde-213">可以使用此类信息规划容量和管理性能：</span><span class="sxs-lookup"><span data-stu-id="a9fde-213">You can use such information for capacity planning and performance management:</span></span><br /><br /> <span data-ttu-id="a9fde-214">-创建通道。</span><span class="sxs-lookup"><span data-stu-id="a9fde-214">-   Channels are created.</span></span><br /><span data-ttu-id="a9fde-215">-已创建终结点侦听器。</span><span class="sxs-lookup"><span data-stu-id="a9fde-215">-   Endpoint listeners are created.</span></span><br /><span data-ttu-id="a9fde-216">-消息进入/离开传输。</span><span class="sxs-lookup"><span data-stu-id="a9fde-216">-   Message enters/leaves transport.</span></span><br /><span data-ttu-id="a9fde-217">-已检索到安全令牌。</span><span class="sxs-lookup"><span data-stu-id="a9fde-217">-   Security token is retrieved.</span></span><br /><span data-ttu-id="a9fde-218">-已读取配置设置。</span><span class="sxs-lookup"><span data-stu-id="a9fde-218">-   Configuration setting is read.</span></span>|<span data-ttu-id="a9fde-219">Administrators</span><span class="sxs-lookup"><span data-stu-id="a9fde-219">Administrators</span></span><br /><br /> <span data-ttu-id="a9fde-220">应用程序开发人员</span><span class="sxs-lookup"><span data-stu-id="a9fde-220">Application developers</span></span><br /><br /> <span data-ttu-id="a9fde-221">产品开发人员。</span><span class="sxs-lookup"><span data-stu-id="a9fde-221">Product developers.</span></span>|  
|<span data-ttu-id="a9fde-222">“详细”</span><span class="sxs-lookup"><span data-stu-id="a9fde-222">Verbose</span></span>|<span data-ttu-id="a9fde-223">"正" 事件：标记成功里程碑的事件。</span><span class="sxs-lookup"><span data-stu-id="a9fde-223">"Positive" events: events that mark successful milestones.</span></span>|<span data-ttu-id="a9fde-224">发出用于用户代码和服务的低级别事件。</span><span class="sxs-lookup"><span data-stu-id="a9fde-224">Low-level events for both user code and servicing are emitted.</span></span>|<span data-ttu-id="a9fde-225">通常，可以使用此级别进行调试或应用程序优化。</span><span class="sxs-lookup"><span data-stu-id="a9fde-225">In general, you can use this level for debugging or application optimization.</span></span><br /><br /> <span data-ttu-id="a9fde-226">-理解的消息标头。</span><span class="sxs-lookup"><span data-stu-id="a9fde-226">-   Understood message header.</span></span>|<span data-ttu-id="a9fde-227">Administrators</span><span class="sxs-lookup"><span data-stu-id="a9fde-227">Administrators</span></span><br /><br /> <span data-ttu-id="a9fde-228">应用程序开发人员</span><span class="sxs-lookup"><span data-stu-id="a9fde-228">Application developers</span></span><br /><br /> <span data-ttu-id="a9fde-229">产品开发人员。</span><span class="sxs-lookup"><span data-stu-id="a9fde-229">Product developers.</span></span>|  
|<span data-ttu-id="a9fde-230">活动跟踪</span><span class="sxs-lookup"><span data-stu-id="a9fde-230">ActivityTracing</span></span>||<span data-ttu-id="a9fde-231">处理活动与组件之间的流事件。</span><span class="sxs-lookup"><span data-stu-id="a9fde-231">Flow events between processing activities and components.</span></span>|<span data-ttu-id="a9fde-232">此级别允许管理员和开发人员关联同一应用程序域中的各应用程序：</span><span class="sxs-lookup"><span data-stu-id="a9fde-232">This level allows administrators and developers to correlate applications in the same application domain:</span></span><br /><br /> <span data-ttu-id="a9fde-233">-跟踪活动边界，如启动/停止。</span><span class="sxs-lookup"><span data-stu-id="a9fde-233">-   Traces for activity boundaries, such as start/stop.</span></span><br /><span data-ttu-id="a9fde-234">-传输跟踪。</span><span class="sxs-lookup"><span data-stu-id="a9fde-234">-   Traces for transfers.</span></span>|<span data-ttu-id="a9fde-235">All</span><span class="sxs-lookup"><span data-stu-id="a9fde-235">All</span></span>|  
|<span data-ttu-id="a9fde-236">All</span><span class="sxs-lookup"><span data-stu-id="a9fde-236">All</span></span>||<span data-ttu-id="a9fde-237">应用程序可能工作正常。</span><span class="sxs-lookup"><span data-stu-id="a9fde-237">Application may function properly.</span></span> <span data-ttu-id="a9fde-238">发出所有事件。</span><span class="sxs-lookup"><span data-stu-id="a9fde-238">All events are emitted.</span></span>|<span data-ttu-id="a9fde-239">先前的所有事件。</span><span class="sxs-lookup"><span data-stu-id="a9fde-239">All previous events.</span></span>|<span data-ttu-id="a9fde-240">All</span><span class="sxs-lookup"><span data-stu-id="a9fde-240">All</span></span>|  
  
 <span data-ttu-id="a9fde-241">从“详细”到“严重”的级别彼此堆叠，即每个跟踪级别都包括其上除“禁用”级别以外的所有级别。</span><span class="sxs-lookup"><span data-stu-id="a9fde-241">The levels from Verbose to Critical are stacked on top of each other, that is, each trace level includes all levels above it except the Off level.</span></span> <span data-ttu-id="a9fde-242">例如，在“警告”级别进行侦听的侦听器会接收到“严重”、“错误”和“警告”跟踪。</span><span class="sxs-lookup"><span data-stu-id="a9fde-242">For example, a listener listening at the Warning level receives Critical, Error, and Warning traces.</span></span> <span data-ttu-id="a9fde-243">“全部”级别包括从“详细”到“严重”的事件以及活动跟踪事件。</span><span class="sxs-lookup"><span data-stu-id="a9fde-243">The All level includes events from Verbose to Critical and Activity tracing events.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="a9fde-244">“信息”、“详细”和“ActivityTracing”级别会生成大量跟踪，这可能会对消息吞吐量产生不利影响（如果计算机上的所有可用资源均已用尽）。</span><span class="sxs-lookup"><span data-stu-id="a9fde-244">The Information, Verbose, and ActivityTracing levels generate a lot of traces, which may negatively impact message throughput if you have used up all available resources on the machine.</span></span>  
  
## <a name="configuring-activity-tracing-and-propagation-for-correlation"></a><span data-ttu-id="a9fde-245">配置用于关联的活动跟踪和传播</span><span class="sxs-lookup"><span data-stu-id="a9fde-245">Configuring Activity Tracing and Propagation for Correlation</span></span>  

 <span data-ttu-id="a9fde-246">为 `activityTracing` 属性指定的 `switchValue` 值用于启用活动跟踪，这会在终结点内发出活动边界跟踪和传输跟踪。</span><span class="sxs-lookup"><span data-stu-id="a9fde-246">The `activityTracing` value specified for the `switchValue` attribute is used to enable activity tracing, which emits traces for activity boundaries and transfers within endpoints.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a9fde-247">在 WCF 中使用某些扩展功能时，您可能会收到 <xref:System.NullReferenceException> 活动跟踪启用的时间。</span><span class="sxs-lookup"><span data-stu-id="a9fde-247">When you use certain extensibility features in WCF, you might get a <xref:System.NullReferenceException> when activity tracing is enabled.</span></span> <span data-ttu-id="a9fde-248">要解决此问题，请检查应用程序配置文件，并确保跟踪源的 `switchValue` 属性未设置为 `activityTracing`。</span><span class="sxs-lookup"><span data-stu-id="a9fde-248">To fix this problem, check your application's configuration file and ensure that the `switchValue` attribute for your trace source is not set to `activityTracing`.</span></span>  
  
 <span data-ttu-id="a9fde-249">`propagateActivity` 属性指示是否应将活动传播到参与消息交换的其他终结点。</span><span class="sxs-lookup"><span data-stu-id="a9fde-249">The `propagateActivity` attribute indicates whether the activity should be propagated to other endpoints that participate in the message exchange.</span></span> <span data-ttu-id="a9fde-250">将此值设置为 `true` 后，可以获取由任意两个终结点生成的跟踪文件，然后观察某一终结点上的一组跟踪是如何流向另一终结点上的一组跟踪的。</span><span class="sxs-lookup"><span data-stu-id="a9fde-250">By setting this value to `true`, you can take trace files generated by any two endpoints and observe how a set of traces on one endpoint flowed to a set of traces on another endpoint.</span></span>  
  
 <span data-ttu-id="a9fde-251">有关活动跟踪和传播的详细信息，请参阅 [传播](propagation.md)。</span><span class="sxs-lookup"><span data-stu-id="a9fde-251">For more information about activity tracing and propagation, see [Propagation](propagation.md).</span></span>  
  
 <span data-ttu-id="a9fde-252">`propagateActivity`和 `ActivityTracing` 布尔值均适用于 system.servicemodel TraceSource。</span><span class="sxs-lookup"><span data-stu-id="a9fde-252">Both `propagateActivity` and `ActivityTracing` Boolean values apply to the System.ServiceModel TraceSource.</span></span> <span data-ttu-id="a9fde-253">`ActivityTracing`值还适用于任何跟踪源，包括 WCF 或用户定义的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="a9fde-253">The `ActivityTracing` value also applies to any trace source, including WCF or user-defined ones.</span></span>  
  
 <span data-ttu-id="a9fde-254">不能将 `propagateActivity` 属性与用户定义的跟踪源一起使用。</span><span class="sxs-lookup"><span data-stu-id="a9fde-254">You cannot use the `propagateActivity` attribute with user-defined trace sources.</span></span> <span data-ttu-id="a9fde-255">对于用户代码活动 ID 传播，请确保未设置 ServiceModel `ActivityTracing`，而同时仍将 ServiceModel `propagateActivity` 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="a9fde-255">For user code activity ID propagation, make sure you do not set ServiceModel `ActivityTracing`, while still having ServiceModel `propagateActivity` attribute set to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9fde-256">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a9fde-256">See also</span></span>

- [<span data-ttu-id="a9fde-257">跟踪</span><span class="sxs-lookup"><span data-stu-id="a9fde-257">Tracing</span></span>](index.md)
- [<span data-ttu-id="a9fde-258">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="a9fde-258">Administration and Diagnostics</span></span>](../index.md)
- [<span data-ttu-id="a9fde-259">如何：创建和初始化跟踪侦听器</span><span class="sxs-lookup"><span data-stu-id="a9fde-259">How to: Create and Initialize Trace Listeners</span></span>](../../../debug-trace-profile/how-to-create-and-initialize-trace-listeners.md)
- [<span data-ttu-id="a9fde-260">Creating a Custom TraceListener（创建自定义 TraceListener）</span><span class="sxs-lookup"><span data-stu-id="a9fde-260">Creating a Custom TraceListener</span></span>](/archive/msdn-magazine/2006/april/clr-inside-out-extending-system-diagnostics)
