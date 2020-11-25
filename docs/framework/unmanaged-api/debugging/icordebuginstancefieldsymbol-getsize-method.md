---
title: ICorDebugInstanceFieldSymbol::GetSize 方法
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
ms.openlocfilehash: c4b193b45e30b0eba3367f18cb1e4c2b4e108fa8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724905"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="39f4a-102">ICorDebugInstanceFieldSymbol::GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="39f4a-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>

<span data-ttu-id="39f4a-103">获取实例字段的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="39f4a-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39f4a-104">语法</span><span class="sxs-lookup"><span data-stu-id="39f4a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39f4a-105">参数</span><span class="sxs-lookup"><span data-stu-id="39f4a-105">Parameters</span></span>  

 `pcbSize`  
 <span data-ttu-id="39f4a-106">[out] 指向字段长度的指针。</span><span class="sxs-lookup"><span data-stu-id="39f4a-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39f4a-107">注解</span><span class="sxs-lookup"><span data-stu-id="39f4a-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="39f4a-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="39f4a-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39f4a-109">要求</span><span class="sxs-lookup"><span data-stu-id="39f4a-109">Requirements</span></span>  

 <span data-ttu-id="39f4a-110">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="39f4a-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39f4a-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="39f4a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="39f4a-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39f4a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39f4a-113">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39f4a-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39f4a-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39f4a-114">See also</span></span>

- [<span data-ttu-id="39f4a-115">ICorDebugInstanceFieldSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="39f4a-115">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="39f4a-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="39f4a-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
