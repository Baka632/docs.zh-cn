---
title: CorRefToDefCheck 枚举
ms.date: 03/30/2017
api_name:
- CorRefToDefCheck
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRefToDefCheck
helpviewer_keywords:
- CorRefToDefCheck enumeration [.NET Framework metadata]
ms.assetid: f9a80f1a-55af-4459-b095-8441aae16119
topic_type:
- apiref
ms.openlocfilehash: e7ce604acddb88d5a15844cbce2622b21e364cc1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706107"
---
# <a name="correftodefcheck-enumeration"></a><span data-ttu-id="8c5d5-102">CorRefToDefCheck 枚举</span><span class="sxs-lookup"><span data-stu-id="8c5d5-102">CorRefToDefCheck Enumeration</span></span>

<span data-ttu-id="8c5d5-103">指定用于控制将哪些引用项转换为相应定义以优化代码的标志。</span><span class="sxs-lookup"><span data-stu-id="8c5d5-103">Specifies flags to control which referenced items are converted to their definitions in order to optimize the code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c5d5-104">语法</span><span class="sxs-lookup"><span data-stu-id="8c5d5-104">Syntax</span></span>  
  
```cpp  
typedef enum CorRefToDefCheck {  
    MDRefToDefDefault           = 0x00000003,  
    MDRefToDefAll               = 0xffffffff,  
    MDRefToDefNone              = 0x00000000,  
    MDTypeRefToDef              = 0x00000001,  
    MDMemberRefToDef            = 0x00000002  
} CorRefToDefCheck;  
```  
  
## <a name="members"></a><span data-ttu-id="8c5d5-105">成员</span><span class="sxs-lookup"><span data-stu-id="8c5d5-105">Members</span></span>  
  
|<span data-ttu-id="8c5d5-106">成员</span><span class="sxs-lookup"><span data-stu-id="8c5d5-106">Member</span></span>|<span data-ttu-id="8c5d5-107">说明</span><span class="sxs-lookup"><span data-stu-id="8c5d5-107">Description</span></span>|  
|------------|-----------------|  
|`MDRefToDefDefault`|<span data-ttu-id="8c5d5-108">指定应将类型引用和成员引用转换为定义。</span><span class="sxs-lookup"><span data-stu-id="8c5d5-108">Specifies that type references and member references should be converted to definitions.</span></span> <span data-ttu-id="8c5d5-109">这是 (&#124;) 的默认值 `MDTypeRefToDef` `MDMemberRefToDef` 。</span><span class="sxs-lookup"><span data-stu-id="8c5d5-109">This is the default value (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).</span></span>|  
|`MDRefToDefAll`|<span data-ttu-id="8c5d5-110">指定所有引用项都应转换为定义。</span><span class="sxs-lookup"><span data-stu-id="8c5d5-110">Specifies that all referenced items should be converted to definitions.</span></span>|  
|`MDRefToDefNone`|<span data-ttu-id="8c5d5-111">指定不应将引用项转换为定义。</span><span class="sxs-lookup"><span data-stu-id="8c5d5-111">Specifies that no referenced items should be converted to definitions.</span></span>|  
|`MDTypeRefToDef`|<span data-ttu-id="8c5d5-112">指定仅类型引用应转换为类型定义。</span><span class="sxs-lookup"><span data-stu-id="8c5d5-112">Specifies that only type references should be converted to type definitions.</span></span>|  
|`MDMemberRefToDef`|<span data-ttu-id="8c5d5-113">指定只应将成员引用转换为定义。</span><span class="sxs-lookup"><span data-stu-id="8c5d5-113">Specifies that only member references should be converted to definitions.</span></span> <span data-ttu-id="8c5d5-114">也就是说，应将成员引用转换为方法定义或字段定义。</span><span class="sxs-lookup"><span data-stu-id="8c5d5-114">That is, member references should be converted to either method definitions or field definitions.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8c5d5-115">要求</span><span class="sxs-lookup"><span data-stu-id="8c5d5-115">Requirements</span></span>  

 <span data-ttu-id="8c5d5-116">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8c5d5-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c5d5-117">**标头：** Corhdr。h</span><span class="sxs-lookup"><span data-stu-id="8c5d5-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="8c5d5-118">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c5d5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c5d5-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8c5d5-119">See also</span></span>

- [<span data-ttu-id="8c5d5-120">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="8c5d5-120">Metadata Enumerations</span></span>](metadata-enumerations.md)
