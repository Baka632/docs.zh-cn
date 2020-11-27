---
title: 工作流托管选项
ms.date: 03/30/2017
ms.assetid: 37bcd668-9c5c-4e7c-81da-a1f1b3a16514
ms.openlocfilehash: 8ddb83f068eab8480bacc8b80bc5d44b7755fa59
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293775"
---
# <a name="workflow-hosting-options"></a><span data-ttu-id="037c5-102">工作流托管选项</span><span class="sxs-lookup"><span data-stu-id="037c5-102">Workflow Hosting Options</span></span>

<span data-ttu-id="037c5-103">大多数 Windows Workflow Foundation (WF) 示例使用托管在控制台应用程序中的工作流，但这不是实际工作流的现实方案。</span><span class="sxs-lookup"><span data-stu-id="037c5-103">Most of the Windows Workflow Foundation (WF) samples use workflows that are hosted in a console application, but this isn't a realistic scenario for real-world workflows.</span></span> <span data-ttu-id="037c5-104">实际业务应用程序中的工作流将托管在持久的进程中，无论是开发人员编写的 Windows 服务，还是 IIS 7.0 或 AppFabric 等服务器应用程序。</span><span class="sxs-lookup"><span data-stu-id="037c5-104">Workflows in actual business applications will be hosted in persistent processes- either a Windows service authored by the developer, or a server application such as IIS 7.0 or AppFabric.</span></span> <span data-ttu-id="037c5-105">这些方法之间的区别如下。</span><span class="sxs-lookup"><span data-stu-id="037c5-105">The differences between these approaches are as follows.</span></span>

## <a name="hosting-workflows-in-iis-with-windows-appfabric"></a><span data-ttu-id="037c5-106">用配有 Windows AppFabric 的 IIS 承载工作流</span><span class="sxs-lookup"><span data-stu-id="037c5-106">Hosting workflows in IIS with Windows AppFabric</span></span>

<span data-ttu-id="037c5-107">用配有 AppFabric 的 IIS 是承载工作流的首选方法。</span><span class="sxs-lookup"><span data-stu-id="037c5-107">Using IIS with AppFabric is the preferred host for workflows.</span></span> <span data-ttu-id="037c5-108">用 AppFabric 来承载工作流的应用程序是 Windows Activation Service，它解除了仅通过 IIS 对 HTTP 的依赖。</span><span class="sxs-lookup"><span data-stu-id="037c5-108">The host application for workflows using AppFabric is Windows Activation Service, which removes the dependency on HTTP over IIS alone.</span></span>

## <a name="hosting-workflows-in-iis-alone"></a><span data-ttu-id="037c5-109">仅用 IIS 来承载工作流</span><span class="sxs-lookup"><span data-stu-id="037c5-109">Hosting workflows in IIS alone</span></span>

<span data-ttu-id="037c5-110">建议不要使用 IIS 7.0，因为 AppFabric 提供了一些管理和监视工具，可帮助维护正在运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="037c5-110">Using IIS 7.0 alone is not recommended, as there are management and monitoring tools available with AppFabric that facilitate maintenance of running applications.</span></span> <span data-ttu-id="037c5-111">如果在迁移到 AppFabric 时出现基础结构问题，则仅应在 IIS 7.0 中承载工作流。</span><span class="sxs-lookup"><span data-stu-id="037c5-111">Workflows should only be hosted in IIS 7.0 alone if there are infrastructure concerns with moving to AppFabric.</span></span>

> [!WARNING]
> <span data-ttu-id="037c5-112">IIS 7.0 会出于各种原因定期回收应用程序池。</span><span class="sxs-lookup"><span data-stu-id="037c5-112">IIS 7.0 recycles application pools periodically for various reasons.</span></span> <span data-ttu-id="037c5-113">当应用程序池被回收时，IIS 即停止接受发给旧应用程序池的消息，并实例化一个新的应用程序池以接受新请求。</span><span class="sxs-lookup"><span data-stu-id="037c5-113">When an application pool is recycled, IIS stops accepting messages to the old pool, and instantiates a new application pool to accept new requests.</span></span> <span data-ttu-id="037c5-114">如果工作流在发送响应后继续工作，则 IIS 7.0 将不知道正在执行的工作，并可能回收宿主应用程序池。</span><span class="sxs-lookup"><span data-stu-id="037c5-114">If a workflow continues working after sending a response, IIS 7.0 will not be aware of the work being done, and may recycle the hosting application pool.</span></span> <span data-ttu-id="037c5-115">如果发生这种情况，则工作流将中止，并且跟踪服务将记录 [1004 一个 WorkflowInstanceAborted](1004-workflowinstanceaborted.md) 消息，其中包含空的原因字段。</span><span class="sxs-lookup"><span data-stu-id="037c5-115">If this happens, the workflow will abort, and tracking services will record a [1004 - WorkflowInstanceAborted](1004-workflowinstanceaborted.md) message with an empty Reason field.</span></span>
>
> <span data-ttu-id="037c5-116">如果使用了持久化机制，则主机必须显式地从上一个持久化点重启被中止的实例。</span><span class="sxs-lookup"><span data-stu-id="037c5-116">If persistence is used, the host must explicitly restart aborted instances from the last persistence point.</span></span>
>
> <span data-ttu-id="037c5-117">如果使用了 AppFabric，则工作流管理服务最终将从上次成功持久化的点恢复工作流（如果使用了持久化机制）。</span><span class="sxs-lookup"><span data-stu-id="037c5-117">If AppFabric is used, the workflow management service will eventually resume the workflow from the last successful persistence point if persistence is used.</span></span> <span data-ttu-id="037c5-118">如果未使用持久化机制，则该工作流执行非“请求/响应”模式的操作，当工作流中止时，数据也将丢失。</span><span class="sxs-lookup"><span data-stu-id="037c5-118">If no persistence is used, and the workflow performs operations outside a Request/Response pattern, data will be lost when the workflow aborts.</span></span>

## <a name="hosting-a-workflow-in-a-custom-windows-service"></a><span data-ttu-id="037c5-119">在自定义 Windows 服务中承载工作流</span><span class="sxs-lookup"><span data-stu-id="037c5-119">Hosting a workflow in a custom Windows Service</span></span>

<span data-ttu-id="037c5-120">若要创建自定义工作流服务来承载工作流，要求开发人员复制 AppFabric 自带的许多功能，但允许通过自定义功能实现更大的灵活性。</span><span class="sxs-lookup"><span data-stu-id="037c5-120">Creating a custom workflow service to host the workflow will require the developer to duplicate a lot of the functionality provided out-of-box by AppFabric, but will allow for more flexibility with custom functionality.</span></span> <span data-ttu-id="037c5-121">仅当 AppFabric 经证不合适时，才应考虑这一选项。</span><span class="sxs-lookup"><span data-stu-id="037c5-121">This option should only be considered if AppFabric proves to not be an option.</span></span>
