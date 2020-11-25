---
title: CorDebugMappingResult 枚举
ms.date: 03/30/2017
api_name:
- CorDebugMappingResult
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugMappingResult
helpviewer_keywords:
- CorDebugMappingResult enumeration [.NET Framework debugging]
ms.assetid: 701281dd-2936-45c8-a1f0-3bf7332b093b
topic_type:
- apiref
ms.openlocfilehash: 0e7afa386af1bd2eebc2b58592d01b764660248f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704690"
---
# <a name="cordebugmappingresult-enumeration"></a><span data-ttu-id="b46d2-102">CorDebugMappingResult 枚举</span><span class="sxs-lookup"><span data-stu-id="b46d2-102">CorDebugMappingResult Enumeration</span></span>

<span data-ttu-id="b46d2-103">提供如何获取指令指针 (IP) 的值的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b46d2-103">Provides the details of how the value of the instruction pointer (IP) was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b46d2-104">语法</span><span class="sxs-lookup"><span data-stu-id="b46d2-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugMappingResult {  
    MAPPING_PROLOG              = 0x1,  
    MAPPING_EPILOG              = 0x2,  
    MAPPING_NO_INFO             = 0x4,  
    MAPPING_UNMAPPED_ADDRESS    = 0x8,  
    MAPPING_EXACT               = 0x10,  
    MAPPING_APPROXIMATE         = 0x20,  
} CorDebugMappingResult;  
```  
  
## <a name="members"></a><span data-ttu-id="b46d2-105">成员</span><span class="sxs-lookup"><span data-stu-id="b46d2-105">Members</span></span>  
  
|<span data-ttu-id="b46d2-106">成员</span><span class="sxs-lookup"><span data-stu-id="b46d2-106">Member</span></span>|<span data-ttu-id="b46d2-107">说明</span><span class="sxs-lookup"><span data-stu-id="b46d2-107">Description</span></span>|  
|------------|-----------------|  
|`MAPPING_PROLOG`|<span data-ttu-id="b46d2-108">本机代码在序言中，因此 IP 的值为0。</span><span class="sxs-lookup"><span data-stu-id="b46d2-108">The native code is in the prolog, so the value of the IP is 0.</span></span>|  
|`MAPPING_EPILOG`|<span data-ttu-id="b46d2-109">本机代码在 epilog 中，因此 IP 的值是方法的最后一条指令的地址。</span><span class="sxs-lookup"><span data-stu-id="b46d2-109">The native code is in an epilog, so the value of the IP is the address of the last instruction of the method.</span></span>|  
|`MAPPING_NO_INFO`|<span data-ttu-id="b46d2-110">此方法没有可用的映射信息，因此 IP 的值为0。</span><span class="sxs-lookup"><span data-stu-id="b46d2-110">No mapping information is available for the method, so the value of the IP is 0.</span></span>|  
|`MAPPING_UNMAPPED_ADDRESS`|<span data-ttu-id="b46d2-111">尽管方法存在映射信息，但当前地址无法映射到 Microsoft 中间语言 (MSIL) 代码。</span><span class="sxs-lookup"><span data-stu-id="b46d2-111">Although there is mapping information for the method, the current address cannot be mapped to Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="b46d2-112">IP 的值为0。</span><span class="sxs-lookup"><span data-stu-id="b46d2-112">The value of the IP is 0.</span></span>|  
|`MAPPING_EXACT`|<span data-ttu-id="b46d2-113">方法完全映射到 MSIL 代码或已解释帧，因此 IP 的值是准确的。</span><span class="sxs-lookup"><span data-stu-id="b46d2-113">Either the method maps exactly to MSIL code or the frame has been interpreted, so the value of the IP is accurate.</span></span>|  
|`MAPPING_APPROXIMATE`|<span data-ttu-id="b46d2-114">已成功映射方法，但 IP 的值可能是近似的。</span><span class="sxs-lookup"><span data-stu-id="b46d2-114">The method was successfully mapped, but the value of the IP may be approximate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b46d2-115">注解</span><span class="sxs-lookup"><span data-stu-id="b46d2-115">Remarks</span></span>  

 <span data-ttu-id="b46d2-116">可以使用 [ICorDebugILFrame：： GetIP](icordebugilframe-getip-method.md) 方法获取指令指针的值。</span><span class="sxs-lookup"><span data-stu-id="b46d2-116">You can use the [ICorDebugILFrame::GetIP](icordebugilframe-getip-method.md) method to obtain the value of the instruction pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b46d2-117">要求</span><span class="sxs-lookup"><span data-stu-id="b46d2-117">Requirements</span></span>  

 <span data-ttu-id="b46d2-118">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b46d2-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b46d2-119">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b46d2-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b46d2-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b46d2-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b46d2-121">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b46d2-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b46d2-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b46d2-122">See also</span></span>

- [<span data-ttu-id="b46d2-123">调试枚举</span><span class="sxs-lookup"><span data-stu-id="b46d2-123">Debugging Enumerations</span></span>](debugging-enumerations.md)
