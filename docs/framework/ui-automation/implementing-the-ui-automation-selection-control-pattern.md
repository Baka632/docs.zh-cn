---
title: 实现 UI 自动化 Selection 控件模式
description: 查看在 UI 自动化中实现 "选择" 控件模式的准则和约定。 请参阅 Iselectionprovider 必需接口的必需成员。
ms.date: 03/30/2017
helpviewer_keywords:
- Selection control pattern
- UI Automation, Selection control pattern
- control patterns, Selection
ms.assetid: 449c3068-a5d6-4f66-84c6-1bcc7dd4d209
ms.openlocfilehash: 7ce6b9765dfd15be320f01151ca0b91393508e55
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96237503"
---
# <a name="implementing-the-ui-automation-selection-control-pattern"></a><span data-ttu-id="58e69-104">实现 UI 自动化 Selection 控件模式</span><span class="sxs-lookup"><span data-stu-id="58e69-104">Implementing the UI Automation Selection Control Pattern</span></span>

> [!NOTE]
> <span data-ttu-id="58e69-105">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="58e69-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="58e69-106">有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](/windows/win32/winauto/entry-uiauto-win32)。</span><span class="sxs-lookup"><span data-stu-id="58e69-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="58e69-107">本主题介绍了实现 <xref:System.Windows.Automation.Provider.ISelectionProvider>的准则和约定，包括有关事件和属性的信息。</span><span class="sxs-lookup"><span data-stu-id="58e69-107">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.ISelectionProvider>, including information about events and properties.</span></span> <span data-ttu-id="58e69-108">本主题的结尾列出了指向其他参考资料的链接。</span><span class="sxs-lookup"><span data-stu-id="58e69-108">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="58e69-109"><xref:System.Windows.Automation.SelectionPattern> 控件模式用于支持作为可选子项集合的容器的控件。</span><span class="sxs-lookup"><span data-stu-id="58e69-109">The <xref:System.Windows.Automation.SelectionPattern> control pattern is used to support controls that act as containers for a collection of selectable child items.</span></span> <span data-ttu-id="58e69-110">此元素的子级必须实现 <xref:System.Windows.Automation.Provider.ISelectionItemProvider>。</span><span class="sxs-lookup"><span data-stu-id="58e69-110">The children of this element must implement <xref:System.Windows.Automation.Provider.ISelectionItemProvider>.</span></span> <span data-ttu-id="58e69-111">有关实现此控件模式的控件示例，请参阅 [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="58e69-111">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>

## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="58e69-112">实现准则和约定</span><span class="sxs-lookup"><span data-stu-id="58e69-112">Implementation Guidelines and Conventions</span></span>  

 <span data-ttu-id="58e69-113">在实现“选项”控件模式时，请注意以下准则和约定：</span><span class="sxs-lookup"><span data-stu-id="58e69-113">When implementing the Selection control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="58e69-114">实现 <xref:System.Windows.Automation.Provider.ISelectionProvider> 的控件允许选择单个或多个子项。</span><span class="sxs-lookup"><span data-stu-id="58e69-114">Controls that implement <xref:System.Windows.Automation.Provider.ISelectionProvider> allow either single or multiple child items to be selected.</span></span> <span data-ttu-id="58e69-115">例如，列表框、列表视图和树视图支持多个选项，而组合框、滑块和单选按钮组则支持单个选项。</span><span class="sxs-lookup"><span data-stu-id="58e69-115">For example, list box, list view, and tree view support multiple selections whereas combo box, slider, and radio button group support single selection.</span></span>  
  
- <span data-ttu-id="58e69-116">具有最小、最大和连续范围的控件（如“卷”  滑块控件）应实现 <xref:System.Windows.Automation.Provider.IRangeValueProvider> 而不是 <xref:System.Windows.Automation.Provider.ISelectionProvider>。</span><span class="sxs-lookup"><span data-stu-id="58e69-116">Controls that have a minimum, maximum, and continuous range, such as the **Volume** slider control, should implement <xref:System.Windows.Automation.Provider.IRangeValueProvider> instead of <xref:System.Windows.Automation.Provider.ISelectionProvider>.</span></span>  
  
- <span data-ttu-id="58e69-117">用于管理实现的子控件的单选控件（ <xref:System.Windows.Automation.Provider.IRawElementProviderFragmentRoot> 如 "**显示属性**" 对话框中的 "**屏幕分辨率**" 滑块或 Microsoft)  (Word 中的 "**颜色选取器**" 选择控件）应实现 <xref:System.Windows.Automation.Provider.ISelectionProvider> ; 其子控件应实现 <xref:System.Windows.Automation.Provider.IRawElementProviderFragment> 和 <xref:System.Windows.Automation.Provider.ISelectionItemProvider> 。</span><span class="sxs-lookup"><span data-stu-id="58e69-117">Single-selection controls that manage child controls that implement <xref:System.Windows.Automation.Provider.IRawElementProviderFragmentRoot>, such as the **Screen Resolution** slider in the **Display Properties** dialog box or the **Color Picker** selection control from Microsoft Word (illustrated below), should implement <xref:System.Windows.Automation.Provider.ISelectionProvider>; their children should implement both <xref:System.Windows.Automation.Provider.IRawElementProviderFragment> and <xref:System.Windows.Automation.Provider.ISelectionItemProvider>.</span></span>  
  
 <span data-ttu-id="58e69-118">![突出显示黄色的颜色选取器。](./media/uia-valuepattern-colorpicker.png "UIA_ValuePattern_ColorPicker")</span><span class="sxs-lookup"><span data-stu-id="58e69-118">![Color picker with yellow highlighted.](./media/uia-valuepattern-colorpicker.png "UIA_ValuePattern_ColorPicker")</span></span>  
<span data-ttu-id="58e69-119">颜色样本字符串映射的示例</span><span class="sxs-lookup"><span data-stu-id="58e69-119">Example of Color Swatch String Mapping</span></span>  
  
- <span data-ttu-id="58e69-120">菜单不支持 <xref:System.Windows.Automation.SelectionPattern>。</span><span class="sxs-lookup"><span data-stu-id="58e69-120">Menus do not support <xref:System.Windows.Automation.SelectionPattern>.</span></span> <span data-ttu-id="58e69-121">如果要使用同时包含图形和文本的菜单项 (如 Microsoft Outlook 的 "**视图**" 菜单中的 "**预览窗格**" 项) 并需要传达状态，则应实现 <xref:System.Windows.Automation.Provider.IToggleProvider> 。</span><span class="sxs-lookup"><span data-stu-id="58e69-121">If you are working with menu items that include both graphics and text (such as the **Preview Pane** items in the **View** menu in Microsoft Outlook) and need to convey state, you should implement <xref:System.Windows.Automation.Provider.IToggleProvider>.</span></span>  
  
<a name="Required_Members_for_ISelectionProvider"></a>

## <a name="required-members-for-iselectionprovider"></a><span data-ttu-id="58e69-122">ISelectionProvider 必需的成员</span><span class="sxs-lookup"><span data-stu-id="58e69-122">Required Members for ISelectionProvider</span></span>  

 <span data-ttu-id="58e69-123">以下属性、方法和事件都是 <xref:System.Windows.Automation.Provider.ISelectionProvider> 接口所必需的。</span><span class="sxs-lookup"><span data-stu-id="58e69-123">The following properties, methods, and events are required for the <xref:System.Windows.Automation.Provider.ISelectionProvider> interface.</span></span>  
  
|<span data-ttu-id="58e69-124">必需的成员</span><span class="sxs-lookup"><span data-stu-id="58e69-124">Required members</span></span>|<span data-ttu-id="58e69-125">类型</span><span class="sxs-lookup"><span data-stu-id="58e69-125">Type</span></span>|<span data-ttu-id="58e69-126">注释</span><span class="sxs-lookup"><span data-stu-id="58e69-126">Notes</span></span>|  
|----------------------|----------|-----------|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.CanSelectMultiple%2A>|<span data-ttu-id="58e69-127">属性</span><span class="sxs-lookup"><span data-stu-id="58e69-127">Property</span></span>|<span data-ttu-id="58e69-128">应支持使用 <xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A> 和 <xref:System.Windows.Automation.Automation.RemoveAutomationPropertyChangedEventHandler%2A>的属性更改事件。</span><span class="sxs-lookup"><span data-stu-id="58e69-128">Should support property changed events using <xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A> and <xref:System.Windows.Automation.Automation.RemoveAutomationPropertyChangedEventHandler%2A>.</span></span>|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.IsSelectionRequired%2A>|<span data-ttu-id="58e69-129">属性</span><span class="sxs-lookup"><span data-stu-id="58e69-129">Property</span></span>|<span data-ttu-id="58e69-130">应支持使用 <xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A> 和 <xref:System.Windows.Automation.Automation.RemoveAutomationPropertyChangedEventHandler%2A>的属性更改事件。</span><span class="sxs-lookup"><span data-stu-id="58e69-130">Should support property changed events using <xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A> and <xref:System.Windows.Automation.Automation.RemoveAutomationPropertyChangedEventHandler%2A>.</span></span>|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.GetSelection%2A>|<span data-ttu-id="58e69-131">方法</span><span class="sxs-lookup"><span data-stu-id="58e69-131">Method</span></span>|<span data-ttu-id="58e69-132">无</span><span class="sxs-lookup"><span data-stu-id="58e69-132">None</span></span>|  
|<xref:System.Windows.Automation.SelectionPatternIdentifiers.InvalidatedEvent>|<span data-ttu-id="58e69-133">事件</span><span class="sxs-lookup"><span data-stu-id="58e69-133">Event</span></span>|<span data-ttu-id="58e69-134">在容器中的选项发生重大更改并需要发送多于 <xref:System.Windows.Automation.Provider.AutomationInteropProvider.InvalidateLimit> 常量所允许的添加和移除事件时引发。</span><span class="sxs-lookup"><span data-stu-id="58e69-134">Raised when a selection in a container has changed significantly and requires sending more addition and removal events than the <xref:System.Windows.Automation.Provider.AutomationInteropProvider.InvalidateLimit> constant permits.</span></span>|  
  
 <span data-ttu-id="58e69-135"><xref:System.Windows.Automation.Provider.ISelectionProvider.IsSelectionRequired%2A> 和 <xref:System.Windows.Automation.Provider.ISelectionProvider.CanSelectMultiple%2A> 属性可以是动态的。</span><span class="sxs-lookup"><span data-stu-id="58e69-135">The <xref:System.Windows.Automation.Provider.ISelectionProvider.IsSelectionRequired%2A> and <xref:System.Windows.Automation.Provider.ISelectionProvider.CanSelectMultiple%2A> properties can be dynamic.</span></span> <span data-ttu-id="58e69-136">例如，控件的初始状态默认可能未选择任何项，指示 <xref:System.Windows.Automation.Provider.ISelectionProvider.IsSelectionRequired%2A> 是 `false`。</span><span class="sxs-lookup"><span data-stu-id="58e69-136">For example, the initial state of a control might not have any items selected by default, indicating that <xref:System.Windows.Automation.Provider.ISelectionProvider.IsSelectionRequired%2A> is `false`.</span></span> <span data-ttu-id="58e69-137">但是，选择某一项后，该控件必须始终具有至少一个选定的项。</span><span class="sxs-lookup"><span data-stu-id="58e69-137">However, after an item is selected, the control must always have at least one item selected.</span></span> <span data-ttu-id="58e69-138">同样，在极少数情况下，控件可能允许在初始状态下选择多个项，但随后仅允许选择一个选项。</span><span class="sxs-lookup"><span data-stu-id="58e69-138">Similarly, in rare cases, a control might allow multiple items to be selected on initialization, but subsequently allow only single selections to be made.</span></span>  
  
<a name="Exceptions"></a>

## <a name="exceptions"></a><span data-ttu-id="58e69-139">异常</span><span class="sxs-lookup"><span data-stu-id="58e69-139">Exceptions</span></span>  

 <span data-ttu-id="58e69-140">提供程序必须引发以下异常。</span><span class="sxs-lookup"><span data-stu-id="58e69-140">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="58e69-141">异常类型</span><span class="sxs-lookup"><span data-stu-id="58e69-141">Exception Type</span></span>|<span data-ttu-id="58e69-142">条件</span><span class="sxs-lookup"><span data-stu-id="58e69-142">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.Windows.Automation.ElementNotEnabledException>|<span data-ttu-id="58e69-143">如果未启用该控件。</span><span class="sxs-lookup"><span data-stu-id="58e69-143">If the control is not enabled.</span></span>|  
|<xref:System.InvalidOperationException>|<span data-ttu-id="58e69-144">如果该控件是隐藏的。</span><span class="sxs-lookup"><span data-stu-id="58e69-144">If the control is hidden.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="58e69-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58e69-145">See also</span></span>

- [<span data-ttu-id="58e69-146">UI 自动化控件模式概述</span><span class="sxs-lookup"><span data-stu-id="58e69-146">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="58e69-147">在 UI 自动化提供程序中支持控件模式</span><span class="sxs-lookup"><span data-stu-id="58e69-147">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="58e69-148">客户端的 UI 自动化控件模式</span><span class="sxs-lookup"><span data-stu-id="58e69-148">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="58e69-149">实现 UI 自动化 SelectionItem 控件模式</span><span class="sxs-lookup"><span data-stu-id="58e69-149">Implementing the UI Automation SelectionItem Control Pattern</span></span>](implementing-the-ui-automation-selectionitem-control-pattern.md)
- [<span data-ttu-id="58e69-150">UI 自动化树概述</span><span class="sxs-lookup"><span data-stu-id="58e69-150">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="58e69-151">在 UI 自动化中使用缓存</span><span class="sxs-lookup"><span data-stu-id="58e69-151">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
