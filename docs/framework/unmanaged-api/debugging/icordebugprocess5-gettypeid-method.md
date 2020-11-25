---
title: ICorDebugProcess5::GetTypeID 方法
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugProcess5.GetTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeID
helpviewer_keywords:
- ICorDebugProcess5::GetTypeID method [.NET Framework debugging]
- GetTypeID method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 47dbaea4-8857-462e-93ba-fff880fc9e50
topic_type:
- apiref
ms.openlocfilehash: 3a9ef06f312126319875544caf272903b9f7c716
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701024"
---
# <a name="icordebugprocess5gettypeid-method"></a><span data-ttu-id="1b408-102">ICorDebugProcess5::GetTypeID 方法</span><span class="sxs-lookup"><span data-stu-id="1b408-102">ICorDebugProcess5::GetTypeID Method</span></span>

<span data-ttu-id="1b408-103">将对象地址转换为 [COR_TYPEID](cor-typeid-structure.md) 的标识符。</span><span class="sxs-lookup"><span data-stu-id="1b408-103">Converts an object address to a [COR_TYPEID](cor-typeid-structure.md) identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b408-104">语法</span><span class="sxs-lookup"><span data-stu-id="1b408-104">Syntax</span></span>  
  
```cpp
HRESULT GetTypeID(  
    [in] CORDB_ADDRESS obj,  
    [out] COR_TYPEID *pId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b408-105">参数</span><span class="sxs-lookup"><span data-stu-id="1b408-105">Parameters</span></span>  

 `obj`  
 <span data-ttu-id="1b408-106">中对象地址。</span><span class="sxs-lookup"><span data-stu-id="1b408-106">[in] The object address.</span></span>  
  
 `pId`  
 <span data-ttu-id="1b408-107">一个指针，指向用于标识对象的 [COR_TYPEID](cor-typeid-structure.md) 值。</span><span class="sxs-lookup"><span data-stu-id="1b408-107">A pointer to the [COR_TYPEID](cor-typeid-structure.md) value that identifies the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b408-108">备注</span><span class="sxs-lookup"><span data-stu-id="1b408-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b408-109">要求</span><span class="sxs-lookup"><span data-stu-id="1b408-109">Requirements</span></span>  

 <span data-ttu-id="1b408-110">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1b408-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b408-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1b408-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1b408-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b408-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b408-113">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b408-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b408-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1b408-114">See also</span></span>

- [<span data-ttu-id="1b408-115">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="1b408-115">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="1b408-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="1b408-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
