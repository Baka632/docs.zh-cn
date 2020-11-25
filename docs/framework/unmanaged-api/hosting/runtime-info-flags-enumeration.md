---
title: RUNTIME_INFO_FLAGS 枚举
ms.date: 03/30/2017
api_name:
- RUNTIME_INFO_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- RUNTIME_INFO_FLAGS
helpviewer_keywords:
- RUNTIME_INFO_FLAGS enumeration [.NET Framework hosting]
ms.assetid: adba37be-f775-4cdb-8919-5746ce694f33
topic_type:
- apiref
ms.openlocfilehash: 6f4fbb40053628d60ba7f094fcb5d50a94d63e1a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729936"
---
# <a name="runtime_info_flags-enumeration"></a><span data-ttu-id="24fdc-102">RUNTIME_INFO_FLAGS 枚举</span><span class="sxs-lookup"><span data-stu-id="24fdc-102">RUNTIME_INFO_FLAGS Enumeration</span></span>

<span data-ttu-id="24fdc-103">包含一些值，这些值指示应返回 (CLR) 的公共语言运行时信息。</span><span class="sxs-lookup"><span data-stu-id="24fdc-103">Contains values that indicate what information about the common language runtime (CLR) should be returned.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24fdc-104">语法</span><span class="sxs-lookup"><span data-stu-id="24fdc-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
  
    RUNTIME_INFO_UPGRADE_VERSION             = 0x01,  
    RUNTIME_INFO_REQUEST_IA64                = 0x02,  
    RUNTIME_INFO_REQUEST_AMD64               = 0x04,  
    RUNTIME_INFO_REQUEST_X86                 = 0x08,  
    RUNTIME_INFO_DONT_RETURN_DIRECTORY       = 0x10,  
    RUNTIME_INFO_DONT_RETURN_VERSION         = 0x20,  
    RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG      = 0x40,  
    RUNTIME_INFO_IGNORE_ERROR_MODE           = 0x1000  
  
} RUNTIME_INFO_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="24fdc-105">成员</span><span class="sxs-lookup"><span data-stu-id="24fdc-105">Members</span></span>  
  
|<span data-ttu-id="24fdc-106">成员</span><span class="sxs-lookup"><span data-stu-id="24fdc-106">Member</span></span>|<span data-ttu-id="24fdc-107">说明</span><span class="sxs-lookup"><span data-stu-id="24fdc-107">Description</span></span>|  
|------------|-----------------|  
|`RUNTIME_INFO_DONT_RETURN_DIRECTORY`|<span data-ttu-id="24fdc-108">指示不应包含目录信息。</span><span class="sxs-lookup"><span data-stu-id="24fdc-108">Indicates that directory information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_RETURN_VERSION`|<span data-ttu-id="24fdc-109">指示不应包含版本信息。</span><span class="sxs-lookup"><span data-stu-id="24fdc-109">Indicates that version information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG`|<span data-ttu-id="24fdc-110">指示在失败时不应显示错误对话框。</span><span class="sxs-lookup"><span data-stu-id="24fdc-110">Indicates that an error dialog box should not be shown upon failure.</span></span>|  
|`RUNTIME_INFO_IGNORE_ERROR_MODE`|<span data-ttu-id="24fdc-111">指示应重写调用带有 SEM_FAILCRITICALERRORS 标志的 [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) 函数的效果。</span><span class="sxs-lookup"><span data-stu-id="24fdc-111">Indicates that the effects of calling the [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) function with the SEM_FAILCRITICALERRORS flag should be overridden.</span></span> <span data-ttu-id="24fdc-112">也就是说，出现故障时应显示安装对话框，而不是取消显示。</span><span class="sxs-lookup"><span data-stu-id="24fdc-112">That is, an installation dialog box should be shown upon failure, instead of being suppressed.</span></span>|  
|`RUNTIME_INFO_REQUEST_AMD64`|<span data-ttu-id="24fdc-113">指示对与 AMD-64 兼容的运行时版本的信息的请求。</span><span class="sxs-lookup"><span data-stu-id="24fdc-113">Indicates a request for information about an AMD-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_IA64`|<span data-ttu-id="24fdc-114">指示对与 IA-64 兼容的运行时版本有关的信息的请求。</span><span class="sxs-lookup"><span data-stu-id="24fdc-114">Indicates a request for information about an IA-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_X86`|<span data-ttu-id="24fdc-115">指示对与 x86 兼容的运行时版本有关的信息的请求。</span><span class="sxs-lookup"><span data-stu-id="24fdc-115">Indicates a request for information about an x86-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_UPGRADE_VERSION`|<span data-ttu-id="24fdc-116">指示应包含版本升级信息。</span><span class="sxs-lookup"><span data-stu-id="24fdc-116">Indicates that version upgrade information should be included.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="24fdc-117">注解</span><span class="sxs-lookup"><span data-stu-id="24fdc-117">Remarks</span></span>  

 <span data-ttu-id="24fdc-118">以下平台体系结构标志一次只能指定一个，且不能组合使用：</span><span class="sxs-lookup"><span data-stu-id="24fdc-118">The following platform architecture flags can be specified only one at a time and cannot be combined:</span></span>  
  
- <span data-ttu-id="24fdc-119">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="24fdc-119">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
- <span data-ttu-id="24fdc-120">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="24fdc-120">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
- <span data-ttu-id="24fdc-121">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="24fdc-121">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24fdc-122">要求</span><span class="sxs-lookup"><span data-stu-id="24fdc-122">Requirements</span></span>  

 <span data-ttu-id="24fdc-123">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="24fdc-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24fdc-124">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="24fdc-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="24fdc-125">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="24fdc-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="24fdc-126">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24fdc-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24fdc-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24fdc-127">See also</span></span>

- [<span data-ttu-id="24fdc-128">承载枚举</span><span class="sxs-lookup"><span data-stu-id="24fdc-128">Hosting Enumerations</span></span>](hosting-enumerations.md)
