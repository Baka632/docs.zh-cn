---
title: ICorPublish 接口
ms.date: 03/30/2017
api_name:
- ICorPublish
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish
helpviewer_keywords:
- ICorPublish interface [.NET Framework debugging]
ms.assetid: 87c4fcb2-7703-4a2e-afb6-42973381b960
topic_type:
- apiref
ms.openlocfilehash: 3ff4efe8b3e2932da7f65246bf4ad614a4dd86cd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95694394"
---
# <a name="icorpublish-interface"></a><span data-ttu-id="51469-102">ICorPublish 接口</span><span class="sxs-lookup"><span data-stu-id="51469-102">ICorPublish Interface</span></span>

<span data-ttu-id="51469-103">用作发布有关进程的信息，以及有关这些进程中的应用程序域的信息。</span><span class="sxs-lookup"><span data-stu-id="51469-103">Serves as the general interface for publishing information about processes and information about the application domains in those processes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="51469-104">方法</span><span class="sxs-lookup"><span data-stu-id="51469-104">Methods</span></span>  
  
|<span data-ttu-id="51469-105">方法</span><span class="sxs-lookup"><span data-stu-id="51469-105">Method</span></span>|<span data-ttu-id="51469-106">说明</span><span class="sxs-lookup"><span data-stu-id="51469-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="51469-107">EnumProcesses 方法</span><span class="sxs-lookup"><span data-stu-id="51469-107">EnumProcesses Method</span></span>](icorpublish-enumprocesses-method.md)|<span data-ttu-id="51469-108">获取一个 [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) 实例，它包含在此计算机上运行的托管进程。</span><span class="sxs-lookup"><span data-stu-id="51469-108">Gets an [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) instance that contains the managed processes running on this computer.</span></span>|  
|[<span data-ttu-id="51469-109">GetProcess 方法</span><span class="sxs-lookup"><span data-stu-id="51469-109">GetProcess Method</span></span>](icorpublish-getprocess-method.md)|<span data-ttu-id="51469-110">获取一个表示具有指定标识符的进程的 [ICorPublishProcess](icorpublishprocess-interface.md) 实例。</span><span class="sxs-lookup"><span data-stu-id="51469-110">Gets an [ICorPublishProcess](icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="51469-111">要求</span><span class="sxs-lookup"><span data-stu-id="51469-111">Requirements</span></span>  

 <span data-ttu-id="51469-112">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="51469-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51469-113">**标头：** CorPub，CorPub</span><span class="sxs-lookup"><span data-stu-id="51469-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="51469-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51469-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51469-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51469-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51469-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="51469-116">See also</span></span>

- [<span data-ttu-id="51469-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="51469-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="51469-118">CorpubPublish Coclass</span><span class="sxs-lookup"><span data-stu-id="51469-118">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
