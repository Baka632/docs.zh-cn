---
title: ICorDebugProcess::GetID 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetID
helpviewer_keywords:
- GetID method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::GetID method [.NET Framework debugging]
ms.assetid: b0ba8453-fa7e-4c14-93e5-335409cd4a47
topic_type:
- apiref
ms.openlocfilehash: 65d9c3688f3a41312a17e6058f73596fc2503dd4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95694979"
---
# <a name="icordebugprocessgetid-method"></a><span data-ttu-id="80c8a-102">ICorDebugProcess::GetID 方法</span><span class="sxs-lookup"><span data-stu-id="80c8a-102">ICorDebugProcess::GetID Method</span></span>

<span data-ttu-id="80c8a-103">获取进程的操作系统 (操作系统) ID。</span><span class="sxs-lookup"><span data-stu-id="80c8a-103">Gets the operating system (OS) ID of the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80c8a-104">语法</span><span class="sxs-lookup"><span data-stu-id="80c8a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID([out] DWORD *pdwProcessId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80c8a-105">参数</span><span class="sxs-lookup"><span data-stu-id="80c8a-105">Parameters</span></span>  

 `pdwProcessId`  
 <span data-ttu-id="80c8a-106">弄进程的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="80c8a-106">[out] The unique ID of the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80c8a-107">要求</span><span class="sxs-lookup"><span data-stu-id="80c8a-107">Requirements</span></span>  

 <span data-ttu-id="80c8a-108">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="80c8a-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80c8a-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="80c8a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="80c8a-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="80c8a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="80c8a-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80c8a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
