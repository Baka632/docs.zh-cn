---
title: WAIT_OPTION 枚举
ms.date: 03/30/2017
api_name:
- WAIT_OPTION
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAIT_OPTION
helpviewer_keywords:
- WAIT_OPTION enumeration [.NET Framework hosting]
ms.assetid: 962fc293-8ded-4b3b-90ce-2c21a4f1b244
topic_type:
- apiref
ms.openlocfilehash: 056d41df328de5796eec9f04589205d18b408f1f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732796"
---
# <a name="wait_option-enumeration"></a><span data-ttu-id="1eda2-102">WAIT_OPTION 枚举</span><span class="sxs-lookup"><span data-stu-id="1eda2-102">WAIT_OPTION Enumeration</span></span>

<span data-ttu-id="1eda2-103">包含一些值，这些值指示当公共语言运行时 (CLR) 块发出请求的操作时，主机应执行的操作。</span><span class="sxs-lookup"><span data-stu-id="1eda2-103">Contains values that indicate the action a host should take if an operation requested by the common language runtime (CLR) blocks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1eda2-104">语法</span><span class="sxs-lookup"><span data-stu-id="1eda2-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a><span data-ttu-id="1eda2-105">成员</span><span class="sxs-lookup"><span data-stu-id="1eda2-105">Members</span></span>  
  
|<span data-ttu-id="1eda2-106">成员</span><span class="sxs-lookup"><span data-stu-id="1eda2-106">Member</span></span>|<span data-ttu-id="1eda2-107">说明</span><span class="sxs-lookup"><span data-stu-id="1eda2-107">Description</span></span>|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|<span data-ttu-id="1eda2-108">如果 CLR 调用 [IHostTask：： Alert](ihosttask-alert-method.md) 方法，则通知宿主应唤醒任务。</span><span class="sxs-lookup"><span data-stu-id="1eda2-108">Notifies the host that the task should be awakened if the CLR calls the [IHostTask::Alert](ihosttask-alert-method.md) method.</span></span>|  
|`WAIT_MSGPUMP`|<span data-ttu-id="1eda2-109">当线程被阻止时，通知宿主必须在当前 OS 线程上抽取消息。</span><span class="sxs-lookup"><span data-stu-id="1eda2-109">Notifies the host that it must pump messages on the current OS thread if the thread becomes blocked.</span></span> <span data-ttu-id="1eda2-110">运行时仅在线程上指定此值 <xref:System.Threading.ApartmentState.STA> 。</span><span class="sxs-lookup"><span data-stu-id="1eda2-110">The runtime specifies this value only on an <xref:System.Threading.ApartmentState.STA> thread.</span></span>|  
|`WAIT_NOTINDEADLOCK`|<span data-ttu-id="1eda2-111">向宿主通知指定的同步请求无法被宿主中断。</span><span class="sxs-lookup"><span data-stu-id="1eda2-111">Notifies the host that the specified synchronization request cannot be broken by a host.</span></span> <span data-ttu-id="1eda2-112">也就是说，主机无法返回 `HOST_E_DEADLOCK` 。</span><span class="sxs-lookup"><span data-stu-id="1eda2-112">That is, the host cannot return `HOST_E_DEADLOCK`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1eda2-113">注解</span><span class="sxs-lookup"><span data-stu-id="1eda2-113">Remarks</span></span>  

 <span data-ttu-id="1eda2-114">[IHostTaskManager：： Sleep](ihosttaskmanager-sleep-method.md)和[IHostTaskManager：： SwitchToTask](ihosttaskmanager-switchtotask-method.md)方法都采用此类型的参数。</span><span class="sxs-lookup"><span data-stu-id="1eda2-114">The [IHostTaskManager::Sleep](ihosttaskmanager-sleep-method.md) and [IHostTaskManager::SwitchToTask](ihosttaskmanager-switchtotask-method.md) methods both take a parameter of this type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1eda2-115">要求</span><span class="sxs-lookup"><span data-stu-id="1eda2-115">Requirements</span></span>  

 <span data-ttu-id="1eda2-116">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1eda2-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1eda2-117">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1eda2-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1eda2-118">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1eda2-118">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1eda2-119">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1eda2-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eda2-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1eda2-120">See also</span></span>

- [<span data-ttu-id="1eda2-121">承载枚举</span><span class="sxs-lookup"><span data-stu-id="1eda2-121">Hosting Enumerations</span></span>](hosting-enumerations.md)
