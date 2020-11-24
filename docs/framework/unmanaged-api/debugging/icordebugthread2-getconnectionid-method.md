---
title: ICorDebugThread2::GetConnectionID 方法
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetConnectionID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetConnectionID
helpviewer_keywords:
- ICorDebugThread2::GetConnectionID method [.NET Framework debugging]
- GetConnectionID method [.NET Framework debugging]
ms.assetid: 9c76b587-f941-4fa1-8b86-f3494fb10c8e
topic_type:
- apiref
ms.openlocfilehash: 1507715e80761c871dfdb0b8d25dc708a2130678
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678683"
---
# <a name="icordebugthread2getconnectionid-method"></a><span data-ttu-id="4cb94-102">ICorDebugThread2::GetConnectionID 方法</span><span class="sxs-lookup"><span data-stu-id="4cb94-102">ICorDebugThread2::GetConnectionID Method</span></span>

<span data-ttu-id="4cb94-103">获取此 ICorDebugThread2 对象的连接标识符。</span><span class="sxs-lookup"><span data-stu-id="4cb94-103">Gets the connection identifier for this ICorDebugThread2 object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cb94-104">语法</span><span class="sxs-lookup"><span data-stu-id="4cb94-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConnectionID (  
    [out] CONNID *pdwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4cb94-105">参数</span><span class="sxs-lookup"><span data-stu-id="4cb94-105">Parameters</span></span>  

 `pdwConnectionId`  
 <span data-ttu-id="4cb94-106">弄一个 `CONNID` 表示连接标识符的。</span><span class="sxs-lookup"><span data-stu-id="4cb94-106">[out] A `CONNID` that represents the connection identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4cb94-107">注解</span><span class="sxs-lookup"><span data-stu-id="4cb94-107">Remarks</span></span>  

 <span data-ttu-id="4cb94-108">`GetConnectionID` `pdwConnectionId` 如果此线程不是连接的一部分，则该方法将在参数中返回零。</span><span class="sxs-lookup"><span data-stu-id="4cb94-108">The `GetConnectionID` method returns zero in the `pdwConnectionId` parameter, if this thread is not part of a connection.</span></span>  
  
 <span data-ttu-id="4cb94-109">如果此线程连接到 (SSAS) Microsoft SQL Server 2005 Analysis Services 的实例，则 `CONNID` 映射到服务器进程标识符 (SPID) 。</span><span class="sxs-lookup"><span data-stu-id="4cb94-109">If this thread is connected to an instance of Microsoft SQL Server 2005 Analysis Services (SSAS), the `CONNID` maps to a server process identifier (SPID).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cb94-110">要求</span><span class="sxs-lookup"><span data-stu-id="4cb94-110">Requirements</span></span>  

 <span data-ttu-id="4cb94-111">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4cb94-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cb94-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4cb94-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4cb94-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4cb94-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4cb94-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cb94-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
