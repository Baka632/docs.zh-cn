---
title: ICorDebugChainEnum::Next 方法
ms.date: 03/30/2017
api_name:
- ICorDebugChainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChainEnum::Next
helpviewer_keywords:
- ICorDebugChainEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugChainEnum interface [.NET Framework debugging]
ms.assetid: 6b791351-bcc5-4ddd-9cab-eff2f7dd5142
topic_type:
- apiref
ms.openlocfilehash: 0f42020821ec71d1e59ae8097f22ee530e16a576
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706172"
---
# <a name="icordebugchainenumnext-method"></a><span data-ttu-id="71082-102">ICorDebugChainEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="71082-102">ICorDebugChainEnum::Next Method</span></span>

<span data-ttu-id="71082-103">从当前位置开始，从枚举中获取指定数量的 ICorDebugChain 实例。</span><span class="sxs-lookup"><span data-stu-id="71082-103">Gets the specified number of ICorDebugChain instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71082-104">语法</span><span class="sxs-lookup"><span data-stu-id="71082-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugChain *chains[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71082-105">参数</span><span class="sxs-lookup"><span data-stu-id="71082-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="71082-106">中 `ICorDebugChain` 要检索的实例数。</span><span class="sxs-lookup"><span data-stu-id="71082-106">[in] The number of `ICorDebugChain` instances to be retrieved.</span></span>  
  
 `chains`  
 <span data-ttu-id="71082-107">弄一个指针数组，其中每个指针指向一个 `ICorDebugChain` 表示链的对象。</span><span class="sxs-lookup"><span data-stu-id="71082-107">[out] An array of pointers, each of which points to an `ICorDebugChain` object that represents a chain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="71082-108">弄一个指针，指向 `ICorDebugChain` 实际返回的实例数。</span><span class="sxs-lookup"><span data-stu-id="71082-108">[out] A pointer to the number of `ICorDebugChain` instances actually returned.</span></span> <span data-ttu-id="71082-109">如果为1，则此值可以为 null `celt` 。</span><span class="sxs-lookup"><span data-stu-id="71082-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71082-110">要求</span><span class="sxs-lookup"><span data-stu-id="71082-110">Requirements</span></span>  

 <span data-ttu-id="71082-111">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="71082-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71082-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="71082-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="71082-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71082-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71082-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71082-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
