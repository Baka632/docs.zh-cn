---
title: GetStartupNotificationEvent 函数
ms.date: 03/30/2017
api_name:
- GetStartupNotificationEvent
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- GetStartupNotificationEvent
helpviewer_keywords:
- GetStartupNotificationEvent function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: c94b1b61-045a-4695-bacd-0f18c5acc246
topic_type:
- apiref
ms.openlocfilehash: 1c6ad35cd42760a4d88cf78bb084a25cf58a1064
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676083"
---
# <a name="getstartupnotificationevent-function"></a><span data-ttu-id="724e9-102">GetStartupNotificationEvent 函数</span><span class="sxs-lookup"><span data-stu-id="724e9-102">GetStartupNotificationEvent Function</span></span>

<span data-ttu-id="724e9-103">创建或打开一个事件句柄，由在指定目标进程中加载的公共语言运行时 (CLR) 对其发出信号。</span><span class="sxs-lookup"><span data-stu-id="724e9-103">Creates or opens an event handle that will be signaled upon by any common language runtime (CLR) that is loading in the specified target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="724e9-104">语法</span><span class="sxs-lookup"><span data-stu-id="724e9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartupNotificationEvent  
    (  
    [in]  DWORD     debuggeePID,  
    [out]  HANDLE*  phStartupEvent  
    );  
```  
  
## <a name="parameters"></a><span data-ttu-id="724e9-105">参数</span><span class="sxs-lookup"><span data-stu-id="724e9-105">Parameters</span></span>  

 `debuggeePID`  
 <span data-ttu-id="724e9-106">[in] 从其中接收 CLR 启动通知的目标进程的进程标识符。</span><span class="sxs-lookup"><span data-stu-id="724e9-106">[in] Process identifier of the target process from which to receive CLR startup notifications.</span></span>  
  
 `phStartupEvent`  
 <span data-ttu-id="724e9-107">[out] 指向在启动时由 CLR 发出信号通知的句柄的指针。</span><span class="sxs-lookup"><span data-stu-id="724e9-107">[out] A pointer to a handle that will be signaled by a CLR on startup.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="724e9-108">返回值</span><span class="sxs-lookup"><span data-stu-id="724e9-108">Return Value</span></span>  

 <span data-ttu-id="724e9-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="724e9-109">S_OK</span></span>  
 <span data-ttu-id="724e9-110">成功获取启动通知事件的句柄。</span><span class="sxs-lookup"><span data-stu-id="724e9-110">Successfully obtained the handle to the startup notification event.</span></span>  
  
 <span data-ttu-id="724e9-111">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="724e9-111">E_INVALIDARG</span></span>  
 <span data-ttu-id="724e9-112">`phStartupEvent` 为 null 或 `debuggeePID` 不引用当前正在运行的进程。</span><span class="sxs-lookup"><span data-stu-id="724e9-112">`phStartupEvent` is null or `debuggeePID` does not refer to a process that is currently running.</span></span>  
  
 <span data-ttu-id="724e9-113">E_FAIL（或其他 E_ 返回代码）</span><span class="sxs-lookup"><span data-stu-id="724e9-113">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="724e9-114">无法获取启动通知事件的句柄。</span><span class="sxs-lookup"><span data-stu-id="724e9-114">Unable to obtain the handle to the startup notification event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="724e9-115">注解</span><span class="sxs-lookup"><span data-stu-id="724e9-115">Remarks</span></span>  

 <span data-ttu-id="724e9-116">在 Windows 操作系统上，`debuggeePID` 映射到 OS 进程标识符。</span><span class="sxs-lookup"><span data-stu-id="724e9-116">On the Windows operating system, `debuggeePID` maps to an OS process identifier.</span></span>  
  
 <span data-ttu-id="724e9-117">在发出信号通知事件的 CLR 执行任何托管代码之前，对该事件发出了信号。</span><span class="sxs-lookup"><span data-stu-id="724e9-117">The event is signaled before any managed code is executed by the CLR that signaled the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="724e9-118">要求</span><span class="sxs-lookup"><span data-stu-id="724e9-118">Requirements</span></span>  

 <span data-ttu-id="724e9-119">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="724e9-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="724e9-120">**标头：** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="724e9-120">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="724e9-121">**库：** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="724e9-121">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="724e9-122">**.NET Framework 版本：** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="724e9-122">**.NET Framework Versions:** 3.5 SP1</span></span>
