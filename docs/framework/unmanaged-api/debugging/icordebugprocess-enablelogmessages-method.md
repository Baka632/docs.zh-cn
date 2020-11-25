---
title: ICorDebugProcess::EnableLogMessages 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.EnableLogMessages
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::EnableLogMessages
helpviewer_keywords:
- ICorDebugProcess::EnableLogMessages method [.NET Framework debugging]
- EnableLogMessages method [.NET Framework debugging]
ms.assetid: 14a4e5a3-3eaf-4f53-9dd1-762726963a23
topic_type:
- apiref
ms.openlocfilehash: 86cb1a2eb18840419d2a4e8ee4f6475edafe8397
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724609"
---
# <a name="icordebugprocessenablelogmessages-method"></a><span data-ttu-id="1af85-102">ICorDebugProcess::EnableLogMessages 方法</span><span class="sxs-lookup"><span data-stu-id="1af85-102">ICorDebugProcess::EnableLogMessages Method</span></span>

<span data-ttu-id="1af85-103">启用和禁用向调试器传输日志消息。</span><span class="sxs-lookup"><span data-stu-id="1af85-103">Enables and disables the transmission of log messages to the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1af85-104">语法</span><span class="sxs-lookup"><span data-stu-id="1af85-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableLogMessages([in]BOOL fOnOff);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1af85-105">参数</span><span class="sxs-lookup"><span data-stu-id="1af85-105">Parameters</span></span>  

 `fOnOff`  
 <span data-ttu-id="1af85-106">[in] `true` 启用日志消息的传输; `false` 禁用传输。</span><span class="sxs-lookup"><span data-stu-id="1af85-106">[in] `true` enables the transmission of log messages; `false` disables the transmission.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1af85-107">注解</span><span class="sxs-lookup"><span data-stu-id="1af85-107">Remarks</span></span>  

 <span data-ttu-id="1af85-108">此方法仅在 [ICorDebugManagedCallback：： CreateProcess](icordebugmanagedcallback-createprocess-method.md) 回调发生之后有效。</span><span class="sxs-lookup"><span data-stu-id="1af85-108">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback occurs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1af85-109">要求</span><span class="sxs-lookup"><span data-stu-id="1af85-109">Requirements</span></span>  

 <span data-ttu-id="1af85-110">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1af85-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1af85-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1af85-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1af85-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1af85-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1af85-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1af85-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
