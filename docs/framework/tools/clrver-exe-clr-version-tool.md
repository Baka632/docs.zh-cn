---
title: Clrver.exe（CLR 版本工具）
description: 查看 Clrver.exe（CLR 版本工具）。 此工具报告计算机上公共语言运行时 (CLR) 的所有已安装版本。
ms.date: 03/30/2017
helpviewer_keywords:
- Clrver.exe
- CLR Version tool
ms.assetid: cbc2ee86-bdc8-4a65-a8f1-ba23bce3a699
ms.openlocfilehash: 3a7a585d990051553aa8fdc0e99b2dc206273cf4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96247221"
---
# <a name="clrverexe-clr-version-tool"></a><span data-ttu-id="70654-104">Clrver.exe（CLR 版本工具）</span><span class="sxs-lookup"><span data-stu-id="70654-104">Clrver.exe (CLR Version Tool)</span></span>

<span data-ttu-id="70654-105">CLR 版本工具 (Clrver.exe) 报告计算机上的公共语言运行时 (CLR) 的所有已安装版本。</span><span class="sxs-lookup"><span data-stu-id="70654-105">The CLR Version tool (Clrver.exe) reports all the installed versions of the common language runtime (CLR) on the computer.</span></span>  
  
 <span data-ttu-id="70654-106">此工具会自动随 Visual Studio 一起安装。</span><span class="sxs-lookup"><span data-stu-id="70654-106">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="70654-107">若要运行此工具，请使用 Visual Studio 开发人员命令提示（或 Windows 7 中的 Visual Studio 命令提示）。</span><span class="sxs-lookup"><span data-stu-id="70654-107">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="70654-108">有关详细信息，请参阅[命令提示](developer-command-prompt-for-vs.md)。</span><span class="sxs-lookup"><span data-stu-id="70654-108">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="70654-109">在命令提示符处，键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="70654-109">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70654-110">语法</span><span class="sxs-lookup"><span data-stu-id="70654-110">Syntax</span></span>  
  
```console  
clrver [option]  
```  
  
## <a name="options"></a><span data-ttu-id="70654-111">选项</span><span class="sxs-lookup"><span data-stu-id="70654-111">Options</span></span>  
  
|<span data-ttu-id="70654-112">选项</span><span class="sxs-lookup"><span data-stu-id="70654-112">Option</span></span>|<span data-ttu-id="70654-113">说明</span><span class="sxs-lookup"><span data-stu-id="70654-113">Description</span></span>|  
|------------|-----------------|  
|`-all`|<span data-ttu-id="70654-114">显示正在使用的 CLR 的计算机上的所有进程。</span><span class="sxs-lookup"><span data-stu-id="70654-114">Displays all processes on the computer that are using the CLR.</span></span>|  
|<span data-ttu-id="70654-115">pid</span><span class="sxs-lookup"><span data-stu-id="70654-115">*pid*</span></span>|<span data-ttu-id="70654-116">显示具有指定的进程 ID (PID) 的进程所使用的 CLR 版本。</span><span class="sxs-lookup"><span data-stu-id="70654-116">Displays the version(s) of the CLR used by the process that has the specified process ID (PID).</span></span>|  
|`-?`|<span data-ttu-id="70654-117">显示该工具的命令语法和选项。</span><span class="sxs-lookup"><span data-stu-id="70654-117">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70654-118">备注</span><span class="sxs-lookup"><span data-stu-id="70654-118">Remarks</span></span>  

 <span data-ttu-id="70654-119">如果你未使用任何选项调用 Clrver.exe，则它将显示所有已安装的 CLR 版本。</span><span class="sxs-lookup"><span data-stu-id="70654-119">If you call Clrver.exe with no options, it displays all installed CLR versions.</span></span> <span data-ttu-id="70654-120">如果你指定了另一个用户的 PID，则你必须具有管理权限才能获取版本信息。</span><span class="sxs-lookup"><span data-stu-id="70654-120">If you specify a PID for another user, you must have administrative permissions to obtain the version information.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="70654-121">在 Windows Vista 或更高版本中，用户帐户控制 (UAC) 决定用户的特权。</span><span class="sxs-lookup"><span data-stu-id="70654-121">In Windows Vista and later, User Account Control (UAC) determines the privileges of a user.</span></span> <span data-ttu-id="70654-122">如果您是内置的 Administrators 组的成员，将为您分配两个运行时访问令牌：一个标准用户访问令牌和一个管理员访问令牌。</span><span class="sxs-lookup"><span data-stu-id="70654-122">If you are a member of the Built-in Administrators group, you are assigned two run-time access tokens: a standard user access token and an administrator access token.</span></span> <span data-ttu-id="70654-123">默认情况下，您拥有标准用户角色。</span><span class="sxs-lookup"><span data-stu-id="70654-123">By default, you are in the standard user role.</span></span> <span data-ttu-id="70654-124">要执行需要管理权限的代码，首先必须将你的特权从标准用户提升至管理员。</span><span class="sxs-lookup"><span data-stu-id="70654-124">To execute code that requires administrative permission, you must first elevate your privileges from standard user to administrator.</span></span> <span data-ttu-id="70654-125">你可以通过以下方式执行此操作：在启动命令提示符时，右键单击命令提示符图标并指示你希望以管理员身份运行。</span><span class="sxs-lookup"><span data-stu-id="70654-125">You can do this when you start the command prompt by right-clicking the command prompt icon and indicating that you want to run as an administrator.</span></span>  
  
 <span data-ttu-id="70654-126">尝试确定 SYSTEM、LOCAL SERVICE 和 NETWORK SERVICE 过程的 CLR 版本会导致出现一条消息，指示该 PID 不存在。</span><span class="sxs-lookup"><span data-stu-id="70654-126">Attempting to determine the CLR version for SYSTEM, LOCAL SERVICE, and NETWORK SERVICE processes results in a message indicating that the PID doesn't exist.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="70654-127">示例</span><span class="sxs-lookup"><span data-stu-id="70654-127">Examples</span></span>  

 <span data-ttu-id="70654-128">以下命令显示在计算机上安装的 CLR 的所有版本。</span><span class="sxs-lookup"><span data-stu-id="70654-128">The following command displays all the versions of the CLR installed on the computer.</span></span>  
  
 `clrver`  
  
 <span data-ttu-id="70654-129">以下命令显示进程 128 所用的 CLR 版本。</span><span class="sxs-lookup"><span data-stu-id="70654-129">The following command displays the version of the CLR used by process 128.</span></span>  
  
 `clrver 128`  
  
 <span data-ttu-id="70654-130">以下命令显示所有托管进程及其使用的 CLR 版本。</span><span class="sxs-lookup"><span data-stu-id="70654-130">The following command displays all the managed processes and the version of the CLR they are using.</span></span>  
  
 `Clrver -all`  
  
## <a name="see-also"></a><span data-ttu-id="70654-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="70654-131">See also</span></span>

- [<span data-ttu-id="70654-132">工具</span><span class="sxs-lookup"><span data-stu-id="70654-132">Tools</span></span>](index.md)
- [<span data-ttu-id="70654-133">命令提示</span><span class="sxs-lookup"><span data-stu-id="70654-133">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
