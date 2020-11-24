---
title: CorMethodSemanticsAttr 枚举
ms.date: 03/30/2017
api_name:
- CorMethodSemanticsAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodSemanticsAttr
helpviewer_keywords:
- CorMethodSemanticsAttr enumeration [.NET Framework metadata]
ms.assetid: ca2af325-eb9d-4a91-90e4-267e45b98611
topic_type:
- apiref
ms.openlocfilehash: 347b323951b0125ffa5f82626b2d9b235079492c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676941"
---
# <a name="cormethodsemanticsattr-enumeration"></a><span data-ttu-id="94442-102">CorMethodSemanticsAttr 枚举</span><span class="sxs-lookup"><span data-stu-id="94442-102">CorMethodSemanticsAttr Enumeration</span></span>

<span data-ttu-id="94442-103">包含一些值，用于描述方法和关联属性或事件之间的关系。</span><span class="sxs-lookup"><span data-stu-id="94442-103">Contains values that describe the relationship between a method and an associated property or event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94442-104">语法</span><span class="sxs-lookup"><span data-stu-id="94442-104">Syntax</span></span>  
  
```cpp  
typedef enum CorMethodSemanticsAttr {  
  
    msSetter    =   0x0001,  
    msGetter    =   0x0002,  
    msOther     =   0x0004,  
    msAddOn     =   0x0008,  
    msRemoveOn  =   0x0010,  
    msFire      =   0x0020,  
  
} CorMethodSemanticsAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="94442-105">成员</span><span class="sxs-lookup"><span data-stu-id="94442-105">Members</span></span>  
  
|<span data-ttu-id="94442-106">成员</span><span class="sxs-lookup"><span data-stu-id="94442-106">Member</span></span>|<span data-ttu-id="94442-107">说明</span><span class="sxs-lookup"><span data-stu-id="94442-107">Description</span></span>|  
|------------|-----------------|  
|`msSetter`|<span data-ttu-id="94442-108">指定该方法是属性的 `set` 访问器。</span><span class="sxs-lookup"><span data-stu-id="94442-108">Specifies that the method is a `set` accessor for a property.</span></span>|  
|`msGetter`|<span data-ttu-id="94442-109">指定该方法是属性的 `get` 访问器。</span><span class="sxs-lookup"><span data-stu-id="94442-109">Specifies that the method is a `get` accessor for a property.</span></span>|  
|`msOther`|<span data-ttu-id="94442-110">指定该方法与在此处定义的属性或事件无关。</span><span class="sxs-lookup"><span data-stu-id="94442-110">Specifies that the method has a relationship to a property or an event other than those defined here.</span></span>|  
|`msAddOn`|<span data-ttu-id="94442-111">指定方法为事件添加处理程序方法。</span><span class="sxs-lookup"><span data-stu-id="94442-111">Specifies that the method adds handler methods for an event.</span></span>|  
|`msRemoveOn`|<span data-ttu-id="94442-112">指定该方法移除事件的处理程序方法。</span><span class="sxs-lookup"><span data-stu-id="94442-112">Specifies that the method removes handler methods for an event.</span></span>|  
|`msFire`|<span data-ttu-id="94442-113">指定方法引发事件。</span><span class="sxs-lookup"><span data-stu-id="94442-113">Specifies that the method raises an event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="94442-114">要求</span><span class="sxs-lookup"><span data-stu-id="94442-114">Requirements</span></span>  

 <span data-ttu-id="94442-115">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="94442-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94442-116">**标头：** Corhdr。h</span><span class="sxs-lookup"><span data-stu-id="94442-116">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="94442-117">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94442-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94442-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94442-118">See also</span></span>

- [<span data-ttu-id="94442-119">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="94442-119">Metadata Enumerations</span></span>](metadata-enumerations.md)
