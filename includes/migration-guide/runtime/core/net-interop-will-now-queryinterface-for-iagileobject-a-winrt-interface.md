---
ms.openlocfilehash: 65fa5d8629ce8e426cf1623590a056e5cad0b91f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497433"
---
### <a name="net-interop-will-now-queryinterface-for-iagileobject-a-winrt-interface"></a><span data-ttu-id="ffb2e-101">.NET Interop 现将为 IAgileObject 的 QueryInterface（WinRT 接口）</span><span class="sxs-lookup"><span data-stu-id="ffb2e-101">.NET Interop will now QueryInterface for IAgileObject (a WinRT interface)</span></span>

#### <a name="details"></a><span data-ttu-id="ffb2e-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="ffb2e-102">Details</span></span>

<span data-ttu-id="ffb2e-103">自 .NET Framework 4.8 起，使用带有 .NET 委托的 WinRT 事件时，Windows 将为 IAgileObject 进行 QI。</span><span class="sxs-lookup"><span data-stu-id="ffb2e-103">When using a WinRT event with a .NET delegate, Windows will QI for IAgileObject starting with the .NET Framework 4.8.</span></span>  <span data-ttu-id="ffb2e-104">在以前版本的 .NET Framework 中，运行时进行该 QI 将失败，并且无法订阅事件。</span><span class="sxs-lookup"><span data-stu-id="ffb2e-104">In previous versions of the .NET Framework, the runtime would fail that QI, and the event could not be subscribed.</span></span><ul><li><span data-ttu-id="ffb2e-105">[x] Quirked</span><span class="sxs-lookup"><span data-stu-id="ffb2e-105">[ x ] Quirked</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="ffb2e-106">建议</span><span class="sxs-lookup"><span data-stu-id="ffb2e-106">Suggestion</span></span>

<span data-ttu-id="ffb2e-107">如果为 IAgileObject 启用 QI 会中断执行，则可以通过设置以下配置来禁用此代码。</span><span class="sxs-lookup"><span data-stu-id="ffb2e-107">If enabling the QI for IAgileObject breaks execution, you can disable this code by setting the following configuration.</span></span> <h4><span data-ttu-id="ffb2e-108">方法 1：环境变量</span><span class="sxs-lookup"><span data-stu-id="ffb2e-108">Method 1: Environment variable</span></span></h4> <span data-ttu-id="ffb2e-109">设置以下环境变量：COMPLUS_DisableCCWSupportIAgileObject=1 此方法会影响任何继承此环境变量的环境。</span><span class="sxs-lookup"><span data-stu-id="ffb2e-109">Set the following environment variable:COMPLUS_DisableCCWSupportIAgileObject=1This method affects any environment that inherits this environment variable.</span></span> <span data-ttu-id="ffb2e-110">这可能只是一个控制台会话，如果在全局范围内设置环境变量，它可能会影响整个计算机。</span><span class="sxs-lookup"><span data-stu-id="ffb2e-110">This might be just a single console session, or it might affect the entire machine if you set the environment variable globally.</span></span> <span data-ttu-id="ffb2e-111">环境变量名称不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="ffb2e-111">The environment variable name is not case-sensitive.</span></span> <h4><span data-ttu-id="ffb2e-112">方法 2：注册表</span><span class="sxs-lookup"><span data-stu-id="ffb2e-112">Method 2: Registry</span></span></h4> <span data-ttu-id="ffb2e-113">使用注册表编辑器 (regedit.exe)，查找以下某个子项：HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft.NETFramework HKEY_CURRENT_USER\SOFTWARE\Microsoft.NETFramework 然后添加以下内容：值名称：DisableCCWSupportIAgileObject 类型：DWORD（32 位）值（也称为 REG_WORD）值：1 可以使用 Windows REG.EXE 工具从命令行或脚本环境添加此值。</span><span class="sxs-lookup"><span data-stu-id="ffb2e-113">Using Registry Editor (regedit.exe), find either of the following subkeys:HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft.NETFramework HKEY_CURRENT_USER\SOFTWARE\Microsoft.NETFrameworkThen add the following:Value name: DisableCCWSupportIAgileObject Type: DWORD (32-bit) Value (also called REG_WORD) Value: 1You can use the Windows REG.EXE tool to add this value from a command-line or scripting environment.</span></span> <span data-ttu-id="ffb2e-114">例如：</span><span class="sxs-lookup"><span data-stu-id="ffb2e-114">For example:</span></span><pre><code class="lang-console">reg add HKLM\SOFTWARE\Microsoft\.NETFramework /v DisableCCWSupportIAgileObject /t REG_DWORD /d 1&#13;&#10;</code></pre><span data-ttu-id="ffb2e-115">在这种情况下，使用 <code>HKLM</code> 而不使用 <code>HKEY_LOCAL_MACHINE</code>。</span><span class="sxs-lookup"><span data-stu-id="ffb2e-115">In this case, <code>HKLM</code> is used instead of <code>HKEY_LOCAL_MACHINE</code>.</span></span> <span data-ttu-id="ffb2e-116">使用 <code>reg add /?</code> 查看有关此语法的帮助内容。</span><span class="sxs-lookup"><span data-stu-id="ffb2e-116">Use <code>reg add /?</code> to see help on this syntax.</span></span> <span data-ttu-id="ffb2e-117">注册表值名称不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="ffb2e-117">The registry value name is not case-sensitive.</span></span>

| <span data-ttu-id="ffb2e-118">“属性”</span><span class="sxs-lookup"><span data-stu-id="ffb2e-118">Name</span></span>    | <span data-ttu-id="ffb2e-119">“值”</span><span class="sxs-lookup"><span data-stu-id="ffb2e-119">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ffb2e-120">范围</span><span class="sxs-lookup"><span data-stu-id="ffb2e-120">Scope</span></span>   |<span data-ttu-id="ffb2e-121">边缘</span><span class="sxs-lookup"><span data-stu-id="ffb2e-121">Edge</span></span>|
|<span data-ttu-id="ffb2e-122">Version</span><span class="sxs-lookup"><span data-stu-id="ffb2e-122">Version</span></span>|<span data-ttu-id="ffb2e-123">4.8</span><span class="sxs-lookup"><span data-stu-id="ffb2e-123">4.8</span></span>|
|<span data-ttu-id="ffb2e-124">类型</span><span class="sxs-lookup"><span data-stu-id="ffb2e-124">Type</span></span>|<span data-ttu-id="ffb2e-125">运行时</span><span class="sxs-lookup"><span data-stu-id="ffb2e-125">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="ffb2e-126">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="ffb2e-126">Affected APIs</span></span>

<span data-ttu-id="ffb2e-127">无法通过 API 分析检测到。</span><span class="sxs-lookup"><span data-stu-id="ffb2e-127">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
