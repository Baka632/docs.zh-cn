---
title: '下一个函数 (非托管 API 引用) '
description: Next 函数检索枚举中的下一个属性。
ms.date: 11/06/2017
api_name:
- Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Next
helpviewer_keywords:
- Next function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: c2a7fae32e82caae40a95bfdad10fa78082988ef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726777"
---
# <a name="next-function"></a><span data-ttu-id="93719-103">Next 函数</span><span class="sxs-lookup"><span data-stu-id="93719-103">Next function</span></span>

<span data-ttu-id="93719-104">检索枚举中的下一个属性，该属性以对 [endenumeration](beginenumeration.md)的调用开始。</span><span class="sxs-lookup"><span data-stu-id="93719-104">Retrieves the next property in an enumeration that begins with a call to [BeginEnumeration](beginenumeration.md).</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="93719-105">语法</span><span class="sxs-lookup"><span data-stu-id="93719-105">Syntax</span></span>

```cpp
HRESULT Next (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              lFlags,
   [out] BSTR*            pstrName,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor
);
```

## <a name="parameters"></a><span data-ttu-id="93719-106">参数</span><span class="sxs-lookup"><span data-stu-id="93719-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="93719-107">中此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="93719-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="93719-108">中指向 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 实例的指针。</span><span class="sxs-lookup"><span data-stu-id="93719-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`\
<span data-ttu-id="93719-109">[in] 保留。</span><span class="sxs-lookup"><span data-stu-id="93719-109">[in] Reserved.</span></span> <span data-ttu-id="93719-110">此参数必须为0。</span><span class="sxs-lookup"><span data-stu-id="93719-110">This parameter must be 0.</span></span>

`pstrName`\
<span data-ttu-id="93719-111">弄一个新 `BSTR` 的，它包含属性名称。</span><span class="sxs-lookup"><span data-stu-id="93719-111">[out] A new `BSTR` that contains the property name.</span></span> <span data-ttu-id="93719-112">`null`如果名称不是必需的，则可以将此参数设置为。</span><span class="sxs-lookup"><span data-stu-id="93719-112">You can set this parameter to `null` if the name is not required.</span></span>

`pVal`\
<span data-ttu-id="93719-113">弄 `VARIANT` 用属性的值填充的。</span><span class="sxs-lookup"><span data-stu-id="93719-113">[out] A `VARIANT` filled with the value of the property.</span></span> <span data-ttu-id="93719-114">`null`如果值不是必需的，则可以将此参数设置为。</span><span class="sxs-lookup"><span data-stu-id="93719-114">You can set this parameter to `null` if the value is not required.</span></span> <span data-ttu-id="93719-115">如果函数返回错误代码，则 `VARIANT` `pVal` 不会修改传递到的。</span><span class="sxs-lookup"><span data-stu-id="93719-115">If the function returns an error code, the `VARIANT` passed to `pVal` is left unmodified.</span></span>

`pvtType`\
<span data-ttu-id="93719-116">弄指向一个变量的指针， `CIMTYPE` 该变量 (`LONG`) 的属性的类型。</span><span class="sxs-lookup"><span data-stu-id="93719-116">[out] A pointer to a `CIMTYPE` variable (a `LONG` into which the type of the property is placed).</span></span> <span data-ttu-id="93719-117">此属性的值可以是 `VT_NULL_VARIANT` ，在这种情况下，需要确定属性的实际类型。</span><span class="sxs-lookup"><span data-stu-id="93719-117">The value of this property can be a `VT_NULL_VARIANT`, in which case it is necessary to determine the actual type of the property.</span></span> <span data-ttu-id="93719-118">此参数还可以为 `null` 。</span><span class="sxs-lookup"><span data-stu-id="93719-118">This parameter can also be `null`.</span></span>

`plFlavor`\
<span data-ttu-id="93719-119">[out] `null` 或一个值，该值接收有关属性的源的信息。</span><span class="sxs-lookup"><span data-stu-id="93719-119">[out] `null`, or a value that receives information on the origin of the property.</span></span> <span data-ttu-id="93719-120">有关可能的值，请参阅 [备注] 部分。</span><span class="sxs-lookup"><span data-stu-id="93719-120">See the [Remarks] section for possible values.</span></span>

## <a name="return-value"></a><span data-ttu-id="93719-121">返回值</span><span class="sxs-lookup"><span data-stu-id="93719-121">Return value</span></span>

