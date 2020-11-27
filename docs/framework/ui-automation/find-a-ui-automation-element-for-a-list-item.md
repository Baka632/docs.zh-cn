---
title: 查找列表项的 UI 自动化元素
description: 查看一个示例，该示例演示如何在已知项的索引时查找列表项的 UI 自动化元素。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items, finding elements for
- elements, finding for list items
- UI Automation, finding elements for List items
ms.assetid: c326ad2b-2144-4f64-ae4c-d850c74f95c5
ms.openlocfilehash: 95f6b558cc53b00701232f247f8de7f8c603e3ac
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276472"
---
# <a name="find-a-ui-automation-element-for-a-list-item"></a><span data-ttu-id="6a72d-103">查找列表项的 UI 自动化元素</span><span class="sxs-lookup"><span data-stu-id="6a72d-103">Find a UI Automation Element for a List Item</span></span>

> [!NOTE]
> <span data-ttu-id="6a72d-104">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="6a72d-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="6a72d-105">有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](/windows/win32/winauto/entry-uiauto-win32)。</span><span class="sxs-lookup"><span data-stu-id="6a72d-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="6a72d-106">本主题演示如何 <xref:System.Windows.Automation.AutomationElement> 在已知项的索引时检索列表中的项。</span><span class="sxs-lookup"><span data-stu-id="6a72d-106">This topic shows how to retrieve an <xref:System.Windows.Automation.AutomationElement> for an item within a list when the index of the item is known.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a72d-107">示例</span><span class="sxs-lookup"><span data-stu-id="6a72d-107">Example</span></span>  

 <span data-ttu-id="6a72d-108">下面的示例演示了两种方法，用于从列表中检索指定的项，一个使用 <xref:System.Windows.Automation.TreeWalker> ，另一个使用 <xref:System.Windows.Automation.AutomationElement.FindAll%2A> 。</span><span class="sxs-lookup"><span data-stu-id="6a72d-108">The following example shows two ways of retrieving a specified item from a list, one using <xref:System.Windows.Automation.TreeWalker> and the other using <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.</span></span>  
  
 <span data-ttu-id="6a72d-109">第一种方法往往比 Win32 控件更快，但第二种方法的 Windows Presentation Foundation (WPF) 控件的速度更快。</span><span class="sxs-lookup"><span data-stu-id="6a72d-109">The first technique tends to be faster for Win32 controls, but the second is faster for Windows Presentation Foundation (WPF) controls.</span></span>  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a><span data-ttu-id="6a72d-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6a72d-110">See also</span></span>

- [<span data-ttu-id="6a72d-111">获取 UI 自动化元素</span><span class="sxs-lookup"><span data-stu-id="6a72d-111">Obtaining UI Automation Elements</span></span>](obtaining-ui-automation-elements.md)
