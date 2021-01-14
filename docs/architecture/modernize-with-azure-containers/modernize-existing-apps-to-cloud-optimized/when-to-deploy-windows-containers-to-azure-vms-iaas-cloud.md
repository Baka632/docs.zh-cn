---
title: 何时将 Windows 容器部署到 Azure VM（IaaS 云）
description: 通过 Azure 云和 Windows 容器现代化现有 .NET 应用程序 | 何时将 Windows 容器部署到 Azure VM（IaaS 云）
ms.date: 12/21/2020
ms.openlocfilehash: 64ba53fa56227266ee0e61a128d18373a2dbbc93
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2021
ms.locfileid: "98025089"
---
# <a name="when-to-deploy-windows-containers-to-azure-vms-iaas-cloud"></a><span data-ttu-id="adae1-103">何时将 Windows 容器部署到 Azure VM（IaaS 云）</span><span class="sxs-lookup"><span data-stu-id="adae1-103">When to deploy Windows Containers to Azure VMs (IaaS cloud)</span></span>

<span data-ttu-id="adae1-104">如果你的组织使用 Azure VM，则即使你还使用 Windows 容器，仍将处理 IaaS。</span><span class="sxs-lookup"><span data-stu-id="adae1-104">If your organization is using Azure VMs, even if you are also using Windows Containers, you are still dealing with IaaS.</span></span> <span data-ttu-id="adae1-105">这意味着，当你需要在负载均衡的基础结构中部署到多个 VM 时，应处理高度可缩放的应用程序的基础结构操作、VM 操作系统修补程序和基础结构复杂性。</span><span class="sxs-lookup"><span data-stu-id="adae1-105">That means that dealing with infrastructure operations, VM OS patches, and infrastructure complexity for highly scalable applications when you need to deploy to multiple VMs in a load-balanced infrastructure.</span></span> <span data-ttu-id="adae1-106">在 Azure VM 中使用 Windows 容器的主要方案是：</span><span class="sxs-lookup"><span data-stu-id="adae1-106">The main scenarios for using Windows Containers in an Azure VM are:</span></span>

- <span data-ttu-id="adae1-107">**开发/测试环境**：云中的 VM 非常适合在云中进行开发和测试。</span><span class="sxs-lookup"><span data-stu-id="adae1-107">**Dev/test environment**: A VM in the cloud is perfect for development and testing in the cloud.</span></span> <span data-ttu-id="adae1-108">可以根据需要快速创建或停止环境。</span><span class="sxs-lookup"><span data-stu-id="adae1-108">You can rapidly create or stop the environment depending on your needs.</span></span>

- <span data-ttu-id="adae1-109">**中小型的可伸缩性需求**：如果生产环境只需要几个 VM，管理少量 VM 的开销可能还负担得起，除非迁移到更高级的 PaaS 环境（如业务流程协调程序）。</span><span class="sxs-lookup"><span data-stu-id="adae1-109">**Small and medium scalability needs**: In scenarios where you might need just a couple of VMs for your production environment, managing a few VMs might be affordable until you can move to more advanced PaaS environments, like orchestrators.</span></span>

- <span data-ttu-id="adae1-110">**包含现有部署工具的生产环境**：可能迁移自本地环境，在该环境中，已对工具进行投资来对 VM 或裸机服务器（如 Puppet 或类似的工具）进行复杂的部署。</span><span class="sxs-lookup"><span data-stu-id="adae1-110">**Production environment with existing deployment tools**: You might be moving from an on-premises environment in which you have invested in tools to make complex deployments to VMs or bare-metal servers (like Puppet or similar tools).</span></span> <span data-ttu-id="adae1-111">若要通过对生产环境部署过程进行少量的更改来迁移到云，可以继续使用这些工具部署到 Azure VM。</span><span class="sxs-lookup"><span data-stu-id="adae1-111">To move to the cloud with minimal changes to production environment deployment procedures, you might continue to use those tools to deploy to Azure VMs.</span></span> <span data-ttu-id="adae1-112">但是，你需要将 Windows 容器用作部署单位来改善部署体验。</span><span class="sxs-lookup"><span data-stu-id="adae1-112">However, you'll want to use Windows Containers as the unit of deployment to improve the deployment experience.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="adae1-113">[上一页](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
>[下一页](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)</span><span class="sxs-lookup"><span data-stu-id="adae1-113">[Previous](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
[Next](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)</span></span>
