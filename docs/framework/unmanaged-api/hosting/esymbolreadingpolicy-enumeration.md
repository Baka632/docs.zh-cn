---
title: ESymbolReadingPolicy 枚举
ms.date: 03/30/2017
api_name:
- ESymbolReadingPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ESymbolReadingPolicy
helpviewer_keywords:
- ESymbolReadingPolicy enumeration [.NET Framework hosting]
ms.assetid: 4dc6c80d-b694-480b-a378-d5b18420ce17
topic_type:
- apiref
ms.openlocfilehash: 42ce1f02294db98c5c593a5f16de5226703d5f9d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733706"
---
# <a name="esymbolreadingpolicy-enumeration"></a><span data-ttu-id="fa0b5-102">ESymbolReadingPolicy 枚举</span><span class="sxs-lookup"><span data-stu-id="fa0b5-102">ESymbolReadingPolicy Enumeration</span></span>

<span data-ttu-id="fa0b5-103">包含一些值，这些值设置用于读取程序数据库 (PDB) 文件的策略。</span><span class="sxs-lookup"><span data-stu-id="fa0b5-103">Contains values that set the policy for reading program database (PDB) files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa0b5-104">语法</span><span class="sxs-lookup"><span data-stu-id="fa0b5-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="fa0b5-105">成员</span><span class="sxs-lookup"><span data-stu-id="fa0b5-105">Members</span></span>  
  
|<span data-ttu-id="fa0b5-106">成员</span><span class="sxs-lookup"><span data-stu-id="fa0b5-106">Member</span></span>|<span data-ttu-id="fa0b5-107">说明</span><span class="sxs-lookup"><span data-stu-id="fa0b5-107">Description</span></span>|  
|------------|-----------------|  
|`eSymbolReadingAlways`|<span data-ttu-id="fa0b5-108">指定调试器应始终读取 PDB 文件。</span><span class="sxs-lookup"><span data-stu-id="fa0b5-108">Specifies that the debugger should always read PDB files.</span></span>|  
|`eSymbolReadingFullTrustOnly`|<span data-ttu-id="fa0b5-109">指定调试器只应读取与完全信任程序集关联的 PDB 文件。</span><span class="sxs-lookup"><span data-stu-id="fa0b5-109">Specifies that the debugger should read only PDB files that are associated with full-trust assemblies.</span></span>|  
|`eSymbolReadingNever`|<span data-ttu-id="fa0b5-110">指定调试器不应读取 PDB 文件。</span><span class="sxs-lookup"><span data-stu-id="fa0b5-110">Specifies that the debugger should never read PDB files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa0b5-111">注解</span><span class="sxs-lookup"><span data-stu-id="fa0b5-111">Remarks</span></span>  

 <span data-ttu-id="fa0b5-112">`ESymbolReadingPolicy`枚举与[ICLRDebugManager：： SetSymbolReadingPolicy](iclrdebugmanager-setsymbolreadingpolicy-method.md)方法一起使用。</span><span class="sxs-lookup"><span data-stu-id="fa0b5-112">The `ESymbolReadingPolicy` enumeration is used with the [ICLRDebugManager::SetSymbolReadingPolicy](iclrdebugmanager-setsymbolreadingpolicy-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa0b5-113">要求</span><span class="sxs-lookup"><span data-stu-id="fa0b5-113">Requirements</span></span>  

 <span data-ttu-id="fa0b5-114">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fa0b5-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa0b5-115">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="fa0b5-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fa0b5-116">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fa0b5-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fa0b5-117">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa0b5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa0b5-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fa0b5-118">See also</span></span>

- [<span data-ttu-id="fa0b5-119">承载枚举</span><span class="sxs-lookup"><span data-stu-id="fa0b5-119">Hosting Enumerations</span></span>](hosting-enumerations.md)
