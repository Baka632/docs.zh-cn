---
title: ICorDebugManagedCallback2::Exception 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.Exception
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::Exception
helpviewer_keywords:
- ICorDebugManagedCallback2::Exception method [.NET Framework debugging]
- Exception method, ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: 78b0f14f-2fae-4e63-8412-4df119ee8468
topic_type:
- apiref
ms.openlocfilehash: c5be9231bcd5aaddfa0cf1b0051f8e1184faef04
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687627"
---
# <a name="icordebugmanagedcallback2exception-method"></a><span data-ttu-id="d7b40-102">ICorDebugManagedCallback2::Exception 方法</span><span class="sxs-lookup"><span data-stu-id="d7b40-102">ICorDebugManagedCallback2::Exception Method</span></span>

<span data-ttu-id="d7b40-103">通知调试器已开始搜索异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="d7b40-103">Notifies the debugger that a search for an exception handler has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7b40-104">语法</span><span class="sxs-lookup"><span data-stu-id="d7b40-104">Syntax</span></span>  
  
```cpp  
HRESULT Exception (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFrame       *pFrame,  
    [in] ULONG32              nOffset,  
    [in] CorDebugExceptionCallbackType dwEventType,  
    [in] DWORD                dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7b40-105">参数</span><span class="sxs-lookup"><span data-stu-id="d7b40-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="d7b40-106">中指向 ICorDebugAppDomain 对象的指针，该对象表示包含引发异常的线程的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="d7b40-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread on which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="d7b40-107">中指向 ICorDebugThread 对象的指针，该对象表示引发异常的线程。</span><span class="sxs-lookup"><span data-stu-id="d7b40-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the exception was thrown.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="d7b40-108">中指向 ICorDebugFrame 对象的指针，该对象表示由参数确定的帧 `dwEventType` 。</span><span class="sxs-lookup"><span data-stu-id="d7b40-108">[in] A pointer to an ICorDebugFrame object that represents a frame, as determined by the `dwEventType` parameter.</span></span> <span data-ttu-id="d7b40-109">有关详细信息，请参阅 "备注" 部分中的表。</span><span class="sxs-lookup"><span data-stu-id="d7b40-109">For more information, see the table in the Remarks section.</span></span>  
  
 `nOffset`  
 <span data-ttu-id="d7b40-110">中一个整数，指定由参数确定的偏移量 `dwEventType` 。</span><span class="sxs-lookup"><span data-stu-id="d7b40-110">[in] An integer that specifies an offset, as determined by the `dwEventType` parameter.</span></span> <span data-ttu-id="d7b40-111">有关详细信息，请参阅 "备注" 部分中的表。</span><span class="sxs-lookup"><span data-stu-id="d7b40-111">For more information, see the table in the Remarks section.</span></span>  
  
 `dwEventType`  
 <span data-ttu-id="d7b40-112">中CorDebugExceptionCallbackType 枚举的一个值，该值指定此异常回调的类型。</span><span class="sxs-lookup"><span data-stu-id="d7b40-112">[in] A value of the CorDebugExceptionCallbackType enumeration that specifies the type of this exception callback.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="d7b40-113">中 [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) 枚举的一个值，该值指定有关异常的其他信息</span><span class="sxs-lookup"><span data-stu-id="d7b40-113">[in] A value of the [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) enumeration that specifies additional information about the exception</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7b40-114">注解</span><span class="sxs-lookup"><span data-stu-id="d7b40-114">Remarks</span></span>  

 <span data-ttu-id="d7b40-115">在 `Exception` 异常处理过程的搜索阶段，会在不同的点调用回调。</span><span class="sxs-lookup"><span data-stu-id="d7b40-115">The `Exception` callback is called at various points during the search phase of the exception-handling process.</span></span> <span data-ttu-id="d7b40-116">也就是说，可以在展开异常时多次调用它。</span><span class="sxs-lookup"><span data-stu-id="d7b40-116">That is, it can be called more than once while unwinding an exception.</span></span>  
  
 <span data-ttu-id="d7b40-117">可以从参数引用的 ICorDebugThread 对象中检索正在处理的异常 `pThread` 。</span><span class="sxs-lookup"><span data-stu-id="d7b40-117">The exception being processed can be retrieved from the ICorDebugThread object referenced by the `pThread` parameter.</span></span>  
  
 <span data-ttu-id="d7b40-118">特定的帧和偏移由参数确定， `dwEventType` 如下所示：</span><span class="sxs-lookup"><span data-stu-id="d7b40-118">The particular frame and offset are determined by the `dwEventType` parameter as follows:</span></span>  
  
|<span data-ttu-id="d7b40-119">`dwEventType` 的值</span><span class="sxs-lookup"><span data-stu-id="d7b40-119">Value of `dwEventType`</span></span>|<span data-ttu-id="d7b40-120">`pFrame` 的值</span><span class="sxs-lookup"><span data-stu-id="d7b40-120">Value of `pFrame`</span></span>|<span data-ttu-id="d7b40-121">`nOffset` 的值</span><span class="sxs-lookup"><span data-stu-id="d7b40-121">Value of `nOffset`</span></span>|  
|----------------------------|-----------------------|------------------------|  
|<span data-ttu-id="d7b40-122">DEBUG_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="d7b40-122">DEBUG_EXCEPTION_FIRST_CHANCE</span></span>|<span data-ttu-id="d7b40-123">引发异常的帧。</span><span class="sxs-lookup"><span data-stu-id="d7b40-123">The frame that threw the exception.</span></span>|<span data-ttu-id="d7b40-124">帧中的指令指针。</span><span class="sxs-lookup"><span data-stu-id="d7b40-124">The instruction pointer in the frame.</span></span>|  
|<span data-ttu-id="d7b40-125">DEBUG_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="d7b40-125">DEBUG_EXCEPTION_USER_FIRST_CHANCE</span></span>|<span data-ttu-id="d7b40-126">最接近引发的异常点的用户代码框架。</span><span class="sxs-lookup"><span data-stu-id="d7b40-126">The user-code frame closest to the point of the thrown exception.</span></span>|<span data-ttu-id="d7b40-127">帧中的指令指针。</span><span class="sxs-lookup"><span data-stu-id="d7b40-127">The instruction pointer in the frame.</span></span>|  
|<span data-ttu-id="d7b40-128">DEBUG_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="d7b40-128">DEBUG_EXCEPTION_CATCH_HANDLER_FOUND</span></span>|<span data-ttu-id="d7b40-129">包含 catch 处理程序的帧。</span><span class="sxs-lookup"><span data-stu-id="d7b40-129">The frame that contains the catch handler.</span></span>|<span data-ttu-id="d7b40-130">Microsoft 中间语言 (MSIL) catch 处理程序开头的偏移量。</span><span class="sxs-lookup"><span data-stu-id="d7b40-130">The Microsoft intermediate language (MSIL) offset of the beginning of the catch handler.</span></span>|  
|<span data-ttu-id="d7b40-131">DEBUG_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="d7b40-131">DEBUG_EXCEPTION_UNHANDLED</span></span>|<span data-ttu-id="d7b40-132">Null</span><span class="sxs-lookup"><span data-stu-id="d7b40-132">NULL</span></span>|<span data-ttu-id="d7b40-133">未定义。</span><span class="sxs-lookup"><span data-stu-id="d7b40-133">Undefined.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d7b40-134">要求</span><span class="sxs-lookup"><span data-stu-id="d7b40-134">Requirements</span></span>  

 <span data-ttu-id="d7b40-135">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d7b40-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7b40-136">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d7b40-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d7b40-137">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7b40-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7b40-138">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7b40-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7b40-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7b40-139">See also</span></span>

- [<span data-ttu-id="d7b40-140">ICorDebugManagedCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="d7b40-140">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="d7b40-141">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="d7b40-141">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
