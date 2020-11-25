---
title: ICorDebugModuleDebugEvent 接口
ms.date: 03/30/2017
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
ms.openlocfilehash: 62d419a193cff000e1dd748d0cbb6b61775a81aa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695811"
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="81f16-102">ICorDebugModuleDebugEvent 接口</span><span class="sxs-lookup"><span data-stu-id="81f16-102">ICorDebugModuleDebugEvent Interface</span></span>

<span data-ttu-id="81f16-103">扩展 [ICorDebugDebugEvent](icordebugdebugevent-interface.md) 接口以支持模块级事件。</span><span class="sxs-lookup"><span data-stu-id="81f16-103">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="81f16-104">方法</span><span class="sxs-lookup"><span data-stu-id="81f16-104">Methods</span></span>  
  
|<span data-ttu-id="81f16-105">方法</span><span class="sxs-lookup"><span data-stu-id="81f16-105">Method</span></span>|<span data-ttu-id="81f16-106">说明</span><span class="sxs-lookup"><span data-stu-id="81f16-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="81f16-107">GetModule 方法</span><span class="sxs-lookup"><span data-stu-id="81f16-107">GetModule Method</span></span>](icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="81f16-108">获取刚加载或卸载的合并模块。</span><span class="sxs-lookup"><span data-stu-id="81f16-108">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81f16-109">注解</span><span class="sxs-lookup"><span data-stu-id="81f16-109">Remarks</span></span>  

 <span data-ttu-id="81f16-110">[MODULE_LOADED](cordebugdebugeventkind-enumeration.md)和[MODULE_UNLOADED](cordebugdebugeventkind-enumeration.md)事件类型实现此接口。</span><span class="sxs-lookup"><span data-stu-id="81f16-110">The [MODULE_LOADED](cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="81f16-111">此接口仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="81f16-111">The interface is available with .NET Native only.</span></span> <span data-ttu-id="81f16-112">尝试调用 `QueryInterface` 来检索接口指针会为 .NET Native 外部的 ICorDebug 方案返回 `E_NOINTERFACE`。</span><span class="sxs-lookup"><span data-stu-id="81f16-112">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81f16-113">要求</span><span class="sxs-lookup"><span data-stu-id="81f16-113">Requirements</span></span>  

 <span data-ttu-id="81f16-114">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="81f16-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81f16-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="81f16-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="81f16-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81f16-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81f16-117">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81f16-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81f16-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81f16-118">See also</span></span>

- [<span data-ttu-id="81f16-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="81f16-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="81f16-120">调试</span><span class="sxs-lookup"><span data-stu-id="81f16-120">Debugging</span></span>](index.md)
