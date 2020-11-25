---
title: CreateDebuggingInterfaceFromVersion 函数
ms.date: 03/30/2017
api_name:
- CreateDebuggingInterfaceFromVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function [.NET Framework hosting]
ms.assetid: a746a849-463c-44f5-a2f0-9e812ed8bcc3
topic_type:
- apiref
ms.openlocfilehash: b68fbc713374642c9f55d49ee51a88c5785cf4b2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727869"
---
# <a name="createdebugginginterfacefromversion-function"></a><span data-ttu-id="bbf76-102">CreateDebuggingInterfaceFromVersion 函数</span><span class="sxs-lookup"><span data-stu-id="bbf76-102">CreateDebuggingInterfaceFromVersion Function</span></span>

<span data-ttu-id="bbf76-103">基于指定的版本信息创建 [ICorDebug](../debugging/icordebug-interface.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="bbf76-103">Creates an [ICorDebug](../debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 <span data-ttu-id="bbf76-104">此函数在 .NET Framework 4 中已过时。</span><span class="sxs-lookup"><span data-stu-id="bbf76-104">This function is obsolete in the .NET Framework 4.</span></span> <span data-ttu-id="bbf76-105">相反，若要获取公共语言运行时的接口 (CLR) 2.0，请使用 [ICLRRuntimeInfo：： GetInterface](iclrruntimeinfo-getinterface-method.md) 方法并指定类标识符 CLSID_CLRDebuggingLegacy 和接口标识符 IID_ICorDebug。</span><span class="sxs-lookup"><span data-stu-id="bbf76-105">Instead, to get an interface for the common language runtime (CLR) 2.0, use the [ICLRRuntimeInfo::GetInterface](iclrruntimeinfo-getinterface-method.md) method and specify the class identifier CLSID_CLRDebuggingLegacy and the interface identifier IID_ICorDebug.</span></span> <span data-ttu-id="bbf76-106">若要获取 CLR 4 或更高版本的接口，请调用 [CLRCreateInstance](clrcreateinstance-function.md) 函数并指定类标识符 CLSID_CLRDebugging 和接口标识符 IID_ICLRDebugging。</span><span class="sxs-lookup"><span data-stu-id="bbf76-106">To get an interface for CLR 4 or later, call the [CLRCreateInstance](clrcreateinstance-function.md) function and specify the class identifier CLSID_CLRDebugging and the interface identifier IID_ICLRDebugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbf76-107">语法</span><span class="sxs-lookup"><span data-stu-id="bbf76-107">Syntax</span></span>  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,
    [in]  LPCWSTR  szDebuggeeVersion,
    [out] IUnknown **ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bbf76-108">参数</span><span class="sxs-lookup"><span data-stu-id="bbf76-108">Parameters</span></span>  

 `iDebuggerVersion`  
 <span data-ttu-id="bbf76-109">中调试器所需的的版本 `ICorDebug` 。</span><span class="sxs-lookup"><span data-stu-id="bbf76-109">[in] The version of `ICorDebug` that is expected by the debugger.</span></span> <span data-ttu-id="bbf76-110">有关有效值，请参阅 [CorDebugInterfaceVersion](../debugging/cordebuginterfaceversion-enumeration.md) 枚举。</span><span class="sxs-lookup"><span data-stu-id="bbf76-110">See the [CorDebugInterfaceVersion](../debugging/cordebuginterfaceversion-enumeration.md) enumeration for valid values.</span></span>  
  
 `szDebuggeeVersion`  
 <span data-ttu-id="bbf76-111">中与要调试的应用程序或进程关联的公共语言运行时版本。</span><span class="sxs-lookup"><span data-stu-id="bbf76-111">[in] The common language runtime version associated with the application or process to be debugged.</span></span> <span data-ttu-id="bbf76-112">有关检索此值的信息，请参阅 [GetVersionFromProcess](getversionfromprocess-function.md) 或 [GetRequestedRuntimeVersion](getrequestedruntimeversion-function.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="bbf76-112">See the [GetVersionFromProcess](getversionfromprocess-function.md) or [GetRequestedRuntimeVersion](getrequestedruntimeversion-function.md) method for information on retrieving this value.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="bbf76-113">弄接收指向对象的指针的位置 `ICorDebug` 。</span><span class="sxs-lookup"><span data-stu-id="bbf76-113">[out] The location that receives a pointer to the `ICorDebug` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bbf76-114">返回值</span><span class="sxs-lookup"><span data-stu-id="bbf76-114">Return Value</span></span>  

 <span data-ttu-id="bbf76-115">除以下值外，此方法还返回 Winerror.h 文件中定义的标准 COM 错误代码。</span><span class="sxs-lookup"><span data-stu-id="bbf76-115">This method returns standard COM error codes as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="bbf76-116">返回代码</span><span class="sxs-lookup"><span data-stu-id="bbf76-116">Return code</span></span>|<span data-ttu-id="bbf76-117">说明</span><span class="sxs-lookup"><span data-stu-id="bbf76-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="bbf76-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="bbf76-118">S_OK</span></span>|<span data-ttu-id="bbf76-119">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="bbf76-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="bbf76-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="bbf76-120">E_INVALIDARG</span></span>|<span data-ttu-id="bbf76-121">`szDebuggeeVersion` 或 `ppCordb` 为 null，或者版本字符串不正确。</span><span class="sxs-lookup"><span data-stu-id="bbf76-121">`szDebuggeeVersion` or `ppCordb` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bbf76-122">注解</span><span class="sxs-lookup"><span data-stu-id="bbf76-122">Remarks</span></span>  

 <span data-ttu-id="bbf76-123">`szDebuggeeVersion`参数映射到 MSCorDbi.dll 的相应版本。</span><span class="sxs-lookup"><span data-stu-id="bbf76-123">The `szDebuggeeVersion` parameter maps to the corresponding version of MSCorDbi.dll.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbf76-124">要求</span><span class="sxs-lookup"><span data-stu-id="bbf76-124">Requirements</span></span>  

 <span data-ttu-id="bbf76-125">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bbf76-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbf76-126">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="bbf76-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bbf76-127">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bbf76-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bbf76-128">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbf76-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbf76-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bbf76-129">See also</span></span>

- [<span data-ttu-id="bbf76-130">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="bbf76-130">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
