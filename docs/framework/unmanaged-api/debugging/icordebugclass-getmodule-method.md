---
title: ICorDebugClass::GetModule 方法
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetModule
helpviewer_keywords:
- GetModule method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetModule method [.NET Framework debugging]
ms.assetid: 87029cc4-e5e1-42d5-8b98-655bb7ece520
topic_type:
- apiref
ms.openlocfilehash: e95d10512da73d9f483b87557fd7cd4574503c70
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728454"
---
# <a name="icordebugclassgetmodule-method"></a><span data-ttu-id="01786-102">ICorDebugClass::GetModule 方法</span><span class="sxs-lookup"><span data-stu-id="01786-102">ICorDebugClass::GetModule Method</span></span>

<span data-ttu-id="01786-103">获取定义此类的模块。</span><span class="sxs-lookup"><span data-stu-id="01786-103">Gets the module that defines this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01786-104">语法</span><span class="sxs-lookup"><span data-stu-id="01786-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule (  
    [out] ICorDebugModule    **pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01786-105">参数</span><span class="sxs-lookup"><span data-stu-id="01786-105">Parameters</span></span>  

 `pModule`  
 <span data-ttu-id="01786-106">弄指向 ICorDebugModule 对象的地址的指针，该对象表示在其中定义此类的模块。</span><span class="sxs-lookup"><span data-stu-id="01786-106">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this class is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01786-107">要求</span><span class="sxs-lookup"><span data-stu-id="01786-107">Requirements</span></span>  

 <span data-ttu-id="01786-108">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="01786-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01786-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="01786-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="01786-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="01786-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="01786-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01786-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
