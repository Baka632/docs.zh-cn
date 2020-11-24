---
title: CorLinkerOptions 枚举
ms.date: 03/30/2017
api_name:
- CorLinkerOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorLinkerOptions
helpviewer_keywords:
- CorLinkerOptions enumeration [.NET Framework metadata]
ms.assetid: a656aad6-cc7e-4994-8251-004a6a45e18f
topic_type:
- apiref
ms.openlocfilehash: 188301d31b2fcfaf7b1c6139111e8f1296ccf7e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677223"
---
# <a name="corlinkeroptions-enumeration"></a><span data-ttu-id="6955a-102">CorLinkerOptions 枚举</span><span class="sxs-lookup"><span data-stu-id="6955a-102">CorLinkerOptions Enumeration</span></span>

<span data-ttu-id="6955a-103">指定用于选择元数据链接器的选项的标志。</span><span class="sxs-lookup"><span data-stu-id="6955a-103">Specifies flags to select options for the metadata linker.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6955a-104">语法</span><span class="sxs-lookup"><span data-stu-id="6955a-104">Syntax</span></span>  
  
```cpp  
typedef enum CorLinkerOptions {  
    MDAssembly          = 0x00000000,  
    MDNetModule         = 0x00000001,  
} CorLinkerOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="6955a-105">成员</span><span class="sxs-lookup"><span data-stu-id="6955a-105">Members</span></span>  
  
|<span data-ttu-id="6955a-106">成员</span><span class="sxs-lookup"><span data-stu-id="6955a-106">Member</span></span>|<span data-ttu-id="6955a-107">说明</span><span class="sxs-lookup"><span data-stu-id="6955a-107">Description</span></span>|  
|------------|-----------------|  
|`MDAssembly`|<span data-ttu-id="6955a-108">不保留私有类型和全局函数。</span><span class="sxs-lookup"><span data-stu-id="6955a-108">The private types and global functions are not preserved.</span></span>|  
|`MDNetModule`|<span data-ttu-id="6955a-109">私有类型和全局函数会被保留。</span><span class="sxs-lookup"><span data-stu-id="6955a-109">The private types and global functions are preserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6955a-110">要求</span><span class="sxs-lookup"><span data-stu-id="6955a-110">Requirements</span></span>  

 <span data-ttu-id="6955a-111">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6955a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6955a-112">**标头：** Corhdr。h</span><span class="sxs-lookup"><span data-stu-id="6955a-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="6955a-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6955a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6955a-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6955a-114">See also</span></span>

- [<span data-ttu-id="6955a-115">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="6955a-115">Metadata Enumerations</span></span>](metadata-enumerations.md)
