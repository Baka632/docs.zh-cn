---
title: 何时不部署到 Windows 容器
description: 通过 Azure 云和 Windows 容器现代化现有 .NET 应用程序 | 何时不部署到 Windows 容器
ms.date: 12/21/2020
ms.openlocfilehash: 4eea24ab8deb3719c778b45b3ddc1309277a3f50
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2021
ms.locfileid: "98025168"
---
# <a name="when-not-to-deploy-to-windows-containers"></a><span data-ttu-id="20288-103">何时不部署到 Windows 容器</span><span class="sxs-lookup"><span data-stu-id="20288-103">When not to deploy to Windows Containers</span></span>

<span data-ttu-id="20288-104">Windows 容器不支持某些 Windows 技术。</span><span class="sxs-lookup"><span data-stu-id="20288-104">Some Windows technologies are not supported by Windows Containers.</span></span> <span data-ttu-id="20288-105">在这些情况下，你仍需要迁移到标准 VM（通常只需要 Windows 和 IIS）。</span><span class="sxs-lookup"><span data-stu-id="20288-105">In those cases, you still need to migrate to the standards VMs, usually with just Windows and IIS.</span></span>

<span data-ttu-id="20288-106">从 2018 年 5 月开始，Windows 容器不支持的情况为：</span><span class="sxs-lookup"><span data-stu-id="20288-106">Cases not supported in Windows Containers, as of May 2018:</span></span>

- <span data-ttu-id="20288-107">Microsoft 消息队列 (MSMQ) 当前只能在基于 Windows Server v1803 版本的 Windows 容器中使用，而不能在任何其他以前版本中使用。</span><span class="sxs-lookup"><span data-stu-id="20288-107">Microsoft Message Queuing (MSMQ) currently is only available in Windows Containers based on Windows Server v1803 release, but not in any other prior releases.</span></span>

  - [<span data-ttu-id="20288-108">UserVoice 请求论坛</span><span class="sxs-lookup"><span data-stu-id="20288-108">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

  - [<span data-ttu-id="20288-109">讨论论坛</span><span class="sxs-lookup"><span data-stu-id="20288-109">Discussion forum</span></span>](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

- <span data-ttu-id="20288-110">Windows 容器目前不支持 Microsoft 分布式事务处理协调器 (MSDTC)。</span><span class="sxs-lookup"><span data-stu-id="20288-110">Microsoft Distributed Transaction Coordinator (MSDTC) currently is not supported in Windows Containers.</span></span>

  - [<span data-ttu-id="20288-111">GitHub 问题</span><span class="sxs-lookup"><span data-stu-id="20288-111">GitHub issue</span></span>](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

- <span data-ttu-id="20288-112">Microsoft Office 目前不支持容器。</span><span class="sxs-lookup"><span data-stu-id="20288-112">Microsoft Office currently does not support containers.</span></span>

  - [<span data-ttu-id="20288-113">UserVoice 请求论坛</span><span class="sxs-lookup"><span data-stu-id="20288-113">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

- <span data-ttu-id="20288-114">UI 应用（具有可视用户界面的客户端应用）不是受支持的方案。</span><span class="sxs-lookup"><span data-stu-id="20288-114">UI apps (client apps with a visual user interface) are not supported scenarios.</span></span>

- <span data-ttu-id="20288-115">Windows 基础结构角色（DNS、DHCP、DC、NTP、PRINT、文件服务器、IAM 等）不是受支持的方案。</span><span class="sxs-lookup"><span data-stu-id="20288-115">Windows infrastructure roles (DNS, DHCP, DC, NTP, PRINT, File server, IAM etc.) are not supported scenarios.</span></span>

<span data-ttu-id="20288-116">有关其他不受支持的方案和社区中的请求，请参阅适用于 Windows 容器的 UserVoice 论坛：<https://windowsserver.uservoice.com/forums/304624-containers>。</span><span class="sxs-lookup"><span data-stu-id="20288-116">For other nonsupported scenarios and requests from the community, see the UserVoice forum for Windows Containers: <https://windowsserver.uservoice.com/forums/304624-containers>.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="20288-117">其他资源</span><span class="sxs-lookup"><span data-stu-id="20288-117">Additional resources</span></span>

- <span data-ttu-id="20288-118">**Azure 中的虚拟机和容器**</span><span class="sxs-lookup"><span data-stu-id="20288-118">**Virtual machines and containers in Azure**</span></span>

    <https://azure.microsoft.com/overview/containers/>

> [!div class="step-by-step"]
> <span data-ttu-id="20288-119">[上一页](deploy-existing-net-apps-as-windows-containers.md)
> [下一页](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="20288-119">[Previous](deploy-existing-net-apps-as-windows-containers.md)
[Next](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span></span>
