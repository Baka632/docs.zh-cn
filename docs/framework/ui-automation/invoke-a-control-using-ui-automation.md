---
title: 使用 UI 自动化调用控件
description: 使用 UI 自动化查找与特定属性条件相匹配的控件、创建 AutomationElement 和获取 InvokePattern，并使用控件上的 Invoke。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- invoking controls
- UI Automation, invoking controls
- controls, invoking
ms.assetid: 5ee2de3f-256c-43ec-b64c-62ace91f9983
ms.openlocfilehash: 7c6f5d26d16642f978fd79fd40701c240a53f16a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96277993"
---
# <a name="invoke-a-control-using-ui-automation"></a><span data-ttu-id="66326-103">使用 UI 自动化调用控件</span><span class="sxs-lookup"><span data-stu-id="66326-103">Invoke a Control Using UI Automation</span></span>

> [!NOTE]
> <span data-ttu-id="66326-104">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="66326-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="66326-105">有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](/windows/win32/winauto/entry-uiauto-win32)。</span><span class="sxs-lookup"><span data-stu-id="66326-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="66326-106">本主题演示如何执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="66326-106">This topic demonstrates how to perform the following tasks:</span></span>  
  
- <span data-ttu-id="66326-107">通过遍历目标应用程序 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 树的控件视图，查找与特定属性条件相匹配的控件。</span><span class="sxs-lookup"><span data-stu-id="66326-107">Find a control that matches specific property conditions by walking the control view of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree for the target application.</span></span>  
  
- <span data-ttu-id="66326-108">为每个控件创建 <xref:System.Windows.Automation.AutomationElement> 。</span><span class="sxs-lookup"><span data-stu-id="66326-108">Create an <xref:System.Windows.Automation.AutomationElement> for each control.</span></span>  
  
- <span data-ttu-id="66326-109">从发现的任何支持 <xref:System.Windows.Automation.InvokePattern> 控件模式的 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 元素中获取 <xref:System.Windows.Automation.InvokePattern> 对象。</span><span class="sxs-lookup"><span data-stu-id="66326-109">Obtain an <xref:System.Windows.Automation.InvokePattern> object from any [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element found that supports the <xref:System.Windows.Automation.InvokePattern> control pattern.</span></span>  
  
- <span data-ttu-id="66326-110">使用 <xref:System.Windows.Automation.InvokePattern.Invoke%2A> 以从客户端事件处理程序调用该控件。</span><span class="sxs-lookup"><span data-stu-id="66326-110">Use <xref:System.Windows.Automation.InvokePattern.Invoke%2A> to invoke the control from a client event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66326-111">示例</span><span class="sxs-lookup"><span data-stu-id="66326-111">Example</span></span>  

 <span data-ttu-id="66326-112">此示例使用 <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> 类的 <xref:System.Windows.Automation.AutomationElement> 方法来生成 <xref:System.Windows.Automation.InvokePattern> 对象，并通过使用 <xref:System.Windows.Automation.InvokePattern.Invoke%2A> 方法调用控件。</span><span class="sxs-lookup"><span data-stu-id="66326-112">This example uses the <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> method of the <xref:System.Windows.Automation.AutomationElement> class to generate an <xref:System.Windows.Automation.InvokePattern> object and invoke a control by using the <xref:System.Windows.Automation.InvokePattern.Invoke%2A> method.</span></span>  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
[!code-csharp[InvokePatternApp#1102](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1102)]
[!code-vb[InvokePatternApp#1102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1102)]  
  
## <a name="see-also"></a><span data-ttu-id="66326-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="66326-113">See also</span></span>

- [<span data-ttu-id="66326-114">InvokePattern、ExpandCollapsePattern 和 TogglePattern 示例</span><span class="sxs-lookup"><span data-stu-id="66326-114">InvokePattern, ExpandCollapsePattern, and TogglePattern Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/InvokePattern)
