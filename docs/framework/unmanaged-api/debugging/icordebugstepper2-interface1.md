---
title: ICorDebugStepper2 接口
ms.date: 03/30/2017
api_name:
- ICorDebugStepper2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper2
helpviewer_keywords:
- ICorDebugStepper2 interface [.NET Framework debugging]
ms.assetid: 7a191c2a-95ea-4d47-83b0-44de2b632d63
topic_type:
- apiref
ms.openlocfilehash: ecbedfbca37a3630fc6d40c173f8a6cd05b4d3fb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727635"
---
# <a name="icordebugstepper2-interface"></a><span data-ttu-id="4817e-102">ICorDebugStepper2 接口</span><span class="sxs-lookup"><span data-stu-id="4817e-102">ICorDebugStepper2 Interface</span></span>

<span data-ttu-id="4817e-103"> (JMC) 调试提供 "仅我的代码" 支持。</span><span class="sxs-lookup"><span data-stu-id="4817e-103">Provides support for just my code (JMC) debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4817e-104">方法</span><span class="sxs-lookup"><span data-stu-id="4817e-104">Methods</span></span>  
  
|<span data-ttu-id="4817e-105">方法</span><span class="sxs-lookup"><span data-stu-id="4817e-105">Method</span></span>|<span data-ttu-id="4817e-106">说明</span><span class="sxs-lookup"><span data-stu-id="4817e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4817e-107">SetJMC 方法</span><span class="sxs-lookup"><span data-stu-id="4817e-107">SetJMC Method</span></span>](icordebugstepper2-setjmc-method.md)|<span data-ttu-id="4817e-108">设置一个值，该值指定此 ICorDebugStepper 是否仅通过应用程序开发人员编写的代码执行步骤。</span><span class="sxs-lookup"><span data-stu-id="4817e-108">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4817e-109">注解</span><span class="sxs-lookup"><span data-stu-id="4817e-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4817e-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="4817e-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4817e-111">要求</span><span class="sxs-lookup"><span data-stu-id="4817e-111">Requirements</span></span>  

 <span data-ttu-id="4817e-112">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4817e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4817e-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4817e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4817e-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4817e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4817e-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4817e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4817e-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4817e-116">See also</span></span>

- [<span data-ttu-id="4817e-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="4817e-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
