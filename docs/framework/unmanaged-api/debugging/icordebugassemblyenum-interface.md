---
title: ICorDebugAssemblyEnum 接口
ms.date: 03/30/2017
api_name:
- ICorDebugAssemblyEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssemblyEnum
helpviewer_keywords:
- ICorDebugAssemblyEnum interface [.NET Framework debugging]
ms.assetid: 891ceb43-5161-421e-a0bf-299962fd7efd
topic_type:
- apiref
ms.openlocfilehash: dea5c0fd5d4ed1f830d9e75097d49c544dac2e57
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719237"
---
# <a name="icordebugassemblyenum-interface"></a><span data-ttu-id="831bc-102">ICorDebugAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="831bc-102">ICorDebugAssemblyEnum Interface</span></span>

<span data-ttu-id="831bc-103">实现 ICorDebugEnum 方法并枚举 ICorDebugAssembly 数组。</span><span class="sxs-lookup"><span data-stu-id="831bc-103">Implements ICorDebugEnum methods and enumerates ICorDebugAssembly arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="831bc-104">方法</span><span class="sxs-lookup"><span data-stu-id="831bc-104">Methods</span></span>  
  
|<span data-ttu-id="831bc-105">方法</span><span class="sxs-lookup"><span data-stu-id="831bc-105">Method</span></span>|<span data-ttu-id="831bc-106">说明</span><span class="sxs-lookup"><span data-stu-id="831bc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="831bc-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="831bc-107">Next Method</span></span>](icordebugassemblyenum-next-method.md)|<span data-ttu-id="831bc-108">`ICorDebugAssembly`从当前位置开始，获取枚举中指定数量的实例。</span><span class="sxs-lookup"><span data-stu-id="831bc-108">Gets the specified number of `ICorDebugAssembly` instances in the enumeration, starting from the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="831bc-109">注解</span><span class="sxs-lookup"><span data-stu-id="831bc-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="831bc-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="831bc-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="831bc-111">要求</span><span class="sxs-lookup"><span data-stu-id="831bc-111">Requirements</span></span>  

 <span data-ttu-id="831bc-112">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="831bc-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="831bc-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="831bc-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="831bc-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="831bc-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="831bc-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="831bc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="831bc-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="831bc-116">See also</span></span>

- [<span data-ttu-id="831bc-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="831bc-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
