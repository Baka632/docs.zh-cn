---
title: ICorPublishProcess::IsManaged 方法
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::IsManaged
helpviewer_keywords:
- IsManaged method, ICorPublishProcess interface [.NET Framework debugging]
- ICorPublishProcess::IsManaged method [.NET Framework debugging]
ms.assetid: 06b1f7cc-acdf-47a6-9d53-d9dec2424152
topic_type:
- apiref
ms.openlocfilehash: dfe247bda75c3695c7c09b85729b4e057c13c62d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95692626"
---
# <a name="icorpublishprocessismanaged-method"></a><span data-ttu-id="b282f-102">ICorPublishProcess::IsManaged 方法</span><span class="sxs-lookup"><span data-stu-id="b282f-102">ICorPublishProcess::IsManaged Method</span></span>

<span data-ttu-id="b282f-103">获取一个值，该值指示此 [ICorPublishProcess](icorpublishprocess-interface.md) 引用的进程是否已知具有托管代码。</span><span class="sxs-lookup"><span data-stu-id="b282f-103">Gets a value that indicates whether the process referenced by this [ICorPublishProcess](icorpublishprocess-interface.md) is known to have managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b282f-104">语法</span><span class="sxs-lookup"><span data-stu-id="b282f-104">Syntax</span></span>  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b282f-105">参数</span><span class="sxs-lookup"><span data-stu-id="b282f-105">Parameters</span></span>  

 `pbManaged`  
 <span data-ttu-id="b282f-106">弄一个指向布尔值的指针，该布尔值指示进程是否具有托管代码。</span><span class="sxs-lookup"><span data-stu-id="b282f-106">[out] A pointer to a Boolean value that indicates whether the process has managed code.</span></span> <span data-ttu-id="b282f-107">`true`如果进程具有托管代码，则该值为; 否则为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="b282f-107">The value is `true` if the process has managed code; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b282f-108">注解</span><span class="sxs-lookup"><span data-stu-id="b282f-108">Remarks</span></span>  

 <span data-ttu-id="b282f-109">由于的当前版本 `ICorPublishProcess` 只允许访问具有托管代码的进程，因此 `IsManaged` 总是返回 `true` 。</span><span class="sxs-lookup"><span data-stu-id="b282f-109">Since the current version of `ICorPublishProcess` allows access only to processes that have managed code, `IsManaged` always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b282f-110">要求</span><span class="sxs-lookup"><span data-stu-id="b282f-110">Requirements</span></span>  

 <span data-ttu-id="b282f-111">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b282f-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b282f-112">**标头：** CorPub，CorPub</span><span class="sxs-lookup"><span data-stu-id="b282f-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="b282f-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b282f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b282f-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b282f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b282f-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b282f-115">See also</span></span>

- [<span data-ttu-id="b282f-116">ICorPublishProcess 接口</span><span class="sxs-lookup"><span data-stu-id="b282f-116">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
