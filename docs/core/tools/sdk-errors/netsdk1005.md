---
title: NETSDK1005 和 NETSDK1047：资产文件缺少目标
description: 如何解决资产文件缺少目标的问题。
author: sfoslund
ms.topic: error-reference
ms.date: 10/09/2020
f1_keywords:
- NETSDK1005
- NETSDK1047
ms.openlocfilehash: 207c8b0274c13e7af594e05cfac2a95907f85b81
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717898"
---
# <a name="netsdk1005-and-netsdk1047-asset-file-is-missing-target"></a><span data-ttu-id="881f7-103">NETSDK1005 和 NETSDK1047：资产文件缺少目标</span><span class="sxs-lookup"><span data-stu-id="881f7-103">NETSDK1005 and NETSDK1047: Asset file is missing target</span></span>

<span data-ttu-id="881f7-104">本文适用于：✔️ .NET Core 2.1.100 SDK 及更高版本</span><span class="sxs-lookup"><span data-stu-id="881f7-104">**This article applies to:** ✔️ .NET Core 2.1.100 SDK and later versions</span></span>

<span data-ttu-id="881f7-105">当 .NET SDK 发出错误 NETSDK1005 或 NETSDK1047 时，项目的资产文件缺失某个目标框架的相关信息。</span><span class="sxs-lookup"><span data-stu-id="881f7-105">When the .NET SDK issues error NETSDK1005 or NETSDK1047, the project's assets file is missing information on one of your target frameworks.</span></span> <span data-ttu-id="881f7-106">通常，确保还原正常运行并将缺失的目标值包含在项目的 `TargetFrameworks` 属性中即可解决此问题。</span><span class="sxs-lookup"><span data-stu-id="881f7-106">This can usually be fixed by ensuring that restore is run and that the missing target value is included in the `TargetFrameworks` property of your project.</span></span>

> [!NOTE]
> <span data-ttu-id="881f7-107">Visual Studio 16.8 预览版与 .NET 5 预览版 8 的早期版本一起使用时存在一个已知问题，会导致此错误。</span><span class="sxs-lookup"><span data-stu-id="881f7-107">There was a known issue with early builds of .NET 5 preview 8 when used with versions of Visual Studio 16.8 previews which resulted in this error.</span></span> <span data-ttu-id="881f7-108">具体来讲，如果缺失目标 `net5.0-windows7.0` 或 `net5.0`，请确保 Visual Studio 和 .NET 5 SDK 已更新到最新版本。</span><span class="sxs-lookup"><span data-stu-id="881f7-108">Specifically, if the missing target is `net5.0-windows7.0` or `net5.0`, ensure that you have updated to the latest versions of Visual Studio and the .NET 5 SDK.</span></span>
