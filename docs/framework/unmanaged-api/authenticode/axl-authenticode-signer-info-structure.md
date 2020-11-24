---
title: AXL_AUTHENTICODE_SIGNER_INFO 结构
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
ms.openlocfilehash: 1bb6df4aa82f8dfc367083732af2065aba9d07b1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679983"
---
# <a name="axl_authenticode_signer_info-structure"></a><span data-ttu-id="c3d78-102">AXL_AUTHENTICODE_SIGNER_INFO 结构</span><span class="sxs-lookup"><span data-stu-id="c3d78-102">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>

<span data-ttu-id="c3d78-103">定义验证码签署人的信息。</span><span class="sxs-lookup"><span data-stu-id="c3d78-103">Defines the Authenticode signer information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3d78-104">语法</span><span class="sxs-lookup"><span data-stu-id="c3d78-104">Syntax</span></span>  
  
```cpp  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    LPCWSTR pwszHash  
    LPCWSTR pwszDescription;  
    LPCWSTR pwszDescriptionUrl;  
    PCCERT_CHAIN_CONTEXT pChainContext  
} AXL_AUTHENTICODE_SIGNER_INFO, * PAXL_AUTHENTICODE_SIGNER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="c3d78-105">成员</span><span class="sxs-lookup"><span data-stu-id="c3d78-105">Members</span></span>  
  
|<span data-ttu-id="c3d78-106">成员</span><span class="sxs-lookup"><span data-stu-id="c3d78-106">Member</span></span>|<span data-ttu-id="c3d78-107">说明</span><span class="sxs-lookup"><span data-stu-id="c3d78-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="c3d78-108">此结构的大小。</span><span class="sxs-lookup"><span data-stu-id="c3d78-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="c3d78-109">错误代码。</span><span class="sxs-lookup"><span data-stu-id="c3d78-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="c3d78-110">哈希算法。</span><span class="sxs-lookup"><span data-stu-id="c3d78-110">The hash algorithm.</span></span>|  
|`pwszHash`|<span data-ttu-id="c3d78-111">哈希。</span><span class="sxs-lookup"><span data-stu-id="c3d78-111">The hash.</span></span>|  
|`pwszDescription`|<span data-ttu-id="c3d78-112">说明。</span><span class="sxs-lookup"><span data-stu-id="c3d78-112">The description.</span></span>|  
|`pwszDescriptionUrl`|<span data-ttu-id="c3d78-113">说明的 URL。</span><span class="sxs-lookup"><span data-stu-id="c3d78-113">The URL of the description.</span></span>|  
|`pChainContext`|<span data-ttu-id="c3d78-114">签署人的链上下文。</span><span class="sxs-lookup"><span data-stu-id="c3d78-114">The chain context of the signer.</span></span> <span data-ttu-id="c3d78-115">请参阅 [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) 结构。</span><span class="sxs-lookup"><span data-stu-id="c3d78-115">See the [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c3d78-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c3d78-116">See also</span></span>

- [<span data-ttu-id="c3d78-117">验证码</span><span class="sxs-lookup"><span data-stu-id="c3d78-117">Authenticode</span></span>](index.md)
