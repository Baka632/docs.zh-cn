---
title: ICorDebugProcess::GetHandle 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::GetHandle method [.NET Framework debugging]
ms.assetid: e7d3ecf5-09d2-4d94-abb6-ff3483deebb6
topic_type:
- apiref
ms.openlocfilehash: 87b7b7381ef53f7e2abebc053b5c9f87f94d96c2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695057"
---
# <a name="icordebugprocessgethandle-method"></a><span data-ttu-id="5f8af-102">ICorDebugProcess::GetHandle 方法</span><span class="sxs-lookup"><span data-stu-id="5f8af-102">ICorDebugProcess::GetHandle Method</span></span>

<span data-ttu-id="5f8af-103">获取进程的句柄。</span><span class="sxs-lookup"><span data-stu-id="5f8af-103">Gets a handle to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f8af-104">语法</span><span class="sxs-lookup"><span data-stu-id="5f8af-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandle([out] HPROCESS *phProcessHandle);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f8af-105">参数</span><span class="sxs-lookup"><span data-stu-id="5f8af-105">Parameters</span></span>  

 `phProcessHandle`  
 <span data-ttu-id="5f8af-106">弄指向 `HPROCESS` 的指针，它是进程的句柄。</span><span class="sxs-lookup"><span data-stu-id="5f8af-106">[out] A pointer to an `HPROCESS` that is the handle to the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f8af-107">注解</span><span class="sxs-lookup"><span data-stu-id="5f8af-107">Remarks</span></span>  

 <span data-ttu-id="5f8af-108">检索的句柄由调试接口拥有。</span><span class="sxs-lookup"><span data-stu-id="5f8af-108">The retrieved handle is owned by the debugging interface.</span></span> <span data-ttu-id="5f8af-109">调试器应在使用之前复制句柄。</span><span class="sxs-lookup"><span data-stu-id="5f8af-109">The debugger should duplicate the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f8af-110">要求</span><span class="sxs-lookup"><span data-stu-id="5f8af-110">Requirements</span></span>  

 <span data-ttu-id="5f8af-111">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5f8af-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f8af-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5f8af-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f8af-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f8af-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f8af-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f8af-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
