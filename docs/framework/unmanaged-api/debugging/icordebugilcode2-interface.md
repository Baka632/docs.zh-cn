---
title: ICorDebugILCode2 接口
ms.date: 03/30/2017
api_name:
- ICorDebugILCode2
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: f9dc2afd-df8a-464d-bdbf-5af0a1d4bf85
topic_type:
- apiref
ms.openlocfilehash: b9289b5afc88c926ce585a4e620364cf2dc979d5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703325"
---
# <a name="icordebugilcode2-interface"></a><span data-ttu-id="61449-102">ICorDebugILCode2 接口</span><span class="sxs-lookup"><span data-stu-id="61449-102">ICorDebugILCode2 Interface</span></span>

<span data-ttu-id="61449-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="61449-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="61449-104">对 [ICorDebugILCode](icordebugilcode-interface.md) 接口进行逻辑扩展，以提供返回函数的局部变量签名的标记的方法，并将探查器检测到的中间语言 (il) 偏移量映射到原始方法的 il 偏移量。</span><span class="sxs-lookup"><span data-stu-id="61449-104">Logically extends the [ICorDebugILCode](icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="61449-105">方法</span><span class="sxs-lookup"><span data-stu-id="61449-105">Methods</span></span>  
  
|<span data-ttu-id="61449-106">方法</span><span class="sxs-lookup"><span data-stu-id="61449-106">Method</span></span>|<span data-ttu-id="61449-107">说明</span><span class="sxs-lookup"><span data-stu-id="61449-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="61449-108">GetInstrumentedILMap 方法</span><span class="sxs-lookup"><span data-stu-id="61449-108">GetInstrumentedILMap Method</span></span>](icordebugilcode2-getinstrumentedilmap-method.md)|<span data-ttu-id="61449-109">返回从探查器检测到的 IL 偏移量到此实例的原始方法的 IL 偏移量的映射。</span><span class="sxs-lookup"><span data-stu-id="61449-109">Returns a map from profiler instrumented IL offsets to original method IL offsets for this instance.</span></span>|  
|[<span data-ttu-id="61449-110">GetLocalVarSigToken 方法</span><span class="sxs-lookup"><span data-stu-id="61449-110">GetLocalVarSigToken Method</span></span>](icordebugilcode2-getlocalvarsigtoken-method.md)|<span data-ttu-id="61449-111">获取元数据标记，用于由此实例表示的函数的局部变量签名。</span><span class="sxs-lookup"><span data-stu-id="61449-111">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="61449-112">要求</span><span class="sxs-lookup"><span data-stu-id="61449-112">Requirements</span></span>  

 <span data-ttu-id="61449-113">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="61449-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61449-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="61449-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="61449-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61449-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61449-116">**.NET Framework 版本：**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61449-116">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61449-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61449-117">See also</span></span>

- [<span data-ttu-id="61449-118">ICorDebugILCode 接口</span><span class="sxs-lookup"><span data-stu-id="61449-118">ICorDebugILCode Interface</span></span>](icordebugilcode-interface.md)
- [<span data-ttu-id="61449-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="61449-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="61449-120">调试</span><span class="sxs-lookup"><span data-stu-id="61449-120">Debugging</span></span>](index.md)
