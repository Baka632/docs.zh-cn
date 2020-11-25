---
title: ICorDebugHeapValue3::GetThreadOwningMonitorLock 方法
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3.GetThreadOwningMonitorLock
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3::GetThreadOwningMonitorLock
helpviewer_keywords:
- GetThreadOwningMonitorLock method [.NET Framework debugging]
- ICorDebugHeapValue3::GetThreadOwningMonitorLock method [.NET Framework debugging]
ms.assetid: e06fc19d-2cf4-4cad-81a3-137a68af8969
topic_type:
- apiref
ms.openlocfilehash: fef0902aedbcd8572d2dc67fae7927f754af4489
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723306"
---
# <a name="icordebugheapvalue3getthreadowningmonitorlock-method"></a><span data-ttu-id="efecf-102">ICorDebugHeapValue3::GetThreadOwningMonitorLock 方法</span><span class="sxs-lookup"><span data-stu-id="efecf-102">ICorDebugHeapValue3::GetThreadOwningMonitorLock Method</span></span>

<span data-ttu-id="efecf-103">返回拥有此对象的监视器锁的托管线程。</span><span class="sxs-lookup"><span data-stu-id="efecf-103">Returns the managed thread that owns the monitor lock on this object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efecf-104">语法</span><span class="sxs-lookup"><span data-stu-id="efecf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadOwningMonitorLock (  
    [out] ICorDebugThread   **ppThread,  
    [out] DWORD              *pAcquisitionCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="efecf-105">参数</span><span class="sxs-lookup"><span data-stu-id="efecf-105">Parameters</span></span>  

 `ppThread`  
 <span data-ttu-id="efecf-106">弄拥有此对象的监视器锁的托管线程。</span><span class="sxs-lookup"><span data-stu-id="efecf-106">[out] The managed thread that owns the monitor lock on this object.</span></span>  
  
 `pAcquisitionCount`  
 <span data-ttu-id="efecf-107">弄此线程在返回为无所有者之前必须释放该锁的次数。</span><span class="sxs-lookup"><span data-stu-id="efecf-107">[out] The number of times this thread would have to release the lock before it returns to being unowned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="efecf-108">返回值</span><span class="sxs-lookup"><span data-stu-id="efecf-108">Return Value</span></span>  

 <span data-ttu-id="efecf-109">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="efecf-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="efecf-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="efecf-110">HRESULT</span></span>|<span data-ttu-id="efecf-111">说明</span><span class="sxs-lookup"><span data-stu-id="efecf-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="efecf-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="efecf-112">S_OK</span></span>|<span data-ttu-id="efecf-113">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="efecf-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="efecf-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="efecf-114">S_FALSE</span></span>|<span data-ttu-id="efecf-115">没有托管线程拥有此对象的监视器锁。</span><span class="sxs-lookup"><span data-stu-id="efecf-115">No managed thread owns the monitor lock on this object.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="efecf-116">例外</span><span class="sxs-lookup"><span data-stu-id="efecf-116">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="efecf-117">备注</span><span class="sxs-lookup"><span data-stu-id="efecf-117">Remarks</span></span>  

 <span data-ttu-id="efecf-118">如果托管线程拥有此对象的监视器锁：</span><span class="sxs-lookup"><span data-stu-id="efecf-118">If a managed thread owns the monitor lock on this object:</span></span>  
  
- <span data-ttu-id="efecf-119">方法返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="efecf-119">The method returns S_OK.</span></span>  
  
- <span data-ttu-id="efecf-120">线程对象在线程退出之前有效。</span><span class="sxs-lookup"><span data-stu-id="efecf-120">The thread object is valid until the thread exits.</span></span>  
  
 <span data-ttu-id="efecf-121">如果没有托管线程拥有此对象的监视器锁， `ppThread` 且未 `pAcquisitionCount` 更改，则该方法将返回 S_FALSE。</span><span class="sxs-lookup"><span data-stu-id="efecf-121">If no managed thread owns the monitor lock on this object, `ppThread` and `pAcquisitionCount` are unchanged, and the method returns S_FALSE.</span></span>  
  
 <span data-ttu-id="efecf-122">如果 `ppThread` 或 `pAcquisitionCount` 不是有效的指针，则结果是不确定的。</span><span class="sxs-lookup"><span data-stu-id="efecf-122">If `ppThread` or `pAcquisitionCount` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="efecf-123">如果发生错误，因此无法确定线程（如果有）线程拥有此对象的监视器锁，则方法将返回指示失败的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="efecf-123">If an error occurs such that it cannot be determined which, if any, thread owns the monitor lock on this object, the method returns an HRESULT that indicates failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efecf-124">要求</span><span class="sxs-lookup"><span data-stu-id="efecf-124">Requirements</span></span>  

 <span data-ttu-id="efecf-125">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="efecf-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efecf-126">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="efecf-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="efecf-127">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="efecf-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="efecf-128">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efecf-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efecf-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="efecf-129">See also</span></span>

- [<span data-ttu-id="efecf-130">调试接口</span><span class="sxs-lookup"><span data-stu-id="efecf-130">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="efecf-131">调试</span><span class="sxs-lookup"><span data-stu-id="efecf-131">Debugging</span></span>](index.md)
