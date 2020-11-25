---
title: ICorDebugHeapValue3::GetMonitorEventWaitList 方法
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3.GetMonitorEventWaitList
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3::GetMonitorEventWaitList
helpviewer_keywords:
- ICorDebugHeapValue3::GetMonitorEventWaitList method [.NET Framework debugging]
- GetMonitorEventWaitList method [.NET Framework debugging]
ms.assetid: 035a9035-ac66-4953-b48a-99652b42b7fe
topic_type:
- apiref
ms.openlocfilehash: 21bf0122039a720ff8a1d38d62e77c2560dcc435
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726530"
---
# <a name="icordebugheapvalue3getmonitoreventwaitlist-method"></a><span data-ttu-id="a75da-102">ICorDebugHeapValue3::GetMonitorEventWaitList 方法</span><span class="sxs-lookup"><span data-stu-id="a75da-102">ICorDebugHeapValue3::GetMonitorEventWaitList Method</span></span>

<span data-ttu-id="a75da-103">提供在与监视器锁关联的事件上排队的线程的排序列表。</span><span class="sxs-lookup"><span data-stu-id="a75da-103">Provides an ordered list of threads that are queued on the event that is associated with a monitor lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a75da-104">语法</span><span class="sxs-lookup"><span data-stu-id="a75da-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMonitorEventWaitList (  
    [out] ICorDebugThreadEnum **ppThreadEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a75da-105">参数</span><span class="sxs-lookup"><span data-stu-id="a75da-105">Parameters</span></span>  

 `ppThreadEnum`  
 <span data-ttu-id="a75da-106">弄提供线程有序列表的 ICorDebugThreadEnum 枚举器。</span><span class="sxs-lookup"><span data-stu-id="a75da-106">[out] The ICorDebugThreadEnum enumerator that provides the ordered list of threads.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a75da-107">返回值</span><span class="sxs-lookup"><span data-stu-id="a75da-107">Return Value</span></span>  

 <span data-ttu-id="a75da-108">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="a75da-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a75da-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a75da-109">HRESULT</span></span>|<span data-ttu-id="a75da-110">说明</span><span class="sxs-lookup"><span data-stu-id="a75da-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a75da-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a75da-111">S_OK</span></span>|<span data-ttu-id="a75da-112">该列表不为空。</span><span class="sxs-lookup"><span data-stu-id="a75da-112">The list is not empty.</span></span>|  
|<span data-ttu-id="a75da-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="a75da-113">S_FALSE</span></span>|<span data-ttu-id="a75da-114">列表为空。</span><span class="sxs-lookup"><span data-stu-id="a75da-114">The list is empty.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="a75da-115">例外</span><span class="sxs-lookup"><span data-stu-id="a75da-115">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a75da-116">备注</span><span class="sxs-lookup"><span data-stu-id="a75da-116">Remarks</span></span>  

 <span data-ttu-id="a75da-117">列表中的第一个线程是下一次调用时释放的第一个线程 <xref:System.Threading.Monitor.Pulse%28System.Object%29?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="a75da-117">The first thread in the list is the first thread that is released by the next call to <xref:System.Threading.Monitor.Pulse%28System.Object%29?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a75da-118">此列表中的下一个线程将在以下调用上释放，依此类推。</span><span class="sxs-lookup"><span data-stu-id="a75da-118">The next thread in the list is released on the following call, and so on.</span></span>  
  
 <span data-ttu-id="a75da-119">如果列表不为空，则此方法返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="a75da-119">If the list is not empty, this method returns S_OK.</span></span> <span data-ttu-id="a75da-120">如果列表为空，则该方法返回 S_FALSE;在这种情况下，枚举仍有效，但它是空的。</span><span class="sxs-lookup"><span data-stu-id="a75da-120">If the list is empty, the method returns S_FALSE; in this case, the enumeration is still valid, although it is empty.</span></span>  
  
 <span data-ttu-id="a75da-121">在任一情况下，枚举接口仅在当前已同步状态的持续时间内可用。</span><span class="sxs-lookup"><span data-stu-id="a75da-121">In either case, the enumeration interface is usable only for the duration of the current synchronized state.</span></span> <span data-ttu-id="a75da-122">但是，在线程退出之前，从它分配的线程的接口是有效的。</span><span class="sxs-lookup"><span data-stu-id="a75da-122">However, the thread's interfaces dispensed from it are valid until the thread exits.</span></span>  
  
 <span data-ttu-id="a75da-123">如果不是 `ppThreadEnum` 有效的指针，则结果是不确定的。</span><span class="sxs-lookup"><span data-stu-id="a75da-123">If `ppThreadEnum` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="a75da-124">如果发生错误，导致无法确定线程（如果有）正在等待监视器的线程，则该方法将返回一个指示失败的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="a75da-124">If an error occurs such that it cannot be determined which, if any, threads are waiting for the monitor, the method returns an HRESULT that indicates failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a75da-125">要求</span><span class="sxs-lookup"><span data-stu-id="a75da-125">Requirements</span></span>  

 <span data-ttu-id="a75da-126">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a75da-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a75da-127">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a75da-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a75da-128">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a75da-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a75da-129">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a75da-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a75da-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a75da-130">See also</span></span>

- [<span data-ttu-id="a75da-131">调试接口</span><span class="sxs-lookup"><span data-stu-id="a75da-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="a75da-132">调试</span><span class="sxs-lookup"><span data-stu-id="a75da-132">Debugging</span></span>](index.md)
