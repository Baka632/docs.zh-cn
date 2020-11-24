---
title: IMetaDataTables::GetStringHeapSize 方法
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetStringHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetStringHeapSize
helpviewer_keywords:
- IMetaDataTables::GetStringHeapSize method [.NET Framework metadata]
- GetStringHeapSize method [.NET Framework metadata]
ms.assetid: ed8f6335-81f5-4c09-81a9-2a909fc530c9
topic_type:
- apiref
ms.openlocfilehash: e3f6afaa79b7b299fa374c8220f5c2c3ad545ac9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672552"
---
# <a name="imetadatatablesgetstringheapsize-method"></a><span data-ttu-id="ce4a8-102">IMetaDataTables::GetStringHeapSize 方法</span><span class="sxs-lookup"><span data-stu-id="ce4a8-102">IMetaDataTables::GetStringHeapSize Method</span></span>

<span data-ttu-id="ce4a8-103">获取字符串堆的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="ce4a8-103">Gets the size, in bytes, of the string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce4a8-104">语法</span><span class="sxs-lookup"><span data-stu-id="ce4a8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStringHeapSize (  
    [out] ULONG   *pcbStrings  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce4a8-105">参数</span><span class="sxs-lookup"><span data-stu-id="ce4a8-105">Parameters</span></span>  

 `pcbStrings`  
 <span data-ttu-id="ce4a8-106">弄一个指针，指向字符串堆的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="ce4a8-106">[out] A pointer to the size, in bytes, of the string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce4a8-107">要求</span><span class="sxs-lookup"><span data-stu-id="ce4a8-107">Requirements</span></span>  

 <span data-ttu-id="ce4a8-108">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ce4a8-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce4a8-109">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="ce4a8-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ce4a8-110">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ce4a8-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ce4a8-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce4a8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce4a8-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ce4a8-112">See also</span></span>

- [<span data-ttu-id="ce4a8-113">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="ce4a8-113">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="ce4a8-114">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="ce4a8-114">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
