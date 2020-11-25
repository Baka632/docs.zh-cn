---
title: CorDebugJITCompilerFlags 枚举
ms.date: 03/30/2017
api_name:
- CorDebugJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugJITCompilerFlags
helpviewer_keywords:
- CorDebugJITCompilerFlags enumeration [.NET Framework debugging]
ms.assetid: c0774f70-5bed-45e8-9922-fdad778c4c33
topic_type:
- apiref
ms.openlocfilehash: 0c8398b9e423414f32a391edcd5ea1c709af37f5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696552"
---
# <a name="cordebugjitcompilerflags-enumeration"></a><span data-ttu-id="37605-102">CorDebugJITCompilerFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="37605-102">CorDebugJITCompilerFlags Enumeration</span></span>

<span data-ttu-id="37605-103">包含影响托管的实时 (JIT) 编译器的行为的值。</span><span class="sxs-lookup"><span data-stu-id="37605-103">Contains values that influence the behavior of the managed just-in-time (JIT) compiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37605-104">语法</span><span class="sxs-lookup"><span data-stu-id="37605-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugJITCompilerFlags {  
  
    CORDEBUG_JIT_DEFAULT = 0x1,  
    CORDEBUG_JIT_DISABLE_OPTIMIZATION = 0x3,  
    CORDEBUG_JIT_ENABLE_ENC = 0x7  
  
} CorDebugJITCompilerFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="37605-105">成员</span><span class="sxs-lookup"><span data-stu-id="37605-105">Members</span></span>  
  
|<span data-ttu-id="37605-106">成员</span><span class="sxs-lookup"><span data-stu-id="37605-106">Member</span></span>|<span data-ttu-id="37605-107">说明</span><span class="sxs-lookup"><span data-stu-id="37605-107">Description</span></span>|  
|------------|-----------------|  
|`CORDEBUG_JIT_DEFAULT`|<span data-ttu-id="37605-108">指定编译器应跟踪编译数据，并允许优化。</span><span class="sxs-lookup"><span data-stu-id="37605-108">Specifies that the compiler should track compilation data, and allows optimizations.</span></span>|  
|`CORDEBUG_JIT_DISABLE_OPTIMIZATION`|<span data-ttu-id="37605-109">指定编译器应跟踪编译数据，但禁用优化。</span><span class="sxs-lookup"><span data-stu-id="37605-109">Specifies that the compiler should track compilation data, but disables optimizations.</span></span>|  
|`CORDEBUG_JIT_ENABLE_ENC`|<span data-ttu-id="37605-110">指定编译器应跟踪编译数据，禁用优化，并启用 "编辑并继续" 技术。</span><span class="sxs-lookup"><span data-stu-id="37605-110">Specifies that the compiler should track compilation data, disables optimizations, and enables Edit and Continue technologies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="37605-111">要求</span><span class="sxs-lookup"><span data-stu-id="37605-111">Requirements</span></span>  

 <span data-ttu-id="37605-112">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="37605-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37605-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="37605-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="37605-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37605-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="37605-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37605-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37605-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="37605-116">See also</span></span>

- [<span data-ttu-id="37605-117">调试枚举</span><span class="sxs-lookup"><span data-stu-id="37605-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
