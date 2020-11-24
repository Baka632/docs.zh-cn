---
title: IMetaDataTables::GetTableInfo 方法
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetTableInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetTableInfo
helpviewer_keywords:
- IMetaDataTables::GetTableInfo method [.NET Framework metadata]
- GetTableInfo method [.NET Framework metadata]
ms.assetid: 50cbe557-2322-41aa-8e0d-f967602eaa0f
topic_type:
- apiref
ms.openlocfilehash: 65943ac169106a95feaff7d44017444e65764b60
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672521"
---
# <a name="imetadatatablesgettableinfo-method"></a><span data-ttu-id="69eb9-102">IMetaDataTables::GetTableInfo 方法</span><span class="sxs-lookup"><span data-stu-id="69eb9-102">IMetaDataTables::GetTableInfo Method</span></span>

<span data-ttu-id="69eb9-103">获取指定表的名称、行大小、行数、列数和键列索引。</span><span class="sxs-lookup"><span data-stu-id="69eb9-103">Gets the name, row size, number of rows, number of columns, and key column index of the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69eb9-104">语法</span><span class="sxs-lookup"><span data-stu-id="69eb9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTableInfo (  
    [in]  ULONG       ixTbl,  
    [out] ULONG       *pcbRow,  
    [out] ULONG       *pcRows,  
    [out] ULONG       *pcCols,  
    [out] ULONG       *piKey,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69eb9-105">参数</span><span class="sxs-lookup"><span data-stu-id="69eb9-105">Parameters</span></span>  

 `ixTbl`  
 <span data-ttu-id="69eb9-106">中要返回其属性的表的标识符。</span><span class="sxs-lookup"><span data-stu-id="69eb9-106">[in] The identifier of the table whose properties to return.</span></span>  
  
 `pcbRow`  
 <span data-ttu-id="69eb9-107">弄一个指针，指向表行的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="69eb9-107">[out] A pointer to the size, in bytes, of a table row.</span></span>  
  
 `pcRows`  
 <span data-ttu-id="69eb9-108">弄一个指针，指向表中的行数。</span><span class="sxs-lookup"><span data-stu-id="69eb9-108">[out] A pointer to the number of rows in the table.</span></span>  
  
 `pcCols`  
 <span data-ttu-id="69eb9-109">弄指向表中的列数的指针。</span><span class="sxs-lookup"><span data-stu-id="69eb9-109">[out] A pointer to the number of columns in the table.</span></span>  
  
 `piKey`  
 <span data-ttu-id="69eb9-110">弄指向键列的索引的指针; 如果表没有键列，则为-1。</span><span class="sxs-lookup"><span data-stu-id="69eb9-110">[out] A pointer to the index of the key column, or -1 if the table has no key column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="69eb9-111">弄指向表名称的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="69eb9-111">[out] A pointer to a pointer to the table name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69eb9-112">要求</span><span class="sxs-lookup"><span data-stu-id="69eb9-112">Requirements</span></span>  

 <span data-ttu-id="69eb9-113">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="69eb9-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69eb9-114">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="69eb9-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="69eb9-115">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="69eb9-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="69eb9-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69eb9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69eb9-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="69eb9-117">See also</span></span>

- [<span data-ttu-id="69eb9-118">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="69eb9-118">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="69eb9-119">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="69eb9-119">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
