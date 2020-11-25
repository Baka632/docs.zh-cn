---
title: 'DeleteMethod 函数 (非托管 API 参考) '
description: DeleteMethod 函数从 CIM 类定义中删除指定的方法。
ms.date: 11/06/2017
api_name:
- DeleteMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- DeleteMethod
helpviewer_keywords:
- DeleteMethod function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 8ca58ed3510360b20577890055e4284869d1bf94
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708096"
---
# <a name="deletemethod-function"></a><span data-ttu-id="635c4-103">DeleteMethod 函数</span><span class="sxs-lookup"><span data-stu-id="635c4-103">DeleteMethod function</span></span>

<span data-ttu-id="635c4-104">从 CIM 类定义中删除指定的方法。</span><span class="sxs-lookup"><span data-stu-id="635c4-104">Deletes the specified method from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="635c4-105">语法</span><span class="sxs-lookup"><span data-stu-id="635c4-105">Syntax</span></span>  
  
```cpp  
HRESULT Delete (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName
);
```  

## <a name="parameters"></a><span data-ttu-id="635c4-106">参数</span><span class="sxs-lookup"><span data-stu-id="635c4-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="635c4-107">中此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="635c4-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="635c4-108">中指向 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 实例的指针。</span><span class="sxs-lookup"><span data-stu-id="635c4-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="635c4-109">中要从类表中删除的方法的名称。</span><span class="sxs-lookup"><span data-stu-id="635c4-109">[in] The name of the method to remove from the class table.</span></span> <span data-ttu-id="635c4-110">`wszName` 必须是指向有效的的指针 `LPCWSTR` 。</span><span class="sxs-lookup"><span data-stu-id="635c4-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="635c4-111">返回值</span><span class="sxs-lookup"><span data-stu-id="635c4-111">Return value</span></span>

<span data-ttu-id="635c4-112">此函数返回的以下值是在 *WbemCli* 头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="635c4-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="635c4-113">返回的常量</span><span class="sxs-lookup"><span data-stu-id="635c4-113">Constant</span></span>  |<span data-ttu-id="635c4-114">Value</span><span class="sxs-lookup"><span data-stu-id="635c4-114">Value</span></span>  |<span data-ttu-id="635c4-115">说明</span><span class="sxs-lookup"><span data-stu-id="635c4-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="635c4-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="635c4-116">0x80041002</span></span> | <span data-ttu-id="635c4-117">指定的方法不存在。</span><span class="sxs-lookup"><span data-stu-id="635c4-117">The specified method does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="635c4-118">0x80041006</span><span class="sxs-lookup"><span data-stu-id="635c4-118">0x80041006</span></span> | <span data-ttu-id="635c4-119">内存不足，无法完成此操作。</span><span class="sxs-lookup"><span data-stu-id="635c4-119">There is not enough memory to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="635c4-120">0</span><span class="sxs-lookup"><span data-stu-id="635c4-120">0</span></span> | <span data-ttu-id="635c4-121">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="635c4-121">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="635c4-122">注解</span><span class="sxs-lookup"><span data-stu-id="635c4-122">Remarks</span></span>

<span data-ttu-id="635c4-123">此函数包装对 [IWbemClassObject：:D eletemethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod) 方法的调用。</span><span class="sxs-lookup"><span data-stu-id="635c4-123">This function wraps a call to the [IWbemClassObject::DeleteMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod) method.</span></span>

<span data-ttu-id="635c4-124">指向 CIM 实例的 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 指针不支持方法删除。</span><span class="sxs-lookup"><span data-stu-id="635c4-124">Method deletion is not supported for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

## <a name="requirements"></a><span data-ttu-id="635c4-125">要求</span><span class="sxs-lookup"><span data-stu-id="635c4-125">Requirements</span></span>  

 <span data-ttu-id="635c4-126">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="635c4-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="635c4-127">**标头：** WMINet_Utils .idl</span><span class="sxs-lookup"><span data-stu-id="635c4-127">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="635c4-128">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="635c4-128">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="635c4-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="635c4-129">See also</span></span>

- [<span data-ttu-id="635c4-130">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="635c4-130">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
