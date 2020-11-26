---
title: 实现 UI 自动化 Scroll 控件模式
description: 查看在 UI 自动化中实现 Scroll 控件模式的准则和约定。 请参阅 Iscrollprovider 必需接口的必需成员。
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Scroll control pattern
- control patterns, Scroll
- Scroll control pattern
ms.assetid: 73d64242-6cbb-424c-92dd-dc69530b7899
ms.openlocfilehash: 4069772530d8b4db817aa1b7a9be86a3ee83881e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239258"
---
# <a name="implementing-the-ui-automation-scroll-control-pattern"></a><span data-ttu-id="74f29-104">实现 UI 自动化 Scroll 控件模式</span><span class="sxs-lookup"><span data-stu-id="74f29-104">Implementing the UI Automation Scroll Control Pattern</span></span>

> [!NOTE]
> <span data-ttu-id="74f29-105">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="74f29-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="74f29-106">有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](/windows/win32/winauto/entry-uiauto-win32)。</span><span class="sxs-lookup"><span data-stu-id="74f29-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="74f29-107">本主题介绍了实现 <xref:System.Windows.Automation.Provider.IScrollProvider>的准则和约定，包括有关事件和属性的信息。</span><span class="sxs-lookup"><span data-stu-id="74f29-107">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IScrollProvider>, including information about events and properties.</span></span> <span data-ttu-id="74f29-108">本主题的结尾列出了指向其他参考资料的链接。</span><span class="sxs-lookup"><span data-stu-id="74f29-108">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="74f29-109"><xref:System.Windows.Automation.ScrollPattern> 控件模式用于支持充当子对象集合的可滚动容器的控件。</span><span class="sxs-lookup"><span data-stu-id="74f29-109">The <xref:System.Windows.Automation.ScrollPattern> control pattern is used to support a control that acts as a scrollable container for a collection of child objects.</span></span> <span data-ttu-id="74f29-110">尽管通常需要使用滚动条来支持滚动功能，但该控件并不需要。</span><span class="sxs-lookup"><span data-stu-id="74f29-110">The control is not required to use scrollbars to support the scrolling functionality, although it commonly does.</span></span>  
  
 <span data-ttu-id="74f29-111">![无滚动栏的滚动控件。](./media/uia-scrollpattern-without-scrollbars.PNG "UIA_ScrollPattern_Without_Scrollbars")</span><span class="sxs-lookup"><span data-stu-id="74f29-111">![Scroll control without scrollbars.](./media/uia-scrollpattern-without-scrollbars.PNG "UIA_ScrollPattern_Without_Scrollbars")</span></span>  
