---
description: -out（C# 编译器选项）
title: -out（C# 编译器选项）
ms.date: 07/20/2015
f1_keywords:
- /out
helpviewer_keywords:
- /out compiler option [C#]
- out compiler option [C#]
- -out compiler option [C#]
ms.assetid: 70d91d01-7bd2-4aea-ba8b-4e9807e9caa5
ms.openlocfilehash: 409760ee0b147065a2128c62c304fb5d70cfcf42
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "91193876"
---
# <a name="-out-c-compiler-options"></a><span data-ttu-id="73630-103">-out（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="73630-103">-out (C# Compiler Options)</span></span>

<span data-ttu-id="73630-104">-out 选项指定输出文件的名称。</span><span class="sxs-lookup"><span data-stu-id="73630-104">The **-out** option specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73630-105">语法</span><span class="sxs-lookup"><span data-stu-id="73630-105">Syntax</span></span>  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="73630-106">自变量</span><span class="sxs-lookup"><span data-stu-id="73630-106">Arguments</span></span>  

 `filename`  
 <span data-ttu-id="73630-107">编译器创建的输出文件的名称。</span><span class="sxs-lookup"><span data-stu-id="73630-107">The name of the output file created by the compiler.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73630-108">备注</span><span class="sxs-lookup"><span data-stu-id="73630-108">Remarks</span></span>  

 <span data-ttu-id="73630-109">在命令行中，可以为编译指定多个输出文件。</span><span class="sxs-lookup"><span data-stu-id="73630-109">On the command line, it is possible to specify multiple output files for your compilation.</span></span> <span data-ttu-id="73630-110">编译器应在 -out 选项下查找一个或多个源代码文件。</span><span class="sxs-lookup"><span data-stu-id="73630-110">The compiler expects to find one or more source code files following the **-out** option.</span></span> <span data-ttu-id="73630-111">然后，所有源代码文件都将编译为 -out 选项指定的输出文件。</span><span class="sxs-lookup"><span data-stu-id="73630-111">Then, all source code files will be compiled into the output file specified by that **-out** option.</span></span>  
  
 <span data-ttu-id="73630-112">指定想要创建的文件的完整名称和扩展名。</span><span class="sxs-lookup"><span data-stu-id="73630-112">Specify the full name and extension of the file you want to create.</span></span>  
  
 <span data-ttu-id="73630-113">如果不指定输出文件的名称：</span><span class="sxs-lookup"><span data-stu-id="73630-113">If you do not specify the name of the output file:</span></span>  
  
- <span data-ttu-id="73630-114">.exe 将采用包含 Main 方法的源代码文件中的名称。</span><span class="sxs-lookup"><span data-stu-id="73630-114">An .exe will take its name from the source code file that contains the **Main** method.</span></span>  
  
- <span data-ttu-id="73630-115">.dll 或者 .netmodule 将从第一个源代码文件中获取其名称。</span><span class="sxs-lookup"><span data-stu-id="73630-115">A .dll or .netmodule will take its name from the first source code file.</span></span>  
  
 <span data-ttu-id="73630-116">用于编译一个输出文件的源代码文件不能同样用于编译另一输出文件。</span><span class="sxs-lookup"><span data-stu-id="73630-116">A source code file used to compile one output file cannot be used in the same compilation for the compilation of another output file.</span></span>  
  
 <span data-ttu-id="73630-117">如果在命令行编译中生成多个输出文件，请记住，仅其中一个输出文件可以是程序集，且只有（使用 -out 隐式或显式）指定的第一个输出文件可以是程序集。</span><span class="sxs-lookup"><span data-stu-id="73630-117">When producing multiple output files in a command-line compilation, keep in mind that only one of the output files can be an assembly and that only the first output file specified (implicitly or explicitly with **-out**) can be the assembly.</span></span>  
  
 <span data-ttu-id="73630-118">在编译时生成的任何模块都将成为与编译时生成的程序集关联的文件。</span><span class="sxs-lookup"><span data-stu-id="73630-118">Any modules produced as part of a compilation become files associated with any assembly also produced in the compilation.</span></span> <span data-ttu-id="73630-119">使用 [ildasm.exe](../../../framework/tools/ildasm-exe-il-disassembler.md) 查看程序集清单，了解关联文件。</span><span class="sxs-lookup"><span data-stu-id="73630-119">Use [ildasm.exe](../../../framework/tools/ildasm-exe-il-disassembler.md) to view the assembly manifest to see the associated files.</span></span>  
  
 <span data-ttu-id="73630-120">为使 exe 成为友元程序集的目标，-out 编译器选项是必需的。</span><span class="sxs-lookup"><span data-stu-id="73630-120">The -out compiler option is required in order for an exe to be the target of a friend assembly.</span></span> <span data-ttu-id="73630-121">有关详细信息，请参阅[友元程序集](../../../standard/assembly/friend.md)。</span><span class="sxs-lookup"><span data-stu-id="73630-121">For more information see [Friend Assemblies](../../../standard/assembly/friend.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="73630-122">在 Visual Studio 开发环境中设置此编译器选项</span><span class="sxs-lookup"><span data-stu-id="73630-122">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="73630-123">打开项目的“属性”页。</span><span class="sxs-lookup"><span data-stu-id="73630-123">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="73630-124">单击“应用程序”属性页。</span><span class="sxs-lookup"><span data-stu-id="73630-124">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="73630-125">修改程序集名称属性。</span><span class="sxs-lookup"><span data-stu-id="73630-125">Modify the **Assembly name** property.</span></span>  
  
     <span data-ttu-id="73630-126">以编程方式设置此编译器选项：<xref:VSLangProj80.ProjectProperties3.OutputFileName%2A> 是只读属性，由项目类型（exe、库等）和程序集名称的组合决定。</span><span class="sxs-lookup"><span data-stu-id="73630-126">To set this compiler option programmatically: the <xref:VSLangProj80.ProjectProperties3.OutputFileName%2A> is a read-only property, which is determined by a combination of the project type (exe, library, and so forth) and the assembly name.</span></span> <span data-ttu-id="73630-127">设置输出文件名称必须修改一个或两个属性。</span><span class="sxs-lookup"><span data-stu-id="73630-127">Modifying one or both of these properties will be necessary to set the output file name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73630-128">示例</span><span class="sxs-lookup"><span data-stu-id="73630-128">Example</span></span>  

 <span data-ttu-id="73630-129">编译 `t.cs` 并创建输出文件 `t.exe`以及生成 `t2.cs` 并创建模块输出文件 `mymodule.netmodule`：</span><span class="sxs-lookup"><span data-stu-id="73630-129">Compile `t.cs` and create output file `t.exe`, as well as build `t2.cs` and create module output file `mymodule.netmodule`:</span></span>  
  
```console  
csc t.cs -out:mymodule.netmodule -target:module t2.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="73630-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="73630-130">See also</span></span>

- [<span data-ttu-id="73630-131">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="73630-131">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="73630-132">友元程序集</span><span class="sxs-lookup"><span data-stu-id="73630-132">Friend Assemblies</span></span>](../../../standard/assembly/friend.md)
- [<span data-ttu-id="73630-133">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="73630-133">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
