---
title: ASM_CMP_FLAGS 枚举
ms.date: 03/30/2017
api_name:
- ASM_CMP_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASM_CMP_FLAGS
helpviewer_keywords:
- ASM_CMP_FLAGS enumeration [.NET Framework fusion]
ms.assetid: 4d1e6700-d4be-4fbd-8796-bfb4c07abbc8
topic_type:
- apiref
ms.openlocfilehash: fea06a3e6d06aeff56ba7e20e8e64f0a6feb5e69
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731054"
---
# <a name="asm_cmp_flags-enumeration"></a><span data-ttu-id="ef6d0-102">ASM_CMP_FLAGS 枚举</span><span class="sxs-lookup"><span data-stu-id="ef6d0-102">ASM_CMP_FLAGS Enumeration</span></span>

<span data-ttu-id="ef6d0-103">指示由 [IAssemblyName：： IsEqual](iassemblyname-isequal-method.md) 方法进行比较的两个程序集的版本、生成、区域性、签名等。</span><span class="sxs-lookup"><span data-stu-id="ef6d0-103">Indicates the version, build, culture, signature, and so on, of two assemblies to be compared by the [IAssemblyName::IsEqual](iassemblyname-isequal-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef6d0-104">语法</span><span class="sxs-lookup"><span data-stu-id="ef6d0-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
  
    ASM_CMPF_NAME                   = 0x1,  
    ASM_CMPF_MAJOR_VERSION          = 0x2,  
    ASM_CMPF_MINOR_VERSION          = 0x4,  
    ASM_CMPF_BUILD_NUMBER           = 0x8,  
    ASM_CMPF_REVISION_NUMBER        = 0x10,  
  
    ASM_CMPF_VERSION                =
                 ASM_CMPF_MAJOR_VERSION |
                 ASM_CMPF_MINOR_VERSION |
                 ASM_CMPF_BUILD_NUMBER  |
                 ASM_CMPF_REVISION_NUMBER,  
  
    ASM_CMPF_PUBLIC_KEY_TOKEN       = 0x20,  
    ASM_CMPF_CULTURE                = 0x40,  
    ASM_CMPF_CUSTOM                 = 0x80,  
    ASM_CMPF_DEFAULT                = 0x100,  
    ASM_CMPF_RETARGET               = 0x200,  
    ASM_CMPF_ARCHITECTURE           = 0x400,  
    ASM_CMPF_CONFIG_MASK            = 0x800,  
    ASM_CMPF_MVID                   = 0x1000,  
    ASM_CMPF_SIGNATURE              = 0x2000,  
  
    ASM_CMPF_IL_ALL                 =
                 ASM_CMPF_NAME             |
                 ASM_CMPF_VERSION          |
                 ASM_CMPF_PUBLIC_KEY_TOKEN |
                 ASM_CMPF_CULTURE,  
  
    ASM_CMPF_IL_NO_VERSION          =
                 ASM_CMPF_NAME             |
                 ASM_CMPF_PUBLIC_KEY_TOKEN |
                 ASM_CMPF_CULTURE  
  
} ASM_CMP_FLAGS;  
```  
  
## <a name="requirements"></a><span data-ttu-id="ef6d0-105">要求</span><span class="sxs-lookup"><span data-stu-id="ef6d0-105">Requirements</span></span>  

 <span data-ttu-id="ef6d0-106">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ef6d0-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef6d0-107">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="ef6d0-107">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ef6d0-108">**库：** 作为中的资源包含 MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ef6d0-108">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ef6d0-109">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef6d0-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef6d0-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ef6d0-110">See also</span></span>

- [<span data-ttu-id="ef6d0-111">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="ef6d0-111">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="ef6d0-112">合成枚举</span><span class="sxs-lookup"><span data-stu-id="ef6d0-112">Fusion Enumerations</span></span>](fusion-enumerations.md)
