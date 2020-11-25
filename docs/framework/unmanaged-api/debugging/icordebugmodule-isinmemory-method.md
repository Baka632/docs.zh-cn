---
title: ICorDebugModule::IsInMemory 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModule.IsInMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::IsInMemory
helpviewer_keywords:
- IsInMemory method [.NET Framework debugging]
- ICorDebugModule::IsInMemory method [.NET Framework debugging]
ms.assetid: 89940711-98e7-4aa6-bffc-5e39e91e1b7d
topic_type:
- apiref
ms.openlocfilehash: 637cac67e73d38aca0fdc5eaeae5405c4a859aa3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709812"
---
# <a name="icordebugmoduleisinmemory-method"></a><span data-ttu-id="7ef4d-102">ICorDebugModule::IsInMemory 方法</span><span class="sxs-lookup"><span data-stu-id="7ef4d-102">ICorDebugModule::IsInMemory Method</span></span>

<span data-ttu-id="7ef4d-103">获取一个值，该值指示此模块是否仅存在于内存中。</span><span class="sxs-lookup"><span data-stu-id="7ef4d-103">Gets a value that indicates whether this module exists only in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ef4d-104">语法</span><span class="sxs-lookup"><span data-stu-id="7ef4d-104">Syntax</span></span>  
  
```cpp  
HRESULT IsInMemory(  
    [out] BOOL *pInMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ef4d-105">参数</span><span class="sxs-lookup"><span data-stu-id="7ef4d-105">Parameters</span></span>  

 `pInMemory`  
 <span data-ttu-id="7ef4d-106">[out] `true` 如果此模块仅存在于内存中，则为;否则为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="7ef4d-106">[out] `true` if this module exists only in memory; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ef4d-107">注解</span><span class="sxs-lookup"><span data-stu-id="7ef4d-107">Remarks</span></span>  

 <span data-ttu-id="7ef4d-108">公共语言运行时 (CLR) 支持从原始字节流加载模块。</span><span class="sxs-lookup"><span data-stu-id="7ef4d-108">The common language runtime (CLR) supports the loading of modules from raw streams of bytes.</span></span> <span data-ttu-id="7ef4d-109">此类模块称为 *内存中模块* ，不存在于磁盘上。</span><span class="sxs-lookup"><span data-stu-id="7ef4d-109">Such modules are called *in-memory modules* and do not exist on disk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ef4d-110">要求</span><span class="sxs-lookup"><span data-stu-id="7ef4d-110">Requirements</span></span>  

 <span data-ttu-id="7ef4d-111">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7ef4d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ef4d-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ef4d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ef4d-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ef4d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ef4d-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ef4d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ef4d-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ef4d-115">See also</span></span>
