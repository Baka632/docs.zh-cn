---
title: ICorDebugManagedCallback3::CustomNotification 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback3.CustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback3::CustomNotification
helpviewer_keywords:
- ICorDebugManagedCallback3::CustomNotification method [.NET Framework debugging]
- CustomNotification method [.NET Framework debugging]
ms.assetid: 5e5422ac-afa1-403d-a894-2d7348673e38
topic_type:
- apiref
ms.openlocfilehash: f30c9b6746d0e1594994870a96e94eb8105e4c94
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700829"
---
# <a name="icordebugmanagedcallback3customnotification-method"></a><span data-ttu-id="82c1b-102">ICorDebugManagedCallback3::CustomNotification 方法</span><span class="sxs-lookup"><span data-stu-id="82c1b-102">ICorDebugManagedCallback3::CustomNotification Method</span></span>

<span data-ttu-id="82c1b-103">指示已引发自定义调试器通知。</span><span class="sxs-lookup"><span data-stu-id="82c1b-103">Indicates that a custom debugger notification has been raised.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82c1b-104">语法</span><span class="sxs-lookup"><span data-stu-id="82c1b-104">Syntax</span></span>  
  
```cpp  
HRESULT CustomNotification(ICorDebugThread *    pThread,  
                           ICorDebugAppDomain * pAppDomain);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82c1b-105">参数</span><span class="sxs-lookup"><span data-stu-id="82c1b-105">Parameters</span></span>  

 `pThread`  
 <span data-ttu-id="82c1b-106">中指向引发通知的线程的指针。</span><span class="sxs-lookup"><span data-stu-id="82c1b-106">[in] A pointer to the thread that raised the notification.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="82c1b-107">中一个指针，指向包含引发通知的线程的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="82c1b-107">[in] A pointer to the application domain that contains the thread that raised the notification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="82c1b-108">返回值</span><span class="sxs-lookup"><span data-stu-id="82c1b-108">Return Value</span></span>  

 <span data-ttu-id="82c1b-109">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="82c1b-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="82c1b-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="82c1b-110">HRESULT</span></span>|<span data-ttu-id="82c1b-111">说明</span><span class="sxs-lookup"><span data-stu-id="82c1b-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="82c1b-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="82c1b-112">S_OK</span></span>|<span data-ttu-id="82c1b-113">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="82c1b-113">The method completed successfully.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="82c1b-114">例外</span><span class="sxs-lookup"><span data-stu-id="82c1b-114">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82c1b-115">备注</span><span class="sxs-lookup"><span data-stu-id="82c1b-115">Remarks</span></span>  

 <span data-ttu-id="82c1b-116">对 [ICorDebugThread4：： GetCurrentCustomDebuggerNotification](icordebugthread4-getcurrentcustomdebuggernotification-method.md) 方法的后续调用将检索传递到该方法的线程对象 <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="82c1b-116">A subsequent call to the [ICorDebugThread4::GetCurrentCustomDebuggerNotification](icordebugthread4-getcurrentcustomdebuggernotification-method.md) method retrieves the thread object that was passed to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="82c1b-117">线程对象的类型必须以前已通过调用 [ICorDebugProcess3：： SetEnableCustomNotification](icordebugprocess3-setenablecustomnotification-method.md) 方法启用。</span><span class="sxs-lookup"><span data-stu-id="82c1b-117">The thread object's type must have been previously enabled by calling the [ICorDebugProcess3::SetEnableCustomNotification](icordebugprocess3-setenablecustomnotification-method.md) method.</span></span> <span data-ttu-id="82c1b-118">调试器可以从 thread 对象的字段中读取特定于类型的参数，并可以将响应存储在字段中。</span><span class="sxs-lookup"><span data-stu-id="82c1b-118">The debugger can read type-specific parameters from the fields of the thread object, and can store responses into fields.</span></span>  
  
 <span data-ttu-id="82c1b-119">[ICorDebug](icordebug-interface.md)接口不对通知类型或其内容施加任何策略，并且通知的语义严格地是调试器、应用程序和 .NET Framework 之间的协定。</span><span class="sxs-lookup"><span data-stu-id="82c1b-119">The [ICorDebug](icordebug-interface.md) interface imposes no policy on the types of notifications or their contents, and the semantics of the notifications are strictly a contract between debuggers, applications, and the .NET Framework.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82c1b-120">要求</span><span class="sxs-lookup"><span data-stu-id="82c1b-120">Requirements</span></span>  

 <span data-ttu-id="82c1b-121">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="82c1b-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82c1b-122">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="82c1b-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="82c1b-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="82c1b-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="82c1b-124">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82c1b-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82c1b-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="82c1b-125">See also</span></span>

- [<span data-ttu-id="82c1b-126">ICorDebugManagedCallback3 接口</span><span class="sxs-lookup"><span data-stu-id="82c1b-126">ICorDebugManagedCallback3 Interface</span></span>](icordebugmanagedcallback3-interface.md)
- [<span data-ttu-id="82c1b-127">调试接口</span><span class="sxs-lookup"><span data-stu-id="82c1b-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="82c1b-128">调试</span><span class="sxs-lookup"><span data-stu-id="82c1b-128">Debugging</span></span>](index.md)
