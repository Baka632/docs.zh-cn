---
title: 'BlessIWbemServicesObject 函数 (非托管 API 参考) '
description: BlessIWbemServicesObject 函数指示用户凭据是否允许访问 IWbemServices 对象
ms.date: 11/06/2017
api_name:
- BlessIWbemServicesObject
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BlessIWbemServicesObject
helpviewer_keywords:
- BlessIWbemServicesObject function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 1aab2076f57f938715a3e65481a3540dc52279c6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719744"
---
# <a name="blessiwbemservicesobject-function"></a><span data-ttu-id="464ba-103">BlessIWbemServicesObject 函数</span><span class="sxs-lookup"><span data-stu-id="464ba-103">BlessIWbemServicesObject function</span></span>

<span data-ttu-id="464ba-104">指示用户凭据是否允许访问指定的 [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) 对象。</span><span class="sxs-lookup"><span data-stu-id="464ba-104">Indicates whether the user credentials permit access to a specified [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="464ba-105">语法</span><span class="sxs-lookup"><span data-stu-id="464ba-105">Syntax</span></span>

```cpp
HRESULT BlessIWbemServicesObject (
   [in] IUnknown* pIUnknown,
   [in] BSTR strUser,
   [in] BSTR strPassword,
   [in] BSTR strAuthority,
   [in] DWORD impLevel,
   [in] DWORD authnLevel
);
```

## <a name="parameters"></a><span data-ttu-id="464ba-106">参数</span><span class="sxs-lookup"><span data-stu-id="464ba-106">Parameters</span></span>

`pIWbemServices`\
<span data-ttu-id="464ba-107">中指向 WMI 服务对象的指针。</span><span class="sxs-lookup"><span data-stu-id="464ba-107">[in] A pointer to a WMI service object.</span></span>

`strUser`\
<span data-ttu-id="464ba-108">中用户名。</span><span class="sxs-lookup"><span data-stu-id="464ba-108">[in] The user name.</span></span>

`strPassword`\
<span data-ttu-id="464ba-109">中与关联的密码 `strUser` 。</span><span class="sxs-lookup"><span data-stu-id="464ba-109">[in] The password associated with `strUser`.</span></span>

`strAuthority`\
<span data-ttu-id="464ba-110">中用户的域名。</span><span class="sxs-lookup"><span data-stu-id="464ba-110">[in] The domain name of the user.</span></span> <span data-ttu-id="464ba-111">有关详细信息，请参阅 [ConnectServerWmi](connectserverwmi.md) 函数。</span><span class="sxs-lookup"><span data-stu-id="464ba-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`impLevel`\
<span data-ttu-id="464ba-112">中模拟级别。</span><span class="sxs-lookup"><span data-stu-id="464ba-112">[in] The impersonation level.</span></span>

`authnLevel`\
<span data-ttu-id="464ba-113">中授权级别。</span><span class="sxs-lookup"><span data-stu-id="464ba-113">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="464ba-114">返回值</span><span class="sxs-lookup"><span data-stu-id="464ba-114">Return value</span></span>

<span data-ttu-id="464ba-115">此函数返回的以下值是在 *winerror.h* 头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="464ba-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="464ba-116">返回的常量</span><span class="sxs-lookup"><span data-stu-id="464ba-116">Constant</span></span>  |<span data-ttu-id="464ba-117">Value</span><span class="sxs-lookup"><span data-stu-id="464ba-117">Value</span></span>  |<span data-ttu-id="464ba-118">说明</span><span class="sxs-lookup"><span data-stu-id="464ba-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="464ba-119">0x80070057</span><span class="sxs-lookup"><span data-stu-id="464ba-119">0x80070057</span></span> | <span data-ttu-id="464ba-120">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="464ba-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="464ba-121">0x80004003</span><span class="sxs-lookup"><span data-stu-id="464ba-121">0x80004003</span></span> | <span data-ttu-id="464ba-122">`pIWbemServices` 为 `null`。</span><span class="sxs-lookup"><span data-stu-id="464ba-122">`pIWbemServices` is `null`.</span></span> |
| `E_FAIL` | <span data-ttu-id="464ba-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="464ba-123">0x80000008</span></span> | <span data-ttu-id="464ba-124">发生了未知错误。</span><span class="sxs-lookup"><span data-stu-id="464ba-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="464ba-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="464ba-125">0x80000002</span></span> | <span data-ttu-id="464ba-126">内存不足，无法执行此操作。</span><span class="sxs-lookup"><span data-stu-id="464ba-126">Insufficient memory is available to perform the operation.</span></span> |
| `S_OK` | <span data-ttu-id="464ba-127">0</span><span class="sxs-lookup"><span data-stu-id="464ba-127">0</span></span> | <span data-ttu-id="464ba-128">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="464ba-128">The function call was successful.</span></span> |

## <a name="requirements"></a><span data-ttu-id="464ba-129">要求</span><span class="sxs-lookup"><span data-stu-id="464ba-129">Requirements</span></span>

 <span data-ttu-id="464ba-130">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="464ba-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="464ba-131">**标头：** WMINet_Utils .idl</span><span class="sxs-lookup"><span data-stu-id="464ba-131">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="464ba-132">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="464ba-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="464ba-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="464ba-133">See also</span></span>

- [<span data-ttu-id="464ba-134">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="464ba-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
