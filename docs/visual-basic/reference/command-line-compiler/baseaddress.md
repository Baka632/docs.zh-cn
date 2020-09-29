---
title: -baseaddress
ms.date: 08/09/2018
f1_keywords:
- /baseaddress
- baseaddress
helpviewer_keywords:
- -baseaddress compiler option [Visual Basic]
- /baseaddress compiler option [Visual Basic]
- baseaddress compiler option [Visual Basic]
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
ms.openlocfilehash: c794d1fc1c9d20e22ffa747e3175c846341ad8ad
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097756"
---
# <a name="-baseaddress"></a><span data-ttu-id="5c592-102">-baseaddress</span><span class="sxs-lookup"><span data-stu-id="5c592-102">-baseaddress</span></span>

<span data-ttu-id="5c592-103">创建 DLL 时指定默认基址。</span><span class="sxs-lookup"><span data-stu-id="5c592-103">Specifies a default base address when creating a DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c592-104">语法</span><span class="sxs-lookup"><span data-stu-id="5c592-104">Syntax</span></span>  
  
```console  
-baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="5c592-105">自变量</span><span class="sxs-lookup"><span data-stu-id="5c592-105">Arguments</span></span>  
  
|<span data-ttu-id="5c592-106">术语</span><span class="sxs-lookup"><span data-stu-id="5c592-106">Term</span></span>|<span data-ttu-id="5c592-107">定义</span><span class="sxs-lookup"><span data-stu-id="5c592-107">Definition</span></span>|  
|---|---|  
|`address`|<span data-ttu-id="5c592-108">必需。</span><span class="sxs-lookup"><span data-stu-id="5c592-108">Required.</span></span> <span data-ttu-id="5c592-109">DLL 的基址。</span><span class="sxs-lookup"><span data-stu-id="5c592-109">The base address for the DLL.</span></span> <span data-ttu-id="5c592-110">此地址必须指定为十六进制数。</span><span class="sxs-lookup"><span data-stu-id="5c592-110">This address must be specified as a hexadecimal number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c592-111">备注</span><span class="sxs-lookup"><span data-stu-id="5c592-111">Remarks</span></span>  

 <span data-ttu-id="5c592-112">DLL 的默认基址由 .NET Framework 设置。</span><span class="sxs-lookup"><span data-stu-id="5c592-112">The default base address for a DLL is set by the .NET Framework.</span></span>  
  
 <span data-ttu-id="5c592-113">请注意，此地址中的低序字将被舍入取整。</span><span class="sxs-lookup"><span data-stu-id="5c592-113">Be aware that the lower-order word in this address is rounded.</span></span> <span data-ttu-id="5c592-114">例如，如果指定 0x11110001，它将被舍入为 0x11110000。</span><span class="sxs-lookup"><span data-stu-id="5c592-114">For example, if you specify 0x11110001, it is rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="5c592-115">若要完成 DLL 的签名过程，请使用强名称工具 (Sn.exe) 的 `–R` 选项。</span><span class="sxs-lookup"><span data-stu-id="5c592-115">To complete the signing process for a DLL, use the `–R` option of the Strong Naming tool (Sn.exe).</span></span>  
  
 <span data-ttu-id="5c592-116">如果目标不是 DLL，则忽略此选项。</span><span class="sxs-lookup"><span data-stu-id="5c592-116">This option is ignored if the target is not a DLL.</span></span>  
  
|<span data-ttu-id="5c592-117">在 Visual Studio IDE 中设置 --baseaddress</span><span class="sxs-lookup"><span data-stu-id="5c592-117">To set -baseaddress in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="5c592-118">1.在 **“解决方案资源管理器”** 中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="5c592-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="5c592-119">在“项目”菜单上，单击“属性”   。</span><span class="sxs-lookup"><span data-stu-id="5c592-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="5c592-120">2.单击“编译”  选项卡。</span><span class="sxs-lookup"><span data-stu-id="5c592-120">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="5c592-121">3.单击 **“高级”** 。</span><span class="sxs-lookup"><span data-stu-id="5c592-121">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="5c592-122">4.修改“DLL 基址”  框中的值。</span><span class="sxs-lookup"><span data-stu-id="5c592-122">4.  Modify the value in the **DLL base address:** box.</span></span> <span data-ttu-id="5c592-123">**注意：**    “DLL 基址:”  框为只读，除非目标是 DLL。</span><span class="sxs-lookup"><span data-stu-id="5c592-123">**Note:**      The **DLL base address:** box is read-only unless the target is a DLL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5c592-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="5c592-124">See also</span></span>

- [<span data-ttu-id="5c592-125">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="5c592-125">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="5c592-126">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5c592-126">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="5c592-127">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="5c592-127">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- <span data-ttu-id="5c592-128">[Sn.exe（强名称工具）](../../../framework/tools/sn-exe-strong-name-tool.md)）</span><span class="sxs-lookup"><span data-stu-id="5c592-128">[Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>
