---
title: EMemoryAvailable 枚举
ms.date: 03/30/2017
api_name:
- EMemoryAvailable
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EMemoryAvailable
helpviewer_keywords:
- EMemoryAvailable enumeration [.NET Framework hosting]
ms.assetid: 38e72a06-dbed-473b-a59b-7e0b3ea4f2af
topic_type:
- apiref
ms.openlocfilehash: 6a8765bfd62a2e6543661804ab8d009ce19f8813
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724307"
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="3ae75-102">EMemoryAvailable 枚举</span><span class="sxs-lookup"><span data-stu-id="3ae75-102">EMemoryAvailable Enumeration</span></span>

<span data-ttu-id="3ae75-103">包含指示计算机上的可用物理内存量的值。</span><span class="sxs-lookup"><span data-stu-id="3ae75-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="3ae75-104">这些值从逻辑上映射到 Windows API 中从函数返回的高和低内存的事件 `CreateMemoryResourceNotification` 。</span><span class="sxs-lookup"><span data-stu-id="3ae75-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Windows API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ae75-105">语法</span><span class="sxs-lookup"><span data-stu-id="3ae75-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="3ae75-106">成员</span><span class="sxs-lookup"><span data-stu-id="3ae75-106">Members</span></span>  
  
|<span data-ttu-id="3ae75-107">成员</span><span class="sxs-lookup"><span data-stu-id="3ae75-107">Member</span></span>|<span data-ttu-id="3ae75-108">说明</span><span class="sxs-lookup"><span data-stu-id="3ae75-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="3ae75-109">有大量物理内存可用。</span><span class="sxs-lookup"><span data-stu-id="3ae75-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="3ae75-110">物理内存非常少。</span><span class="sxs-lookup"><span data-stu-id="3ae75-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="3ae75-111">可用物理内存为中性。</span><span class="sxs-lookup"><span data-stu-id="3ae75-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ae75-112">注解</span><span class="sxs-lookup"><span data-stu-id="3ae75-112">Remarks</span></span>  

 <span data-ttu-id="3ae75-113">使用 [ICLRMemoryNotificationCallback：： OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md) 方法调用，此值由主机传递到公共语言运行时 (CLR) 。</span><span class="sxs-lookup"><span data-stu-id="3ae75-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ae75-114">要求</span><span class="sxs-lookup"><span data-stu-id="3ae75-114">Requirements</span></span>  

 <span data-ttu-id="3ae75-115">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3ae75-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ae75-116">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3ae75-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3ae75-117">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3ae75-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3ae75-118">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ae75-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ae75-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3ae75-119">See also</span></span>

- [<span data-ttu-id="3ae75-120">承载枚举</span><span class="sxs-lookup"><span data-stu-id="3ae75-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
