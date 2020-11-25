---
title: CorDebugExceptionUnwindCallbackType 枚举
ms.date: 03/30/2017
api_name:
- CorDebugExceptionUnwindCallbackType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionUnwindCallbackType
helpviewer_keywords:
- CorDebugExceptionUnwindCallbackType enumeration [.NET Framework debugging]
ms.assetid: 783dce92-8a98-43db-8f78-888d943dd5b2
topic_type:
- apiref
ms.openlocfilehash: 30de1448a7d1452e1e9049411010e7f43d13eb70
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712620"
---
# <a name="cordebugexceptionunwindcallbacktype-enumeration"></a><span data-ttu-id="26089-102">CorDebugExceptionUnwindCallbackType 枚举</span><span class="sxs-lookup"><span data-stu-id="26089-102">CorDebugExceptionUnwindCallbackType Enumeration</span></span>

<span data-ttu-id="26089-103">指示在展开阶段正由回调发送信号的事件。</span><span class="sxs-lookup"><span data-stu-id="26089-103">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26089-104">语法</span><span class="sxs-lookup"><span data-stu-id="26089-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugExceptionUnwindCallbackType {  
    DEBUG_EXCEPTION_UNWIND_BEGIN = 1,  
    DEBUG_EXCEPTION_INTERCEPTED  = 2  
} CorDebugExceptionUnwindCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="26089-105">成员</span><span class="sxs-lookup"><span data-stu-id="26089-105">Members</span></span>  
  
|<span data-ttu-id="26089-106">成员</span><span class="sxs-lookup"><span data-stu-id="26089-106">Member</span></span>|<span data-ttu-id="26089-107">说明</span><span class="sxs-lookup"><span data-stu-id="26089-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_UNWIND_BEGIN`|<span data-ttu-id="26089-108">展开进程的开头。</span><span class="sxs-lookup"><span data-stu-id="26089-108">The beginning of the unwind process.</span></span>|  
|`DEBUG_EXCEPTION_INTERCEPTED`|<span data-ttu-id="26089-109">异常已被截取。</span><span class="sxs-lookup"><span data-stu-id="26089-109">The exception was intercepted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="26089-110">要求</span><span class="sxs-lookup"><span data-stu-id="26089-110">Requirements</span></span>  

 <span data-ttu-id="26089-111">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="26089-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26089-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="26089-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="26089-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26089-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26089-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26089-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26089-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="26089-115">See also</span></span>

- [<span data-ttu-id="26089-116">调试枚举</span><span class="sxs-lookup"><span data-stu-id="26089-116">Debugging Enumerations</span></span>](debugging-enumerations.md)
