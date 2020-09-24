---
title: Windows 窗体重大更改
description: 列出适用于 .NET Core 和 .NET 5 的 Windows 窗体中的中断性变更。
ms.date: 09/08/2020
ms.openlocfilehash: 3e7d077d07203d9c231ae4a7805e593c5432c135
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2020
ms.locfileid: "90678990"
---
# <a name="breaking-changes-in-windows-forms"></a>Windows 窗体中的中断性变更

已在 .NET Core 的版本 3.0 中添加 Windows 窗体支持。 本文按引入了中断性变更的 .NET 版本列出了 Windows 窗体的中断性变更。 如果要从 .NET Framework 或 .NET Core 的早期版本（3.0 或更高版本）升级 Windows 窗体应用，本文能为你提供帮助。

本页记录了以下中断性变更：

| 重大更改 | 引入的版本 |
| - | :-: |
| [对于 WPF 和 WinForms 应用，OutputType 设置为 WinExe](#outputtype-set-to-winexe-for-wpf-and-winforms-apps) | 5.0 |
| [与 DataGridView 相关的 API 现在引发 InvalidOperationException](#datagridview-related-apis-now-throw-invalidoperationexception) | 5.0 |
| [WinForms 和 WPF 应用使用 Microsoft.NET.Sdk](#winforms-and-wpf-apps-use-microsoftnetsdk) | 5.0 |
| [已删除的状态栏控件](#removed-status-bar-controls) | 5.0 |
| [WinForms 方法现在会引发 ArgumentException](#winforms-methods-now-throw-argumentexception) | 5.0 |
| [WinForms 方法现在会引发 ArgumentNullException](#winforms-methods-now-throw-argumentnullexception) | 5.0 |
| [WinForms 属性现在引发 ArgumentOutOfRangeException](#winforms-properties-now-throw-argumentoutofrangeexception) | 5.0 |
| [已删除的控件](#removed-controls) | 3.1 |
| [如果显示工具提示，则不引发 CellFormatting 事件](#cellformatting-event-not-raised-if-tooltip-is-shown) | 3.1 |
| [Control.DefaultFont 已更改为 Segoe UI 9 pt](#default-control-font-changed-to-segoe-ui-9-pt) | 3.0 |
| [FolderBrowserDialog 的现代化](#modernization-of-the-folderbrowserdialog) | 3.0 |
| [已从一些 Windows 窗体类型中删除 SerializableAttribute](#serializableattribute-removed-from-some-windows-forms-types) | 3.0 |
| [不支持 AllowUpdateChildControlIndexForTabControls 兼容性开关](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported) | 3.0 |
| [不支持 DomainUpDown.UseLegacyScrolling 兼容性开关](#domainupdownuselegacyscrolling-compatibility-switch-not-supported) | 3.0 |
| [不支持 DoNotLoadLatestRichEditControl 兼容性开关](#donotloadlatestricheditcontrol-compatibility-switch-not-supported) | 3.0 |
| [不支持 DoNotSupportSelectAllShortcutInMultilineTextBox 兼容性开关](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported) | 3.0 |
| [不支持 DontSupportReentrantFilterMessage 兼容性开关](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported) | 3.0 |
| [不支持 EnableVisualStyleValidation 兼容性开关](#enablevisualstylevalidation-compatibility-switch-not-supported) | 3.0 |
| [不支持 UseLegacyContextMenuStripSourceControlValue 兼容性开关](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported) | 3.0 |
| [不支持 UseLegacyImages 兼容性开关](#uselegacyimages-compatibility-switch-not-supported) | 3.0 |

## <a name="net-50"></a>.NET 5.0

[!INCLUDE [automatically-infer-winexe-output-type](../../../includes/core-changes/windowsforms/5.0/automatically-infer-winexe-output-type.md)]

***

[!INCLUDE [null-owner-causes-invalidoperationexception](../../../includes/core-changes/windowsforms/5.0/null-owner-causes-invalidoperationexception.md)]

***

[!INCLUDE [sdk-and-target-framework-change](../../../includes/core-changes/windowsforms/5.0/sdk-and-target-framework-change.md)]

***

[!INCLUDE [winforms-deprecated-controls](../../../includes/core-changes/windowsforms/5.0/winforms-deprecated-controls.md)]

***

[!INCLUDE [invalid-args-cause-argumentexception](../../../includes/core-changes/windowsforms/5.0/invalid-args-cause-argumentexception.md)]

***

[!INCLUDE [null-args-cause-argumentnullexception](../../../includes/core-changes/windowsforms/5.0/null-args-cause-argumentnullexception.md)]

***

[!INCLUDE [invalid-args-cause-argumentoutofrangeexception](../../../includes/core-changes/windowsforms/5.0/invalid-args-cause-argumentoutofrangeexception.md)]

***

## <a name="net-core-31"></a>.NET Core 3.1

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

## <a name="net-core-30"></a>.NET Core 3.0

[!INCLUDE[Control.DefaultFont changed to Segoe UI 9pt](~/includes/core-changes/windowsforms/3.0/control-defaultfont-changed.md)]

***

[!INCLUDE[Modernization of the FolderBrowserDialog](~/includes/core-changes/windowsforms/3.0/modernized-folderbrowserdialog.md)]

***

[!INCLUDE[SerializableAttribute removed from some Windows Forms types](~/includes/core-changes/windowsforms/3.0/remove-serializationattribute.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-allowupdatechildcontrolindexfortabcontrols.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyscrolling.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotloadlatestricheditcontrol.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotsupportselectallshortcutinmultilinetextbox.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DontSupportReentrantFilterMessage compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-dontsupportreentrantfiltermessage.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-enablevisualstylevalidation.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacycontextmenustripsourcecontrolvalue.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyImages compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyimages.md)]

***

## <a name="see-also"></a>请参阅

- [将 Windows 窗体应用移植到 .NET Core](../porting/winforms.md)
