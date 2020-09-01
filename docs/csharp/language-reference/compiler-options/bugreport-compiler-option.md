---
description: -bugreport（C# 编译器选项）
title: -bugreport（C# 编译器选项）
ms.date: 07/20/2015
f1_keywords:
- /bugreport
helpviewer_keywords:
- /bugreport compiler option [C#]
- -bugreport compiler option [C#]
- bugreport compiler option [C#]
ms.assetid: f39665e3-4f6f-4357-88a2-3274c7bec0c1
ms.openlocfilehash: 2c358b2dda400f6077ffb5ba1dfc8e6e1127fa52
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125990"
---
# <a name="-bugreport-c-compiler-options"></a><span data-ttu-id="22a78-103">-bugreport（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="22a78-103">-bugreport (C# Compiler Options)</span></span>
<span data-ttu-id="22a78-104">指定应使调试信息置于文件中供以后分析。</span><span class="sxs-lookup"><span data-stu-id="22a78-104">Specifies that debug information should be placed in a file for later analysis.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22a78-105">语法</span><span class="sxs-lookup"><span data-stu-id="22a78-105">Syntax</span></span>  
  
```console  
-bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="22a78-106">自变量</span><span class="sxs-lookup"><span data-stu-id="22a78-106">Arguments</span></span>  
 `file`  
 <span data-ttu-id="22a78-107">要包含 Bug 报告的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="22a78-107">The name of the file that you want to contain your bug report.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22a78-108">备注</span><span class="sxs-lookup"><span data-stu-id="22a78-108">Remarks</span></span>  
 <span data-ttu-id="22a78-109">-bugreport 选项指定以下信息应置于 `file` 中：</span><span class="sxs-lookup"><span data-stu-id="22a78-109">The **-bugreport** option specifies that the following information should be placed in `file`:</span></span>  
  
- <span data-ttu-id="22a78-110">编译中所有源代码文件副本。</span><span class="sxs-lookup"><span data-stu-id="22a78-110">A copy of all source code files in the compilation.</span></span>  
  
- <span data-ttu-id="22a78-111">编译中使用的编译器选项列表。</span><span class="sxs-lookup"><span data-stu-id="22a78-111">A listing of the compiler options used in the compilation.</span></span>  
  
- <span data-ttu-id="22a78-112">有关编译器、运行时和操作系统的版本信息。</span><span class="sxs-lookup"><span data-stu-id="22a78-112">Version information about your compiler, run time, and operating system.</span></span>  
  
- <span data-ttu-id="22a78-113">引用的程序集和模块（保存为十六进制数字），.NET Framework 和 SDK 随附的程序集除外。</span><span class="sxs-lookup"><span data-stu-id="22a78-113">Referenced assemblies and modules, saved as hexadecimal digits, except assemblies that ship with the .NET Framework and SDK.</span></span>  
  
- <span data-ttu-id="22a78-114">编译器输出（如有）。</span><span class="sxs-lookup"><span data-stu-id="22a78-114">Compiler output, if any.</span></span>  
  
- <span data-ttu-id="22a78-115">问题说明（系统会提示你提供此信息）。</span><span class="sxs-lookup"><span data-stu-id="22a78-115">A description of the problem, which you will be prompted for.</span></span>  
  
- <span data-ttu-id="22a78-116">有关你认为应如何修复问题的说明（系统会提示你提供此信息）。</span><span class="sxs-lookup"><span data-stu-id="22a78-116">A description of how you think the problem should be fixed, which you will be prompted for.</span></span>  
  
 <span data-ttu-id="22a78-117">如果此选项与 -errorreport: prompt 或 -errorreport:send 一起使用，文件中的信息将发送到 Microsoft Corporation\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22a78-117">If this option is used with **-errorreport:prompt** or **-errorreport:send**, the information in the file will be sent to Microsoft Corporation.</span></span>  
  
 <span data-ttu-id="22a78-118">所有源代码文件的副本将放入 `file`，因此你可能希望在尽可能短小的程序中重现可疑代码缺陷。</span><span class="sxs-lookup"><span data-stu-id="22a78-118">Because a copy of all source code files will be placed in `file`, you might want to reproduce the suspected code defect in the shortest possible program.</span></span>  
  
 <span data-ttu-id="22a78-119">此编译器选项在 Visual Studio 中不可用，并且无法以编程方式更改。</span><span class="sxs-lookup"><span data-stu-id="22a78-119">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
 <span data-ttu-id="22a78-120">请注意，生成文件的内容会公开源代码，这可能会导致意外信息泄露。</span><span class="sxs-lookup"><span data-stu-id="22a78-120">Notice that contents of the generated file expose source code that could result in inadvertent information disclosure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22a78-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="22a78-121">See also</span></span>

- [<span data-ttu-id="22a78-122">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="22a78-122">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="22a78-123">-errorreport（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="22a78-123">-errorreport (C# Compiler Options)</span></span>](./errorreport-compiler-option.md)
- [<span data-ttu-id="22a78-124">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="22a78-124">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
