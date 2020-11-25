---
title: ICLRMetaHost::EnumerateInstalledRuntimes 方法
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.EnumerateInstalledRuntimes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::EnumerateInstalledRuntimes
helpviewer_keywords:
- ICLRMetaHost::EnumerateInstalledRuntimes method [.NET Framework hosting]
- EnumerateInstalledRuntimes method [.NET Framework hosting]
ms.assetid: 9e359384-0d3d-451c-807e-5d7fcebf2be7
topic_type:
- apiref
ms.openlocfilehash: f8f67edde7f99878429ca0bbd89aaf52336aa79c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730443"
---
# <a name="iclrmetahostenumerateinstalledruntimes-method"></a><span data-ttu-id="897e6-102">ICLRMetaHost::EnumerateInstalledRuntimes 方法</span><span class="sxs-lookup"><span data-stu-id="897e6-102">ICLRMetaHost::EnumerateInstalledRuntimes Method</span></span>

<span data-ttu-id="897e6-103">返回一个枚举，该枚举包含 (计算机上安装的 CLR) 的每个公共语言运行时版本的有效 [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) 接口。</span><span class="sxs-lookup"><span data-stu-id="897e6-103">Returns an enumeration that contains a valid [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface for each version of the common language runtime (CLR) that is installed on a computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="897e6-104">语法</span><span class="sxs-lookup"><span data-stu-id="897e6-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateInstalledRuntimes (  
    [out, retval] IEnumUnknown **ppEnumerator);  
```  
  
## <a name="parameters"></a><span data-ttu-id="897e6-105">参数</span><span class="sxs-lookup"><span data-stu-id="897e6-105">Parameters</span></span>  

 `ppEnumerator`  
 <span data-ttu-id="897e6-106">弄与计算机上安装的每个 CLR 版本相对应的 [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) 接口的枚举。</span><span class="sxs-lookup"><span data-stu-id="897e6-106">[out] An enumeration of [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interfaces corresponding to each version of the CLR that is installed on the computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="897e6-107">返回值</span><span class="sxs-lookup"><span data-stu-id="897e6-107">Return Value</span></span>  

 <span data-ttu-id="897e6-108">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="897e6-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="897e6-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="897e6-109">HRESULT</span></span>|<span data-ttu-id="897e6-110">说明</span><span class="sxs-lookup"><span data-stu-id="897e6-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="897e6-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="897e6-111">S_OK</span></span>|<span data-ttu-id="897e6-112">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="897e6-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="897e6-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="897e6-113">E_POINTER</span></span>|<span data-ttu-id="897e6-114">`ppEnumerator` 为 null。</span><span class="sxs-lookup"><span data-stu-id="897e6-114">`ppEnumerator` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="897e6-115">要求</span><span class="sxs-lookup"><span data-stu-id="897e6-115">Requirements</span></span>  

 <span data-ttu-id="897e6-116">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="897e6-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="897e6-117">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="897e6-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="897e6-118">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="897e6-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="897e6-119">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="897e6-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="897e6-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="897e6-120">See also</span></span>

- [<span data-ttu-id="897e6-121">ICLRMetaHost 接口</span><span class="sxs-lookup"><span data-stu-id="897e6-121">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="897e6-122">承载</span><span class="sxs-lookup"><span data-stu-id="897e6-122">Hosting</span></span>](index.md)
