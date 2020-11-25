---
title: ICorPublishProcess::EnumAppDomains 方法
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.EnumAppDomains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::EnumAppDomains
helpviewer_keywords:
- EnumAppDomains method [.NET Framework debugging]
- ICorPublishProcess::EnumAppDomains method [.NET Framework debugging]
ms.assetid: 7da621fc-e7d0-4c00-9439-5c93619d7414
topic_type:
- apiref
ms.openlocfilehash: 2acf8fb507ab617e066a31c9c2657b1ef0d18e47
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95693276"
---
# <a name="icorpublishprocessenumappdomains-method"></a><span data-ttu-id="efe53-102">ICorPublishProcess::EnumAppDomains 方法</span><span class="sxs-lookup"><span data-stu-id="efe53-102">ICorPublishProcess::EnumAppDomains Method</span></span>

<span data-ttu-id="efe53-103">获取此 [ICorPublishProcess](icorpublishprocess-interface.md)引用的进程中的应用程序域的枚举器。</span><span class="sxs-lookup"><span data-stu-id="efe53-103">Gets an enumerator for the application domains in the process that is referenced by this [ICorPublishProcess](icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efe53-104">语法</span><span class="sxs-lookup"><span data-stu-id="efe53-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumAppDomains (  
    [out] ICorPublishAppDomainEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="efe53-105">参数</span><span class="sxs-lookup"><span data-stu-id="efe53-105">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="efe53-106">弄一个指针，指向允许在此进程中通过应用程序域集合进行迭代的 [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) 实例的地址。</span><span class="sxs-lookup"><span data-stu-id="efe53-106">[out] A pointer to the address of an [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) instance that allows iteration through the collection of application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="efe53-107">注解</span><span class="sxs-lookup"><span data-stu-id="efe53-107">Remarks</span></span>  

 <span data-ttu-id="efe53-108">应用程序域的列表基于在调用方法时存在的应用程序域的快照 `EnumAppDomains` 。</span><span class="sxs-lookup"><span data-stu-id="efe53-108">The list of application domains is based on a snapshot of the application domains that exist when the `EnumAppDomains` method is called.</span></span> <span data-ttu-id="efe53-109">可以多次调用此方法来创建新的最新列表。</span><span class="sxs-lookup"><span data-stu-id="efe53-109">This method may be called more than once to create a new up-to-date list.</span></span> <span data-ttu-id="efe53-110">此方法的后续调用将不会影响现有列表。</span><span class="sxs-lookup"><span data-stu-id="efe53-110">Existing lists will not be affected by subsequent calls of this method.</span></span>  
  
 <span data-ttu-id="efe53-111">如果进程已终止， `EnumAppDomains` 则将失败，并且 HRESULT 值为 CORDBG_E_PROCESS_TERMINATED。</span><span class="sxs-lookup"><span data-stu-id="efe53-111">If the process has been terminated, `EnumAppDomains` will fail with an HRESULT value of CORDBG_E_PROCESS_TERMINATED.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efe53-112">要求</span><span class="sxs-lookup"><span data-stu-id="efe53-112">Requirements</span></span>  

 <span data-ttu-id="efe53-113">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="efe53-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efe53-114">**标头：** CorPub，CorPub</span><span class="sxs-lookup"><span data-stu-id="efe53-114">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="efe53-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="efe53-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="efe53-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efe53-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efe53-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="efe53-117">See also</span></span>

- [<span data-ttu-id="efe53-118">ICorPublishProcess 接口</span><span class="sxs-lookup"><span data-stu-id="efe53-118">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
