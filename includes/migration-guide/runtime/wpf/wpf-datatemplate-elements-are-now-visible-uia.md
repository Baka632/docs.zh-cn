---
ms.openlocfilehash: 4394e69dafeb6cce2d7719a67bbce396d3bc1086
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497722"
---
### <a name="wpf-datatemplate-elements-are-now-visible-to-uia"></a><span data-ttu-id="4ed96-101">WPF DataTemplate 元素现在对 UIA 可见</span><span class="sxs-lookup"><span data-stu-id="4ed96-101">WPF DataTemplate elements are now visible to UIA</span></span>

#### <a name="details"></a><span data-ttu-id="4ed96-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="4ed96-102">Details</span></span>

<span data-ttu-id="4ed96-103">以前 <xref:System.Windows.DataTemplate?displayProperty=fullName> 元素对 UI 自动化不可见。</span><span class="sxs-lookup"><span data-stu-id="4ed96-103">Previously, <xref:System.Windows.DataTemplate?displayProperty=fullName> elements were invisible to UI Automation.</span></span> <span data-ttu-id="4ed96-104">从 4.5 开始，UI 自动化将能检测到这些元素。</span><span class="sxs-lookup"><span data-stu-id="4ed96-104">Beginning in 4.5, UI Automation will detect these elements.</span></span> <span data-ttu-id="4ed96-105">这在许多情况下很有用，但可能会中断依赖于不包含 <xref:System.Windows.DataTemplate?displayProperty=fullName> 元素的 UIA 树的测试。</span><span class="sxs-lookup"><span data-stu-id="4ed96-105">This is useful in many cases, but can break tests that depend on UIA trees not containing <xref:System.Windows.DataTemplate?displayProperty=fullName> elements.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4ed96-106">建议</span><span class="sxs-lookup"><span data-stu-id="4ed96-106">Suggestion</span></span>

<span data-ttu-id="4ed96-107">此应用的 UI 自动化测试需要更新，以便考虑到 UIA 树现在所包含的以前不可见的 <xref:System.Windows.DataTemplate?displayProperty=fullName> 元素。</span><span class="sxs-lookup"><span data-stu-id="4ed96-107">UI Automation tests for this app may need updated to account for the UIA tree now including previously invisible <xref:System.Windows.DataTemplate?displayProperty=fullName> elements.</span></span> <span data-ttu-id="4ed96-108">例如，对于预计某些元素彼此相邻的测试，现在需要考虑到其间之前不可见的 UIA 元素。</span><span class="sxs-lookup"><span data-stu-id="4ed96-108">For example, tests that expect some elements to be next to each other may now need to expect previously invisible UIA elements in between.</span></span> <span data-ttu-id="4ed96-109">否则，依赖 UIA 元素的特定计数或索引的测试可能需要使用新值进行更新。</span><span class="sxs-lookup"><span data-stu-id="4ed96-109">Or tests that rely on certain counts or indexes for UIA elements may need updated with new values.</span></span>

| <span data-ttu-id="4ed96-110">“属性”</span><span class="sxs-lookup"><span data-stu-id="4ed96-110">Name</span></span>    | <span data-ttu-id="4ed96-111">“值”</span><span class="sxs-lookup"><span data-stu-id="4ed96-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4ed96-112">范围</span><span class="sxs-lookup"><span data-stu-id="4ed96-112">Scope</span></span>   |<span data-ttu-id="4ed96-113">边缘</span><span class="sxs-lookup"><span data-stu-id="4ed96-113">Edge</span></span>|
|<span data-ttu-id="4ed96-114">Version</span><span class="sxs-lookup"><span data-stu-id="4ed96-114">Version</span></span>|<span data-ttu-id="4ed96-115">4.5</span><span class="sxs-lookup"><span data-stu-id="4ed96-115">4.5</span></span>|
|<span data-ttu-id="4ed96-116">类型</span><span class="sxs-lookup"><span data-stu-id="4ed96-116">Type</span></span>|<span data-ttu-id="4ed96-117">运行时</span><span class="sxs-lookup"><span data-stu-id="4ed96-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="4ed96-118">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="4ed96-118">Affected APIs</span></span>

- <xref:System.Windows.DataTemplate.%23ctor>
- <xref:System.Windows.DataTemplate.%23ctor(System.Object)>

<!--

#### Affected APIs

- `M:System.Windows.DataTemplate.#ctor`
- `M:System.Windows.DataTemplate.#ctor(System.Object)`

-->
