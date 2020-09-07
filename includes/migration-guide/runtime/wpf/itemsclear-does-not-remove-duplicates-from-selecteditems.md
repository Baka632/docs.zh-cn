---
ms.openlocfilehash: 25ce391f917bd270d4d9a75f608e4a8ec763d15c
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496341"
---
### <a name="itemsclear-does-not-remove-duplicates-from-selecteditems"></a><span data-ttu-id="dfa35-101">Items.Clear 不会从 SelectedItems 删除重复项</span><span class="sxs-lookup"><span data-stu-id="dfa35-101">Items.Clear does not remove duplicates from SelectedItems</span></span>

#### <a name="details"></a><span data-ttu-id="dfa35-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="dfa35-102">Details</span></span>

<span data-ttu-id="dfa35-103">假设选择器（已启用多个选择）在其 <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> 集合中有多个重复项（出现不止一次的相同项）。</span><span class="sxs-lookup"><span data-stu-id="dfa35-103">Suppose a Selector (with multiple selection enabled) has duplicates in its <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> collection - the same item appears more than once.</span></span>  <span data-ttu-id="dfa35-104">从数据源删除这些项（例如通过调用 Items.Clear）不会从 <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> 删除它们；仅删除第一个实例。</span><span class="sxs-lookup"><span data-stu-id="dfa35-104">Removing those items from the data source (e.g. by calling Items.Clear) fails to remove them from <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName>; only the first instance is removed.</span></span> <span data-ttu-id="dfa35-105">此外，随后使用 <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName>（例如 SelectedItems.Clear()）可能会遇到 <xref:System.ArgumentException?displayProperty=fullName> 等问题，这是因为 <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> 包含不再出现在数据源中的项。</span><span class="sxs-lookup"><span data-stu-id="dfa35-105">Furthermore, subsequent use of <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> (e.g. SelectedItems.Clear()) can encounter problems such as <xref:System.ArgumentException?displayProperty=fullName>, because <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> contains items that are no longer in the data source.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="dfa35-106">建议</span><span class="sxs-lookup"><span data-stu-id="dfa35-106">Suggestion</span></span>

<span data-ttu-id="dfa35-107">如果可能请升级到 .NET Framework 4.6.2。</span><span class="sxs-lookup"><span data-stu-id="dfa35-107">Upgrade if possible to .NET Framework 4.6.2.</span></span>

| <span data-ttu-id="dfa35-108">“属性”</span><span class="sxs-lookup"><span data-stu-id="dfa35-108">Name</span></span>    | <span data-ttu-id="dfa35-109">“值”</span><span class="sxs-lookup"><span data-stu-id="dfa35-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="dfa35-110">范围</span><span class="sxs-lookup"><span data-stu-id="dfa35-110">Scope</span></span>   |<span data-ttu-id="dfa35-111">次要</span><span class="sxs-lookup"><span data-stu-id="dfa35-111">Minor</span></span>|
|<span data-ttu-id="dfa35-112">Version</span><span class="sxs-lookup"><span data-stu-id="dfa35-112">Version</span></span>|<span data-ttu-id="dfa35-113">4.5</span><span class="sxs-lookup"><span data-stu-id="dfa35-113">4.5</span></span>|
|<span data-ttu-id="dfa35-114">类型</span><span class="sxs-lookup"><span data-stu-id="dfa35-114">Type</span></span>|<span data-ttu-id="dfa35-115">运行时</span><span class="sxs-lookup"><span data-stu-id="dfa35-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="dfa35-116">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="dfa35-116">Affected APIs</span></span>

- <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Windows.Controls.Primitives.MultiSelector.SelectedItems`

-->
