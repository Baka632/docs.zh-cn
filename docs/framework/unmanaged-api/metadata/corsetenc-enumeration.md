---
title: CorSetENC 枚举
ms.date: 03/30/2017
api_name:
- CorSetENC
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSetENC
helpviewer_keywords:
- CorSetENC enumeration [.NET Framework metadata]
ms.assetid: fe4150e8-071d-43fb-8e06-c3c616dbeed2
topic_type:
- apiref
ms.openlocfilehash: df945803f2d56d04ccc68f314eb55665579ed7fd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705977"
---
# <a name="corsetenc-enumeration"></a><span data-ttu-id="58136-102">CorSetENC 枚举</span><span class="sxs-lookup"><span data-stu-id="58136-102">CorSetENC Enumeration</span></span>

<span data-ttu-id="58136-103">包含一些值，用于在元数据生成期间影响行为。</span><span class="sxs-lookup"><span data-stu-id="58136-103">Contains values used to influence behavior during the generation of metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58136-104">语法</span><span class="sxs-lookup"><span data-stu-id="58136-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSetENC {  
  
    MDSetENCOn                  = 0x00000001,  
    MDSetENCOff                 = 0x00000002,  
  
    MDUpdateENC                 = 0x00000001,  
    MDUpdateFull                = 0x00000002,  
    MDUpdateExtension           = 0x00000003,  
    MDUpdateIncremental         = 0x00000004,  
    MDUpdateDelta               = 0x00000005,  
    MDUpdateMask                = 0x00000007  
  
} CorSetENC;  
```  
  
## <a name="members"></a><span data-ttu-id="58136-105">成员</span><span class="sxs-lookup"><span data-stu-id="58136-105">Members</span></span>  
  
|<span data-ttu-id="58136-106">成员</span><span class="sxs-lookup"><span data-stu-id="58136-106">Member</span></span>|<span data-ttu-id="58136-107">说明</span><span class="sxs-lookup"><span data-stu-id="58136-107">Description</span></span>|  
|------------|-----------------|  
|`MDSetENCOn`|<span data-ttu-id="58136-108">已过时。</span><span class="sxs-lookup"><span data-stu-id="58136-108">Obsolete.</span></span>|  
|`MDSetENCOff`|<span data-ttu-id="58136-109">已过时。</span><span class="sxs-lookup"><span data-stu-id="58136-109">Obsolete.</span></span>|  
|`MDUpdateENC`|<span data-ttu-id="58136-110">指示可以更新元数据，而不能移动标记。</span><span class="sxs-lookup"><span data-stu-id="58136-110">Indicates that whereas metadata can be updated, tokens cannot be moved.</span></span>|  
|`MDUpdateFull`|<span data-ttu-id="58136-111">指示在更新过程中可以移动令牌。</span><span class="sxs-lookup"><span data-stu-id="58136-111">Indicates that tokens can be moved during updates.</span></span>|  
|`MDUpdateExtension`|<span data-ttu-id="58136-112">指示更新只能包含添加内容。</span><span class="sxs-lookup"><span data-stu-id="58136-112">Indicates that updates can consist only of additions.</span></span> <span data-ttu-id="58136-113">无法移动令牌。</span><span class="sxs-lookup"><span data-stu-id="58136-113">Tokens cannot be moved.</span></span>|  
|`MDUpdateIncremental`|<span data-ttu-id="58136-114">指示编译是递增的。</span><span class="sxs-lookup"><span data-stu-id="58136-114">Indicates that compilation is incremental.</span></span>|  
|`MDUpdateDelta`|<span data-ttu-id="58136-115">指示仅保存更改的元数据。</span><span class="sxs-lookup"><span data-stu-id="58136-115">Indicates that only changed metadata should be saved.</span></span>|  
|`MDUpdateMask`|<span data-ttu-id="58136-116">包括 `MDUpdateENC` 、 `MDUpdateFull` 和 `MDUpdateIncremental` 。</span><span class="sxs-lookup"><span data-stu-id="58136-116">Includes `MDUpdateENC`, `MDUpdateFull` and `MDUpdateIncremental`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="58136-117">要求</span><span class="sxs-lookup"><span data-stu-id="58136-117">Requirements</span></span>  

 <span data-ttu-id="58136-118">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="58136-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58136-119">**标头：** Corhdr。h</span><span class="sxs-lookup"><span data-stu-id="58136-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="58136-120">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58136-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58136-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58136-121">See also</span></span>

- [<span data-ttu-id="58136-122">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="58136-122">Metadata Enumerations</span></span>](metadata-enumerations.md)