<span data-ttu-id="93719-122">此函数返回的以下值是在 *WbemCli* 头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="93719-122">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="93719-123">返回的常量</span><span class="sxs-lookup"><span data-stu-id="93719-123">Constant</span></span>  |<span data-ttu-id="93719-124">Value</span><span class="sxs-lookup"><span data-stu-id="93719-124">Value</span></span>  |<span data-ttu-id="93719-125">说明</span><span class="sxs-lookup"><span data-stu-id="93719-125">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="93719-126">0x80041001</span><span class="sxs-lookup"><span data-stu-id="93719-126">0x80041001</span></span> | <span data-ttu-id="93719-127">出现一般错误。</span><span class="sxs-lookup"><span data-stu-id="93719-127">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="93719-128">0x80041008</span><span class="sxs-lookup"><span data-stu-id="93719-128">0x80041008</span></span> | <span data-ttu-id="93719-129">参数无效。</span><span class="sxs-lookup"><span data-stu-id="93719-129">A parameter is invalid.</span></span> |
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="93719-130">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="93719-130">0x8004101d</span></span> | <span data-ttu-id="93719-131">没有对函数的调用 [`BeginEnumeration`](beginenumeration.md) 。</span><span class="sxs-lookup"><span data-stu-id="93719-131">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="93719-132">0x80041006</span><span class="sxs-lookup"><span data-stu-id="93719-132">0x80041006</span></span> | <span data-ttu-id="93719-133">没有足够的内存可用于开始新的枚举。</span><span class="sxs-lookup"><span data-stu-id="93719-133">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="93719-134">0x80041015</span><span class="sxs-lookup"><span data-stu-id="93719-134">0x80041015</span></span> | <span data-ttu-id="93719-135">当前进程与 Windows Management 之间的远程过程调用失败。</span><span class="sxs-lookup"><span data-stu-id="93719-135">The remote procedure call between the current process and Windows Management failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="93719-136">0</span><span class="sxs-lookup"><span data-stu-id="93719-136">0</span></span> | <span data-ttu-id="93719-137">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="93719-137">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="93719-138">0x40005</span><span class="sxs-lookup"><span data-stu-id="93719-138">0x40005</span></span> | <span data-ttu-id="93719-139">枚举中没有更多属性。</span><span class="sxs-lookup"><span data-stu-id="93719-139">There are no more properties in the enumeration.</span></span> |

## <a name="remarks"></a><span data-ttu-id="93719-140">注解</span><span class="sxs-lookup"><span data-stu-id="93719-140">Remarks</span></span>

<span data-ttu-id="93719-141">此函数包装对 [IWbemClassObject：： Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-next) 方法的调用。</span><span class="sxs-lookup"><span data-stu-id="93719-141">This function wraps a call to the [IWbemClassObject::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-next) method.</span></span>

<span data-ttu-id="93719-142">此方法还返回系统属性。</span><span class="sxs-lookup"><span data-stu-id="93719-142">This method also returns system properties.</span></span>

<span data-ttu-id="93719-143">如果属性的基础类型是对象路径、日期或时间或其他特殊类型，则返回的类型不包含足够的信息。</span><span class="sxs-lookup"><span data-stu-id="93719-143">If the underlying type of the property is an object path, a date or time, or another special type, then the returned type does not contain enough information.</span></span> <span data-ttu-id="93719-144">调用方必须检查 `CIMTYPE` 指定属性的，以确定该属性是对象引用、日期、时间还是其他特殊类型。</span><span class="sxs-lookup"><span data-stu-id="93719-144">The caller must examine the `CIMTYPE` for the specified property to determine if the property is an object reference, a date or time, or another special type.</span></span>

<span data-ttu-id="93719-145">如果不 `plFlavor` 为 `null` ，则 `LONG` 值接收有关属性的来源的信息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="93719-145">If `plFlavor` is not `null`, the `LONG` value receives information about the origin of the property, as follows:</span></span>

|<span data-ttu-id="93719-146">返回的常量</span><span class="sxs-lookup"><span data-stu-id="93719-146">Constant</span></span>  |<span data-ttu-id="93719-147">Value</span><span class="sxs-lookup"><span data-stu-id="93719-147">Value</span></span>  |<span data-ttu-id="93719-148">说明</span><span class="sxs-lookup"><span data-stu-id="93719-148">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | <span data-ttu-id="93719-149">0x40</span><span class="sxs-lookup"><span data-stu-id="93719-149">0x40</span></span> | <span data-ttu-id="93719-150">属性为标准系统属性。</span><span class="sxs-lookup"><span data-stu-id="93719-150">The property is a standard system property.</span></span> |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | <span data-ttu-id="93719-151">0x20</span><span class="sxs-lookup"><span data-stu-id="93719-151">0x20</span></span> | <span data-ttu-id="93719-152">对于类：属性是从父类继承的。</span><span class="sxs-lookup"><span data-stu-id="93719-152">For a class: The property is inherited from the parent class.</span></span> <br> <span data-ttu-id="93719-153">对于实例：从父类继承的属性未被实例修改。</span><span class="sxs-lookup"><span data-stu-id="93719-153">For an instance: The property, while inherited from the parent class, has not been modified by the instance.</span></span>  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | <span data-ttu-id="93719-154">0</span><span class="sxs-lookup"><span data-stu-id="93719-154">0</span></span> | <span data-ttu-id="93719-155">对于类：属性属于派生类。</span><span class="sxs-lookup"><span data-stu-id="93719-155">For a class: The property belongs to the derived class.</span></span> <br> <span data-ttu-id="93719-156">对于实例：属性由实例进行修改;也就是说，提供了一个值，或者添加或修改了限定符。</span><span class="sxs-lookup"><span data-stu-id="93719-156">For an instance: The property is modified by the instance; that is, a value was supplied, or a qualifier was added or modified.</span></span> |

## <a name="requirements"></a><span data-ttu-id="93719-157">要求</span><span class="sxs-lookup"><span data-stu-id="93719-157">Requirements</span></span>

<span data-ttu-id="93719-158">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="93719-158">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="93719-159">**标头：** WMINet_Utils .idl</span><span class="sxs-lookup"><span data-stu-id="93719-159">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="93719-160">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="93719-160">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="93719-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="93719-161">See also</span></span>

- [<span data-ttu-id="93719-162">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="93719-162">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
