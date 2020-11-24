---
title: LoggingLevelEnum 枚举
ms.date: 03/30/2017
api_name:
- LoggingLevelEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- LoggingLevelEnum
helpviewer_keywords:
- LoggingLevelEnum enumeration [.NET Framework debugging]
ms.assetid: 09daac08-005a-46b2-beab-408d0820c5e5
topic_type:
- apiref
ms.openlocfilehash: 389edbeb746fbeaf60d88bf9ee2a3a0731822e55
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671999"
---
# <a name="logginglevelenum-enumeration"></a><span data-ttu-id="d6415-102">LoggingLevelEnum 枚举</span><span class="sxs-lookup"><span data-stu-id="d6415-102">LoggingLevelEnum Enumeration</span></span>

<span data-ttu-id="d6415-103">指示在托管线程记录事件时写入事件日志的描述性消息的严重级别。</span><span class="sxs-lookup"><span data-stu-id="d6415-103">Indicates the severity level of a descriptive message that is written to the event log when a managed thread logs an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6415-104">语法</span><span class="sxs-lookup"><span data-stu-id="d6415-104">Syntax</span></span>  
  
```cpp  
typedef enum LoggingLevelEnum {  
    LTraceLevel0 = 0,  
    LTraceLevel1,  
    LTraceLevel2,  
    LTraceLevel3,  
    LTraceLevel4,  
    LStatusLevel0 = 20,  
    LStatusLevel1,  
    LStatusLevel2,  
    LStatusLevel3,  
    LStatusLevel4,  
    LWarningLevel = 40,  
    LErrorLevel = 50,  
    LPanicLevel = 100  
} LoggingLevelEnum;  
```  
  
## <a name="members"></a><span data-ttu-id="d6415-105">成员</span><span class="sxs-lookup"><span data-stu-id="d6415-105">Members</span></span>  
  
|<span data-ttu-id="d6415-106">成员</span><span class="sxs-lookup"><span data-stu-id="d6415-106">Member</span></span>|<span data-ttu-id="d6415-107">说明</span><span class="sxs-lookup"><span data-stu-id="d6415-107">Description</span></span>|  
|------------|-----------------|  
|`LTraceLevel0`|<span data-ttu-id="d6415-108">消息为跟踪级别0。</span><span class="sxs-lookup"><span data-stu-id="d6415-108">The message is a trace level 0.</span></span>|  
|`LTraceLevel1`|<span data-ttu-id="d6415-109">消息为跟踪级别1。</span><span class="sxs-lookup"><span data-stu-id="d6415-109">The message is a trace level 1.</span></span>|  
|`LTraceLevel2`|<span data-ttu-id="d6415-110">消息为跟踪级别2。</span><span class="sxs-lookup"><span data-stu-id="d6415-110">The message is a trace level 2.</span></span>|  
|`LTraceLevel3`|<span data-ttu-id="d6415-111">消息为跟踪级别3。</span><span class="sxs-lookup"><span data-stu-id="d6415-111">The message is a trace level 3.</span></span>|  
|`LTraceLevel4`|<span data-ttu-id="d6415-112">消息为跟踪级别4。</span><span class="sxs-lookup"><span data-stu-id="d6415-112">The message is a trace level 4.</span></span>|  
|`LStatusLevel0`|<span data-ttu-id="d6415-113">消息为状态级别0。</span><span class="sxs-lookup"><span data-stu-id="d6415-113">The message is a status level 0.</span></span>|  
|`LStatusLevel1`|<span data-ttu-id="d6415-114">消息为状态级别1。</span><span class="sxs-lookup"><span data-stu-id="d6415-114">The message is a status level 1.</span></span>|  
|`LStatusLevel2`|<span data-ttu-id="d6415-115">消息为状态等级2。</span><span class="sxs-lookup"><span data-stu-id="d6415-115">The message is a status level 2.</span></span>|  
|`LStatusLevel3`|<span data-ttu-id="d6415-116">消息为状态级别3。</span><span class="sxs-lookup"><span data-stu-id="d6415-116">The message is a status level 3.</span></span>|  
|`LStatusLevel4`|<span data-ttu-id="d6415-117">消息为状态等级4。</span><span class="sxs-lookup"><span data-stu-id="d6415-117">The message is a status level 4.</span></span>|  
|`LWarningLevel`|<span data-ttu-id="d6415-118">消息为警告等级。</span><span class="sxs-lookup"><span data-stu-id="d6415-118">The message is a warning level.</span></span>|  
|`LErrorLevel`|<span data-ttu-id="d6415-119">消息为错误级别。</span><span class="sxs-lookup"><span data-stu-id="d6415-119">The message is an error level.</span></span>|  
|`LPanicLevel`|<span data-ttu-id="d6415-120">消息是一个紧急级别。</span><span class="sxs-lookup"><span data-stu-id="d6415-120">The message is a panic level.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6415-121">注解</span><span class="sxs-lookup"><span data-stu-id="d6415-121">Remarks</span></span>  

 <span data-ttu-id="d6415-122">公共语言运行时 (CLR) 调用 [ICorDebugManagedCallback：： LogMessage](icordebugmanagedcallback-logmessage-method.md) 方法来通知调试器，托管线程已记录事件。</span><span class="sxs-lookup"><span data-stu-id="d6415-122">The common language runtime (CLR) calls the [ICorDebugManagedCallback::LogMessage](icordebugmanagedcallback-logmessage-method.md) method to notify the debugger that a managed thread has logged an event.</span></span> <span data-ttu-id="d6415-123">CLR 传递枚举的值 `LoggingLevelEnum` ，以指示托管线程写入事件日志的消息的严重性级别。</span><span class="sxs-lookup"><span data-stu-id="d6415-123">The CLR passes a value of the `LoggingLevelEnum` enumeration to indicate the severity level of the message that the managed thread wrote to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6415-124">要求</span><span class="sxs-lookup"><span data-stu-id="d6415-124">Requirements</span></span>  

 <span data-ttu-id="d6415-125">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d6415-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6415-126">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6415-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6415-127">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6415-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6415-128">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6415-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6415-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6415-129">See also</span></span>

- <xref:System.Diagnostics.EventLog>
- [<span data-ttu-id="d6415-130">调试枚举</span><span class="sxs-lookup"><span data-stu-id="d6415-130">Debugging Enumerations</span></span>](debugging-enumerations.md)
