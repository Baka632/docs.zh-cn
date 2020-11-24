---
title: CorPEKind 枚举
ms.date: 03/30/2017
api_name:
- CorPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPEKind
helpviewer_keywords:
- CorPEKind enumeration [.NET Framework metadata]
ms.assetid: 22dc6dea-b1b9-4982-a730-a022d586b117
topic_type:
- apiref
ms.openlocfilehash: 001be0c5e8897bacf76d2a044fb9400768473052
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673522"
---
# <a name="corpekind-enumeration"></a><span data-ttu-id="b2863-102">CorPEKind 枚举</span><span class="sxs-lookup"><span data-stu-id="b2863-102">CorPEKind Enumeration</span></span>

<span data-ttu-id="b2863-103">包含一些值，用于描述从 [IMetaDataImport2：： GetPEKind](imetadataimport2-getpekind-method.md)调用返回的可移植可执行文件 (PE) 文件。</span><span class="sxs-lookup"><span data-stu-id="b2863-103">Contains values that describe a portable executable (PE) file, as returned from a call to [IMetaDataImport2::GetPEKind](imetadataimport2-getpekind-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2863-104">语法</span><span class="sxs-lookup"><span data-stu-id="b2863-104">Syntax</span></span>  
  
```cpp  
typedef enum CorPEKind {  
  
    peNot           = 0x00000000,  
    peILonly        = 0x00000001,  
    pe32BitRequired = 0x00000002,  
    pe32Plus        = 0x00000004,  
    pe32Unmanaged   = 0x00000008,  
    pe32BitPreferred= 0x00000010  
  
} CorPEKind;  
```  
  
## <a name="members"></a><span data-ttu-id="b2863-105">成员</span><span class="sxs-lookup"><span data-stu-id="b2863-105">Members</span></span>  
  
|<span data-ttu-id="b2863-106">成员</span><span class="sxs-lookup"><span data-stu-id="b2863-106">Member</span></span>|<span data-ttu-id="b2863-107">说明</span><span class="sxs-lookup"><span data-stu-id="b2863-107">Description</span></span>|  
|------------|-----------------|  
|`peNot`|<span data-ttu-id="b2863-108">指示这不是 PE 文件。</span><span class="sxs-lookup"><span data-stu-id="b2863-108">Indicates that this is not a PE file.</span></span>|  
|`peILOnly`|<span data-ttu-id="b2863-109">指示此 PE 文件仅包含托管代码。</span><span class="sxs-lookup"><span data-stu-id="b2863-109">Indicates that this PE file contains only managed code.</span></span>|  
|`pe32BitRequired`|<span data-ttu-id="b2863-110">指示此 PE 文件进行 Win32 调用。</span><span class="sxs-lookup"><span data-stu-id="b2863-110">Indicates that this PE file makes Win32 calls.</span></span>|  
|`pe32Plus`|<span data-ttu-id="b2863-111">指示此 PE 文件在64位平台上运行。</span><span class="sxs-lookup"><span data-stu-id="b2863-111">Indicates that this PE file runs on a 64-bit platform.</span></span>|  
|`pe32Unmanaged`|<span data-ttu-id="b2863-112">指示此 PE 文件是本机代码。</span><span class="sxs-lookup"><span data-stu-id="b2863-112">Indicates that this PE file is native code.</span></span>|  
|<span data-ttu-id="b2863-113">pe32BitPreferred</span><span class="sxs-lookup"><span data-stu-id="b2863-113">pe32BitPreferred</span></span>|<span data-ttu-id="b2863-114">指示此 PE 文件与平台无关，并倾向于在32位环境中加载。</span><span class="sxs-lookup"><span data-stu-id="b2863-114">Indicates that this PE file is platform-neutral and prefers to be loaded in a 32-bit environment.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2863-115">注解</span><span class="sxs-lookup"><span data-stu-id="b2863-115">Remarks</span></span>  

 <span data-ttu-id="b2863-116">这些值可用于按位组合。</span><span class="sxs-lookup"><span data-stu-id="b2863-116">These values can be used in bitwise combinations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2863-117">要求</span><span class="sxs-lookup"><span data-stu-id="b2863-117">Requirements</span></span>  

 <span data-ttu-id="b2863-118">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b2863-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2863-119">**标头：** Corhdr。h</span><span class="sxs-lookup"><span data-stu-id="b2863-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="b2863-120">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2863-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2863-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b2863-121">See also</span></span>

- [<span data-ttu-id="b2863-122">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="b2863-122">Metadata Enumerations</span></span>](metadata-enumerations.md)
