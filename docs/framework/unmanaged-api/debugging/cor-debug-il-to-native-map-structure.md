---
title: COR_DEBUG_IL_TO_NATIVE_MAP 结构
ms.date: 03/30/2017
api_name:
- COR_DEBUG_IL_TO_NATIVE_MAP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP
helpviewer_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP structure [.NET Framework debugging]
ms.assetid: 06f3b504-085f-4142-934a-25381fe23d4c
topic_type:
- apiref
ms.openlocfilehash: 61544d0dfe876f35fdfbe5afa945fad0620c0eb5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726647"
---
# <a name="cor_debug_il_to_native_map-structure"></a><span data-ttu-id="2e9f9-102">COR_DEBUG_IL_TO_NATIVE_MAP 结构</span><span class="sxs-lookup"><span data-stu-id="2e9f9-102">COR_DEBUG_IL_TO_NATIVE_MAP Structure</span></span>

<span data-ttu-id="2e9f9-103">包含用于将 Microsoft 中间语言 (MSIL) 代码映射到本机代码的偏移量。</span><span class="sxs-lookup"><span data-stu-id="2e9f9-103">Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e9f9-104">语法</span><span class="sxs-lookup"><span data-stu-id="2e9f9-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_DEBUG_IL_TO_NATIVE_MAP {  
    ULONG32  ilOffset;  
    ULONG32  nativeStartOffset;  
    ULONG32  nativeEndOffset;  
} COR_DEBUG_IL_TO_NATIVE_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="2e9f9-105">成员</span><span class="sxs-lookup"><span data-stu-id="2e9f9-105">Members</span></span>  
  
|<span data-ttu-id="2e9f9-106">成员</span><span class="sxs-lookup"><span data-stu-id="2e9f9-106">Member</span></span>|<span data-ttu-id="2e9f9-107">说明</span><span class="sxs-lookup"><span data-stu-id="2e9f9-107">Description</span></span>|  
|------------|-----------------|  
|`ilOffset`|<span data-ttu-id="2e9f9-108">MSIL 代码的偏移量。</span><span class="sxs-lookup"><span data-stu-id="2e9f9-108">The offset of the MSIL code.</span></span>|  
|`nativeStartOffset`|<span data-ttu-id="2e9f9-109">本机代码起始位置的偏移量。</span><span class="sxs-lookup"><span data-stu-id="2e9f9-109">The offset of the start of the native code.</span></span>|  
|`nativeEndOffset`|<span data-ttu-id="2e9f9-110">本机代码末尾的偏移量。</span><span class="sxs-lookup"><span data-stu-id="2e9f9-110">The offset of the end of the native code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2e9f9-111">要求</span><span class="sxs-lookup"><span data-stu-id="2e9f9-111">Requirements</span></span>  

 <span data-ttu-id="2e9f9-112">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2e9f9-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e9f9-113">**标头：** Corprof.idl、Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="2e9f9-113">**Header:** CorProf.idl, CorDebug.idl</span></span>  
  
 <span data-ttu-id="2e9f9-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e9f9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e9f9-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e9f9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e9f9-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e9f9-116">See also</span></span>

- [<span data-ttu-id="2e9f9-117">GetILToNativeMapping 方法</span><span class="sxs-lookup"><span data-stu-id="2e9f9-117">GetILToNativeMapping Method</span></span>](../profiling/icorprofilerinfo-getiltonativemapping-method.md)
- [<span data-ttu-id="2e9f9-118">GetILToNativeMapping 方法</span><span class="sxs-lookup"><span data-stu-id="2e9f9-118">GetILToNativeMapping Method</span></span>](icordebugcode-getiltonativemapping-method.md)
- [<span data-ttu-id="2e9f9-119">调试结构</span><span class="sxs-lookup"><span data-stu-id="2e9f9-119">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="2e9f9-120">调试</span><span class="sxs-lookup"><span data-stu-id="2e9f9-120">Debugging</span></span>](index.md)
