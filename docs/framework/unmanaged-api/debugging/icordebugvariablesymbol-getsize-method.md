---
title: ICorDebugVariableSymbol::GetSize 方法
ms.date: 03/30/2017
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
ms.openlocfilehash: 1079351e75ec9c48a9657f514ee56e2e6a4b0920
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731366"
---
# <a name="icordebugvariablesymbolgetsize-method"></a><span data-ttu-id="443dd-102">ICorDebugVariableSymbol::GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="443dd-102">ICorDebugVariableSymbol::GetSize Method</span></span>

<span data-ttu-id="443dd-103">获取变量的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="443dd-103">Gets the size of a variable in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="443dd-104">语法</span><span class="sxs-lookup"><span data-stu-id="443dd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="443dd-105">参数</span><span class="sxs-lookup"><span data-stu-id="443dd-105">Parameters</span></span>  

 `pcbValue`  
 <span data-ttu-id="443dd-106">指向包含变量大小的 32 位无符号整数的指针。</span><span class="sxs-lookup"><span data-stu-id="443dd-106">A pointer to a 32-bit unsigned integer containing the size of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="443dd-107">注解</span><span class="sxs-lookup"><span data-stu-id="443dd-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="443dd-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="443dd-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="443dd-109">要求</span><span class="sxs-lookup"><span data-stu-id="443dd-109">Requirements</span></span>  

 <span data-ttu-id="443dd-110">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="443dd-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="443dd-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="443dd-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="443dd-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="443dd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="443dd-113">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="443dd-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="443dd-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="443dd-114">See also</span></span>

- [<span data-ttu-id="443dd-115">ICorDebugVariableSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="443dd-115">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="443dd-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="443dd-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
