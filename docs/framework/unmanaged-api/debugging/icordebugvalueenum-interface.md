---
title: ICorDebugValueEnum 接口
ms.date: 03/30/2017
api_name:
- ICorDebugValueEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueEnum
helpviewer_keywords:
- ICorDebugValueEnum interface [.NET Framework debugging]
ms.assetid: 88989482-a09f-4bd0-9adb-16f47b0291fd
topic_type:
- apiref
ms.openlocfilehash: e3934cbce76df3997fa07d8fa3a99bd8ddab09a2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684338"
---
# <a name="icordebugvalueenum-interface"></a><span data-ttu-id="7f99b-102">ICorDebugValueEnum 接口</span><span class="sxs-lookup"><span data-stu-id="7f99b-102">ICorDebugValueEnum Interface</span></span>

<span data-ttu-id="7f99b-103">实现 "ICorDebugEnum" 方法并枚举 "ICorDebugValue" 数组。</span><span class="sxs-lookup"><span data-stu-id="7f99b-103">Implements "ICorDebugEnum" methods and enumerates "ICorDebugValue" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7f99b-104">方法</span><span class="sxs-lookup"><span data-stu-id="7f99b-104">Methods</span></span>  
  
|<span data-ttu-id="7f99b-105">方法</span><span class="sxs-lookup"><span data-stu-id="7f99b-105">Method</span></span>|<span data-ttu-id="7f99b-106">说明</span><span class="sxs-lookup"><span data-stu-id="7f99b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7f99b-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="7f99b-107">Next Method</span></span>](icordebugvalueenum-next-method.md)|<span data-ttu-id="7f99b-108">`ICorDebugValue`从当前位置开始，从枚举中获取指定数目的实例。</span><span class="sxs-lookup"><span data-stu-id="7f99b-108">Gets the specified number of `ICorDebugValue` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f99b-109">注解</span><span class="sxs-lookup"><span data-stu-id="7f99b-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7f99b-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="7f99b-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f99b-111">要求</span><span class="sxs-lookup"><span data-stu-id="7f99b-111">Requirements</span></span>  

 <span data-ttu-id="7f99b-112">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7f99b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f99b-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7f99b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7f99b-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f99b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7f99b-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f99b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f99b-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7f99b-116">See also</span></span>

- [<span data-ttu-id="7f99b-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="7f99b-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
