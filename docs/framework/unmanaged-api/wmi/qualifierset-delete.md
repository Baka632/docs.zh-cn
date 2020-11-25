---
title: 'QualifierSet_Delete 函数 (非托管 API 参考) '
description: QualifierSet_Delete 函数按名称删除限定符。
ms.date: 11/06/2017
api_name:
- QualifierSet_Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Delete
helpviewer_keywords:
- QualifierSet_Delete function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 2000de77903c3dabb43116fa1700b4ed393aeb5a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721148"
---
# <a name="qualifierset_delete-function"></a><span data-ttu-id="c3452-103">QualifierSet_Delete 函数</span><span class="sxs-lookup"><span data-stu-id="c3452-103">QualifierSet_Delete function</span></span>

<span data-ttu-id="c3452-104">按名称删除指定限定符。</span><span class="sxs-lookup"><span data-stu-id="c3452-104">Deletes a specified qualifier by name.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="c3452-105">语法</span><span class="sxs-lookup"><span data-stu-id="c3452-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_Delete (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LPCWSTR              wszName
);
```  

## <a name="parameters"></a><span data-ttu-id="c3452-106">参数</span><span class="sxs-lookup"><span data-stu-id="c3452-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="c3452-107">中此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="c3452-107">[in] This parameter is unused.</span></span>

<span data-ttu-id="c3452-108">`ptr` 中指向 [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) 实例的指针。</span><span class="sxs-lookup"><span data-stu-id="c3452-108">`ptr` [in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

<span data-ttu-id="c3452-109">`wszName` 中要删除的限定符的名称。</span><span class="sxs-lookup"><span data-stu-id="c3452-109">`wszName` [in] The name of the qualifier to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="c3452-110">返回值</span><span class="sxs-lookup"><span data-stu-id="c3452-110">Return value</span></span>

<span data-ttu-id="c3452-111">此函数返回的以下值是在 *WbemCli* 头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="c3452-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="c3452-112">返回的常量</span><span class="sxs-lookup"><span data-stu-id="c3452-112">Constant</span></span>  |<span data-ttu-id="c3452-113">Value</span><span class="sxs-lookup"><span data-stu-id="c3452-113">Value</span></span>  |<span data-ttu-id="c3452-114">说明</span><span class="sxs-lookup"><span data-stu-id="c3452-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="c3452-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="c3452-115">0x80041008</span></span> | <span data-ttu-id="c3452-116">`wszName` 参数无效。</span><span class="sxs-lookup"><span data-stu-id="c3452-116">The `wszName` parameter is not valid.</span></span> |
|`WBEM_E_INVALID_OPERATION` | <span data-ttu-id="c3452-117">0x80041016</span><span class="sxs-lookup"><span data-stu-id="c3452-117">0x80041016</span></span> | <span data-ttu-id="c3452-118">删除此限定符是非法的。</span><span class="sxs-lookup"><span data-stu-id="c3452-118">Deleting this qualifier is illegal.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="c3452-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="c3452-119">0x80041002</span></span> | <span data-ttu-id="c3452-120">找不到指定的限定符。</span><span class="sxs-lookup"><span data-stu-id="c3452-120">The specified qualifier was not found.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="c3452-121">0</span><span class="sxs-lookup"><span data-stu-id="c3452-121">0</span></span> | <span data-ttu-id="c3452-122">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="c3452-122">The function call was successful.</span></span>  |
| `WBEM_S_RESET_TO_DEFAULT` | <span data-ttu-id="c3452-123">0x40002</span><span class="sxs-lookup"><span data-stu-id="c3452-123">0x40002</span></span> | <span data-ttu-id="c3452-124">已删除本地替代，并且父对象的原始限定符已恢复范围。</span><span class="sxs-lookup"><span data-stu-id="c3452-124">The local override was deleted and the original qualifier from the parent object has resumed scope.</span></span> |

## <a name="remarks"></a><span data-ttu-id="c3452-125">注解</span><span class="sxs-lookup"><span data-stu-id="c3452-125">Remarks</span></span>

<span data-ttu-id="c3452-126">此函数包装对 [IWbemQualifierSet：:D e) ](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) 方法的调用。</span><span class="sxs-lookup"><span data-stu-id="c3452-126">This function wraps a call to the [IWbemQualifierSet::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) method.</span></span>

<span data-ttu-id="c3452-127">由于限定符传播规则，特定限定符可能已从另一个对象继承，并且仅在当前类或实例中被重写。</span><span class="sxs-lookup"><span data-stu-id="c3452-127">Due to qualifier propagation rules, a particular qualifier may have been inherited from another object and merely overridden in the current class or instance.</span></span> <span data-ttu-id="c3452-128">在这种情况下，方法会将 `QualifierSet_Delete` 限定符重置为其原始的继承值。</span><span class="sxs-lookup"><span data-stu-id="c3452-128">In this case, the `QualifierSet_Delete` method resets the qualifier to its original inherited value.</span></span> <span data-ttu-id="c3452-129">在这种情况下，函数将返回状态代码 `WBEM_S_RESET_TO_DEFAULT` 。</span><span class="sxs-lookup"><span data-stu-id="c3452-129">The function in this case returns the status code `WBEM_S_RESET_TO_DEFAULT`.</span></span>

## <a name="requirements"></a><span data-ttu-id="c3452-130">要求</span><span class="sxs-lookup"><span data-stu-id="c3452-130">Requirements</span></span>  

 <span data-ttu-id="c3452-131">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c3452-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3452-132">**标头：** WMINet_Utils .idl</span><span class="sxs-lookup"><span data-stu-id="c3452-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="c3452-133">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c3452-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3452-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c3452-134">See also</span></span>

- [<span data-ttu-id="c3452-135">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="c3452-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
