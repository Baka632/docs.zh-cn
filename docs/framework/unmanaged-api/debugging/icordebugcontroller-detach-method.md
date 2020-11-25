---
title: ICorDebugController::Detach 方法
ms.date: 03/30/2017
api_name:
- ICorDebugController.Detach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Detach
helpviewer_keywords:
- Detach method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Detach method [.NET Framework debugging]
ms.assetid: 06fae364-f2c6-4a50-aa7e-3da9f2684dc3
topic_type:
- apiref
ms.openlocfilehash: 55acb6e3ec60925cba3d8aa5328547c54f270356
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732666"
---
# <a name="icordebugcontrollerdetach-method"></a><span data-ttu-id="62d8f-102">ICorDebugController::Detach 方法</span><span class="sxs-lookup"><span data-stu-id="62d8f-102">ICorDebugController::Detach Method</span></span>

<span data-ttu-id="62d8f-103">将调试器与进程或应用程序域分离。</span><span class="sxs-lookup"><span data-stu-id="62d8f-103">Detaches the debugger from the process or application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62d8f-104">语法</span><span class="sxs-lookup"><span data-stu-id="62d8f-104">Syntax</span></span>  
  
```cpp  
HRESULT Detach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="62d8f-105">备注</span><span class="sxs-lookup"><span data-stu-id="62d8f-105">Remarks</span></span>  

 <span data-ttu-id="62d8f-106">进程或应用程序域将继续正常执行，但 "ICorDebugProcess" 或 "ICorDebugAppDomain" 对象不再有效，且不会发生进一步的回调。</span><span class="sxs-lookup"><span data-stu-id="62d8f-106">The process or application domain continues execution normally, but the "ICorDebugProcess" or "ICorDebugAppDomain" object is no longer valid and no further callbacks will occur.</span></span>  
  
 <span data-ttu-id="62d8f-107">在 .NET Framework 版本2.0 中，如果启用了非托管调试，则此方法将因操作系统限制而失败。</span><span class="sxs-lookup"><span data-stu-id="62d8f-107">In the .NET Framework version 2.0, if unmanaged debugging is enabled, this method will fail due to operating system limitations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62d8f-108">要求</span><span class="sxs-lookup"><span data-stu-id="62d8f-108">Requirements</span></span>  

 <span data-ttu-id="62d8f-109">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="62d8f-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62d8f-110">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="62d8f-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="62d8f-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62d8f-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62d8f-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62d8f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62d8f-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="62d8f-113">See also</span></span>
