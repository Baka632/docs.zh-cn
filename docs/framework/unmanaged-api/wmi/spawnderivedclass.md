---
title: 'SpawnDerivedClass 函数 (非托管 API 参考) '
description: SpawnDerivedClass 函数创建派生自对象的新对象。
ms.date: 11/06/2017
api_name:
- SpawnDerivedClass
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnDerivedClass
helpviewer_keywords:
- SpawnDerivedClass function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 8020dd851b6773e6c76c53892c4b2bc21e4261bb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716507"
---
# <a name="spawnderivedclass-function"></a><span data-ttu-id="02c6b-103">SpawnDerivedClass 函数</span><span class="sxs-lookup"><span data-stu-id="02c6b-103">SpawnDerivedClass function</span></span>

<span data-ttu-id="02c6b-104">从指定对象创建新派生的类对象。</span><span class="sxs-lookup"><span data-stu-id="02c6b-104">Creates a newly derived class object from a specified object.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="02c6b-105">语法</span><span class="sxs-lookup"><span data-stu-id="02c6b-105">Syntax</span></span>  
  
```cpp  
HRESULT SpawnDerivedClass (
   [in] int                  vFunc,
   [in] IWbemClassObject*    ptr,
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewClass);
```  

## <a name="parameters"></a><span data-ttu-id="02c6b-106">参数</span><span class="sxs-lookup"><span data-stu-id="02c6b-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="02c6b-107">中此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="02c6b-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="02c6b-108">中指向 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 实例的指针。</span><span class="sxs-lookup"><span data-stu-id="02c6b-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="02c6b-109">[in] 保留。</span><span class="sxs-lookup"><span data-stu-id="02c6b-109">[in] Reserved.</span></span> <span data-ttu-id="02c6b-110">此参数必须为0。</span><span class="sxs-lookup"><span data-stu-id="02c6b-110">This parameter must be 0.</span></span>

`ppNewClass`  
<span data-ttu-id="02c6b-111">弄接收指向新类定义对象的指针。</span><span class="sxs-lookup"><span data-stu-id="02c6b-111">[out] Receives the pointer to the new class definition object.</span></span> <span data-ttu-id="02c6b-112">如果发生错误，则不会返回新的对象，也不会 `ppNewClass` 将其保持不变。</span><span class="sxs-lookup"><span data-stu-id="02c6b-112">If an error occurs, a new object is not returned, and `ppNewClass` is left unmodified.</span></span> <span data-ttu-id="02c6b-113">它的值不能为 `null` 。</span><span class="sxs-lookup"><span data-stu-id="02c6b-113">Its value cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="02c6b-114">返回值</span><span class="sxs-lookup"><span data-stu-id="02c6b-114">Return value</span></span>

<span data-ttu-id="02c6b-115">此函数返回的以下值是在 *WbemCli* 头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="02c6b-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="02c6b-116">返回的常量</span><span class="sxs-lookup"><span data-stu-id="02c6b-116">Constant</span></span>  |<span data-ttu-id="02c6b-117">Value</span><span class="sxs-lookup"><span data-stu-id="02c6b-117">Value</span></span>  |<span data-ttu-id="02c6b-118">说明</span><span class="sxs-lookup"><span data-stu-id="02c6b-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="02c6b-119">0x80041001</span><span class="sxs-lookup"><span data-stu-id="02c6b-119">0x80041001</span></span> | <span data-ttu-id="02c6b-120">出现一般错误。</span><span class="sxs-lookup"><span data-stu-id="02c6b-120">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="02c6b-121">0x80041016</span><span class="sxs-lookup"><span data-stu-id="02c6b-121">0x80041016</span></span> | <span data-ttu-id="02c6b-122">请求了无效的操作，例如，从实例中生成类。</span><span class="sxs-lookup"><span data-stu-id="02c6b-122">An invalid operation, such as spawning a class from an instance, was requested.</span></span> |
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="02c6b-123">源类未完全定义或未在 Windows 管理中注册，因此不允许使用新的派生类。</span><span class="sxs-lookup"><span data-stu-id="02c6b-123">The source class was not completely defined or registered with Windows Management, so a new derived class is not permitted.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="02c6b-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="02c6b-124">0x80041006</span></span> | <span data-ttu-id="02c6b-125">没有足够的可用内存来完成该操作。</span><span class="sxs-lookup"><span data-stu-id="02c6b-125">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="02c6b-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="02c6b-126">0x80041008</span></span> | <span data-ttu-id="02c6b-127">`ppNewClass` 为 `null`。</span><span class="sxs-lookup"><span data-stu-id="02c6b-127">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="02c6b-128">0</span><span class="sxs-lookup"><span data-stu-id="02c6b-128">0</span></span> | <span data-ttu-id="02c6b-129">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="02c6b-129">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="02c6b-130">注解</span><span class="sxs-lookup"><span data-stu-id="02c6b-130">Remarks</span></span>

<span data-ttu-id="02c6b-131">此函数包装对 [IWbemClassObject：： SpawnDerivedClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) 方法的调用。</span><span class="sxs-lookup"><span data-stu-id="02c6b-131">This function wraps a call to the [IWbemClassObject::SpawnDerivedClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="02c6b-132">`ptr` 必须是成为衍生对象的父类的类定义。</span><span class="sxs-lookup"><span data-stu-id="02c6b-132">`ptr` must be a class definition that becomes the parent class of the spawned object.</span></span> <span data-ttu-id="02c6b-133">返回的对象将成为当前对象的子类。</span><span class="sxs-lookup"><span data-stu-id="02c6b-133">The returned object becomes a subclass of the current object.</span></span>

<span data-ttu-id="02c6b-134">返回的新对象 `ppNewClass` 将自动成为当前对象的子类。</span><span class="sxs-lookup"><span data-stu-id="02c6b-134">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="02c6b-135">不能重写此行为。</span><span class="sxs-lookup"><span data-stu-id="02c6b-135">This behavior cannot be overridden.</span></span> <span data-ttu-id="02c6b-136">无法创建子类 (派生类) 的其他方法。</span><span class="sxs-lookup"><span data-stu-id="02c6b-136">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="02c6b-137">要求</span><span class="sxs-lookup"><span data-stu-id="02c6b-137">Requirements</span></span>  

 <span data-ttu-id="02c6b-138">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="02c6b-138">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02c6b-139">**标头：** WMINet_Utils .idl</span><span class="sxs-lookup"><span data-stu-id="02c6b-139">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="02c6b-140">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="02c6b-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02c6b-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="02c6b-141">See also</span></span>

- [<span data-ttu-id="02c6b-142">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="02c6b-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