<span data-ttu-id="74f29-112">不使用滚动条的滚动控件示例</span><span class="sxs-lookup"><span data-stu-id="74f29-112">Example of a Scrolling Control that Does Not Use Scrollbars</span></span>  
  
 <span data-ttu-id="74f29-113">有关实现此控件的控件示例，请参阅 [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="74f29-113">For examples of controls that implement this control, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>

## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="74f29-114">实现准则和约定</span><span class="sxs-lookup"><span data-stu-id="74f29-114">Implementation Guidelines and Conventions</span></span>  

 <span data-ttu-id="74f29-115">在实现 Scroll 控件模式时，请注意以下准则和约定：</span><span class="sxs-lookup"><span data-stu-id="74f29-115">When implementing the Scroll control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="74f29-116">此控件的子级必须实现 <xref:System.Windows.Automation.Provider.IScrollItemProvider>。</span><span class="sxs-lookup"><span data-stu-id="74f29-116">The children of this control must implement <xref:System.Windows.Automation.Provider.IScrollItemProvider>.</span></span>  
  
- <span data-ttu-id="74f29-117">容器控件的滚动条不支持 <xref:System.Windows.Automation.ScrollPattern> 控件模式。</span><span class="sxs-lookup"><span data-stu-id="74f29-117">The scrollbars of a container control do not support the <xref:System.Windows.Automation.ScrollPattern> control pattern.</span></span> <span data-ttu-id="74f29-118">相反，它们必须支持 <xref:System.Windows.Automation.RangeValuePattern> 控件模式。</span><span class="sxs-lookup"><span data-stu-id="74f29-118">They must support the <xref:System.Windows.Automation.RangeValuePattern> control pattern instead.</span></span>  
  
- <span data-ttu-id="74f29-119">当以百分比度量滚动时，与滚动刻度相关的所有值或量必须规范化为 0 到 100 的范围。</span><span class="sxs-lookup"><span data-stu-id="74f29-119">When scrolling is measured in percentages, all values or amounts related to scroll graduation must be normalized to a range of 0 to 100.</span></span>  
  
- <span data-ttu-id="74f29-120"><xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty> 和 <xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty> 独立于 <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty>。</span><span class="sxs-lookup"><span data-stu-id="74f29-120"><xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty> and <xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty> are independent of the <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty>.</span></span>  
  
- <span data-ttu-id="74f29-121">如果 <xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty> = `false` 则 <xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalViewSizeProperty> 应设置为 100%，且 <xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalScrollPercentProperty> 应设置为 <xref:System.Windows.Automation.ScrollPatternIdentifiers.NoScroll>。</span><span class="sxs-lookup"><span data-stu-id="74f29-121">If <xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty> = `false` then <xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalViewSizeProperty> should be set to 100% and <xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalScrollPercentProperty> should be set to <xref:System.Windows.Automation.ScrollPatternIdentifiers.NoScroll>.</span></span> <span data-ttu-id="74f29-122">类似，如果 <xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty> = `false` 则 <xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalViewSizeProperty> 应设置为 100%，且 <xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalScrollPercentProperty> 应设置为 <xref:System.Windows.Automation.ScrollPatternIdentifiers.NoScroll>。</span><span class="sxs-lookup"><span data-stu-id="74f29-122">Likewise, if <xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty> = `false` then <xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalViewSizeProperty> should be set to 100 percent and <xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalScrollPercentProperty> should be set to <xref:System.Windows.Automation.ScrollPatternIdentifiers.NoScroll>.</span></span> <span data-ttu-id="74f29-123">这样一来，UI 自动化客户端就可以在该方法中使用这些属性值， <xref:System.Windows.Automation.ScrollPattern.SetScrollPercent%2A> 同时避免 [争用条件](https://support.microsoft.com/default.aspx?scid=kb;en-us;317723) （如果客户端不感兴趣地激活）。</span><span class="sxs-lookup"><span data-stu-id="74f29-123">This allows a UI Automation client to use these property values within the <xref:System.Windows.Automation.ScrollPattern.SetScrollPercent%2A> method while avoiding a [race condition](https://support.microsoft.com/default.aspx?scid=kb;en-us;317723) if a direction the client is not interested in scrolling becomes activated.</span></span>  
  
- <span data-ttu-id="74f29-124"><xref:System.Windows.Automation.Provider.IScrollProvider.HorizontalScrollPercent%2A> 是特定于区域设置。</span><span class="sxs-lookup"><span data-stu-id="74f29-124"><xref:System.Windows.Automation.Provider.IScrollProvider.HorizontalScrollPercent%2A> is locale-specific.</span></span> <span data-ttu-id="74f29-125">设置 HorizontalScrollPercent = 100.0 时，则对于英语等从左到右阅读的语言，必须将控件的滚动位置设置为等于其最右位置。</span><span class="sxs-lookup"><span data-stu-id="74f29-125">Setting HorizontalScrollPercent = 100.0 must set the scrolling location of the control to the equivalent of its rightmost position for languages such as English that read left to right.</span></span> <span data-ttu-id="74f29-126">而对于阿拉伯语等从右到左阅读的语言，设置 HorizontalScrollPercent = 100.0 时必须将滚动位置设置为最左位置。</span><span class="sxs-lookup"><span data-stu-id="74f29-126">Alternately, for languages such as Arabic that read right to left, setting HorizontalScrollPercent = 100.0 must set the scroll location to the leftmost position.</span></span>  
  
<a name="Required_Members_for_IScrollProvider"></a>

## <a name="required-members-for-iscrollprovider"></a><span data-ttu-id="74f29-127">IScrollProvider 必需的成员</span><span class="sxs-lookup"><span data-stu-id="74f29-127">Required Members for IScrollProvider</span></span>  

 <span data-ttu-id="74f29-128">实现 <xref:System.Windows.Automation.Provider.IScrollProvider>需要以下属性和方法。</span><span class="sxs-lookup"><span data-stu-id="74f29-128">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.IScrollProvider>.</span></span>  
  
|<span data-ttu-id="74f29-129">必需的成员</span><span class="sxs-lookup"><span data-stu-id="74f29-129">Required member</span></span>|<span data-ttu-id="74f29-130">成员类型</span><span class="sxs-lookup"><span data-stu-id="74f29-130">Member type</span></span>|<span data-ttu-id="74f29-131">说明</span><span class="sxs-lookup"><span data-stu-id="74f29-131">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.HorizontalScrollPercent%2A>|<span data-ttu-id="74f29-132">属性</span><span class="sxs-lookup"><span data-stu-id="74f29-132">Property</span></span>|<span data-ttu-id="74f29-133">无</span><span class="sxs-lookup"><span data-stu-id="74f29-133">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.VerticalScrollPercent%2A>|<span data-ttu-id="74f29-134">属性</span><span class="sxs-lookup"><span data-stu-id="74f29-134">Property</span></span>|<span data-ttu-id="74f29-135">无</span><span class="sxs-lookup"><span data-stu-id="74f29-135">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.HorizontalViewSize%2A>|<span data-ttu-id="74f29-136">属性</span><span class="sxs-lookup"><span data-stu-id="74f29-136">Property</span></span>|<span data-ttu-id="74f29-137">无</span><span class="sxs-lookup"><span data-stu-id="74f29-137">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.VerticalViewSize%2A>|<span data-ttu-id="74f29-138">属性</span><span class="sxs-lookup"><span data-stu-id="74f29-138">Property</span></span>|<span data-ttu-id="74f29-139">无</span><span class="sxs-lookup"><span data-stu-id="74f29-139">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.HorizontallyScrollable%2A>|<span data-ttu-id="74f29-140">属性</span><span class="sxs-lookup"><span data-stu-id="74f29-140">Property</span></span>|<span data-ttu-id="74f29-141">无</span><span class="sxs-lookup"><span data-stu-id="74f29-141">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.VerticallyScrollable%2A>|<span data-ttu-id="74f29-142">属性</span><span class="sxs-lookup"><span data-stu-id="74f29-142">Property</span></span>|<span data-ttu-id="74f29-143">无</span><span class="sxs-lookup"><span data-stu-id="74f29-143">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.Scroll%2A>|<span data-ttu-id="74f29-144">方法</span><span class="sxs-lookup"><span data-stu-id="74f29-144">Method</span></span>|<span data-ttu-id="74f29-145">无</span><span class="sxs-lookup"><span data-stu-id="74f29-145">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.SetScrollPercent%2A>|<span data-ttu-id="74f29-146">方法</span><span class="sxs-lookup"><span data-stu-id="74f29-146">Method</span></span>|<span data-ttu-id="74f29-147">无</span><span class="sxs-lookup"><span data-stu-id="74f29-147">None</span></span>|  
  
 <span data-ttu-id="74f29-148">没有与此控件模式关联的事件。</span><span class="sxs-lookup"><span data-stu-id="74f29-148">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>

## <a name="exceptions"></a><span data-ttu-id="74f29-149">异常</span><span class="sxs-lookup"><span data-stu-id="74f29-149">Exceptions</span></span>  

 <span data-ttu-id="74f29-150">提供程序必须引发以下异常。</span><span class="sxs-lookup"><span data-stu-id="74f29-150">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="74f29-151">异常类型</span><span class="sxs-lookup"><span data-stu-id="74f29-151">Exception Type</span></span>|<span data-ttu-id="74f29-152">条件</span><span class="sxs-lookup"><span data-stu-id="74f29-152">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="74f29-153">如果控件仅对于水平或垂直滚动支持<xref:System.Windows.Automation.Provider.IScrollProvider.Scroll%2A> 值，而传入了 <xref:System.Windows.Automation.ScrollAmount.SmallIncrement> 值，则 <xref:System.Windows.Automation.ScrollAmount.LargeIncrement> 将引发此异常。</span><span class="sxs-lookup"><span data-stu-id="74f29-153"><xref:System.Windows.Automation.Provider.IScrollProvider.Scroll%2A> throws this exception if a control supports <xref:System.Windows.Automation.ScrollAmount.SmallIncrement> values exclusively for horizontal or vertical scrolling, but a <xref:System.Windows.Automation.ScrollAmount.LargeIncrement> value is passed in.</span></span>|  
|<xref:System.ArgumentException>|<span data-ttu-id="74f29-154">当传入值无法转换为双精度时，<xref:System.Windows.Automation.Provider.IScrollProvider.SetScrollPercent%2A> 会引发此异常。</span><span class="sxs-lookup"><span data-stu-id="74f29-154"><xref:System.Windows.Automation.Provider.IScrollProvider.SetScrollPercent%2A> throws this exception when a value that cannot be converted to a double is passed in.</span></span>|  
|<xref:System.ArgumentOutOfRangeException>|<span data-ttu-id="74f29-155">当传入大于 100 或小于 0 的值（-1 除外，因为它等效于<xref:System.Windows.Automation.Provider.IScrollProvider.SetScrollPercent%2A> ）时， <xref:System.Windows.Automation.ScrollPatternIdentifiers.NoScroll>会引发此异常。</span><span class="sxs-lookup"><span data-stu-id="74f29-155"><xref:System.Windows.Automation.Provider.IScrollProvider.SetScrollPercent%2A> throws this exception when a value greater than 100 or less than 0 is passed in (except -1 which is equivalent to <xref:System.Windows.Automation.ScrollPatternIdentifiers.NoScroll>).</span></span>|  
|<xref:System.InvalidOperationException>|<span data-ttu-id="74f29-156">当尝试在不支持的方向进行滚动时， <xref:System.Windows.Automation.Provider.IScrollProvider.Scroll%2A> 和 <xref:System.Windows.Automation.Provider.IScrollProvider.SetScrollPercent%2A> 都引发此异常。</span><span class="sxs-lookup"><span data-stu-id="74f29-156">Both <xref:System.Windows.Automation.Provider.IScrollProvider.Scroll%2A> and <xref:System.Windows.Automation.Provider.IScrollProvider.SetScrollPercent%2A> throw this exception when an attempt is made to scroll in an unsupported direction.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="74f29-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74f29-157">See also</span></span>

- [<span data-ttu-id="74f29-158">UI 自动化控件模式概述</span><span class="sxs-lookup"><span data-stu-id="74f29-158">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="74f29-159">在 UI 自动化提供程序中支持控件模式</span><span class="sxs-lookup"><span data-stu-id="74f29-159">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="74f29-160">客户端的 UI 自动化控件模式</span><span class="sxs-lookup"><span data-stu-id="74f29-160">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="74f29-161">UI 自动化树概述</span><span class="sxs-lookup"><span data-stu-id="74f29-161">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="74f29-162">在 UI 自动化中使用缓存</span><span class="sxs-lookup"><span data-stu-id="74f29-162">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
