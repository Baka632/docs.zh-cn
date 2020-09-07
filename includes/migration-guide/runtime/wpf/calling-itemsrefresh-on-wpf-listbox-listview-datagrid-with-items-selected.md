---
ms.openlocfilehash: 972601874d80d82ebae8b79779acfed82e5570cb
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496632"
---
### <a name="calling-itemsrefresh-on-a-wpf-listbox-listview-or-datagrid-with-items-selected-can-cause-duplicate-items-to-appear-in-the-element"></a><span data-ttu-id="c6739-101">在选定项目的 WPF ListBox、ListView 或 DataGrid 上调用 Items.Refresh 可能会导致元素中出现重复项目</span><span class="sxs-lookup"><span data-stu-id="c6739-101">Calling Items.Refresh on a WPF ListBox, ListView, or DataGrid with items selected can cause duplicate items to appear in the element</span></span>

#### <a name="details"></a><span data-ttu-id="c6739-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="c6739-102">Details</span></span>

<span data-ttu-id="c6739-103">在 .NET Framework 4.5 中，在项目已在 <xref:System.Windows.Controls.ListBox?displayProperty=fullName> 中选定的同时从代码中调用 ListBox.Items.Refresh 可能会导致选定项目在列表中重复。</span><span class="sxs-lookup"><span data-stu-id="c6739-103">In the .NET Framework 4.5, calling ListBox.Items.Refresh from code while items are selected in a <xref:System.Windows.Controls.ListBox?displayProperty=fullName> can cause the selected items to be duplicated in the list.</span></span> <span data-ttu-id="c6739-104"><xref:System.Windows.Controls.ListView?displayProperty=fullName> 和 <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> 会出现类似问题。</span><span class="sxs-lookup"><span data-stu-id="c6739-104">A similar issue occurs with <xref:System.Windows.Controls.ListView?displayProperty=fullName> and <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>.</span></span> <span data-ttu-id="c6739-105">此问题已在 .NET Framework 4.6 中解决。</span><span class="sxs-lookup"><span data-stu-id="c6739-105">This is fixed in the .NET Framework 4.6.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c6739-106">建议</span><span class="sxs-lookup"><span data-stu-id="c6739-106">Suggestion</span></span>

<span data-ttu-id="c6739-107">在调用 <xref:System.Windows.Data.CollectionView.Refresh?displayProperty=fullName> 前以编程方式取消选择项，然后在调用完成后重新选择它们，可以解决此问题。</span><span class="sxs-lookup"><span data-stu-id="c6739-107">This issue may be worked around by programmatically unselecting items before <xref:System.Windows.Data.CollectionView.Refresh?displayProperty=fullName> is called and then re-selecting them after the call is completed.</span></span> <span data-ttu-id="c6739-108">此外，此问题已在 .NET Framework 4.6 中解决，因此升级到该版本的 .NET Framework 即可解决该问题。</span><span class="sxs-lookup"><span data-stu-id="c6739-108">Alternatively, this issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="c6739-109">“属性”</span><span class="sxs-lookup"><span data-stu-id="c6739-109">Name</span></span>    | <span data-ttu-id="c6739-110">“值”</span><span class="sxs-lookup"><span data-stu-id="c6739-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c6739-111">范围</span><span class="sxs-lookup"><span data-stu-id="c6739-111">Scope</span></span>   |<span data-ttu-id="c6739-112">次要</span><span class="sxs-lookup"><span data-stu-id="c6739-112">Minor</span></span>|
|<span data-ttu-id="c6739-113">Version</span><span class="sxs-lookup"><span data-stu-id="c6739-113">Version</span></span>|<span data-ttu-id="c6739-114">4.5</span><span class="sxs-lookup"><span data-stu-id="c6739-114">4.5</span></span>|
|<span data-ttu-id="c6739-115">类型</span><span class="sxs-lookup"><span data-stu-id="c6739-115">Type</span></span>|<span data-ttu-id="c6739-116">运行时</span><span class="sxs-lookup"><span data-stu-id="c6739-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c6739-117">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="c6739-117">Affected APIs</span></span>

- <xref:System.Windows.Data.CollectionView.Refresh?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Data.CollectionView.Refresh`

-->
