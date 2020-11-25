---
title: ICorDebugNativeFrame2 接口
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2
helpviewer_keywords:
- ICorDebugNativeFrame2 interface [.NET Framework debugging]
ms.assetid: 52a80838-af36-4399-bc97-d8a4c6d76df2
topic_type:
- apiref
ms.openlocfilehash: ddf5af0bc0a5e5e21d837d8b2f3f76185ed7e2b1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724710"
---
# <a name="icordebugnativeframe2-interface"></a><span data-ttu-id="62162-102">ICorDebugNativeFrame2 接口</span><span class="sxs-lookup"><span data-stu-id="62162-102">ICorDebugNativeFrame2 Interface</span></span>

<span data-ttu-id="62162-103">提供用于测试子帧与父帧关系的方法。</span><span class="sxs-lookup"><span data-stu-id="62162-103">Provides methods that test for child and parent frame relationships.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="62162-104">方法</span><span class="sxs-lookup"><span data-stu-id="62162-104">Methods</span></span>  
  
|<span data-ttu-id="62162-105">方法</span><span class="sxs-lookup"><span data-stu-id="62162-105">Method</span></span>|<span data-ttu-id="62162-106">说明</span><span class="sxs-lookup"><span data-stu-id="62162-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="62162-107">IsChild 方法</span><span class="sxs-lookup"><span data-stu-id="62162-107">IsChild Method</span></span>](icordebugnativeframe2-ischild-method.md)|<span data-ttu-id="62162-108">确定当前帧是否为子框架。</span><span class="sxs-lookup"><span data-stu-id="62162-108">Determines whether the current frame is a child frame.</span></span>|  
|[<span data-ttu-id="62162-109">IsMatchingParentFrame 方法</span><span class="sxs-lookup"><span data-stu-id="62162-109">IsMatchingParentFrame Method</span></span>](icordebugnativeframe2-ismatchingparentframe-method.md)|<span data-ttu-id="62162-110">确定指定的帧是否为当前帧的父级。</span><span class="sxs-lookup"><span data-stu-id="62162-110">Determines whether the specified frame is the parent of the current frame.</span></span>|  
|[<span data-ttu-id="62162-111">GetStackParameterSize 方法</span><span class="sxs-lookup"><span data-stu-id="62162-111">GetStackParameterSize Method</span></span>](icordebugnativeframe2-getstackparametersize-method.md)|<span data-ttu-id="62162-112">返回 x86 操作系统上堆栈上的参数的累积大小。</span><span class="sxs-lookup"><span data-stu-id="62162-112">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62162-113">注解</span><span class="sxs-lookup"><span data-stu-id="62162-113">Remarks</span></span>  

 <span data-ttu-id="62162-114">此接口以逻辑方式扩展了 "ICorDebugNativeFrame" 接口。</span><span class="sxs-lookup"><span data-stu-id="62162-114">This interface logically extends the "ICorDebugNativeFrame" interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="62162-115">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="62162-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62162-116">要求</span><span class="sxs-lookup"><span data-stu-id="62162-116">Requirements</span></span>  

 <span data-ttu-id="62162-117">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="62162-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62162-118">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="62162-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="62162-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62162-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62162-120">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62162-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62162-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="62162-121">See also</span></span>

- [<span data-ttu-id="62162-122">调试接口</span><span class="sxs-lookup"><span data-stu-id="62162-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="62162-123">调试</span><span class="sxs-lookup"><span data-stu-id="62162-123">Debugging</span></span>](index.md)
