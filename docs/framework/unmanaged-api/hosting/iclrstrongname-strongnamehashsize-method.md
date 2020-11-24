---
title: ICLRStrongName::StrongNameHashSize 方法
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameHashSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameHashSize
helpviewer_keywords:
- ICLRStrongName::StrongNameHashSize method [.NET Framework hosting]
- StrongNameHashSize method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 4a05ee56-08e4-4f3a-86a9-9b52083d5c0f
topic_type:
- apiref
ms.openlocfilehash: 6ee87fdbf75d4a07a7337a1c9fdc58a06191b992
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674810"
---
# <a name="iclrstrongnamestrongnamehashsize-method"></a><span data-ttu-id="bf5c8-102">ICLRStrongName::StrongNameHashSize 方法</span><span class="sxs-lookup"><span data-stu-id="bf5c8-102">ICLRStrongName::StrongNameHashSize Method</span></span>

<span data-ttu-id="bf5c8-103">使用指定的哈希算法获取哈希所需的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="bf5c8-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf5c8-104">语法</span><span class="sxs-lookup"><span data-stu-id="bf5c8-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf5c8-105">参数</span><span class="sxs-lookup"><span data-stu-id="bf5c8-105">Parameters</span></span>  

 `ulHashAlg`  
 <span data-ttu-id="bf5c8-106">中用于计算缓冲区大小的哈希算法。</span><span class="sxs-lookup"><span data-stu-id="bf5c8-106">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="bf5c8-107">弄返回的缓冲区大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="bf5c8-107">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bf5c8-108">返回值</span><span class="sxs-lookup"><span data-stu-id="bf5c8-108">Return Value</span></span>  

 <span data-ttu-id="bf5c8-109">`S_OK` 如果该方法已成功完成，则为;否则，表示失败的 HRESULT 值 (参阅) 列表的 [常见 HRESULT 值](/windows/win32/seccrypto/common-hresult-values) 。</span><span class="sxs-lookup"><span data-stu-id="bf5c8-109">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf5c8-110">要求</span><span class="sxs-lookup"><span data-stu-id="bf5c8-110">Requirements</span></span>  

 <span data-ttu-id="bf5c8-111">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bf5c8-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf5c8-112">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="bf5c8-112">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="bf5c8-113">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bf5c8-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bf5c8-114">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf5c8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf5c8-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bf5c8-115">See also</span></span>

- [<span data-ttu-id="bf5c8-116">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="bf5c8-116">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
