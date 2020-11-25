---
title: GetCORSystemDirectory 函数
ms.date: 03/30/2017
api_name:
- GetCORSystemDirectory
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORSystemDirectory
helpviewer_keywords:
- GetCORSystemDirectory function [.NET Framework hosting]
ms.assetid: 3dcd16a7-dafc-4ca8-b5cd-20ffb37db91d
topic_type:
- apiref
ms.openlocfilehash: 21b01156afceb24ab5c132894fae6922d7b97e59
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733290"
---
# <a name="getcorsystemdirectory-function"></a><span data-ttu-id="ffcaf-102">GetCORSystemDirectory 函数</span><span class="sxs-lookup"><span data-stu-id="ffcaf-102">GetCORSystemDirectory Function</span></span>

<span data-ttu-id="ffcaf-103">返回加载到进程 (CLR) 的公共语言运行时的安装目录。</span><span class="sxs-lookup"><span data-stu-id="ffcaf-103">Returns the installation directory of the common language runtime (CLR) that is loaded into the process.</span></span> <span data-ttu-id="ffcaf-104">安装目录是完全限定的，例如 "c:\windows\microsoft.net\framework\v1.0.3705"。</span><span class="sxs-lookup"><span data-stu-id="ffcaf-104">The installation directory is fully qualified, for example, "c:\windows\microsoft.net\framework\v1.0.3705".</span></span>  
  
 <span data-ttu-id="ffcaf-105">不推荐使用此函数。</span><span class="sxs-lookup"><span data-stu-id="ffcaf-105">This function is deprecated.</span></span> <span data-ttu-id="ffcaf-106">它被 .NET Framework 4 中提供的 [ICLRRuntimeInfo：： GetRuntimeDirectory](iclrruntimeinfo-getruntimedirectory-method.md) 方法取代。</span><span class="sxs-lookup"><span data-stu-id="ffcaf-106">It is superseded by the [ICLRRuntimeInfo::GetRuntimeDirectory](iclrruntimeinfo-getruntimedirectory-method.md) method provided in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffcaf-107">语法</span><span class="sxs-lookup"><span data-stu-id="ffcaf-107">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (
    [out] LPWSTR  pbuffer,
    [in]  DWORD   cchBuffer,
    [out] DWORD*  dwlength  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="ffcaf-108">参数</span><span class="sxs-lookup"><span data-stu-id="ffcaf-108">Parameters</span></span>  

 `pbuffer`  
 <span data-ttu-id="ffcaf-109">弄一个缓冲区，其中运行时返回一个字符串，其中包含加载到进程中的运行时的安装目录的完全限定名称。</span><span class="sxs-lookup"><span data-stu-id="ffcaf-109">[out] A buffer in which the runtime returns a string that contains the fully qualified name of the installation directory for the runtime that is loaded into the process.</span></span> <span data-ttu-id="ffcaf-110">如果运行时尚未加载到进程中，则该函数将为计算机上安装的最新版本的运行时返回相应的目录信息。</span><span class="sxs-lookup"><span data-stu-id="ffcaf-110">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="ffcaf-111">中的大小（以字节为单位） `pbuffer` 。</span><span class="sxs-lookup"><span data-stu-id="ffcaf-111">[in] The size, in bytes, of `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="ffcaf-112">弄中返回的字符数 `pbuffer` 。</span><span class="sxs-lookup"><span data-stu-id="ffcaf-112">[out] The number of characters returned in `pbuffer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ffcaf-113">注解</span><span class="sxs-lookup"><span data-stu-id="ffcaf-113">Remarks</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="ffcaf-114">不要在运行 CLR 版本4的进程中使用此函数。</span><span class="sxs-lookup"><span data-stu-id="ffcaf-114">Do not use this function in processes that are running version 4 of the CLR.</span></span> <span data-ttu-id="ffcaf-115">如果计算机上安装了 CLR 的早期版本，则此函数将返回该版本的安装目录。</span><span class="sxs-lookup"><span data-stu-id="ffcaf-115">If an earlier version of the CLR is installed on the computer, this function returns the installation directory for that version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffcaf-116">要求</span><span class="sxs-lookup"><span data-stu-id="ffcaf-116">Requirements</span></span>  

 <span data-ttu-id="ffcaf-117">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ffcaf-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffcaf-118">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ffcaf-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ffcaf-119">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ffcaf-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ffcaf-120">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffcaf-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffcaf-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ffcaf-121">See also</span></span>

- [<span data-ttu-id="ffcaf-122">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="ffcaf-122">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
