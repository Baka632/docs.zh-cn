---
ms.openlocfilehash: d23d7821e19b9d7f2db13a6bfdf868a8414cf721
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496274"
---
### <a name="item-scrolling-a-flat-list-with-items-of-different-pixel-height"></a><span data-ttu-id="9473c-101">项滚动包含不同像素高度的项的平面列表</span><span class="sxs-lookup"><span data-stu-id="9473c-101">Item-scrolling a flat list with items of different pixel-height</span></span>

#### <a name="details"></a><span data-ttu-id="9473c-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="9473c-102">Details</span></span>

<span data-ttu-id="9473c-103">当 <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> 使用虚拟化 (<code>IsVirtualizing=true</code>) 和项滚动 (<code>ScrollUnit=Item</code>) 显示集合时，以及控件滚动显示像素高度不同于其相邻项的项时，<xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName> 将循环访问集合中的所有项。</span><span class="sxs-lookup"><span data-stu-id="9473c-103">When an <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> displays a collection using virtualization (<code>IsVirtualizing=true</code>) and item- scrolling (<code>ScrollUnit=Item</code>), and when the control scrolls to display an item whose height in pixels differs from its neighbors, the <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName> iterates over all items in the collection.</span></span> <span data-ttu-id="9473c-104">在该迭代过程中，UI 无响应；如果集合很大，可以视之为挂起。</span><span class="sxs-lookup"><span data-stu-id="9473c-104">The UI is unresponsive during this iteration; if the collection is large, this can be perceived as a hang.</span></span> <span data-ttu-id="9473c-105">迭代会发生在其他情况下，甚至在之前的 .NET Framework 版本中也会发生。</span><span class="sxs-lookup"><span data-stu-id="9473c-105">The iteration occurs in other circumstances, even in previous .NET Framework releases.</span></span> <span data-ttu-id="9473c-106">例如，在以下情况下会出现上述情形：遇到像素高度不同的项时进行像素滚动 (<code>ScrollUnit=Pixel</code>)，以及遇到子项数量不同于其相邻项的项时进行项滚动分层数据（例如，<xref:System.Windows.Controls.TreeView?displayProperty=fullName> 或已启用分组的 <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName>）。对于项滚动和不同像素高度的情况，.NET Framework 4.6.1 中引入了迭代以修复分层数据布局中的 bug。</span><span class="sxs-lookup"><span data-stu-id="9473c-106">For example, it occurs when pixel-scrolling (<code>ScrollUnit=Pixel</code>) upon encountering an item with different pixel height, and when item-scrolling hierarchical data (such as a <xref:System.Windows.Controls.TreeView?displayProperty=fullName> or an <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> with grouping enabled) upon encountering an item with a different number of descendant items than its neighbors.For the case of item-scrolling and different pixel height, the iteration was introduced in .NET Framework 4.6.1 to fix bugs in the layout of hierarchical data.</span></span>  <span data-ttu-id="9473c-107">如果数据采用平面结构（没有层次结构），则不需要迭代，.NET Framework 4.6.2 在这种情况下也不会执行该操作。</span><span class="sxs-lookup"><span data-stu-id="9473c-107">It is not needed if the data is flat (no hierarchy), and .NET Framework 4.6.2 does not do it in that case.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="9473c-108">建议</span><span class="sxs-lookup"><span data-stu-id="9473c-108">Suggestion</span></span>

<span data-ttu-id="9473c-109">如果迭代发生在 .NET Framework 4.6.1 中，但在以前版本中并未发生 - 也就是说，如果 <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> 项滚动含有像素高度不同的项的平面列表 - 可采用以下两种补救措施：</span><span class="sxs-lookup"><span data-stu-id="9473c-109">If the iteration occurs in .NET Framework 4.6.1 but not in earlier releases - that is, if the <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> is item- scrolling a flat list with items of different pixel height - there are two remedies:</span></span><ol><li><span data-ttu-id="9473c-110">安装 .NET Framework 4.6.2。</span><span class="sxs-lookup"><span data-stu-id="9473c-110">Install .NET Framework 4.6.2.</span></span></li><li><span data-ttu-id="9473c-111">安装适用于 .NET Framework 4.6.1 的修补程序 HR 1605。</span><span class="sxs-lookup"><span data-stu-id="9473c-111">Install hotfix HR 1605 for .NET Framework 4.6.1.</span></span></li></ol>

| <span data-ttu-id="9473c-112">“属性”</span><span class="sxs-lookup"><span data-stu-id="9473c-112">Name</span></span>    | <span data-ttu-id="9473c-113">“值”</span><span class="sxs-lookup"><span data-stu-id="9473c-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="9473c-114">范围</span><span class="sxs-lookup"><span data-stu-id="9473c-114">Scope</span></span>   |<span data-ttu-id="9473c-115">次要</span><span class="sxs-lookup"><span data-stu-id="9473c-115">Minor</span></span>|
|<span data-ttu-id="9473c-116">Version</span><span class="sxs-lookup"><span data-stu-id="9473c-116">Version</span></span>|<span data-ttu-id="9473c-117">4.6.1</span><span class="sxs-lookup"><span data-stu-id="9473c-117">4.6.1</span></span>|
|<span data-ttu-id="9473c-118">类型</span><span class="sxs-lookup"><span data-stu-id="9473c-118">Type</span></span>|<span data-ttu-id="9473c-119">运行时</span><span class="sxs-lookup"><span data-stu-id="9473c-119">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="9473c-120">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="9473c-120">Affected APIs</span></span>

- <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Windows.Controls.VirtualizingStackPanel`

-->
