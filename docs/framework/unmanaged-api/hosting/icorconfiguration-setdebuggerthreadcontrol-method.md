---
title: ICorConfiguration::SetDebuggerThreadControl 方法
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetDebuggerThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetDebuggerThreadControl
helpviewer_keywords:
- SetDebuggerThreadControl method [.NET Framework hosting]
- ICorConfiguration::SetDebuggerThreadControl method [.NET Framework hosting]
ms.assetid: 1ded7639-dacb-4db1-961c-d1ceaec01959
topic_type:
- apiref
ms.openlocfilehash: 05df50d80c6b8962b3bdfe2708d5f9d30c58aaea
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723917"
---
# <a name="icorconfigurationsetdebuggerthreadcontrol-method"></a><span data-ttu-id="ac0e3-102">ICorConfiguration::SetDebuggerThreadControl 方法</span><span class="sxs-lookup"><span data-stu-id="ac0e3-102">ICorConfiguration::SetDebuggerThreadControl Method</span></span>

<span data-ttu-id="ac0e3-103">设置回调接口，调试服务将调用该接口作为公共语言运行时 (CLR) 线程被阻止和取消阻止以进行调试。</span><span class="sxs-lookup"><span data-stu-id="ac0e3-103">Sets the callback interface that the debugging services will call as common language runtime (CLR) threads are blocked and unblocked for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac0e3-104">语法</span><span class="sxs-lookup"><span data-stu-id="ac0e3-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDebuggerThreadControl (  
    [in] IDebuggerThreadControl* pDebuggerThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac0e3-105">参数</span><span class="sxs-lookup"><span data-stu-id="ac0e3-105">Parameters</span></span>  

 `pDebuggerThreadControl`  
 <span data-ttu-id="ac0e3-106">中指向 [IDebuggerThreadControl](idebuggerthreadcontrol-interface.md) 对象的指针，该对象通知宿主调试服务阻止和取消阻止线程。</span><span class="sxs-lookup"><span data-stu-id="ac0e3-106">[in] A pointer to an [IDebuggerThreadControl](idebuggerthreadcontrol-interface.md) object that notifies the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac0e3-107">要求</span><span class="sxs-lookup"><span data-stu-id="ac0e3-107">Requirements</span></span>  

 <span data-ttu-id="ac0e3-108">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ac0e3-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac0e3-109">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ac0e3-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ac0e3-110">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ac0e3-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ac0e3-111">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac0e3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac0e3-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac0e3-112">See also</span></span>

- [<span data-ttu-id="ac0e3-113">ICorConfiguration 接口</span><span class="sxs-lookup"><span data-stu-id="ac0e3-113">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)
