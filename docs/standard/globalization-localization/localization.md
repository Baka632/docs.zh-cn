---
title: 本地化
ms.date: 03/30/2017
helpviewer_keywords:
- culture, localization
- application development [.NET], localization
- globalization [.NET], localization
- code blocks
- international applications [.NET], localization
- global applications, localization
- world-ready applications, localization
- user interface blocks
- localization [.NET], about localization
- localizing resources
ms.assetid: 49d520d7-92d7-44ee-bb24-8b615db1d41b
ms.openlocfilehash: 5d47d002c714ea80b6f94c810f2dca726c273134
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829825"
---
# <a name="localization"></a><span data-ttu-id="2918e-102">本地化</span><span class="sxs-lookup"><span data-stu-id="2918e-102">Localization</span></span>

<span data-ttu-id="2918e-103">本地化是针对应用支持的每个区域性，将应用资源转换为本地化版本的过程。</span><span class="sxs-lookup"><span data-stu-id="2918e-103">Localization is the process of translating an application's resources into localized versions for each culture that the application will support.</span></span> <span data-ttu-id="2918e-104">只有在完成[可本地化评审](localizability-review.md)步骤，以验证全球化应用是否做好本地化准备后，才应继续执行本地化步骤。</span><span class="sxs-lookup"><span data-stu-id="2918e-104">You should proceed to the localization step only after completing the [Localizability Review](localizability-review.md) step to verify that the globalized application is ready for localization.</span></span>

<span data-ttu-id="2918e-105">可以开始进行本地化的应用程序分为两个概念块：一个是包含所有用户界面元素的块，另一个是包含可执行代码的块。</span><span class="sxs-lookup"><span data-stu-id="2918e-105">An application that is ready for localization is separated into two conceptual blocks: a block that contains all user interface elements and a block that contains executable code.</span></span> <span data-ttu-id="2918e-106">用户界面块仅包含可本地化的用户界面元素，如字符串、错误消息、对话框、菜单、嵌入的对象资源等区域性中性元素。</span><span class="sxs-lookup"><span data-stu-id="2918e-106">The user interface block contains only localizable user-interface elements such as strings, error messages, dialog boxes, menus, embedded object resources, and so on for the neutral culture.</span></span> <span data-ttu-id="2918e-107">代码块仅包含所有支持的区域性要使用的应用代码。</span><span class="sxs-lookup"><span data-stu-id="2918e-107">The code block contains only the application code to be used by all supported cultures.</span></span> <span data-ttu-id="2918e-108">公共语言运行时支持附属程序集资源模型，用于将应用的可执行代码与资源分隔开来。</span><span class="sxs-lookup"><span data-stu-id="2918e-108">The common language runtime supports a satellite assembly resource model that separates an application's executable code from its resources.</span></span> <span data-ttu-id="2918e-109">若要详细了解如何实现此模型，请参阅 [.NET 中的资源](../../framework/resources/index.md)。</span><span class="sxs-lookup"><span data-stu-id="2918e-109">For more information about implementing this model, see [Resources in .NET](../../framework/resources/index.md).</span></span>

<span data-ttu-id="2918e-110">对于应用的每个本地化版本，请添加新的附属程序集，其中包含转换为目标区域性的相应语言的本地化用户界面块。</span><span class="sxs-lookup"><span data-stu-id="2918e-110">For each localized version of your application, add a new satellite assembly that contains the localized user interface block translated into the appropriate language for the target culture.</span></span> <span data-ttu-id="2918e-111">所有区域性的代码块应保持不变。</span><span class="sxs-lookup"><span data-stu-id="2918e-111">The code block for all cultures should remain the same.</span></span> <span data-ttu-id="2918e-112">用户界面块的本地化版本和代码块组合生成了应用的本地化版本。</span><span class="sxs-lookup"><span data-stu-id="2918e-112">The combination of a localized version of the user interface block with the code block produces a localized version of your application.</span></span>

<span data-ttu-id="2918e-113">Windows 软件开发工具包 (SDK) 提供了 Windows 窗体资源编辑器 (Winres.exe)，以便于针对目标区域性快速本地化 Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="2918e-113">The Windows Software Development Kit (SDK) supplies the Windows Forms Resource Editor (Winres.exe) that allows you to quickly localize Windows Forms for target cultures.</span></span> <span data-ttu-id="2918e-114">若要了解如何使用此工具，请参阅 [Winres.exe（Windows 窗体资源编辑器）](../../framework/tools/winres-exe-windows-forms-resource-editor.md)。</span><span class="sxs-lookup"><span data-stu-id="2918e-114">For information about using this tool, see [Winres.exe (Windows Forms Resource Editor)](../../framework/tools/winres-exe-windows-forms-resource-editor.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2918e-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="2918e-115">See also</span></span>

- [<span data-ttu-id="2918e-116">全球化和本地化</span><span class="sxs-lookup"><span data-stu-id="2918e-116">Globalization and Localization</span></span>](index.md)
- [<span data-ttu-id="2918e-117">可本地化性审核</span><span class="sxs-lookup"><span data-stu-id="2918e-117">Localizability Review</span></span>](localizability-review.md)
- [<span data-ttu-id="2918e-118">全球化</span><span class="sxs-lookup"><span data-stu-id="2918e-118">Globalization</span></span>](globalization.md)
- [<span data-ttu-id="2918e-119">桌面应用中的资源</span><span class="sxs-lookup"><span data-stu-id="2918e-119">Resources in Desktop Apps</span></span>](../../framework/resources/index.md)
