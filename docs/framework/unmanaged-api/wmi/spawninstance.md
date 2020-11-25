---
title: 'SpawnInstance 函数 (非托管 API 参考) '
description: SpawnInstance 函数创建类的新实例。
ms.date: 11/06/2017
api_name:
- SpawnInstance
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnInstance
helpviewer_keywords:
- SpawnInstance function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 176bc83dd02381af8c2bc3995a37e7fee7c1bebf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732224"
---
# <a name="spawninstance-function"></a><span data-ttu-id="af2ec-103">SpawnInstance 函数</span><span class="sxs-lookup"><span data-stu-id="af2ec-103">SpawnInstance function</span></span>

<span data-ttu-id="af2ec-104">创建类的新实例。</span><span class="sxs-lookup"><span data-stu-id="af2ec-104">Creates a new instance of a class.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="af2ec-105">语法</span><span class="sxs-lookup"><span data-stu-id="af2ec-105">Syntax</span></span>  
  
```cpp  
HRESULT SpawnInstance (
   [in] int                  vFunc,
   [in] IWbemClassObject*    ptr,
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewInstance);
```  

## <a name="parameters"></a><span data-ttu-id="af2ec-106">参数</span><span class="sxs-lookup"><span data-stu-id="af2ec-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="af2ec-107">中此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="af2ec-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="af2ec-108">中指向 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 实例的指针。</span><span class="sxs-lookup"><span data-stu-id="af2ec-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="af2ec-109">[in] 保留。</span><span class="sxs-lookup"><span data-stu-id="af2ec-109">[in] Reserved.</span></span> <span data-ttu-id="af2ec-110">此参数必须为0。</span><span class="sxs-lookup"><span data-stu-id="af2ec-110">This parameter must be 0.</span></span>

`ppNewInstance`  
<span data-ttu-id="af2ec-111">弄接收指向类的新实例的指针。</span><span class="sxs-lookup"><span data-stu-id="af2ec-111">[out] Receives the pointer to the new instance of the class.</span></span> <span data-ttu-id="af2ec-112">如果发生错误，则不会返回新的对象，也不会 `ppNewInstance` 将其保持不变。</span><span class="sxs-lookup"><span data-stu-id="af2ec-112">If an error occurs, a new object is not returned, and `ppNewInstance` is left unmodified.</span></span>

## <a name="return-value"></a><span data-ttu-id="af2ec-113">返回值</span><span class="sxs-lookup"><span data-stu-id="af2ec-113">Return value</span></span>

<span data-ttu-id="af2ec-114">此函数返回的以下值是在 *WbemCli* 头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="af2ec-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="af2ec-115">返回的常量</span><span class="sxs-lookup"><span data-stu-id="af2ec-115">Constant</span></span>  |<span data-ttu-id="af2ec-116">Value</span><span class="sxs-lookup"><span data-stu-id="af2ec-116">Value</span></span>  |<span data-ttu-id="af2ec-117">说明</span><span class="sxs-lookup"><span data-stu-id="af2ec-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="af2ec-118">0x80041020</span><span class="sxs-lookup"><span data-stu-id="af2ec-118">0x80041020</span></span> | <span data-ttu-id="af2ec-119">`ptr` 不是有效的类定义，无法生成新的实例。</span><span class="sxs-lookup"><span data-stu-id="af2ec-119">`ptr` is not a valid class definition and cannot spawn new instances.</span></span> <span data-ttu-id="af2ec-120">此方法可能是不完整的，也可能是通过调用 [PutClassWmi](putclasswmi.md)在 Windows 管理中注册的。</span><span class="sxs-lookup"><span data-stu-id="af2ec-120">Either it is incomplete or it has not been registered with Windows Management by calling [PutClassWmi](putclasswmi.md).</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="af2ec-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="af2ec-121">0x80041006</span></span> | <span data-ttu-id="af2ec-122">没有足够的可用内存来完成该操作。</span><span class="sxs-lookup"><span data-stu-id="af2ec-122">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="af2ec-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="af2ec-123">0x80041008</span></span> | <span data-ttu-id="af2ec-124">`ppNewClass` 为 `null`。</span><span class="sxs-lookup"><span data-stu-id="af2ec-124">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="af2ec-125">0</span><span class="sxs-lookup"><span data-stu-id="af2ec-125">0</span></span> | <span data-ttu-id="af2ec-126">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="af2ec-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="af2ec-127">注解</span><span class="sxs-lookup"><span data-stu-id="af2ec-127">Remarks</span></span>

<span data-ttu-id="af2ec-128">此函数包装对 [IWbemClassObject：： SpawnInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance) 方法的调用。</span><span class="sxs-lookup"><span data-stu-id="af2ec-128">This function wraps a call to the [IWbemClassObject::SpawnInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance) method.</span></span>

<span data-ttu-id="af2ec-129">`ptr` 必须是从 Windows Management 获取的类定义。</span><span class="sxs-lookup"><span data-stu-id="af2ec-129">`ptr` must be a class definition obtained from Windows Management.</span></span> <span data-ttu-id="af2ec-130"> (请注意，支持从实例生成实例，但返回的实例为空。 ) 然后使用此类定义来创建新的实例。</span><span class="sxs-lookup"><span data-stu-id="af2ec-130">(Note that spawning an instance from an instance is supported but the returned instance is empty.) You then use this class definition to create new instances.</span></span> <span data-ttu-id="af2ec-131">如果要将实例写入 Windows 管理，则需要调用 [PutInstanceWmi](putinstancewmi.md) 函数。</span><span class="sxs-lookup"><span data-stu-id="af2ec-131">A call to the [PutInstanceWmi](putinstancewmi.md) function is required if you intend to write the instance to Windows Management.</span></span>

<span data-ttu-id="af2ec-132">返回的新对象 `ppNewClass` 将自动成为当前对象的子类。</span><span class="sxs-lookup"><span data-stu-id="af2ec-132">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="af2ec-133">不能重写此行为。</span><span class="sxs-lookup"><span data-stu-id="af2ec-133">This behavior cannot be overridden.</span></span> <span data-ttu-id="af2ec-134">无法创建子类 (派生类) 的其他方法。</span><span class="sxs-lookup"><span data-stu-id="af2ec-134">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="af2ec-135">要求</span><span class="sxs-lookup"><span data-stu-id="af2ec-135">Requirements</span></span>  

 <span data-ttu-id="af2ec-136">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="af2ec-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af2ec-137">**标头：** WMINet_Utils .idl</span><span class="sxs-lookup"><span data-stu-id="af2ec-137">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="af2ec-138">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="af2ec-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af2ec-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="af2ec-139">See also</span></span>

- [<span data-ttu-id="af2ec-140">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="af2ec-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
