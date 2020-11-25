---
title: ICorDebugDataTarget3::GetLoadedModules 方法
ms.date: 03/30/2017
ms.assetid: 9a48c05b-1949-416e-933c-52549b6fcf5e
ms.openlocfilehash: efbada02b7a24e0a7ed613b86b8a4a1a0b5b051a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713739"
---
# <a name="icordebugdatatarget3getloadedmodules-method"></a><span data-ttu-id="83181-102">ICorDebugDataTarget3::GetLoadedModules 方法</span><span class="sxs-lookup"><span data-stu-id="83181-102">ICorDebugDataTarget3::GetLoadedModules Method</span></span>

<span data-ttu-id="83181-103">获取到目前为止已加载的模块的列表。</span><span class="sxs-lookup"><span data-stu-id="83181-103">Gets a list of the modules that have been loaded so far.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83181-104">语法</span><span class="sxs-lookup"><span data-stu-id="83181-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLoadedModules(  
   [in] ULONG32 cRequestedModules,  
   [out] ULONG32 *pcFetchedModules,  
   [out, size_is(cRequestedModules), length_is(*pcFetchedModules)] ICorDebugLoadedModule *pLoadedModules[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83181-105">参数</span><span class="sxs-lookup"><span data-stu-id="83181-105">Parameters</span></span>  

 `cRequestedModules`  
 <span data-ttu-id="83181-106">[in] 请求了其信息的模块数。</span><span class="sxs-lookup"><span data-stu-id="83181-106">[in] The number of modules for which information is requested.</span></span>  
  
 `pcFetchedModules`  
 <span data-ttu-id="83181-107">[out] 指向返回了相关信息的模块数的指针。</span><span class="sxs-lookup"><span data-stu-id="83181-107">[out] A pointer to the number of modules about which information was returned.</span></span>  
  
 `pLoadedModules`  
 <span data-ttu-id="83181-108">弄指向 [ICorDebugLoadedModule](icordebugloadedmodule-interface.md) 对象数组的指针，这些对象提供有关已加载模块的信息。</span><span class="sxs-lookup"><span data-stu-id="83181-108">[out] A pointer to an array of [ICorDebugLoadedModule](icordebugloadedmodule-interface.md) objects that provide information about loaded modules.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83181-109">注解</span><span class="sxs-lookup"><span data-stu-id="83181-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="83181-110">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="83181-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83181-111">要求</span><span class="sxs-lookup"><span data-stu-id="83181-111">Requirements</span></span>  

 <span data-ttu-id="83181-112">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="83181-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83181-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="83181-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="83181-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83181-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83181-115">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83181-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83181-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="83181-116">See also</span></span>

- [<span data-ttu-id="83181-117">ICorDebugDataTarget3 接口</span><span class="sxs-lookup"><span data-stu-id="83181-117">ICorDebugDataTarget3 Interface</span></span>](icordebugdatatarget3-interface.md)
- [<span data-ttu-id="83181-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="83181-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
