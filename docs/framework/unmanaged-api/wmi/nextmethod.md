---
title: 'NextMethod 函数 (非托管 API 参考) '
description: NextMethod 函数检索枚举中的下一个方法。
ms.date: 11/06/2017
api_name:
- NextMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- NextMethod
helpviewer_keywords:
- NextMethod function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: a0466aee47b0a6142870640c78b43f49e221ac2b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726764"
---
# <a name="nextmethod-function"></a><span data-ttu-id="fe943-103">NextMethod 函数</span><span class="sxs-lookup"><span data-stu-id="fe943-103">NextMethod function</span></span>

<span data-ttu-id="fe943-104">检索枚举中的下一个方法，该方法以对 [BeginMethodEnumeration](beginmethodenumeration.md)的调用开始。</span><span class="sxs-lookup"><span data-stu-id="fe943-104">Retrieves the next method in an enumeration that begins with a call to [BeginMethodEnumeration](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="fe943-105">语法</span><span class="sxs-lookup"><span data-stu-id="fe943-105">Syntax</span></span>  
  
```cpp  
HRESULT NextMethod (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LONG                lFlags,
   [out] BSTR*              pName,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature
);
```  

## <a name="parameters"></a><span data-ttu-id="fe943-106">参数</span><span class="sxs-lookup"><span data-stu-id="fe943-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="fe943-107">中此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="fe943-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="fe943-108">中指向 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 实例的指针。</span><span class="sxs-lookup"><span data-stu-id="fe943-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="fe943-109">[in] 保留。</span><span class="sxs-lookup"><span data-stu-id="fe943-109">[in] Reserved.</span></span> <span data-ttu-id="fe943-110">此参数必须为0。</span><span class="sxs-lookup"><span data-stu-id="fe943-110">This parameter must be 0.</span></span>

`pName`  
<span data-ttu-id="fe943-111">弄指向调用之前的指针 `null` 。</span><span class="sxs-lookup"><span data-stu-id="fe943-111">[out] A pointer that points to `null` prior to the call.</span></span> <span data-ttu-id="fe943-112">当函数返回时，为 `BSTR` 包含方法名称的新的地址。</span><span class="sxs-lookup"><span data-stu-id="fe943-112">When the function returns, the address of a new `BSTR` that contains the method name.</span></span>

`ppSignatureIn`  
<span data-ttu-id="fe943-113">弄一个指针，该指针接收指向包含方法的参数的 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 的指针 `in` 。</span><span class="sxs-lookup"><span data-stu-id="fe943-113">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `in` parameters for the method.</span></span>

`ppSignatureOut`  
<span data-ttu-id="fe943-114">弄一个指针，该指针接收指向包含方法的参数的 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 的指针 `out` 。</span><span class="sxs-lookup"><span data-stu-id="fe943-114">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `out` parameters for the method.</span></span>

## <a name="return-value"></a><span data-ttu-id="fe943-115">返回值</span><span class="sxs-lookup"><span data-stu-id="fe943-115">Return value</span></span>

<span data-ttu-id="fe943-116">此函数返回的以下值是在 *WbemCli* 头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="fe943-116">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="fe943-117">返回的常量</span><span class="sxs-lookup"><span data-stu-id="fe943-117">Constant</span></span>  |<span data-ttu-id="fe943-118">Value</span><span class="sxs-lookup"><span data-stu-id="fe943-118">Value</span></span>  |<span data-ttu-id="fe943-119">说明</span><span class="sxs-lookup"><span data-stu-id="fe943-119">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="fe943-120">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="fe943-120">0x8004101d</span></span> | <span data-ttu-id="fe943-121">没有对函数的调用 [`BeginEnumeration`](beginenumeration.md) 。</span><span class="sxs-lookup"><span data-stu-id="fe943-121">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="fe943-122">0</span><span class="sxs-lookup"><span data-stu-id="fe943-122">0</span></span> | <span data-ttu-id="fe943-123">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="fe943-123">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="fe943-124">0x40005</span><span class="sxs-lookup"><span data-stu-id="fe943-124">0x40005</span></span> | <span data-ttu-id="fe943-125">枚举中没有更多属性。</span><span class="sxs-lookup"><span data-stu-id="fe943-125">There are no more properties in the enumeration.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="fe943-126">注解</span><span class="sxs-lookup"><span data-stu-id="fe943-126">Remarks</span></span>

<span data-ttu-id="fe943-127">此函数包装对 [IWbemClassObject：： NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) 方法的调用。</span><span class="sxs-lookup"><span data-stu-id="fe943-127">This function wraps a call to the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

<span data-ttu-id="fe943-128">调用方通过调用 [BeginMethodEnumeration](beginmethodenumeration.md) 函数开始枚举序列，然后调用 [NextMethod] 函数直到函数返回 `WBEM_S_NO_MORE_DATA` 。</span><span class="sxs-lookup"><span data-stu-id="fe943-128">The caller begins the enumeration sequence by calling the [BeginMethodEnumeration](beginmethodenumeration.md) function, and then calls the [NextMethod] function until the function returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="fe943-129">或者，调用方可以通过调用 [EndMethodEnumeration](endmethodenumeration.md)来完成序列。</span><span class="sxs-lookup"><span data-stu-id="fe943-129">Optionally, the caller finishes the sequence by calling [EndMethodEnumeration](endmethodenumeration.md).</span></span> <span data-ttu-id="fe943-130">调用方可以在任何时间通过调用 [EndMethodEnumeration](endmethodenumeration.md) 来提前终止枚举。</span><span class="sxs-lookup"><span data-stu-id="fe943-130">The caller may terminate the enumeration early by calling [EndMethodEnumeration](endmethodenumeration.md) at any time.</span></span>

## <a name="example"></a><span data-ttu-id="fe943-131">示例</span><span class="sxs-lookup"><span data-stu-id="fe943-131">Example</span></span>

<span data-ttu-id="fe943-132">有关 c + + 示例，请参见 [IWbemClassObject：： NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) 方法。</span><span class="sxs-lookup"><span data-stu-id="fe943-132">For a C++ example, see the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="fe943-133">要求</span><span class="sxs-lookup"><span data-stu-id="fe943-133">Requirements</span></span>  

 <span data-ttu-id="fe943-134">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fe943-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe943-135">**标头：** WMINet_Utils .idl</span><span class="sxs-lookup"><span data-stu-id="fe943-135">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="fe943-136">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fe943-136">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe943-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fe943-137">See also</span></span>

- [<span data-ttu-id="fe943-138">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="fe943-138">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
