---
title: ICLRStrongName::StrongNameKeyDelete 方法
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyDelete
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyDelete
helpviewer_keywords:
- StrongNameKeyDelete method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameKeyDelete method [.NET Framework hosting]
ms.assetid: 0163412f-f617-4428-89e0-03992fec31e8
topic_type:
- apiref
ms.openlocfilehash: 46345ae570673c9c9c0c58fb6edea1464ba8dd91
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671689"
---
# <a name="iclrstrongnamestrongnamekeydelete-method"></a><span data-ttu-id="99cc6-102">ICLRStrongName::StrongNameKeyDelete 方法</span><span class="sxs-lookup"><span data-stu-id="99cc6-102">ICLRStrongName::StrongNameKeyDelete Method</span></span>

<span data-ttu-id="99cc6-103">删除指定的密钥容器。</span><span class="sxs-lookup"><span data-stu-id="99cc6-103">Deletes the specified key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99cc6-104">语法</span><span class="sxs-lookup"><span data-stu-id="99cc6-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99cc6-105">参数</span><span class="sxs-lookup"><span data-stu-id="99cc6-105">Parameters</span></span>  

 `wszKeyContainer`  
 <span data-ttu-id="99cc6-106">中要删除的密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="99cc6-106">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="99cc6-107">返回值</span><span class="sxs-lookup"><span data-stu-id="99cc6-107">Return Value</span></span>  

 <span data-ttu-id="99cc6-108">`S_OK` 如果该方法已成功完成，则为;否则，表示失败的 HRESULT 值 (参阅) 列表的 [常见 HRESULT 值](/windows/win32/seccrypto/common-hresult-values) 。</span><span class="sxs-lookup"><span data-stu-id="99cc6-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99cc6-109">注解</span><span class="sxs-lookup"><span data-stu-id="99cc6-109">Remarks</span></span>  

 <span data-ttu-id="99cc6-110">使用 [ICLRStrongName：： StrongNameKeyInstall](iclrstrongname-strongnamekeyinstall-method.md) 方法将公钥/私钥对导入到容器中。</span><span class="sxs-lookup"><span data-stu-id="99cc6-110">Use the [ICLRStrongName::StrongNameKeyInstall](iclrstrongname-strongnamekeyinstall-method.md) method to import a public/private key pair into a container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99cc6-111">要求</span><span class="sxs-lookup"><span data-stu-id="99cc6-111">Requirements</span></span>  

 <span data-ttu-id="99cc6-112">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="99cc6-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99cc6-113">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="99cc6-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="99cc6-114">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="99cc6-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="99cc6-115">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99cc6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99cc6-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="99cc6-116">See also</span></span>

- [<span data-ttu-id="99cc6-117">StrongNameKeyInstall 方法</span><span class="sxs-lookup"><span data-stu-id="99cc6-117">StrongNameKeyInstall Method</span></span>](iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="99cc6-118">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="99cc6-118">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
