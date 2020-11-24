---
title: IMetaDataTables::GetRow 方法
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetRow
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetRow
helpviewer_keywords:
- IMetaDataTables::GetRow method [.NET Framework metadata]
- GetRow method [.NET Framework metadata]
ms.assetid: a7408d51-0bce-45a2-b58f-da4660bbc039
topic_type:
- apiref
ms.openlocfilehash: 01c4c1734aa0701f787a2b73787e9e4781901d42
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672638"
---
# <a name="imetadatatablesgetrow-method"></a><span data-ttu-id="509cf-102">IMetaDataTables::GetRow 方法</span><span class="sxs-lookup"><span data-stu-id="509cf-102">IMetaDataTables::GetRow Method</span></span>

<span data-ttu-id="509cf-103">获取位于指定表索引处的表中指定行索引处的行。</span><span class="sxs-lookup"><span data-stu-id="509cf-103">Gets the row at the specified row index, in the table at the specified table index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="509cf-104">语法</span><span class="sxs-lookup"><span data-stu-id="509cf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRow (
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="509cf-105">参数</span><span class="sxs-lookup"><span data-stu-id="509cf-105">Parameters</span></span>  

 `ixTbl`  
 <span data-ttu-id="509cf-106">中要从中检索行的表的索引。</span><span class="sxs-lookup"><span data-stu-id="509cf-106">[in] The index of the table from which the row will be retrieved.</span></span>  
  
 `rid`  
 <span data-ttu-id="509cf-107">中要获取的行的索引。</span><span class="sxs-lookup"><span data-stu-id="509cf-107">[in] The index of the row to get.</span></span>  
  
 `ppRow`  
 <span data-ttu-id="509cf-108">弄指向指向行的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="509cf-108">[out] A pointer to a pointer to the row.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="509cf-109">注解</span><span class="sxs-lookup"><span data-stu-id="509cf-109">Remarks</span></span>  

  <span data-ttu-id="509cf-110">不建议使用此方法，因为它不返回一致的结果。</span><span class="sxs-lookup"><span data-stu-id="509cf-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="509cf-111">有关 GUID 表的信息，请参阅公共语言基础结构 (CLI) 文档，尤其是 "第二部分：元数据定义和语义"。</span><span class="sxs-lookup"><span data-stu-id="509cf-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="509cf-112">文档在线提供;请参阅 [ECMA c # 和公共语言基础结构标准](../../../standard/components.md#applicable-standards) 和 [标准 ECMA-335-公共语言基础结构 (CLI) ](http://www.ecma-international.org/publications/standards/Ecma-335.htm)。</span><span class="sxs-lookup"><span data-stu-id="509cf-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="509cf-113">要求</span><span class="sxs-lookup"><span data-stu-id="509cf-113">Requirements</span></span>  

 <span data-ttu-id="509cf-114">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="509cf-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="509cf-115">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="509cf-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="509cf-116">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="509cf-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="509cf-117">**.NET Framework 版本**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="509cf-117">**.NET Framework Versions**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="509cf-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="509cf-118">See also</span></span>

- [<span data-ttu-id="509cf-119">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="509cf-119">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="509cf-120">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="509cf-120">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
