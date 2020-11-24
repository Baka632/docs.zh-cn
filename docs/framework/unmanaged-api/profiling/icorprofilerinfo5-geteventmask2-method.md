---
title: ICorProfilerInfo5::GetEventMask2 方法
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerInfo5.GetEventMask2
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: f854b68f-009c-4ffb-89cd-ca874d1c0fb7
topic_type:
- apiref
ms.openlocfilehash: 81509db178b0ab1a524dcc4b00f39264e87a220d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682778"
---
# <a name="icorprofilerinfo5geteventmask2-method"></a><span data-ttu-id="e6d38-102">ICorProfilerInfo5::GetEventMask2 方法</span><span class="sxs-lookup"><span data-stu-id="e6d38-102">ICorProfilerInfo5::GetEventMask2 Method</span></span>

<span data-ttu-id="e6d38-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="e6d38-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="e6d38-104">获取探查器要从公共语言运行时 (CLR) 中接收通知的当前事件类别。</span><span class="sxs-lookup"><span data-stu-id="e6d38-104">Gets the current event categories for which the profiler wants to receive notifications from the common language runtime (CLR).</span></span>  <span data-ttu-id="e6d38-105">它提供 [ICorProfilerInfo：： GetEventMask](icorprofilerinfo-geteventmask-method.md) 方法未提供的功能。</span><span class="sxs-lookup"><span data-stu-id="e6d38-105">It provides functionality not provided by the [ICorProfilerInfo::GetEventMask](icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6d38-106">语法</span><span class="sxs-lookup"><span data-stu-id="e6d38-106">Syntax</span></span>  
  
```cpp
HRESULT GetEventMask2(  
        [out] DWORD* pdwEventsLow,  
        [out] DWORD* pdwEventsHigh  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6d38-107">参数</span><span class="sxs-lookup"><span data-stu-id="e6d38-107">Parameters</span></span>  

 `pdwEventsLow`  
 <span data-ttu-id="e6d38-108">[out] 一个指向指定事件类别的 4 字节值的指针。</span><span class="sxs-lookup"><span data-stu-id="e6d38-108">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="e6d38-109">每个位都可控制不同的功能、行为或事件类型。</span><span class="sxs-lookup"><span data-stu-id="e6d38-109">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="e6d38-110">[COR_PRF_MONITOR](cor-prf-monitor-enumeration.md)枚举中描述了这些位。</span><span class="sxs-lookup"><span data-stu-id="e6d38-110">The bits are described in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `pdwEventsHigh`  
 <span data-ttu-id="e6d38-111">[out] 一个指向指定事件类别的 4 字节值的指针。</span><span class="sxs-lookup"><span data-stu-id="e6d38-111">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="e6d38-112">每个位都可控制不同的功能、行为或事件类型。</span><span class="sxs-lookup"><span data-stu-id="e6d38-112">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="e6d38-113">[COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md)枚举中描述了这些位。</span><span class="sxs-lookup"><span data-stu-id="e6d38-113">The bits are described in the [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6d38-114">注解</span><span class="sxs-lookup"><span data-stu-id="e6d38-114">Remarks</span></span>  

 <span data-ttu-id="e6d38-115">`GetEventMask2` 方法用于确定探查器已订阅了哪些回调。</span><span class="sxs-lookup"><span data-stu-id="e6d38-115">The `GetEventMask2` method is used to determine which callbacks the profiler has subscribed to.</span></span> <span data-ttu-id="e6d38-116">通常，您 `pdwEventsLow` 需要对和 `pdwEventsHigh` 值以及要设置的任何新位执行逻辑 "或"，然后调用 [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="e6d38-116">Typically, you perform a logical OR of the `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
 <span data-ttu-id="e6d38-117">此方法是 [GetEventMask](icorprofilerinfo-geteventmask-method.md) 方法的建议替代方法。</span><span class="sxs-lookup"><span data-stu-id="e6d38-117">This method is the recommended alternative to the [GetEventMask](icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6d38-118">要求</span><span class="sxs-lookup"><span data-stu-id="e6d38-118">Requirements</span></span>  

 <span data-ttu-id="e6d38-119">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e6d38-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6d38-120">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e6d38-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e6d38-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6d38-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6d38-122">**.NET Framework 版本：**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6d38-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6d38-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e6d38-123">See also</span></span>

- [<span data-ttu-id="e6d38-124">ICorProfilerInfo5 接口</span><span class="sxs-lookup"><span data-stu-id="e6d38-124">ICorProfilerInfo5 Interface</span></span>](icorprofilerinfo5-interface.md)
- [<span data-ttu-id="e6d38-125">SetEventMask2 方法</span><span class="sxs-lookup"><span data-stu-id="e6d38-125">SetEventMask2 Method</span></span>](icorprofilerinfo5-seteventmask2-method.md)
