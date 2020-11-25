---
title: GetHashFromHandle 函数
ms.date: 03/30/2017
api_name:
- GetHashFromHandle
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle function [.NET Framework strong naming]
ms.assetid: 9e00337f-b307-4602-9bc3-965a8dbf02cd
topic_type:
- apiref
ms.openlocfilehash: 904dcb707e704cfec2dba4e6587f7e3acaf7b538
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732321"
---
# <a name="gethashfromhandle-function"></a><span data-ttu-id="d183e-102">GetHashFromHandle 函数</span><span class="sxs-lookup"><span data-stu-id="d183e-102">GetHashFromHandle Function</span></span>

<span data-ttu-id="d183e-103">使用指定的哈希算法，生成具有指定文件句柄的文件内容的哈希。</span><span class="sxs-lookup"><span data-stu-id="d183e-103">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="d183e-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="d183e-104">This function has been deprecated.</span></span> <span data-ttu-id="d183e-105">改为使用 [ICLRStrongName：： GetHashFromHandle](../hosting/iclrstrongname-gethashfromhandle-method.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="d183e-105">Use the [ICLRStrongName::GetHashFromHandle](../hosting/iclrstrongname-gethashfromhandle-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d183e-106">语法</span><span class="sxs-lookup"><span data-stu-id="d183e-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d183e-107">参数</span><span class="sxs-lookup"><span data-stu-id="d183e-107">Parameters</span></span>  

 `hFile`  
 <span data-ttu-id="d183e-108">中要进行哈希处理的文件的句柄。</span><span class="sxs-lookup"><span data-stu-id="d183e-108">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="d183e-109">[in，out]指定哈希算法的常量。</span><span class="sxs-lookup"><span data-stu-id="d183e-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="d183e-110">对于默认算法，使用零。</span><span class="sxs-lookup"><span data-stu-id="d183e-110">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="d183e-111">弄返回的哈希缓冲区。</span><span class="sxs-lookup"><span data-stu-id="d183e-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="d183e-112">中请求的最大大小 `pbHash` 。</span><span class="sxs-lookup"><span data-stu-id="d183e-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="d183e-113">弄返回的的大小（以字节为单位） `pbHash` 。</span><span class="sxs-lookup"><span data-stu-id="d183e-113">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d183e-114">要求</span><span class="sxs-lookup"><span data-stu-id="d183e-114">Requirements</span></span>  

 <span data-ttu-id="d183e-115">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d183e-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d183e-116">**标头：** Stackexchange.redis.strongname</span><span class="sxs-lookup"><span data-stu-id="d183e-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="d183e-117">**库：** 作为中的资源包含 MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d183e-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d183e-118">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d183e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d183e-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d183e-119">See also</span></span>

- [<span data-ttu-id="d183e-120">GetHashFromHandle 方法</span><span class="sxs-lookup"><span data-stu-id="d183e-120">GetHashFromHandle Method</span></span>](../hosting/iclrstrongname-gethashfromhandle-method.md)
- [<span data-ttu-id="d183e-121">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="d183e-121">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
