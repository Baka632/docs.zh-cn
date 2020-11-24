---
title: COR_PRF_JIT_CACHE 枚举
ms.date: 03/30/2017
api_name:
- COR_PRF_JIT_CACHE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_JIT_CACHE
helpviewer_keywords:
- COR_PRF_JIT_CACHE enumeration [.NET Framework profiling]
ms.assetid: e7b8f6b4-95bc-4ba5-b9eb-f5590a7326a4
topic_type:
- apiref
ms.openlocfilehash: 0bf17e7c9d8ff16dc8f07e4a386f599284828f40
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682232"
---
# <a name="cor_prf_jit_cache-enumeration"></a><span data-ttu-id="2f073-102">COR_PRF_JIT_CACHE 枚举</span><span class="sxs-lookup"><span data-stu-id="2f073-102">COR_PRF_JIT_CACHE Enumeration</span></span>

<span data-ttu-id="2f073-103">指示缓存的函数搜索的结果。</span><span class="sxs-lookup"><span data-stu-id="2f073-103">Indicates the result of a cached function search.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2f073-104">`COR_PRF_CACHED_FUNCTION_FOUND` 的值为零，因此 `COR_PRF_JIT_CACHE` 不能用作布尔代理项。</span><span class="sxs-lookup"><span data-stu-id="2f073-104">`COR_PRF_CACHED_FUNCTION_FOUND` has a value of zero, so `COR_PRF_JIT_CACHE` cannot be used as a Boolean surrogate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f073-105">语法</span><span class="sxs-lookup"><span data-stu-id="2f073-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_CACHED_FUNCTION_FOUND,  
    COR_PRF_CACHED_FUNCTION_NOT_FOUND  
} COR_PRF_JIT_CACHE;  
```  
  
## <a name="members"></a><span data-ttu-id="2f073-106">成员</span><span class="sxs-lookup"><span data-stu-id="2f073-106">Members</span></span>  
  
|<span data-ttu-id="2f073-107">成员</span><span class="sxs-lookup"><span data-stu-id="2f073-107">Member</span></span>|<span data-ttu-id="2f073-108">说明</span><span class="sxs-lookup"><span data-stu-id="2f073-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FUNCTION_FOUND`|<span data-ttu-id="2f073-109">搜索找到函数。</span><span class="sxs-lookup"><span data-stu-id="2f073-109">The search found the function.</span></span>|  
|`COR_PRF_FUNCTION_NOT_FOUND`|<span data-ttu-id="2f073-110">搜索找不到函数。</span><span class="sxs-lookup"><span data-stu-id="2f073-110">The search did not find the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2f073-111">要求</span><span class="sxs-lookup"><span data-stu-id="2f073-111">Requirements</span></span>  

 <span data-ttu-id="2f073-112">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2f073-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f073-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2f073-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2f073-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f073-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f073-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f073-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f073-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2f073-116">See also</span></span>

- [<span data-ttu-id="2f073-117">分析枚举</span><span class="sxs-lookup"><span data-stu-id="2f073-117">Profiling Enumerations</span></span>](profiling-enumerations.md)
