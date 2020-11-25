---
title: “Cor调试解码事件标志窗口”枚举
ms.date: 03/30/2017
api_name:
- CorDebugDecodeEventFlagsWindows
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: aa6cf962-30ae-4cfd-8895-826deeb46a54
topic_type:
- apiref
ms.openlocfilehash: 60eab923aac5dea927105e8ca9fa77eb5708f5ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733355"
---
# <a name="cordebugdecodeeventflagswindows-enumeration"></a><span data-ttu-id="b0643-102">“Cor调试解码事件标志窗口”枚举</span><span class="sxs-lookup"><span data-stu-id="b0643-102">CorDebugDecodeEventFlagsWindows Enumeration</span></span>

<span data-ttu-id="b0643-103">提供关于 Windows 平台上的调试事件的其他信息。</span><span class="sxs-lookup"><span data-stu-id="b0643-103">Provides additional information about debug events on the Windows platform.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0643-104">语法</span><span class="sxs-lookup"><span data-stu-id="b0643-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugDecodeEventFlagsWindows {  
    IS_FIRST_CHANCE = 1,  
} CorDebugDecodeEventFlagsWindows;  
```  
  
## <a name="members"></a><span data-ttu-id="b0643-105">成员</span><span class="sxs-lookup"><span data-stu-id="b0643-105">Members</span></span>  
  
|<span data-ttu-id="b0643-106">成员</span><span class="sxs-lookup"><span data-stu-id="b0643-106">Member</span></span>|<span data-ttu-id="b0643-107">说明</span><span class="sxs-lookup"><span data-stu-id="b0643-107">Description</span></span>|  
|------------|-----------------|  
|`IS_FIRST_CHANCE`|<span data-ttu-id="b0643-108">指出调试事件为最可能的异常。</span><span class="sxs-lookup"><span data-stu-id="b0643-108">Indicates that the debug event is a first-chance exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0643-109">注解</span><span class="sxs-lookup"><span data-stu-id="b0643-109">Remarks</span></span>  

 <span data-ttu-id="b0643-110">[ICorDebugProcess6：:D ecodeevent](icordebugprocess6-decodeevent-method.md)方法包含一个 `dwFlags` 参数，该参数提供有关调试事件的附加信息，并且其值依赖于目标体系结构。</span><span class="sxs-lookup"><span data-stu-id="b0643-110">The [ICorDebugProcess6::DecodeEvent](icordebugprocess6-decodeevent-method.md) method includes a `dwFlags` parameter that provides additional information about a debug event and whose value is dependent on the target architecture.</span></span> <span data-ttu-id="b0643-111">`CorDebugDecodeEventFlagsWindows` 枚举可与 Windows 平台上的调试事件一起使用。</span><span class="sxs-lookup"><span data-stu-id="b0643-111">The `CorDebugDecodeEventFlagsWindows` enumeration can be used with debug events on the Windows platform.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b0643-112">此枚举仅用于 .NET Native 调试方案。</span><span class="sxs-lookup"><span data-stu-id="b0643-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0643-113">要求</span><span class="sxs-lookup"><span data-stu-id="b0643-113">Requirements</span></span>  

 <span data-ttu-id="b0643-114">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b0643-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0643-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0643-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0643-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0643-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0643-117">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0643-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0643-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b0643-118">See also</span></span>

- [<span data-ttu-id="b0643-119">调试枚举</span><span class="sxs-lookup"><span data-stu-id="b0643-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
