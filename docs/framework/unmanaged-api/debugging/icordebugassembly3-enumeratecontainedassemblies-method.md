---
title: ICorDebugAssembly3::EnumerateContainedAssemblies 方法
ms.date: 03/30/2017
ms.assetid: 98f15b05-afad-4616-9e2a-1a9af31948b6
ms.openlocfilehash: 1e040453d5eb7a312f2e665974486492b99de16d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719679"
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a><span data-ttu-id="b5e48-102">ICorDebugAssembly3::EnumerateContainedAssemblies 方法</span><span class="sxs-lookup"><span data-stu-id="b5e48-102">ICorDebugAssembly3::EnumerateContainedAssemblies Method</span></span>

<span data-ttu-id="b5e48-103">获取该程序集中所包含的程序集的枚举器。</span><span class="sxs-lookup"><span data-stu-id="b5e48-103">Gets an enumerator for the assemblies contained in this assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5e48-104">语法</span><span class="sxs-lookup"><span data-stu-id="b5e48-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5e48-105">参数</span><span class="sxs-lookup"><span data-stu-id="b5e48-105">Parameters</span></span>  

 `ppAssemblies`  
 <span data-ttu-id="b5e48-106">[输出] 指针指向 ICor调试程序集枚举器界面对象（即枚举器）的地址。</span><span class="sxs-lookup"><span data-stu-id="b5e48-106">[out] A pointer to the address of an ICorDebugAssemblyEnum interface object that is the enumerator.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b5e48-107">返回值</span><span class="sxs-lookup"><span data-stu-id="b5e48-107">Return Value</span></span>  

 <span data-ttu-id="b5e48-108">`S_OK` 若该 `ICorDebugAssembly3` 对象为容器；反之，`S_FALSE`，枚举为空。</span><span class="sxs-lookup"><span data-stu-id="b5e48-108">`S_OK` if this `ICorDebugAssembly3` object is a container; otherwise, `S_FALSE`, and the enumeration is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5e48-109">注解</span><span class="sxs-lookup"><span data-stu-id="b5e48-109">Remarks</span></span>  

 <span data-ttu-id="b5e48-110">需用符号来列举包含的程序集。</span><span class="sxs-lookup"><span data-stu-id="b5e48-110">Symbols are needed to enumerate the contained assemblies.</span></span> <span data-ttu-id="b5e48-111">如果其并不存在，则方法返回 `S_FALSE`，且不提供有效枚举。</span><span class="sxs-lookup"><span data-stu-id="b5e48-111">If they aren't present, the method returns `S_FALSE`, and no valid enumerator is provided.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b5e48-112">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="b5e48-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5e48-113">要求</span><span class="sxs-lookup"><span data-stu-id="b5e48-113">Requirements</span></span>  

 <span data-ttu-id="b5e48-114">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b5e48-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5e48-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b5e48-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b5e48-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5e48-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b5e48-117">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5e48-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5e48-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b5e48-118">See also</span></span>

- [<span data-ttu-id="b5e48-119">“ICor调试程序集3”接口</span><span class="sxs-lookup"><span data-stu-id="b5e48-119">ICorDebugAssembly3 Interface</span></span>](icordebugassembly3-interface.md)
- [<span data-ttu-id="b5e48-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="b5e48-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
