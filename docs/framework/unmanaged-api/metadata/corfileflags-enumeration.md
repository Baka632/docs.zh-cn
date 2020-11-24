---
title: CorFileFlags 枚举
ms.date: 03/30/2017
api_name:
- CorFileFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFileFlags
helpviewer_keywords:
- CorFileFlags enumeration [.NET Framework metadata]
ms.assetid: d16703fd-518f-412e-92cb-74433d11032e
topic_type:
- apiref
ms.openlocfilehash: 70d789f417700734b546cac6ff527ed5aa84fcf9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688622"
---
# <a name="corfileflags-enumeration"></a><span data-ttu-id="b80f3-102">CorFileFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="b80f3-102">CorFileFlags Enumeration</span></span>

<span data-ttu-id="b80f3-103">包含一些值，这些值描述在对 [IMetaDataAssemblyEmit：:D efinefile](imetadataassemblyemit-definefile-method.md)的调用中定义的文件类型。</span><span class="sxs-lookup"><span data-stu-id="b80f3-103">Contains values that describe the type of file defined in a call to [IMetaDataAssemblyEmit::DefineFile](imetadataassemblyemit-definefile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b80f3-104">语法</span><span class="sxs-lookup"><span data-stu-id="b80f3-104">Syntax</span></span>  
  
```cpp  
typedef enum CorFileFlags {  
  
    ffContainsMetaData      =   0x0000,  
    ffContainsNoMetaData    =   0x0001  
  
} CorFileFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="b80f3-105">成员</span><span class="sxs-lookup"><span data-stu-id="b80f3-105">Members</span></span>  
  
|<span data-ttu-id="b80f3-106">成员</span><span class="sxs-lookup"><span data-stu-id="b80f3-106">Member</span></span>|<span data-ttu-id="b80f3-107">说明</span><span class="sxs-lookup"><span data-stu-id="b80f3-107">Description</span></span>|  
|------------|-----------------|  
|`ffContainsMetaData`|<span data-ttu-id="b80f3-108">指示该文件不是资源文件。</span><span class="sxs-lookup"><span data-stu-id="b80f3-108">Indicates that the file is not a resource file.</span></span>|  
|`ffContainsNoMetaData`|<span data-ttu-id="b80f3-109">指示文件可能不包含元数据，可能是资源文件。</span><span class="sxs-lookup"><span data-stu-id="b80f3-109">Indicates that the file, possibly a resource file, does not contain metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b80f3-110">要求</span><span class="sxs-lookup"><span data-stu-id="b80f3-110">Requirements</span></span>  

 <span data-ttu-id="b80f3-111">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b80f3-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b80f3-112">**标头：** Corhdr。h</span><span class="sxs-lookup"><span data-stu-id="b80f3-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="b80f3-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b80f3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b80f3-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b80f3-114">See also</span></span>

- [<span data-ttu-id="b80f3-115">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="b80f3-115">Metadata Enumerations</span></span>](metadata-enumerations.md)
