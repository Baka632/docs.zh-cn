---
title: -nostdlib
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: 4fcc5305985f5ba32b3e6ffb740c0611821215d3
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097652"
---
# <a name="-nostdlib-visual-basic"></a><span data-ttu-id="d7211-102">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d7211-102">-nostdlib (Visual Basic)</span></span>

<span data-ttu-id="d7211-103">导致编译器不自动引用标准库。</span><span class="sxs-lookup"><span data-stu-id="d7211-103">Causes the compiler not to automatically reference the standard libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7211-104">语法</span><span class="sxs-lookup"><span data-stu-id="d7211-104">Syntax</span></span>  
  
```console  
-nostdlib  
```  
  
## <a name="remarks"></a><span data-ttu-id="d7211-105">备注</span><span class="sxs-lookup"><span data-stu-id="d7211-105">Remarks</span></span>  

 <span data-ttu-id="d7211-106">`-nostdlib` 选项会删除对 System.dll 程序集的自动引用，并防止编译器读取 Vbc.rsp 文件。</span><span class="sxs-lookup"><span data-stu-id="d7211-106">The `-nostdlib` option removes the automatic reference to the System.dll assembly and prevents the compiler from reading the Vbc.rsp file.</span></span> <span data-ttu-id="d7211-107">Vbc.rsp 文件（与 Vbc.exe 文件位于同一个目录）引用常用的 .NET Framework 程序集，并导入 `System` 和 `Microsoft.VisualBasic` 命名空间。</span><span class="sxs-lookup"><span data-stu-id="d7211-107">The Vbc.rsp file, which is located in the same directory as the Vbc.exe file, references the commonly used .NET Framework assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d7211-108">始终引用 Mscorlib.dll 和 Microsoft.VisualBasic.dll 程序集。</span><span class="sxs-lookup"><span data-stu-id="d7211-108">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d7211-109">`-nostdlib` 选项在 Visual Studio 开发环境内无法使用；仅当从命令行编译时才可用。</span><span class="sxs-lookup"><span data-stu-id="d7211-109">The `-nostdlib` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7211-110">示例</span><span class="sxs-lookup"><span data-stu-id="d7211-110">Example</span></span>  

 <span data-ttu-id="d7211-111">下面的代码在不引用标准库的情况下编译 `T2.vb`。</span><span class="sxs-lookup"><span data-stu-id="d7211-111">The following code compiles `T2.vb` without referencing the standard libraries.</span></span> <span data-ttu-id="d7211-112">必须将 `_MYTYPE` 条件编译常量设置为字符串“Empty”，才能删除 `My` 对象。</span><span class="sxs-lookup"><span data-stu-id="d7211-112">You must set the `_MYTYPE` conditional-compilation constant to the string "Empty" to remove the `My` object.</span></span>  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d7211-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7211-113">See also</span></span>

- [<span data-ttu-id="d7211-114">-noconfig</span><span class="sxs-lookup"><span data-stu-id="d7211-114">-noconfig</span></span>](noconfig.md)
- [<span data-ttu-id="d7211-115">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="d7211-115">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="d7211-116">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="d7211-116">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="d7211-117">自定义 My 中可用的对象</span><span class="sxs-lookup"><span data-stu-id="d7211-117">Customizing Which Objects are Available in My</span></span>](../../developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
