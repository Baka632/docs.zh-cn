---
title: ICorDebugStaticFieldSymbol::GetName 方法
ms.date: 03/30/2017
ms.assetid: e2be4af2-15d1-4e6a-8b68-1d78c93294a4
ms.openlocfilehash: 6284a27921e0ba5bd3cedf07ef9f62348460ad06
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677228"
---
# <a name="icordebugstaticfieldsymbolgetname-method"></a><span data-ttu-id="27812-102">ICorDebugStaticFieldSymbol::GetName 方法</span><span class="sxs-lookup"><span data-stu-id="27812-102">ICorDebugStaticFieldSymbol::GetName Method</span></span>

<span data-ttu-id="27812-103">获取静态字段的名称。</span><span class="sxs-lookup"><span data-stu-id="27812-103">Gets the name of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27812-104">语法</span><span class="sxs-lookup"><span data-stu-id="27812-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27812-105">参数</span><span class="sxs-lookup"><span data-stu-id="27812-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="27812-106">[in] `szName` 缓冲区中的字符数。</span><span class="sxs-lookup"><span data-stu-id="27812-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="27812-107">[out] 指向实际写入 `szName` 缓冲区的字符数。缓冲区的字符数的指针。</span><span class="sxs-lookup"><span data-stu-id="27812-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="27812-108">[out] 用于存储返回名称的字符数组。</span><span class="sxs-lookup"><span data-stu-id="27812-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27812-109">注解</span><span class="sxs-lookup"><span data-stu-id="27812-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="27812-110">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="27812-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27812-111">要求</span><span class="sxs-lookup"><span data-stu-id="27812-111">Requirements</span></span>  

 <span data-ttu-id="27812-112">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="27812-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27812-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="27812-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="27812-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27812-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27812-115">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27812-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27812-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="27812-116">See also</span></span>

- [<span data-ttu-id="27812-117">ICorDebugStaticFieldSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="27812-117">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="27812-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="27812-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
