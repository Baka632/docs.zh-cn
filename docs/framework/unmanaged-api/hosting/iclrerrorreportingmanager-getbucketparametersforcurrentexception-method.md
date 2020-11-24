---
title: ICLRErrorReportingManager::GetBucketParametersForCurrentException 方法
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.GetBucketParametersForCurrentException
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::GetBucketParametersForCurrentException
helpviewer_keywords:
- ICLRErrorReportingManager::GetBucketParametersForCurrentException method [.NET Framework hosting]
- GetBucketParametersForCurrentException method [.NET Framework hosting]
ms.assetid: a13ec8a6-8e18-4acb-8054-77f5b1a0e0b9
topic_type:
- apiref
ms.openlocfilehash: 33927cc0e3a3cdaad70d437f9dd5ca5dfdcdc46b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673549"
---
# <a name="iclrerrorreportingmanagergetbucketparametersforcurrentexception-method"></a><span data-ttu-id="3b521-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException 方法</span><span class="sxs-lookup"><span data-stu-id="3b521-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException Method</span></span>

<span data-ttu-id="3b521-103">获取调用线程上的当前异常的 Watson 存储桶。</span><span class="sxs-lookup"><span data-stu-id="3b521-103">Gets the Watson bucket for the current exception on the calling thread.</span></span>  
  
 <span data-ttu-id="3b521-104">*存储桶* 是与相同代码缺陷相关的错误数据的集合。</span><span class="sxs-lookup"><span data-stu-id="3b521-104">A *bucket* is a collection of error data that is related to the same code defect.</span></span> <span data-ttu-id="3b521-105">*Watson* 指的是一组用于收集和分析与异常相关联的数据的技术。</span><span class="sxs-lookup"><span data-stu-id="3b521-105">*Watson* refers to a set of technologies for collecting and analyzing data that is associated with an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b521-106">语法</span><span class="sxs-lookup"><span data-stu-id="3b521-106">Syntax</span></span>  
  
```cpp  
HRESULT GetBucketParametersForCurrentException(  
    [out] BucketParameters *pParams  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b521-107">参数</span><span class="sxs-lookup"><span data-stu-id="3b521-107">Parameters</span></span>  

 `pParams`  
 <span data-ttu-id="3b521-108">弄指向 [BucketParameters](bucketparameters-structure.md) 结构的指针，该结构包含异常的错误数据。</span><span class="sxs-lookup"><span data-stu-id="3b521-108">[out] A pointer to a [BucketParameters](bucketparameters-structure.md) structure that contains error data for the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b521-109">要求</span><span class="sxs-lookup"><span data-stu-id="3b521-109">Requirements</span></span>  

 <span data-ttu-id="3b521-110">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3b521-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b521-111">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3b521-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3b521-112">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3b521-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3b521-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b521-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b521-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3b521-114">See also</span></span>

- [<span data-ttu-id="3b521-115">ICLRErrorReportingManager 接口</span><span class="sxs-lookup"><span data-stu-id="3b521-115">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
