---
title: ICLRStrongName::GetHashFromAssemblyFileW 方法
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromAssemblyFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW method [.NET Framework hosting]
- GetHashFromAssemblyFileW method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5d0b44a2-5a14-44a2-9a0e-e8682fd4e106
topic_type:
- apiref
ms.openlocfilehash: e94bfe6151ed42886355423a838f21e13748ec61
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685768"
---
# <a name="iclrstrongnamegethashfromassemblyfilew-method"></a><span data-ttu-id="05e9d-102">ICLRStrongName::GetHashFromAssemblyFileW 方法</span><span class="sxs-lookup"><span data-stu-id="05e9d-102">ICLRStrongName::GetHashFromAssemblyFileW Method</span></span>

<span data-ttu-id="05e9d-103">生成由 Unicode 字符串指定的文件内容的哈希。</span><span class="sxs-lookup"><span data-stu-id="05e9d-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05e9d-104">语法</span><span class="sxs-lookup"><span data-stu-id="05e9d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05e9d-105">参数</span><span class="sxs-lookup"><span data-stu-id="05e9d-105">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="05e9d-106">中要进行哈希处理的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="05e9d-106">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="05e9d-107">此参数必须是 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="05e9d-107">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="05e9d-108">[in，out]指定哈希算法的常量。</span><span class="sxs-lookup"><span data-stu-id="05e9d-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="05e9d-109">使用零作为默认哈希算法。</span><span class="sxs-lookup"><span data-stu-id="05e9d-109">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="05e9d-110">弄返回的哈希缓冲区。</span><span class="sxs-lookup"><span data-stu-id="05e9d-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="05e9d-111">中请求的最大大小 `pbHash` 。</span><span class="sxs-lookup"><span data-stu-id="05e9d-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="05e9d-112">弄返回的的大小（以字节为单位） `pbHash` 。</span><span class="sxs-lookup"><span data-stu-id="05e9d-112">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="05e9d-113">返回值</span><span class="sxs-lookup"><span data-stu-id="05e9d-113">Return Value</span></span>  

 <span data-ttu-id="05e9d-114">`S_OK` 如果该方法已成功完成，则为;否则，表示失败的 HRESULT 值 (参阅) 列表的 [常见 HRESULT 值](/windows/win32/seccrypto/common-hresult-values) 。</span><span class="sxs-lookup"><span data-stu-id="05e9d-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05e9d-115">要求</span><span class="sxs-lookup"><span data-stu-id="05e9d-115">Requirements</span></span>  

 <span data-ttu-id="05e9d-116">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="05e9d-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05e9d-117">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="05e9d-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="05e9d-118">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="05e9d-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="05e9d-119">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05e9d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05e9d-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="05e9d-120">See also</span></span>

- [<span data-ttu-id="05e9d-121">GetHashFromAssemblyFile 方法</span><span class="sxs-lookup"><span data-stu-id="05e9d-121">GetHashFromAssemblyFile Method</span></span>](iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="05e9d-122">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="05e9d-122">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
