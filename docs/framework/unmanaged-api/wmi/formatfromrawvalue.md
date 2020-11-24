---
title: 'FormatFromRawValue 函数 (非托管 API 参考) '
description: FormatFromRawValue 函数将原始性能数据转换为指定格式。
ms.date: 11/21/2017
api_name:
- FormatFromRawValue
api_location:
- PerfCounter.dll
api_type:
- DLLExport
f1_keywords:
- FormatFromRawValue
helpviewer_keywords:
- FormatFromRawValue function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: e678aca5baf82c07ec9fc5c85cef22630af5ab0a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672326"
---
# <a name="formatfromrawvalue-function"></a><span data-ttu-id="49f75-103">FormatFromRawValue 函数</span><span class="sxs-lookup"><span data-stu-id="49f75-103">FormatFromRawValue function</span></span>

<span data-ttu-id="49f75-104">如果格式转换是基于时间的，则将一个或两个原始性能数据值转换为指定格式。</span><span class="sxs-lookup"><span data-stu-id="49f75-104">Converts one raw performance data value to the specified format, or two raw performance data values if the format conversion is time-based.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="49f75-105">语法</span><span class="sxs-lookup"><span data-stu-id="49f75-105">Syntax</span></span>

```cpp
int FormatFromRawValue (
   [in] uint                    dwCounterType,
   [in] uint                    dwFormat,
   [in] long*                   pTimeBase,
   [in] PDH_RAW_COUNTER*        pRawValue1,
   [in] PDH_RAW_COUNTER*        pRawValue2,
   [out] PDH_FMT_COUNTERVALUE*  pFmtValue
);
```

## <a name="parameters"></a><span data-ttu-id="49f75-106">参数</span><span class="sxs-lookup"><span data-stu-id="49f75-106">Parameters</span></span>

`dwCounterType`\
<span data-ttu-id="49f75-107">中计数器类型。</span><span class="sxs-lookup"><span data-stu-id="49f75-107">[in] The counter type.</span></span> <span data-ttu-id="49f75-108">有关计数器类型的列表，请参阅 [WMI 性能计数器类型](/windows/desktop/WmiSdk/wmi-performance-counter-types)。</span><span class="sxs-lookup"><span data-stu-id="49f75-108">For a list of counter types, see [WMI Performance Counter Types](/windows/desktop/WmiSdk/wmi-performance-counter-types).</span></span> <span data-ttu-id="49f75-109">`dwCounterType` 可以是除和以外的任何计数器类型 `PERF_LARGE_RAW_FRACTION` `PERF_LARGE_RAW_BASE` 。</span><span class="sxs-lookup"><span data-stu-id="49f75-109">`dwCounterType` can be any counter type except for `PERF_LARGE_RAW_FRACTION` and `PERF_LARGE_RAW_BASE`.</span></span>

`dwFormat`\
<span data-ttu-id="49f75-110">中原始性能数据的转换格式。</span><span class="sxs-lookup"><span data-stu-id="49f75-110">[in] The format to which to convert the raw performance data.</span></span> <span data-ttu-id="49f75-111">可以为下列值之一：</span><span class="sxs-lookup"><span data-stu-id="49f75-111">It can be one of the following values:</span></span>

|<span data-ttu-id="49f75-112">返回的常量</span><span class="sxs-lookup"><span data-stu-id="49f75-112">Constant</span></span>  |<span data-ttu-id="49f75-113">Value</span><span class="sxs-lookup"><span data-stu-id="49f75-113">Value</span></span>  |<span data-ttu-id="49f75-114">说明</span><span class="sxs-lookup"><span data-stu-id="49f75-114">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |<span data-ttu-id="49f75-115">0x00000200</span><span class="sxs-lookup"><span data-stu-id="49f75-115">0x00000200</span></span> | <span data-ttu-id="49f75-116">将计算的值作为双精度浮点值返回。</span><span class="sxs-lookup"><span data-stu-id="49f75-116">Return the calculated value as a double-precision floating point value.</span></span> |
| `PDH_FMT_LARGE` | <span data-ttu-id="49f75-117">0x00000400</span><span class="sxs-lookup"><span data-stu-id="49f75-117">0x00000400</span></span> | <span data-ttu-id="49f75-118">将计算的值作为64位整数返回。</span><span class="sxs-lookup"><span data-stu-id="49f75-118">Return the calculated value as a 64-bit integer.</span></span> |
| `PDH_FMT_LONG` | <span data-ttu-id="49f75-119">0x00000100</span><span class="sxs-lookup"><span data-stu-id="49f75-119">0x00000100</span></span> | <span data-ttu-id="49f75-120">将计算的值作为32位整数返回。</span><span class="sxs-lookup"><span data-stu-id="49f75-120">Return the calculated value as a 32-bit integer.</span></span> |

<span data-ttu-id="49f75-121">先前的值之一可以运算以下缩放标志之一：</span><span class="sxs-lookup"><span data-stu-id="49f75-121">One of the previous values can be ORed with one of the following scaling flags:</span></span>

