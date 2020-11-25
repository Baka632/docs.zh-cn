---
title: ICLRRuntimeInfo::GetRuntimeDirectory 方法
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetRuntimeDirectory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetRuntimeDirectory
helpviewer_keywords:
- GetRuntimeDirectory method [.NET Framework hosting]
- ICLRRuntimeInfo::GetRuntimeDirectory method [.NET Framework hosting]
ms.assetid: 4401546e-4d48-453f-a1fb-b2ebda54df5c
topic_type:
- apiref
ms.openlocfilehash: 24679118e4255282f7da3ff8be2ce9c08250e181
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732042"
---
# <a name="iclrruntimeinfogetruntimedirectory-method"></a><span data-ttu-id="fc4f8-102">ICLRRuntimeInfo::GetRuntimeDirectory 方法</span><span class="sxs-lookup"><span data-stu-id="fc4f8-102">ICLRRuntimeInfo::GetRuntimeDirectory Method</span></span>

<span data-ttu-id="fc4f8-103">获取与此接口关联 (CLR) 的公共语言运行时的安装目录。</span><span class="sxs-lookup"><span data-stu-id="fc4f8-103">Gets the installation directory of the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="fc4f8-104">此方法取代了2.0、3.0 和 3.5 .NET Framework 版本中提供的 [GetCORSystemDirectory](getcorsystemdirectory-function.md) 函数。</span><span class="sxs-lookup"><span data-stu-id="fc4f8-104">This method supersedes the [GetCORSystemDirectory](getcorsystemdirectory-function.md) function provided in the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc4f8-105">语法</span><span class="sxs-lookup"><span data-stu-id="fc4f8-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRuntimeDirectory(  
[out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
[in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc4f8-106">参数</span><span class="sxs-lookup"><span data-stu-id="fc4f8-106">Parameters</span></span>  

 `pwzBuffer`  
 <span data-ttu-id="fc4f8-107">弄返回 CLR 安装目录。</span><span class="sxs-lookup"><span data-stu-id="fc4f8-107">[out] Returns the CLR installation directory.</span></span> <span data-ttu-id="fc4f8-108">安装路径是完全限定的;例如 "c:\windows\microsoft.net\framework\v1.0.3705 \\ "。</span><span class="sxs-lookup"><span data-stu-id="fc4f8-108">The installation path is fully qualified; for example, "c:\windows\microsoft.net\framework\v1.0.3705\\".</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="fc4f8-109">[in，out]指定的大小 `pwzBuffer` 以避免缓冲区溢出。</span><span class="sxs-lookup"><span data-stu-id="fc4f8-109">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="fc4f8-110">如果 `pwzBuffer` 为 null，则 `pchBuffer` 返回所需的大小 `pwzBuffer` 。</span><span class="sxs-lookup"><span data-stu-id="fc4f8-110">If `pwzBuffer` is null, `pchBuffer` returns the required size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fc4f8-111">返回值</span><span class="sxs-lookup"><span data-stu-id="fc4f8-111">Return Value</span></span>  

 <span data-ttu-id="fc4f8-112">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="fc4f8-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="fc4f8-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fc4f8-113">HRESULT</span></span>|<span data-ttu-id="fc4f8-114">说明</span><span class="sxs-lookup"><span data-stu-id="fc4f8-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fc4f8-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="fc4f8-115">S_OK</span></span>|<span data-ttu-id="fc4f8-116">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="fc4f8-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="fc4f8-117">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="fc4f8-117">E_POINTER</span></span>|<span data-ttu-id="fc4f8-118">`pwzBuffer` 或 `pchBuffer` 为 null。</span><span class="sxs-lookup"><span data-stu-id="fc4f8-118">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc4f8-119">备注</span><span class="sxs-lookup"><span data-stu-id="fc4f8-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc4f8-120">要求</span><span class="sxs-lookup"><span data-stu-id="fc4f8-120">Requirements</span></span>  

 <span data-ttu-id="fc4f8-121">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fc4f8-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc4f8-122">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="fc4f8-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="fc4f8-123">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fc4f8-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fc4f8-124">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc4f8-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc4f8-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fc4f8-125">See also</span></span>

- [<span data-ttu-id="fc4f8-126">ICLRRuntimeInfo 接口</span><span class="sxs-lookup"><span data-stu-id="fc4f8-126">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="fc4f8-127">承载</span><span class="sxs-lookup"><span data-stu-id="fc4f8-127">Hosting</span></span>](index.md)
