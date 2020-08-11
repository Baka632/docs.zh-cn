---
title: 从 .NET Framework 到 .NET Core 的中断性变更
titleSuffix: ''
description: 列出了从 .NET Framework 到 .NET Core 的中断性变更。
ms.date: 05/05/2020
ms.openlocfilehash: 5f7424fdd959044b729dfb04f4f0147fbc946bfd
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556301"
---
# <a name="breaking-changes-for-migration-from-net-framework-to-net-core"></a><span data-ttu-id="846a9-103">从 .NET Framework 迁移到 .NET Core 的中断性变更</span><span class="sxs-lookup"><span data-stu-id="846a9-103">Breaking changes for migration from .NET Framework to .NET Core</span></span>

<span data-ttu-id="846a9-104">若要将应用从 .NET Framework 迁移到 .NET Core，本文中列出的中断性变更可能会影响你。</span><span class="sxs-lookup"><span data-stu-id="846a9-104">If you're migrating an app from .NET Framework to .NET Core, the breaking changes listed in this article may affect you.</span></span> <span data-ttu-id="846a9-105">中断性变更按类别进行分组，并且在这些类别中按引入的 .NET Core 版本进行分组。</span><span class="sxs-lookup"><span data-stu-id="846a9-105">Breaking changes are grouped by category, and within those categories, by the version of .NET Core in which they were introduced.</span></span>

> [!NOTE]
> <span data-ttu-id="846a9-106">本文不是 .NET Framework 与 .NET Core 之间的中断性变更的完整列表。</span><span class="sxs-lookup"><span data-stu-id="846a9-106">This article is not a complete list of breaking changes between .NET Framework and .NET Core.</span></span> <span data-ttu-id="846a9-107">在我们发现最重要的中断性变更时，会将其添加到此处。</span><span class="sxs-lookup"><span data-stu-id="846a9-107">The most important breaking changes are added here as we become aware of them.</span></span>

## <a name="core-net-libraries"></a><span data-ttu-id="846a9-108">Core .NET 库</span><span class="sxs-lookup"><span data-stu-id="846a9-108">Core .NET libraries</span></span>

