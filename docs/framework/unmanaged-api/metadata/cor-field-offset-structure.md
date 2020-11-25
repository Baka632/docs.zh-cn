---
title: COR_FIELD_OFFSET 结构
ms.date: 03/30/2017
api_name:
- COR_FIELD_OFFSET
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_FIELD_OFFSET
helpviewer_keywords:
- COR_FIELD_OFFSET structure [.NET Framework metadata]
ms.assetid: cced5298-277f-4a5a-8ecf-a0050c1096ea
topic_type:
- apiref
ms.openlocfilehash: 1a8ab5aa5909af60089d5e4cc8092e15bc75e8cc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724177"
---
# <a name="cor_field_offset-structure"></a><span data-ttu-id="3466d-102">COR_FIELD_OFFSET 结构</span><span class="sxs-lookup"><span data-stu-id="3466d-102">COR_FIELD_OFFSET Structure</span></span>

<span data-ttu-id="3466d-103">存储一个类中的指定字段的偏移量。</span><span class="sxs-lookup"><span data-stu-id="3466d-103">Stores the offset, within a class, of the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3466d-104">语法</span><span class="sxs-lookup"><span data-stu-id="3466d-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_FIELD_OFFSET {  
    mdFieldDef  ridOfField;  
    ULONG       ulOffset;  
} COR_FIELD_OFFSET;  
```  
  
## <a name="members"></a><span data-ttu-id="3466d-105">成员</span><span class="sxs-lookup"><span data-stu-id="3466d-105">Members</span></span>  
  
|<span data-ttu-id="3466d-106">成员</span><span class="sxs-lookup"><span data-stu-id="3466d-106">Member</span></span>|<span data-ttu-id="3466d-107">说明</span><span class="sxs-lookup"><span data-stu-id="3466d-107">Description</span></span>|  
|------------|-----------------|  
|`ridOfField`|<span data-ttu-id="3466d-108">`mdFieldDef`表示字段的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="3466d-108">An `mdFieldDef` metadata token that represents the field.</span></span>|  
|`ulOffset`|<span data-ttu-id="3466d-109">字段在其类中的偏移量。</span><span class="sxs-lookup"><span data-stu-id="3466d-109">The field's offset within its class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3466d-110">注解</span><span class="sxs-lookup"><span data-stu-id="3466d-110">Remarks</span></span>  

 <span data-ttu-id="3466d-111">[IMetaDataImport：： GetClassLayout](imetadataimport-getclasslayout-method.md) 和 [IMetaDataEmit：： SetClassLayout](imetadataemit-setclasslayout-method.md) 方法采用类型的参数 `COR_FIELD_OFFSET` 。</span><span class="sxs-lookup"><span data-stu-id="3466d-111">[IMetaDataImport::GetClassLayout](imetadataimport-getclasslayout-method.md) and [IMetaDataEmit::SetClassLayout](imetadataemit-setclasslayout-method.md) methods take a parameter of type `COR_FIELD_OFFSET`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3466d-112">要求</span><span class="sxs-lookup"><span data-stu-id="3466d-112">Requirements</span></span>  

 <span data-ttu-id="3466d-113">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3466d-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3466d-114">**标头：** Corhdr.h，Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="3466d-114">**Header:** CorHdr.h, CorProf.idl</span></span>  
  
 <span data-ttu-id="3466d-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3466d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3466d-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3466d-116">See also</span></span>

- [<span data-ttu-id="3466d-117">元数据结构</span><span class="sxs-lookup"><span data-stu-id="3466d-117">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="3466d-118">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="3466d-118">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="3466d-119">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="3466d-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
