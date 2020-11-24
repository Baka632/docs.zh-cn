---
title: “ICor调试程序集3”接口
ms.date: 03/30/2017
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
ms.openlocfilehash: 0260267a05a880fbb3ac48325e55deff326f5f87
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688362"
---
# <a name="icordebugassembly3-interface"></a><span data-ttu-id="5408f-102">“ICor调试程序集3”接口</span><span class="sxs-lookup"><span data-stu-id="5408f-102">ICorDebugAssembly3 Interface</span></span>

<span data-ttu-id="5408f-103">对 ICorDebugAssembly 接口进行逻辑扩展，从而为容器程序集及其包含的程序集提供支持。</span><span class="sxs-lookup"><span data-stu-id="5408f-103">Logically extends the ICorDebugAssembly interface to provide support for container assemblies and their contained assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5408f-104">方法</span><span class="sxs-lookup"><span data-stu-id="5408f-104">Methods</span></span>  
  
|<span data-ttu-id="5408f-105">方法</span><span class="sxs-lookup"><span data-stu-id="5408f-105">Method</span></span>|<span data-ttu-id="5408f-106">说明</span><span class="sxs-lookup"><span data-stu-id="5408f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5408f-107">EnumerateContainedAssemblies 方法</span><span class="sxs-lookup"><span data-stu-id="5408f-107">EnumerateContainedAssemblies Method</span></span>](icordebugassembly3-enumeratecontainedassemblies-method.md)|<span data-ttu-id="5408f-108">获取该程序集中所包含的程序集的枚举器。</span><span class="sxs-lookup"><span data-stu-id="5408f-108">Gets an enumerator for the assemblies contained in this assembly.</span></span>|  
|[<span data-ttu-id="5408f-109">GetContainerAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="5408f-109">GetContainerAssembly Method</span></span>](icordebugassembly3-getcontainerassembly-method.md)|<span data-ttu-id="5408f-110">返回该 `ICorDebugAssembly3` 对象的容器程序集。</span><span class="sxs-lookup"><span data-stu-id="5408f-110">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5408f-111">注解</span><span class="sxs-lookup"><span data-stu-id="5408f-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5408f-112">此接口仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="5408f-112">The interface is available with .NET Native only.</span></span> <span data-ttu-id="5408f-113">尝试调用 `QueryInterface` 来检索接口指针会为 .NET Native 外部的 ICorDebug 方案返回 `E_NOINTERFACE`。</span><span class="sxs-lookup"><span data-stu-id="5408f-113">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5408f-114">要求</span><span class="sxs-lookup"><span data-stu-id="5408f-114">Requirements</span></span>  

 <span data-ttu-id="5408f-115">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5408f-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5408f-116">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5408f-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5408f-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5408f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5408f-118">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5408f-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5408f-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5408f-119">See also</span></span>

- [<span data-ttu-id="5408f-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="5408f-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="5408f-121">调试</span><span class="sxs-lookup"><span data-stu-id="5408f-121">Debugging</span></span>](index.md)