- [<span data-ttu-id="846a9-109">UseShellExecute 默认值更改</span><span class="sxs-lookup"><span data-stu-id="846a9-109">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute)
- [<span data-ttu-id="846a9-110">FileSystemInfo.Attributes 引发的 UnauthorizedAccessException</span><span class="sxs-lookup"><span data-stu-id="846a9-110">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes)
- [<span data-ttu-id="846a9-111">不支持处理损坏的进程状态异常</span><span class="sxs-lookup"><span data-stu-id="846a9-111">Handling corrupted-process-state exceptions is not supported</span></span>](#handling-corrupted-state-exceptions-is-not-supported)
- [<span data-ttu-id="846a9-112">UriBuilder 属性不再预置前导字符</span><span class="sxs-lookup"><span data-stu-id="846a9-112">UriBuilder properties no longer prepend leading characters</span></span>](#uribuilder-properties-no-longer-prepend-leading-characters)
- [<span data-ttu-id="846a9-113">Process.StartInfo 对未启动的进程引发 InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="846a9-113">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>](#processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start)

### <a name="net-core-21"></a><span data-ttu-id="846a9-114">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="846a9-114">.NET Core 2.1</span></span>

[!INCLUDE[Process.Start changes](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

### <a name="net-core-10"></a><span data-ttu-id="846a9-115">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="846a9-115">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

[!INCLUDE [corrupted-state-exceptions](~/includes/core-changes/corefx/1.0/corrupted-state-exceptions.md)]

***

[!INCLUDE [uribuilder-behavior-changes](../../../includes/core-changes/corefx/1.0/uribuilder-behavior-changes.md)]

***

[!INCLUDE [startinfo-throws-exception](../../../includes/core-changes/corefx/1.0/startinfo-throws-exception.md)]

***

## <a name="cryptography"></a><span data-ttu-id="846a9-116">密码</span><span class="sxs-lookup"><span data-stu-id="846a9-116">Cryptography</span></span>

- [<span data-ttu-id="846a9-117">已考虑 SignedCms.ComputeSignature 的布尔参数</span><span class="sxs-lookup"><span data-stu-id="846a9-117">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>](#boolean-parameter-of-signedcmscomputesignature-is-respected)

### <a name="net-core-21"></a><span data-ttu-id="846a9-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="846a9-118">.NET Core 2.1</span></span>

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

***

## <a name="msbuild"></a><span data-ttu-id="846a9-119">MSBuild</span><span class="sxs-lookup"><span data-stu-id="846a9-119">MSBuild</span></span>

- [<span data-ttu-id="846a9-120">资源清单文件名更改</span><span class="sxs-lookup"><span data-stu-id="846a9-120">Resource manifest file name change</span></span>](#resource-manifest-file-name-change)

### <a name="net-core-30"></a><span data-ttu-id="846a9-121">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="846a9-121">.NET Core 3.0</span></span>

[!INCLUDE[Resource file names](~/includes/core-changes/msbuild/3.0/resource-manifest-name.md)]

***

## <a name="networking"></a><span data-ttu-id="846a9-122">网络</span><span class="sxs-lookup"><span data-stu-id="846a9-122">Networking</span></span>

- [<span data-ttu-id="846a9-123">WebClient.CancelAsync 并不总是立即取消</span><span class="sxs-lookup"><span data-stu-id="846a9-123">WebClient.CancelAsync doesn't always cancel immediately</span></span>](#webclientcancelasync-doesnt-always-cancel-immediately)

### <a name="net-core-20"></a><span data-ttu-id="846a9-124">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="846a9-124">.NET Core 2.0</span></span>

[!INCLUDE [behavior-change-webclient-cancelasync](../../../includes/core-changes/networking/2.0/behavior-change-webclient-cancelasync.md)]

***

## <a name="windows-forms"></a><span data-ttu-id="846a9-125">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="846a9-125">Windows Forms</span></span>

<span data-ttu-id="846a9-126">已在 .NET Core 的版本 3.0 中添加 Windows 窗体支持。</span><span class="sxs-lookup"><span data-stu-id="846a9-126">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="846a9-127">如果将 Windows 窗体应用从 .NET Framework 迁移到 .NET Core，此处列出的中断性变更可能会影响你的应用。</span><span class="sxs-lookup"><span data-stu-id="846a9-127">If you're migrating a Windows Forms app from .NET Framework to .NET Core, the breaking changes listed here may affect your app.</span></span>

- [<span data-ttu-id="846a9-128">已删除的控件</span><span class="sxs-lookup"><span data-stu-id="846a9-128">Removed controls</span></span>](#removed-controls)
- [<span data-ttu-id="846a9-129">如果显示工具提示，则不引发 CellFormatting 事件</span><span class="sxs-lookup"><span data-stu-id="846a9-129">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown)
- [<span data-ttu-id="846a9-130">Control.DefaultFont 已更改为 Segoe UI 9 pt</span><span class="sxs-lookup"><span data-stu-id="846a9-130">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt)
- [<span data-ttu-id="846a9-131">FolderBrowserDialog 的现代化</span><span class="sxs-lookup"><span data-stu-id="846a9-131">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog)
- [<span data-ttu-id="846a9-132">已从一些 Windows 窗体类型中删除 SerializableAttribute</span><span class="sxs-lookup"><span data-stu-id="846a9-132">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types)
- [<span data-ttu-id="846a9-133">不支持 AllowUpdateChildControlIndexForTabControls 兼容性开关</span><span class="sxs-lookup"><span data-stu-id="846a9-133">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported)
- [<span data-ttu-id="846a9-134">不支持 DomainUpDown.UseLegacyScrolling 兼容性开关</span><span class="sxs-lookup"><span data-stu-id="846a9-134">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported)
- [<span data-ttu-id="846a9-135">不支持 DoNotLoadLatestRichEditControl 兼容性开关</span><span class="sxs-lookup"><span data-stu-id="846a9-135">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported)
- [<span data-ttu-id="846a9-136">不支持 DoNotSupportSelectAllShortcutInMultilineTextBox 兼容性开关</span><span class="sxs-lookup"><span data-stu-id="846a9-136">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported)
- [<span data-ttu-id="846a9-137">不支持 DontSupportReentrantFilterMessage 兼容性开关</span><span class="sxs-lookup"><span data-stu-id="846a9-137">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported)
- [<span data-ttu-id="846a9-138">不支持 EnableVisualStyleValidation 兼容性开关</span><span class="sxs-lookup"><span data-stu-id="846a9-138">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported)
- [<span data-ttu-id="846a9-139">不支持 UseLegacyContextMenuStripSourceControlValue 兼容性开关</span><span class="sxs-lookup"><span data-stu-id="846a9-139">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported)
- [<span data-ttu-id="846a9-140">不支持 UseLegacyImages 兼容性开关</span><span class="sxs-lookup"><span data-stu-id="846a9-140">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported)

### <a name="net-core-31"></a><span data-ttu-id="846a9-141">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="846a9-141">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

### <a name="net-core-30"></a><span data-ttu-id="846a9-142">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="846a9-142">.NET Core 3.0</span></span>

[!INCLUDE[Control.DefaultFont changed to Segoe UI 9 pt](~/includes/core-changes/windowsforms/3.0/control-defaultfont-changed.md)]

***

[!INCLUDE[Modernization of the FolderBrowserDialog](~/includes/core-changes/windowsforms/3.0/modernized-folderbrowserdialog.md)]

***

[!INCLUDE[SerializableAttribute removed from some Windows Forms types](~/includes/core-changes/windowsforms/3.0/remove-serializationattribute.md)]

***

[!INCLUDE[AllowUpdateChildControlIndexForTabControls compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-allowupdatechildcontrolindexfortabcontrols.md)]

***

[!INCLUDE[DomainUpDown.UseLegacyScrolling compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyscrolling.md)]

***

[!INCLUDE[DoNotLoadLatestRichEditControl compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotloadlatestricheditcontrol.md)]

***

[!INCLUDE[DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotsupportselectallshortcutinmultilinetextbox.md)]

***

[!INCLUDE[DontSupportReentrantFilterMessage compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-dontsupportreentrantfiltermessage.md)]

***

[!INCLUDE[EnableVisualStyleValidation compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-enablevisualstylevalidation.md)]

***

[!INCLUDE[UseLegacyContextMenuStripSourceControlValue compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacycontextmenustripsourcecontrolvalue.md)]

***

[!INCLUDE[UseLegacyImages compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyimages.md)]

***

## <a name="see-also"></a><span data-ttu-id="846a9-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="846a9-143">See also</span></span>

- [<span data-ttu-id="846a9-144">始终在 .NET Core 上引发异常的 API</span><span class="sxs-lookup"><span data-stu-id="846a9-144">APIs that always throw exceptions on .NET Core</span></span>](unsupported-apis.md)
- [<span data-ttu-id="846a9-145">.NET Framework 技术在 .NET Core 上不可用</span><span class="sxs-lookup"><span data-stu-id="846a9-145">.NET Framework technologies unavailable on .NET Core</span></span>](../porting/net-framework-tech-unavailable.md)
