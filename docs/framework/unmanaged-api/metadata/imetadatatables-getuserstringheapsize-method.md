---
title: IMetaDataTables::GetUserStringHeapSize 方法
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetUserStringHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetUserStringHeapSize
helpviewer_keywords:
- IMetaDataTables::GetUserStringHeapSize method [.NET Framework metadata]
- GetUserStringHeapSize method [.NET Framework metadata]
ms.assetid: cba9e4d6-9461-4420-9614-96ff7039ec9c
topic_type:
- apiref
ms.openlocfilehash: 048010f00f6581a29c6b1a3150bf5ae8822b5664
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672456"
---
# <a name="imetadatatablesgetuserstringheapsize-method"></a><span data-ttu-id="31ddb-102">IMetaDataTables::GetUserStringHeapSize 方法</span><span class="sxs-lookup"><span data-stu-id="31ddb-102">IMetaDataTables::GetUserStringHeapSize Method</span></span>

<span data-ttu-id="31ddb-103">获取用户字符串堆的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="31ddb-103">Gets the size, in bytes, of the user string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31ddb-104">语法</span><span class="sxs-lookup"><span data-stu-id="31ddb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetUserStringHeapSize (  
    [out] ULONG   *pcbBlobs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31ddb-105">参数</span><span class="sxs-lookup"><span data-stu-id="31ddb-105">Parameters</span></span>  

 `pcbBlobs`  
 <span data-ttu-id="31ddb-106">弄一个指针，指向用户字符串堆的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="31ddb-106">[out] A pointer to the size, in bytes, of the user string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31ddb-107">要求</span><span class="sxs-lookup"><span data-stu-id="31ddb-107">Requirements</span></span>  

 <span data-ttu-id="31ddb-108">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="31ddb-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31ddb-109">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="31ddb-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="31ddb-110">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="31ddb-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="31ddb-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31ddb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31ddb-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31ddb-112">See also</span></span>

- [<span data-ttu-id="31ddb-113">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="31ddb-113">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="31ddb-114">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="31ddb-114">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
