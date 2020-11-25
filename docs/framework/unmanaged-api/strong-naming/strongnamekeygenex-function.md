---
title: StrongNameKeyGenEx 函数
ms.date: 03/30/2017
api_name:
- StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGenEx
helpviewer_keywords:
- StrongNameKeyGenEx function [.NET Framework strong naming]
ms.assetid: 36bd10b9-9857-45f3-8d3b-0da091d6169e
topic_type:
- apiref
ms.openlocfilehash: f28ee5767997240018d182b8303e4f65be81c702
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708538"
---
# <a name="strongnamekeygenex-function"></a><span data-ttu-id="6ba42-102">StrongNameKeyGenEx 函数</span><span class="sxs-lookup"><span data-stu-id="6ba42-102">StrongNameKeyGenEx Function</span></span>

<span data-ttu-id="6ba42-103">使用指定的密钥大小生成新的公钥/私钥对，以便使用强名称。</span><span class="sxs-lookup"><span data-stu-id="6ba42-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
 <span data-ttu-id="6ba42-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="6ba42-104">This function has been deprecated.</span></span> <span data-ttu-id="6ba42-105">改为使用 [ICLRStrongName：： StrongNameKeyGenEx](../hosting/iclrstrongname-strongnamekeygenex-method.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="6ba42-105">Use the [ICLRStrongName::StrongNameKeyGenEx](../hosting/iclrstrongname-strongnamekeygenex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ba42-106">语法</span><span class="sxs-lookup"><span data-stu-id="6ba42-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ba42-107">参数</span><span class="sxs-lookup"><span data-stu-id="6ba42-107">Parameters</span></span>  

 `wszKeyContainer`  
 <span data-ttu-id="6ba42-108">中请求的密钥容器名称。</span><span class="sxs-lookup"><span data-stu-id="6ba42-108">[in] The requested key container name.</span></span> <span data-ttu-id="6ba42-109">`wszKeyContainer` 必须为非空字符串，或者为 null 以生成临时名称。</span><span class="sxs-lookup"><span data-stu-id="6ba42-109">`wszKeyContainer` must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="6ba42-110">中指定是否保留注册的密钥。</span><span class="sxs-lookup"><span data-stu-id="6ba42-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="6ba42-111">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="6ba42-111">The following values are supported:</span></span>  
  
- <span data-ttu-id="6ba42-112">0x00000000-在 `wszKeyContainer` 为 null 时用于生成临时密钥容器名称。</span><span class="sxs-lookup"><span data-stu-id="6ba42-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="6ba42-113">0x00000001 (`SN_LEAVE_KEY`) -指定应保持注册该密钥。</span><span class="sxs-lookup"><span data-stu-id="6ba42-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="6ba42-114">中请求的密钥大小，以位为单位。</span><span class="sxs-lookup"><span data-stu-id="6ba42-114">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="6ba42-115">弄返回的公钥/私钥对。</span><span class="sxs-lookup"><span data-stu-id="6ba42-115">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="6ba42-116">弄的大小（以字节为单位） `ppbKeyBlob` 。</span><span class="sxs-lookup"><span data-stu-id="6ba42-116">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6ba42-117">返回值</span><span class="sxs-lookup"><span data-stu-id="6ba42-117">Return Value</span></span>  

 <span data-ttu-id="6ba42-118">`true` 成功完成时;否则为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="6ba42-118">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ba42-119">注解</span><span class="sxs-lookup"><span data-stu-id="6ba42-119">Remarks</span></span>  

 <span data-ttu-id="6ba42-120">.NET Framework 版本1.0 和1.1 需要 `dwKeySize` 1024 位才能使用强名称对程序集进行签名; 版本2.0 增加了对2048位密钥的支持。</span><span class="sxs-lookup"><span data-stu-id="6ba42-120">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="6ba42-121">检索到密钥后，应调用 [StrongNameFreeBuffer](strongnamefreebuffer-function.md) 函数以释放已分配的内存。</span><span class="sxs-lookup"><span data-stu-id="6ba42-121">After the key is retrieved, you should call the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="6ba42-122">如果 `StrongNameKeyGenEx` 函数未成功完成，请调用 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 函数来检索上次生成的错误。</span><span class="sxs-lookup"><span data-stu-id="6ba42-122">If the `StrongNameKeyGenEx` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ba42-123">要求</span><span class="sxs-lookup"><span data-stu-id="6ba42-123">Requirements</span></span>  

 <span data-ttu-id="6ba42-124">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6ba42-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ba42-125">**标头：** Stackexchange.redis.strongname</span><span class="sxs-lookup"><span data-stu-id="6ba42-125">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="6ba42-126">**库：** 作为中的资源包含 MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6ba42-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6ba42-127">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ba42-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ba42-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6ba42-128">See also</span></span>

- [<span data-ttu-id="6ba42-129">StrongNameKeyGenEx 方法</span><span class="sxs-lookup"><span data-stu-id="6ba42-129">StrongNameKeyGenEx Method</span></span>](../hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="6ba42-130">StrongNameKeyGen 方法</span><span class="sxs-lookup"><span data-stu-id="6ba42-130">StrongNameKeyGen Method</span></span>](../hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="6ba42-131">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="6ba42-131">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
