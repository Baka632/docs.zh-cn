---
title: ICorPublishProcess::GetProcessID 方法
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.GetProcessID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::GetProcessID
helpviewer_keywords:
- ICorPublishProcess::GetProcessID method [.NET Framework debugging]
- GetProcessID method [.NET Framework debugging]
ms.assetid: f31185e0-f01d-463a-b392-42163e39bfe9
topic_type:
- apiref
ms.openlocfilehash: b0defd0a9c4197cf91fde1625794ff0d77c83ea0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95693133"
---
# <a name="icorpublishprocessgetprocessid-method"></a><span data-ttu-id="461ff-102">ICorPublishProcess::GetProcessID 方法</span><span class="sxs-lookup"><span data-stu-id="461ff-102">ICorPublishProcess::GetProcessID Method</span></span>

<span data-ttu-id="461ff-103">获取此进程的操作系统标识符。</span><span class="sxs-lookup"><span data-stu-id="461ff-103">Gets the operating system identifier for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="461ff-104">语法</span><span class="sxs-lookup"><span data-stu-id="461ff-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcessID (  
    [out] unsigned   *pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="461ff-105">参数</span><span class="sxs-lookup"><span data-stu-id="461ff-105">Parameters</span></span>  

 `pid`  
 <span data-ttu-id="461ff-106">弄一个指针，指向此 [ICorPublishProcess](icorpublishprocess-interface.md) 对象所表示的进程的标识符。</span><span class="sxs-lookup"><span data-stu-id="461ff-106">[out] A pointer to the identifier of the process represented by this [ICorPublishProcess](icorpublishprocess-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="461ff-107">要求</span><span class="sxs-lookup"><span data-stu-id="461ff-107">Requirements</span></span>  

 <span data-ttu-id="461ff-108">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="461ff-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="461ff-109">**标头：** CorPub，CorPub</span><span class="sxs-lookup"><span data-stu-id="461ff-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="461ff-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="461ff-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="461ff-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="461ff-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="461ff-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="461ff-112">See also</span></span>

- [<span data-ttu-id="461ff-113">ICorPublishProcess 接口</span><span class="sxs-lookup"><span data-stu-id="461ff-113">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
