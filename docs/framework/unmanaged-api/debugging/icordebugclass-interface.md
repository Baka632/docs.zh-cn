---
title: ICorDebugClass 接口
ms.date: 03/30/2017
api_name:
- ICorDebugClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass
helpviewer_keywords:
- ICorDebugClass interface [.NET Framework debugging]
ms.assetid: 03a6facb-f12f-49be-9839-e73b9c791cd5
topic_type:
- apiref
ms.openlocfilehash: 4f488741f4233f06c128e0a262ce798ef27af3ff
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699620"
---
# <a name="icordebugclass-interface"></a><span data-ttu-id="7fdab-102">ICorDebugClass 接口</span><span class="sxs-lookup"><span data-stu-id="7fdab-102">ICorDebugClass Interface</span></span>

<span data-ttu-id="7fdab-103">表示基类型或复杂类型（即用户定义的类型）。</span><span class="sxs-lookup"><span data-stu-id="7fdab-103">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="7fdab-104">如果该类型为泛型类型，则 `ICorDebugClass` 表示实例化的泛型类型。</span><span class="sxs-lookup"><span data-stu-id="7fdab-104">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7fdab-105">方法</span><span class="sxs-lookup"><span data-stu-id="7fdab-105">Methods</span></span>  
  
|<span data-ttu-id="7fdab-106">方法</span><span class="sxs-lookup"><span data-stu-id="7fdab-106">Method</span></span>|<span data-ttu-id="7fdab-107">说明</span><span class="sxs-lookup"><span data-stu-id="7fdab-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7fdab-108">GetModule 方法</span><span class="sxs-lookup"><span data-stu-id="7fdab-108">GetModule Method</span></span>](icordebugclass-getmodule-method.md)|<span data-ttu-id="7fdab-109">获取定义此类的模块。</span><span class="sxs-lookup"><span data-stu-id="7fdab-109">Gets the module that defines this class.</span></span>|  
|[<span data-ttu-id="7fdab-110">GetStaticFieldValue 方法</span><span class="sxs-lookup"><span data-stu-id="7fdab-110">GetStaticFieldValue Method</span></span>](icordebugclass-getstaticfieldvalue-method.md)|<span data-ttu-id="7fdab-111">获取指定的静态字段的值。</span><span class="sxs-lookup"><span data-stu-id="7fdab-111">Gets the value of the specified static field.</span></span>|  
|[<span data-ttu-id="7fdab-112">GetToken 方法</span><span class="sxs-lookup"><span data-stu-id="7fdab-112">GetToken Method</span></span>](icordebugclass-gettoken-method.md)|<span data-ttu-id="7fdab-113">获取 `TypeDef` 此类的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="7fdab-113">Gets the `TypeDef` metadata token for this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7fdab-114">注解</span><span class="sxs-lookup"><span data-stu-id="7fdab-114">Remarks</span></span>  

 <span data-ttu-id="7fdab-115">`ICorDebugClass`接口表示未实例化的泛型类型。</span><span class="sxs-lookup"><span data-stu-id="7fdab-115">The `ICorDebugClass` interface represents an uninstantiated generic type.</span></span> <span data-ttu-id="7fdab-116">ICorDebugType 接口表示一个实例化的泛型类型。</span><span class="sxs-lookup"><span data-stu-id="7fdab-116">The ICorDebugType interface represents an instantiated generic type.</span></span> <span data-ttu-id="7fdab-117">例如，将由 `Hashtable<K, V>` 表示 `ICorDebugClass` ，而将由 `Hashtable<Int32, String>` 表示 `ICorDebugType` 。</span><span class="sxs-lookup"><span data-stu-id="7fdab-117">For example, `Hashtable<K, V>` would be represented by `ICorDebugClass`, whereas `Hashtable<Int32, String>` would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="7fdab-118">非泛型类型由 `ICorDebugClass` 和表示 `ICorDebugType` 。</span><span class="sxs-lookup"><span data-stu-id="7fdab-118">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="7fdab-119">后一种接口在 .NET Framework 版本2.0 中引入，用于处理类型实例化。</span><span class="sxs-lookup"><span data-stu-id="7fdab-119">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7fdab-120">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="7fdab-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fdab-121">要求</span><span class="sxs-lookup"><span data-stu-id="7fdab-121">Requirements</span></span>  

 <span data-ttu-id="7fdab-122">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7fdab-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fdab-123">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7fdab-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7fdab-124">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7fdab-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7fdab-125">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fdab-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fdab-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7fdab-126">See also</span></span>

- [<span data-ttu-id="7fdab-127">调试接口</span><span class="sxs-lookup"><span data-stu-id="7fdab-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
