---
title: ICLRStrongName 接口
ms.date: 03/30/2017
api_name:
- ICLRStrongName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName
helpviewer_keywords:
- ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 2fac66fd-6b3b-4dbd-8baf-86038bd85526
topic_type:
- apiref
ms.openlocfilehash: 691cc3cf4ec8d036a4de04247f243d99daa887d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733628"
---
# <a name="iclrstrongname-interface"></a><span data-ttu-id="357d5-102">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="357d5-102">ICLRStrongName Interface</span></span>

<span data-ttu-id="357d5-103">提供用于对具有强名称的程序集进行签名的基本全局静态函数。</span><span class="sxs-lookup"><span data-stu-id="357d5-103">Provides basic global static functions for signing assemblies with strong names.</span></span> <span data-ttu-id="357d5-104">所有 `ICLRStrongName` 方法都返回标准 COM hresult。</span><span class="sxs-lookup"><span data-stu-id="357d5-104">All `ICLRStrongName` methods return standard COM HRESULTs.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="357d5-105">方法</span><span class="sxs-lookup"><span data-stu-id="357d5-105">Methods</span></span>  
  
|<span data-ttu-id="357d5-106">方法</span><span class="sxs-lookup"><span data-stu-id="357d5-106">Method</span></span>|<span data-ttu-id="357d5-107">说明</span><span class="sxs-lookup"><span data-stu-id="357d5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="357d5-108">GetHashFromAssemblyFile 方法</span><span class="sxs-lookup"><span data-stu-id="357d5-108">GetHashFromAssemblyFile Method</span></span>](iclrstrongname-gethashfromassemblyfile-method.md)|<span data-ttu-id="357d5-109">使用指定的哈希算法获取指定程序集文件的哈希。</span><span class="sxs-lookup"><span data-stu-id="357d5-109">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>|  
|[<span data-ttu-id="357d5-110">GetHashFromAssemblyFileW 方法</span><span class="sxs-lookup"><span data-stu-id="357d5-110">GetHashFromAssemblyFileW Method</span></span>](iclrstrongname-gethashfromassemblyfilew-method.md)|<span data-ttu-id="357d5-111">使用指定的哈希算法获取指定为 Unicode 字符串的程序集文件的哈希。</span><span class="sxs-lookup"><span data-stu-id="357d5-111">Gets a hash of the assembly file specified as a Unicode string, using the specified hash algorithm.</span></span>|  
|[<span data-ttu-id="357d5-112">GetHashFromBlob 方法</span><span class="sxs-lookup"><span data-stu-id="357d5-112">GetHashFromBlob Method</span></span>](iclrstrongname-gethashfromblob-method.md)|<span data-ttu-id="357d5-113">使用指定的哈希算法获取指定内存地址处的程序集的哈希。</span><span class="sxs-lookup"><span data-stu-id="357d5-113">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>|  
|[<span data-ttu-id="357d5-114">GetHashFromFile 方法</span><span class="sxs-lookup"><span data-stu-id="357d5-114">GetHashFromFile Method</span></span>](iclrstrongname-gethashfromfile-method.md)|<span data-ttu-id="357d5-115">生成指定文件内容的哈希。</span><span class="sxs-lookup"><span data-stu-id="357d5-115">Generates a hash over the contents of the specified file.</span></span>|  
|[<span data-ttu-id="357d5-116">GetHashFromFileW 方法</span><span class="sxs-lookup"><span data-stu-id="357d5-116">GetHashFromFileW Method</span></span>](iclrstrongname-gethashfromfilew-method.md)|<span data-ttu-id="357d5-117">生成由 Unicode 字符串指定的文件内容的哈希。</span><span class="sxs-lookup"><span data-stu-id="357d5-117">Generates a hash over the contents of the file specified by a Unicode string.</span></span>|  
|[<span data-ttu-id="357d5-118">GetHashFromHandle 方法</span><span class="sxs-lookup"><span data-stu-id="357d5-118">GetHashFromHandle Method</span></span>](iclrstrongname-gethashfromhandle-method.md)|<span data-ttu-id="357d5-119">使用指定的哈希算法，生成具有指定文件句柄的文件内容的哈希。</span><span class="sxs-lookup"><span data-stu-id="357d5-119">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>|  
|[<span data-ttu-id="357d5-120">StrongNameCompareAssemblies 方法</span><span class="sxs-lookup"><span data-stu-id="357d5-120">StrongNameCompareAssemblies Method</span></span>](iclrstrongname-strongnamecompareassemblies-method.md)|<span data-ttu-id="357d5-121">确定两个程序集是否仅是强名称签名不同。</span><span class="sxs-lookup"><span data-stu-id="357d5-121">Determines whether two assemblies differ only by their strong name signatures.</span></span>|  
|[<span data-ttu-id="357d5-122">StrongNameFreeBuffer 方法</span><span class="sxs-lookup"><span data-stu-id="357d5-122">StrongNameFreeBuffer Method</span></span>](iclrstrongname-strongnamefreebuffer-method.md)|<span data-ttu-id="357d5-123">释放以前对强名称方法（如 [StrongNameGetPublicKey](iclrstrongname-strongnamegetpublickey-method.md)、 [StrongNameTokenFromPublicKey](iclrstrongname-strongnametokenfrompublickey-method.md)或 [StrongNameSignatureGeneration](iclrstrongname-strongnamesignaturegeneration-method.md)）的调用所分配的内存。</span><span class="sxs-lookup"><span data-stu-id="357d5-123">Frees memory that was allocated with a previous call to a strong name method such as [StrongNameGetPublicKey](iclrstrongname-strongnamegetpublickey-method.md), [StrongNameTokenFromPublicKey](iclrstrongname-strongnametokenfrompublickey-method.md), or [StrongNameSignatureGeneration](iclrstrongname-strongnamesignaturegeneration-method.md).</span></span>|  
|[<span data-ttu-id="357d5-124">StrongNameGetBlob 方法</span><span class="sxs-lookup"><span data-stu-id="357d5-124">StrongNameGetBlob Method</span></span>](iclrstrongname-strongnamegetblob-method.md)|<span data-ttu-id="357d5-125">使用指定地址处可执行文件的二进制表示形式填充指定的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="357d5-125">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>|  
|[<span data-ttu-id="357d5-126">StrongNameGetBlobFromImage 方法</span><span class="sxs-lookup"><span data-stu-id="357d5-126">StrongNameGetBlobFromImage Method</span></span>](iclrstrongname-strongnamegetblobfromimage-method.md)|<span data-ttu-id="357d5-127">获取指定内存地址处程序集映像的二进制表示形式。</span><span class="sxs-lookup"><span data-stu-id="357d5-127">Gets a binary representation of the assembly image at the specified memory address.</span></span>|  
|[<span data-ttu-id="357d5-128">StrongNameGetPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="357d5-128">StrongNameGetPublicKey Method</span></span>](iclrstrongname-strongnamegetpublickey-method.md)|<span data-ttu-id="357d5-129">从私钥/公钥对中获取公钥。</span><span class="sxs-lookup"><span data-stu-id="357d5-129">Gets the public key from a private/public key pair.</span></span>|  
|[<span data-ttu-id="357d5-130">StrongNameHashSize 方法</span><span class="sxs-lookup"><span data-stu-id="357d5-130">StrongNameHashSize Method</span></span>](iclrstrongname-strongnamehashsize-method.md)|<span data-ttu-id="357d5-131">使用指定的哈希算法获取哈希所需的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="357d5-131">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>|  
|[<span data-ttu-id="357d5-132">StrongNameKeyDelete 方法</span><span class="sxs-lookup"><span data-stu-id="357d5-132">StrongNameKeyDelete Method</span></span>](iclrstrongname-strongnamekeydelete-method.md)|<span data-ttu-id="357d5-133">删除指定的密钥容器。</span><span class="sxs-lookup"><span data-stu-id="357d5-133">Deletes the specified key container.</span></span>|  
|[<span data-ttu-id="357d5-134">StrongNameKeyGen 方法</span><span class="sxs-lookup"><span data-stu-id="357d5-134">StrongNameKeyGen Method</span></span>](iclrstrongname-strongnamekeygen-method.md)|<span data-ttu-id="357d5-135">创建新的公钥/私钥对，以便强名称使用。</span><span class="sxs-lookup"><span data-stu-id="357d5-135">Creates a new public/private key pair for strong name use.</span></span>|  
|[<span data-ttu-id="357d5-136">StrongNameKeyGenEx 方法</span><span class="sxs-lookup"><span data-stu-id="357d5-136">StrongNameKeyGenEx Method</span></span>](iclrstrongname-strongnamekeygenex-method.md)|<span data-ttu-id="357d5-137">生成具有指定密钥大小的新公钥/私钥对，以便强名称使用。</span><span class="sxs-lookup"><span data-stu-id="357d5-137">Generates a new public/private key pair with the specified key size for strong name use.</span></span>|  
|[<span data-ttu-id="357d5-138">StrongNameKeyInstall 方法</span><span class="sxs-lookup"><span data-stu-id="357d5-138">StrongNameKeyInstall Method</span></span>](iclrstrongname-strongnamekeyinstall-method.md)|<span data-ttu-id="357d5-139">将公钥/私钥对导入容器。</span><span class="sxs-lookup"><span data-stu-id="357d5-139">Imports a public/private key pair into a container.</span></span>|  
|[<span data-ttu-id="357d5-140">StrongNameSignatureGeneration 方法</span><span class="sxs-lookup"><span data-stu-id="357d5-140">StrongNameSignatureGeneration Method</span></span>](iclrstrongname-strongnamesignaturegeneration-method.md)|<span data-ttu-id="357d5-141">为指定的程序集生成强名称签名。</span><span class="sxs-lookup"><span data-stu-id="357d5-141">Generates a strong name signature for the specified assembly.</span></span>|  
|[<span data-ttu-id="357d5-142">StrongNameSignatureGenerationEx 方法</span><span class="sxs-lookup"><span data-stu-id="357d5-142">StrongNameSignatureGenerationEx Method</span></span>](iclrstrongname-strongnamesignaturegenerationex-method.md)|<span data-ttu-id="357d5-143">根据指定标志为指定的程序集生成强名称签名。</span><span class="sxs-lookup"><span data-stu-id="357d5-143">Generates a strong name signature for the specified assembly, based on the specified flags.</span></span>|  
|[<span data-ttu-id="357d5-144">StrongNameSignatureSize 方法</span><span class="sxs-lookup"><span data-stu-id="357d5-144">StrongNameSignatureSize Method</span></span>](iclrstrongname-strongnamesignaturesize-method.md)|<span data-ttu-id="357d5-145">返回强名称签名的大小。</span><span class="sxs-lookup"><span data-stu-id="357d5-145">Returns the size of the strong name signature.</span></span>|  
|[<span data-ttu-id="357d5-146">StrongNameSignatureVerification 方法</span><span class="sxs-lookup"><span data-stu-id="357d5-146">StrongNameSignatureVerification Method</span></span>](iclrstrongname-strongnamesignatureverification-method.md)|<span data-ttu-id="357d5-147">获取一个值，该值指示提供的路径中的程序集清单是否包含根据指定标志验证的强名称签名。</span><span class="sxs-lookup"><span data-stu-id="357d5-147">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>|  
|[<span data-ttu-id="357d5-148">StrongNameSignatureVerificationEx 方法</span><span class="sxs-lookup"><span data-stu-id="357d5-148">StrongNameSignatureVerificationEx Method</span></span>](iclrstrongname-strongnamesignatureverificationex-method.md)|<span data-ttu-id="357d5-149">获取一个值，该值指示提供的路径中的程序集清单是否包含强名称签名。</span><span class="sxs-lookup"><span data-stu-id="357d5-149">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature.</span></span>|  
|[<span data-ttu-id="357d5-150">StrongNameSignatureVerificationFromImage 方法</span><span class="sxs-lookup"><span data-stu-id="357d5-150">StrongNameSignatureVerificationFromImage Method</span></span>](iclrstrongname-strongnamesignatureverificationfromimage-method.md)|<span data-ttu-id="357d5-151">验证已映射到内存的程序集对关联的公钥是否有效。</span><span class="sxs-lookup"><span data-stu-id="357d5-151">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span>|  
|[<span data-ttu-id="357d5-152">StrongNameTokenFromAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="357d5-152">StrongNameTokenFromAssembly Method</span></span>](iclrstrongname-strongnametokenfromassembly-method.md)|<span data-ttu-id="357d5-153">从指定的程序集文件创建强名称令牌。</span><span class="sxs-lookup"><span data-stu-id="357d5-153">Creates a strong name token from the specified assembly file.</span></span>|  
|[<span data-ttu-id="357d5-154">StrongNameTokenFromAssemblyEx 方法</span><span class="sxs-lookup"><span data-stu-id="357d5-154">StrongNameTokenFromAssemblyEx Method</span></span>](iclrstrongname-strongnametokenfromassemblyex-method.md)|<span data-ttu-id="357d5-155">从指定的程序集文件创建强名称令牌并返回公钥。</span><span class="sxs-lookup"><span data-stu-id="357d5-155">Creates a strong name token from the specified assembly file, and returns the public key.</span></span>|  
|[<span data-ttu-id="357d5-156">StrongNameTokenFromPublicKey 方法</span><span class="sxs-lookup"><span data-stu-id="357d5-156">StrongNameTokenFromPublicKey Method</span></span>](iclrstrongname-strongnametokenfrompublickey-method.md)|<span data-ttu-id="357d5-157">获取表示公钥的令牌。</span><span class="sxs-lookup"><span data-stu-id="357d5-157">Gets a token representing a public key.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="357d5-158">注解</span><span class="sxs-lookup"><span data-stu-id="357d5-158">Remarks</span></span>  

 <span data-ttu-id="357d5-159">可以 `ICLRStrongName` 通过使用和作为参数调用 [ICLRRuntimeInfo：： GetInterface](iclrruntimeinfo-getinterface-method.md) 方法来获取的实例 `CLSID_CLRStrongName` `IID_ICLRStrongName` 。</span><span class="sxs-lookup"><span data-stu-id="357d5-159">You can get an instance of the `ICLRStrongName` by calling the [ICLRRuntimeInfo::GetInterface](iclrruntimeinfo-getinterface-method.md) method using `CLSID_CLRStrongName` and `IID_ICLRStrongName` as parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="357d5-160">要求</span><span class="sxs-lookup"><span data-stu-id="357d5-160">Requirements</span></span>  

 <span data-ttu-id="357d5-161">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="357d5-161">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="357d5-162">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="357d5-162">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="357d5-163">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="357d5-163">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="357d5-164">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="357d5-164">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="357d5-165">另请参阅</span><span class="sxs-lookup"><span data-stu-id="357d5-165">See also</span></span>

- [<span data-ttu-id="357d5-166">承载接口</span><span class="sxs-lookup"><span data-stu-id="357d5-166">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="357d5-167">承载</span><span class="sxs-lookup"><span data-stu-id="357d5-167">Hosting</span></span>](index.md)
