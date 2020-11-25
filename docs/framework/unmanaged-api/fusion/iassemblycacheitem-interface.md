---
title: IAssemblyCacheItem 接口
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem
helpviewer_keywords:
- IAssemblyCacheItem interface [.NET Framework fusion]
ms.assetid: ccc9387a-9f44-4f4f-bf8f-0ea6d2afa21b
topic_type:
- apiref
ms.openlocfilehash: 72922d1fd0f8ae5e59fe76c7aa50f9c52dcd5302
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719939"
---
# <a name="iassemblycacheitem-interface"></a><span data-ttu-id="9e780-102">IAssemblyCacheItem 接口</span><span class="sxs-lookup"><span data-stu-id="9e780-102">IAssemblyCacheItem Interface</span></span>

<span data-ttu-id="9e780-103">表示全局程序集缓存中的单个程序集。</span><span class="sxs-lookup"><span data-stu-id="9e780-103">Represents a single assembly in the global assembly cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9e780-104">方法</span><span class="sxs-lookup"><span data-stu-id="9e780-104">Methods</span></span>  
  
|<span data-ttu-id="9e780-105">方法</span><span class="sxs-lookup"><span data-stu-id="9e780-105">Method</span></span>|<span data-ttu-id="9e780-106">说明</span><span class="sxs-lookup"><span data-stu-id="9e780-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9e780-107">AbortItem 方法</span><span class="sxs-lookup"><span data-stu-id="9e780-107">AbortItem Method</span></span>](iassemblycacheitem-abortitem-method.md)|<span data-ttu-id="9e780-108">允许全局程序集缓存中的程序集在发布前执行清除操作。</span><span class="sxs-lookup"><span data-stu-id="9e780-108">Allows the assembly in the global assembly cache to perform cleanup operations before it is released.</span></span>|  
|[<span data-ttu-id="9e780-109">Commit 方法</span><span class="sxs-lookup"><span data-stu-id="9e780-109">Commit Method</span></span>](iassemblycacheitem-commit-method.md)|<span data-ttu-id="9e780-110">将缓存的程序集引用提交到内存。</span><span class="sxs-lookup"><span data-stu-id="9e780-110">Commits the cached assembly reference to memory.</span></span>|  
|[<span data-ttu-id="9e780-111">CreateStream 方法</span><span class="sxs-lookup"><span data-stu-id="9e780-111">CreateStream Method</span></span>](iassemblycacheitem-createstream-method.md)|<span data-ttu-id="9e780-112">创建具有指定名称和格式的流。</span><span class="sxs-lookup"><span data-stu-id="9e780-112">Creates a stream with the specified name and format.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9e780-113">要求</span><span class="sxs-lookup"><span data-stu-id="9e780-113">Requirements</span></span>  

 <span data-ttu-id="9e780-114">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9e780-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e780-115">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="9e780-115">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="9e780-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e780-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e780-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9e780-117">See also</span></span>

- [<span data-ttu-id="9e780-118">合成接口</span><span class="sxs-lookup"><span data-stu-id="9e780-118">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="9e780-119">全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="9e780-119">Global Assembly Cache</span></span>](../../app-domains/gac.md)
- [<span data-ttu-id="9e780-120">IAssemblyCache 接口</span><span class="sxs-lookup"><span data-stu-id="9e780-120">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
