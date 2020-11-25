---
title: ICorDebugModuleBreakpoint 接口
ms.date: 03/30/2017
api_name:
- ICorDebugModuleBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleBreakpoint
helpviewer_keywords:
- ICorDebugModuleBreakpoint interface [.NET Framework debugging]
ms.assetid: 34667162-f314-475f-ae1b-ce9cb0fcbb83
topic_type:
- apiref
ms.openlocfilehash: 14f2b6822744070e649cf9a6722272992c0bf1c8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709513"
---
# <a name="icordebugmodulebreakpoint-interface"></a><span data-ttu-id="50cfa-102">ICorDebugModuleBreakpoint 接口</span><span class="sxs-lookup"><span data-stu-id="50cfa-102">ICorDebugModuleBreakpoint Interface</span></span>

<span data-ttu-id="50cfa-103">提供对特定模块的访问权限。</span><span class="sxs-lookup"><span data-stu-id="50cfa-103">Provides access to specific modules.</span></span> <span data-ttu-id="50cfa-104">此接口是 ICorDebugBreakpoint 接口的子类。</span><span class="sxs-lookup"><span data-stu-id="50cfa-104">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="50cfa-105">方法</span><span class="sxs-lookup"><span data-stu-id="50cfa-105">Methods</span></span>  
  
|<span data-ttu-id="50cfa-106">方法</span><span class="sxs-lookup"><span data-stu-id="50cfa-106">Method</span></span>|<span data-ttu-id="50cfa-107">说明</span><span class="sxs-lookup"><span data-stu-id="50cfa-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="50cfa-108">GetModule 方法</span><span class="sxs-lookup"><span data-stu-id="50cfa-108">GetModule Method</span></span>](icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="50cfa-109">获取一个指向 ICorDebugModule 的接口指针，该指针引用设置此断点的模块。</span><span class="sxs-lookup"><span data-stu-id="50cfa-109">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50cfa-110">注解</span><span class="sxs-lookup"><span data-stu-id="50cfa-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="50cfa-111">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="50cfa-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50cfa-112">要求</span><span class="sxs-lookup"><span data-stu-id="50cfa-112">Requirements</span></span>  

 <span data-ttu-id="50cfa-113">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="50cfa-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50cfa-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="50cfa-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50cfa-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50cfa-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50cfa-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50cfa-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50cfa-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50cfa-117">See also</span></span>

- [<span data-ttu-id="50cfa-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="50cfa-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