|<span data-ttu-id="49f75-122">返回的常量</span><span class="sxs-lookup"><span data-stu-id="49f75-122">Constant</span></span>  |<span data-ttu-id="49f75-123">Value</span><span class="sxs-lookup"><span data-stu-id="49f75-123">Value</span></span>  |<span data-ttu-id="49f75-124">说明</span><span class="sxs-lookup"><span data-stu-id="49f75-124">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | <span data-ttu-id="49f75-125">0x00001000</span><span class="sxs-lookup"><span data-stu-id="49f75-125">0x00001000</span></span> | <span data-ttu-id="49f75-126">不要应用计数器的缩放系数。</span><span class="sxs-lookup"><span data-stu-id="49f75-126">Do not apply the counter's scaling factors.</span></span> |
| `PDH_FMT_1000` | <span data-ttu-id="49f75-127">0x00002000</span><span class="sxs-lookup"><span data-stu-id="49f75-127">0x00002000</span></span> | <span data-ttu-id="49f75-128">将最终值乘以1000。</span><span class="sxs-lookup"><span data-stu-id="49f75-128">Multiply the final value by 1,000.</span></span> |

`pTimeBase`\
<span data-ttu-id="49f75-129">中如果格式转换需要，则为指向时间基准的指针。</span><span class="sxs-lookup"><span data-stu-id="49f75-129">[in] A pointer to the time base, if necessary for the format conversion.</span></span> <span data-ttu-id="49f75-130">如果格式转换不需要时间基准信息，则忽略此参数的值。</span><span class="sxs-lookup"><span data-stu-id="49f75-130">If time base information is not necessary for the format conversion, the value of this parameter is ignored.</span></span>

`pRawValue1`\
<span data-ttu-id="49f75-131">中指向 [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) 结构的指针，该结构表示原始性能值。</span><span class="sxs-lookup"><span data-stu-id="49f75-131">[in] A pointer to a [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) structure that represents a raw performance value.</span></span>

`pRawValue2`\
<span data-ttu-id="49f75-132">中指向 [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) 结构的指针，该结构表示第二个原始性能值。</span><span class="sxs-lookup"><span data-stu-id="49f75-132">[in] A pointer to a [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) structure that represents a second raw performance value.</span></span> <span data-ttu-id="49f75-133">如果不需要第二个原始性能值，则此参数应为 `null` 。</span><span class="sxs-lookup"><span data-stu-id="49f75-133">If a second raw performance value is not necessary, this parameter should be `null`.</span></span>

`pFmtValue`\
<span data-ttu-id="49f75-134">弄指向 [`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue) 结构的指针，该结构接收格式化的性能值。</span><span class="sxs-lookup"><span data-stu-id="49f75-134">[out] A pointer to a [`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue) structure that receives the formatted performance value.</span></span>

## <a name="return-value"></a><span data-ttu-id="49f75-135">返回值</span><span class="sxs-lookup"><span data-stu-id="49f75-135">Return value</span></span>

<span data-ttu-id="49f75-136">此函数返回以下值：</span><span class="sxs-lookup"><span data-stu-id="49f75-136">The following values are returned by this function:</span></span>

|<span data-ttu-id="49f75-137">返回的常量</span><span class="sxs-lookup"><span data-stu-id="49f75-137">Constant</span></span>  |<span data-ttu-id="49f75-138">Value</span><span class="sxs-lookup"><span data-stu-id="49f75-138">Value</span></span>  |<span data-ttu-id="49f75-139">说明</span><span class="sxs-lookup"><span data-stu-id="49f75-139">Description</span></span>  |
|---------|---------|---------|
| `ERROR_SUCCESS` | <span data-ttu-id="49f75-140">0</span><span class="sxs-lookup"><span data-stu-id="49f75-140">0</span></span> | <span data-ttu-id="49f75-141">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="49f75-141">The function call is successful.</span></span> |
| `PDH_INVALID_ARGUMENT` | <span data-ttu-id="49f75-142">0xC0000BBD</span><span class="sxs-lookup"><span data-stu-id="49f75-142">0xC0000BBD</span></span> | <span data-ttu-id="49f75-143">必需的参数缺失或不正确。</span><span class="sxs-lookup"><span data-stu-id="49f75-143">A required argument is missing or incorrect.</span></span> |
| `PDH_INVALID_HANDLE` | <span data-ttu-id="49f75-144">0xC0000BBC</span><span class="sxs-lookup"><span data-stu-id="49f75-144">0xC0000BBC</span></span> | <span data-ttu-id="49f75-145">句柄不是有效的 PDH 对象。</span><span class="sxs-lookup"><span data-stu-id="49f75-145">The handle is not a valid PDH object.</span></span> |

## <a name="remarks"></a><span data-ttu-id="49f75-146">注解</span><span class="sxs-lookup"><span data-stu-id="49f75-146">Remarks</span></span>

<span data-ttu-id="49f75-147">此函数包装对 [FormatFromRawValue](/previous-versions/ms231047(v=vs.85)) 函数的调用。</span><span class="sxs-lookup"><span data-stu-id="49f75-147">This function wraps a call to the [FormatFromRawValue](/previous-versions/ms231047(v=vs.85)) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="49f75-148">要求</span><span class="sxs-lookup"><span data-stu-id="49f75-148">Requirements</span></span>

 <span data-ttu-id="49f75-149">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="49f75-149">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="49f75-150">**库：** PerfCounter.dll</span><span class="sxs-lookup"><span data-stu-id="49f75-150">**Library:** PerfCounter.dll</span></span>

 <span data-ttu-id="49f75-151">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="49f75-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="49f75-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="49f75-152">See also</span></span>

- [<span data-ttu-id="49f75-153">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="49f75-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
