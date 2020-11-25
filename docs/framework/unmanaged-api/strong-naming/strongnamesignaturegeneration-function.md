---
title: StrongNameSignatureGeneration 函数
ms.date: 03/30/2017
api_name:
- StrongNameSignatureGeneration
api_location:
- mscoree.dll
- mscorsn.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration function [.NET Framework strong naming]
ms.assetid: 839b765c-3e41-44ce-bf1b-dc10453db18e
ms.openlocfilehash: 78a89c07b9a7ddbccee9716de37c96d23635f87b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708519"
---
# <a name="strongnamesignaturegeneration-function"></a><span data-ttu-id="a81fc-102">StrongNameSignatureGeneration 函数</span><span class="sxs-lookup"><span data-stu-id="a81fc-102">StrongNameSignatureGeneration Function</span></span>

<span data-ttu-id="a81fc-103">为指定的程序集生成强名称签名。</span><span class="sxs-lookup"><span data-stu-id="a81fc-103">Generates a strong name signature for the specified assembly.</span></span>  
  
 <span data-ttu-id="a81fc-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="a81fc-104">This function has been deprecated.</span></span> <span data-ttu-id="a81fc-105">改为使用 [ICLRStrongName：： StrongNameSignatureGeneration](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="a81fc-105">Use the [ICLRStrongName::StrongNameSignatureGeneration](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a81fc-106">语法</span><span class="sxs-lookup"><span data-stu-id="a81fc-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureGeneration (
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a81fc-107">参数</span><span class="sxs-lookup"><span data-stu-id="a81fc-107">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="a81fc-108">中包含要为其生成强名称签名的程序集清单的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="a81fc-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="a81fc-109">中包含公钥/私钥对的密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="a81fc-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="a81fc-110">如果 `pbKeyBlob` 为 null，则 `wszKeyContainer` 必须在加密服务提供程序 (CSP) 中指定有效容器。</span><span class="sxs-lookup"><span data-stu-id="a81fc-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="a81fc-111">在这种情况下，存储在容器中的密钥对用于对文件进行签名。</span><span class="sxs-lookup"><span data-stu-id="a81fc-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="a81fc-112">如果不为 `pbKeyBlob` null，则假定密钥对包含在关键的二进制大型对象 (BLOB) 中。</span><span class="sxs-lookup"><span data-stu-id="a81fc-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="a81fc-113">密钥必须是1024位 Rivest-Rivest-shamir-adleman (RSA) 签名密钥。</span><span class="sxs-lookup"><span data-stu-id="a81fc-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="a81fc-114">此时不支持其他类型的密钥。</span><span class="sxs-lookup"><span data-stu-id="a81fc-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="a81fc-115">中指向公钥/私钥对的指针。</span><span class="sxs-lookup"><span data-stu-id="a81fc-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="a81fc-116">此对采用 Win32 函数创建的格式 `CryptExportKey` 。</span><span class="sxs-lookup"><span data-stu-id="a81fc-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="a81fc-117">如果 `pbKeyBlob` 为 null，则假定指定的密钥容器 `wszKeyContainer` 包含密钥对。</span><span class="sxs-lookup"><span data-stu-id="a81fc-117">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="a81fc-118">中的大小（以字节为单位） `pbKeyBlob` 。</span><span class="sxs-lookup"><span data-stu-id="a81fc-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="a81fc-119">弄指向公共语言运行时返回签名的位置的指针。</span><span class="sxs-lookup"><span data-stu-id="a81fc-119">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="a81fc-120">如果 `ppbSignatureBlob` 为 null，则运行时将签名存储在指定的文件中 `wszFilePath` 。</span><span class="sxs-lookup"><span data-stu-id="a81fc-120">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="a81fc-121">如果 `ppbSignatureBlob` 不为 null，则公共语言运行时将分配要在其中返回签名的空间。</span><span class="sxs-lookup"><span data-stu-id="a81fc-121">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="a81fc-122">调用方必须使用 [StrongNameFreeBuffer](strongnamefreebuffer-function.md) 函数释放此空间。</span><span class="sxs-lookup"><span data-stu-id="a81fc-122">The caller must free this space using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="a81fc-123">弄返回签名的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="a81fc-123">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a81fc-124">返回值</span><span class="sxs-lookup"><span data-stu-id="a81fc-124">Return Value</span></span>  

 <span data-ttu-id="a81fc-125">`true` 成功完成时;否则为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="a81fc-125">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a81fc-126">注解</span><span class="sxs-lookup"><span data-stu-id="a81fc-126">Remarks</span></span>  

 <span data-ttu-id="a81fc-127">指定 null 以 `wszFilePath` 计算签名大小，而不创建签名。</span><span class="sxs-lookup"><span data-stu-id="a81fc-127">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="a81fc-128">签名可以直接存储在文件中，也可以返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="a81fc-128">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="a81fc-129">如果 `StrongNameSignatureGeneration` 函数未成功完成，请调用 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 函数来检索上次生成的错误。</span><span class="sxs-lookup"><span data-stu-id="a81fc-129">If the `StrongNameSignatureGeneration` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a81fc-130">要求</span><span class="sxs-lookup"><span data-stu-id="a81fc-130">Requirements</span></span>  

 <span data-ttu-id="a81fc-131">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a81fc-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a81fc-132">**标头：** Stackexchange.redis.strongname</span><span class="sxs-lookup"><span data-stu-id="a81fc-132">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="a81fc-133">**库：** 作为中的资源包含 MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a81fc-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a81fc-134">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a81fc-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a81fc-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a81fc-135">See also</span></span>

- [<span data-ttu-id="a81fc-136">StrongNameSignatureGeneration 方法</span><span class="sxs-lookup"><span data-stu-id="a81fc-136">StrongNameSignatureGeneration Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="a81fc-137">StrongNameSignatureGenerationEx 方法</span><span class="sxs-lookup"><span data-stu-id="a81fc-137">StrongNameSignatureGenerationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="a81fc-138">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="a81fc-138">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
