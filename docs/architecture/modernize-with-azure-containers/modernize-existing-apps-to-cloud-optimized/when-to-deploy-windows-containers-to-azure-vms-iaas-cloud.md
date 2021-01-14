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
# <a name="when-to-deploy-windows-containers-to-azure-vms-iaas-cloud"></a>何时将 Windows 容器部署到 Azure VM（IaaS 云）

如果你的组织使用 Azure VM，则即使你还使用 Windows 容器，仍将处理 IaaS。 这意味着，当你需要在负载均衡的基础结构中部署到多个 VM 时，应处理高度可缩放的应用程序的基础结构操作、VM 操作系统修补程序和基础结构复杂性。 在 Azure VM 中使用 Windows 容器的主要方案是：

- **开发/测试环境**：云中的 VM 非常适合在云中进行开发和测试。 可以根据需要快速创建或停止环境。

- **中小型的可伸缩性需求**：如果生产环境只需要几个 VM，管理少量 VM 的开销可能还负担得起，除非迁移到更高级的 PaaS 环境（如业务流程协调程序）。

- **包含现有部署工具的生产环境**：可能迁移自本地环境，在该环境中，已对工具进行投资来对 VM 或裸机服务器（如 Puppet 或类似的工具）进行复杂的部署。 若要通过对生产环境部署过程进行少量的更改来迁移到云，可以继续使用这些工具部署到 Azure VM。 但是，你需要将 Windows 容器用作部署单位来改善部署体验。

>[!div class="step-by-step"]
>[上一页](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
>[下一页](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
