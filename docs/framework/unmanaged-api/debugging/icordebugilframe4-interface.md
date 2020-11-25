---
title: ICorDebugILFrame4 接口
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame4
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 1e739183-3e05-49e5-846f-4075256e41de
topic_type:
- apiref
ms.openlocfilehash: 7d0f3661c7941c5f2f85fa5b0b67af213de75f05
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724944"
---
# <a name="icordebugilframe4-interface"></a><span data-ttu-id="fb2bf-102">ICorDebugILFrame4 接口</span><span class="sxs-lookup"><span data-stu-id="fb2bf-102">ICorDebugILFrame4 Interface</span></span>

<span data-ttu-id="fb2bf-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="fb2bf-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="fb2bf-104">提供使你能够访问中间语言 (IL) 代码的堆栈帧中的局部变量和代码的方法。</span><span class="sxs-lookup"><span data-stu-id="fb2bf-104">Provides methods that allow you to access the local variables and code in a stack frame of intermediate language (IL) code.</span></span> <span data-ttu-id="fb2bf-105">一个用于指定调试器是否可以访问在探查器 ReJIT 检测中添加的变量和代码的参数。</span><span class="sxs-lookup"><span data-stu-id="fb2bf-105">A parameter specifies whether the debugger has access to variables and code added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fb2bf-106">方法</span><span class="sxs-lookup"><span data-stu-id="fb2bf-106">Methods</span></span>  
  
|<span data-ttu-id="fb2bf-107">方法</span><span class="sxs-lookup"><span data-stu-id="fb2bf-107">Method</span></span>|<span data-ttu-id="fb2bf-108">说明</span><span class="sxs-lookup"><span data-stu-id="fb2bf-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fb2bf-109">EnumerateLocalVariablesEx 方法</span><span class="sxs-lookup"><span data-stu-id="fb2bf-109">EnumerateLocalVariablesEx Method</span></span>](icordebugilframe4-enumeratelocalvariablesex-method.md)|<span data-ttu-id="fb2bf-110">返回在当前帧中可用的局部变量的列表。</span><span class="sxs-lookup"><span data-stu-id="fb2bf-110">Returns a list of the local variables available in the current frame.</span></span>|  
|[<span data-ttu-id="fb2bf-111">GetCodeEx 方法</span><span class="sxs-lookup"><span data-stu-id="fb2bf-111">GetCodeEx Method</span></span>](icordebugilframe4-getcodeex-method.md)|<span data-ttu-id="fb2bf-112">返回此堆栈帧正在运行的代码。</span><span class="sxs-lookup"><span data-stu-id="fb2bf-112">Returns the code that this stack frame is running.</span></span>|  
|[<span data-ttu-id="fb2bf-113">GetLocalVariableEx 方法</span><span class="sxs-lookup"><span data-stu-id="fb2bf-113">GetLocalVariableEx Method</span></span>](icordebugilframe4-getlocalvariableex-method.md)|<span data-ttu-id="fb2bf-114">返回 IL 帧中的局部变量的值。</span><span class="sxs-lookup"><span data-stu-id="fb2bf-114">Returns the value of a local variable in the IL frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fb2bf-115">注解</span><span class="sxs-lookup"><span data-stu-id="fb2bf-115">Remarks</span></span>  

 <span data-ttu-id="fb2bf-116">除了 [EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md)、 [GetCode](icordebugframe-getcode-method.md)和 [GetLocalVariable](icordebugilframe-getlocalvariable-method.md) 方法提供的功能外，这些方法还提供功能。</span><span class="sxs-lookup"><span data-stu-id="fb2bf-116">These methods offer functionality in addition to that provided by the [EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md), [GetCode](icordebugframe-getcode-method.md), and [GetLocalVariable](icordebugilframe-getlocalvariable-method.md) methods.</span></span> <span data-ttu-id="fb2bf-117">每个方法都包含一个 `flags` 参数，该参数可指定探查器的 ReJIT 请求定义的附加局部变量或代码是否可见。</span><span class="sxs-lookup"><span data-stu-id="fb2bf-117">Each method includes a `flags` parameter that specifies whether additional local variables or code defined by a profiler's ReJIT request are visible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb2bf-118">要求</span><span class="sxs-lookup"><span data-stu-id="fb2bf-118">Requirements</span></span>  

 <span data-ttu-id="fb2bf-119">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fb2bf-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb2bf-120">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fb2bf-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fb2bf-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb2bf-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb2bf-122">**.NET Framework 版本：**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb2bf-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb2bf-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb2bf-123">See also</span></span>

- [<span data-ttu-id="fb2bf-124">调试接口</span><span class="sxs-lookup"><span data-stu-id="fb2bf-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="fb2bf-125">调试</span><span class="sxs-lookup"><span data-stu-id="fb2bf-125">Debugging</span></span>](index.md)
