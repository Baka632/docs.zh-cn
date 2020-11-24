---
title: IMetaDataTables::GetTableIndex 方法
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetTableIndex
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetTableIndex
helpviewer_keywords:
- GetTableIndex method [.NET Framework metadata]
- IMetaDataTables::GetTableIndex method [.NET Framework metadata]
ms.assetid: c6ec3800-e0d9-4387-afb8-ddc0b818114c
topic_type:
- apiref
ms.openlocfilehash: 52d70a76bdf8380d320edb6e8188443070a36b1b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672547"
---
# <a name="imetadatatablesgettableindex-method"></a><span data-ttu-id="f2fd3-102">IMetaDataTables::GetTableIndex 方法</span><span class="sxs-lookup"><span data-stu-id="f2fd3-102">IMetaDataTables::GetTableIndex Method</span></span>

<span data-ttu-id="f2fd3-103">获取指定的标记所引用的表的索引。</span><span class="sxs-lookup"><span data-stu-id="f2fd3-103">Gets the index for the table referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2fd3-104">语法</span><span class="sxs-lookup"><span data-stu-id="f2fd3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTableIndex (  
    [in]  ULONG   token,  
    [out] ULONG   *pixTbl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2fd3-105">参数</span><span class="sxs-lookup"><span data-stu-id="f2fd3-105">Parameters</span></span>  

 `token`  
 <span data-ttu-id="f2fd3-106">中引用该表的标记。</span><span class="sxs-lookup"><span data-stu-id="f2fd3-106">[in] The token that references the table.</span></span>  
  
 `pixTbl`  
 <span data-ttu-id="f2fd3-107">弄指向所引用表的返回索引的指针。</span><span class="sxs-lookup"><span data-stu-id="f2fd3-107">[out] A pointer to the returned index for the referenced table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2fd3-108">注解</span><span class="sxs-lookup"><span data-stu-id="f2fd3-108">Remarks</span></span>  

 <span data-ttu-id="f2fd3-109">不建议使用此方法，因为它不返回一致的结果。</span><span class="sxs-lookup"><span data-stu-id="f2fd3-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="f2fd3-110">有关 GUID 表的信息，请参阅公共语言基础结构 (CLI) 文档，尤其是 "第二部分：元数据定义和语义"。</span><span class="sxs-lookup"><span data-stu-id="f2fd3-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="f2fd3-111">文档在线提供;请参阅 [ECMA c # 和公共语言基础结构标准](../../../standard/components.md#applicable-standards) 和 [标准 ECMA-335-公共语言基础结构 (CLI) ](http://www.ecma-international.org/publications/standards/Ecma-335.htm)。</span><span class="sxs-lookup"><span data-stu-id="f2fd3-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2fd3-112">要求</span><span class="sxs-lookup"><span data-stu-id="f2fd3-112">Requirements</span></span>  

 <span data-ttu-id="f2fd3-113">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f2fd3-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2fd3-114">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="f2fd3-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f2fd3-115">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f2fd3-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f2fd3-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2fd3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2fd3-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f2fd3-117">See also</span></span>

- [<span data-ttu-id="f2fd3-118">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="f2fd3-118">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="f2fd3-119">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="f2fd3-119">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
