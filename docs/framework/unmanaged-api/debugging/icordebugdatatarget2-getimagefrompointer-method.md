---
title: ICorDebugDataTarget2::GetImageFromPointer 方法
ms.date: 03/30/2017
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
ms.openlocfilehash: 41385fe915733f052af67c82d984c8b9d853c579
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713816"
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a><span data-ttu-id="558a6-102">ICorDebugDataTarget2::GetImageFromPointer 方法</span><span class="sxs-lookup"><span data-stu-id="558a6-102">ICorDebugDataTarget2::GetImageFromPointer Method</span></span>

<span data-ttu-id="558a6-103">返回该模块地址中的模块基址和大小。</span><span class="sxs-lookup"><span data-stu-id="558a6-103">Returns the module base address and size from an address in that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="558a6-104">语法</span><span class="sxs-lookup"><span data-stu-id="558a6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,
   [out] CORDB_ADDRESS *pImageBase,
   [out] ULONG32 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="558a6-105">参数</span><span class="sxs-lookup"><span data-stu-id="558a6-105">Parameters</span></span>  

 `addr`  
 <span data-ttu-id="558a6-106">一个 [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) 值，该值表示模块中的地址。</span><span class="sxs-lookup"><span data-stu-id="558a6-106">A [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) value that represents an address in a module.</span></span>  
  
 `pImageBase`  
 <span data-ttu-id="558a6-107">弄一个 [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) 值，该值表示模块的基址。</span><span class="sxs-lookup"><span data-stu-id="558a6-107">[out] A [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `pSize`  
 <span data-ttu-id="558a6-108">指针指向模块大小。</span><span class="sxs-lookup"><span data-stu-id="558a6-108">A pointer to the module size.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="558a6-109">注解</span><span class="sxs-lookup"><span data-stu-id="558a6-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="558a6-110">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="558a6-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="558a6-111">要求</span><span class="sxs-lookup"><span data-stu-id="558a6-111">Requirements</span></span>  

 <span data-ttu-id="558a6-112">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="558a6-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="558a6-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="558a6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="558a6-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="558a6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="558a6-115">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="558a6-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="558a6-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="558a6-116">See also</span></span>

- [<span data-ttu-id="558a6-117">“ICor调试数据目标2”接口</span><span class="sxs-lookup"><span data-stu-id="558a6-117">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="558a6-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="558a6-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
