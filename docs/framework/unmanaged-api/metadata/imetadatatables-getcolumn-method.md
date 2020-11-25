---
title: IMetaDataTables::GetColumn 方法
ms.date: 02/25/2019
api_name:
- IMetaDataTables.GetColumn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumn
helpviewer_keywords:
- IMetaDataTables::GetColumn method [.NET Framework metadata]
- GetColumn method [.NET Framework metadata]
ms.assetid: 1032055b-cabb-45c5-a50e-7e853201b175
topic_type:
- apiref
ms.openlocfilehash: 270546f0270521e38cfdcae5e4d2137202c13cb1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711062"
---
# <a name="imetadatatablesgetcolumn-method"></a><span data-ttu-id="80c7e-102">IMetaDataTables::GetColumn 方法</span><span class="sxs-lookup"><span data-stu-id="80c7e-102">IMetaDataTables::GetColumn Method</span></span>

<span data-ttu-id="80c7e-103">获取一个指针，该指针指向给定表中指定列和行的单元中包含的值。</span><span class="sxs-lookup"><span data-stu-id="80c7e-103">Gets a pointer to the value contained in the cell of the specified column and row in the given table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80c7e-104">语法</span><span class="sxs-lookup"><span data-stu-id="80c7e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetColumn (
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80c7e-105">参数</span><span class="sxs-lookup"><span data-stu-id="80c7e-105">Parameters</span></span>

 `ixTbl`  
 <span data-ttu-id="80c7e-106">中表的索引。</span><span class="sxs-lookup"><span data-stu-id="80c7e-106">[in] The index of the table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="80c7e-107">中表中的列的索引。</span><span class="sxs-lookup"><span data-stu-id="80c7e-107">[in] The index of the column in the table.</span></span>  
  
 `rid`  
 <span data-ttu-id="80c7e-108">中表中的行的索引。</span><span class="sxs-lookup"><span data-stu-id="80c7e-108">[in] The index of the row in the table.</span></span>  
  
 `pVal`  
 <span data-ttu-id="80c7e-109">弄指向单元格中的值的指针。</span><span class="sxs-lookup"><span data-stu-id="80c7e-109">[out] A pointer to the value in the cell.</span></span>  

## <a name="remarks"></a><span data-ttu-id="80c7e-110">注解</span><span class="sxs-lookup"><span data-stu-id="80c7e-110">Remarks</span></span>

<span data-ttu-id="80c7e-111">返回的值的 interpretion `pVal` 取决于列的类型。</span><span class="sxs-lookup"><span data-stu-id="80c7e-111">The interpretion of the value returned through `pVal` depends on the column's type.</span></span> <span data-ttu-id="80c7e-112">列类型可通过调用 [IMetaDataTables](imetadatatables-getcolumninfo-method.md)来确定。</span><span class="sxs-lookup"><span data-stu-id="80c7e-112">The column type can be determined by calling [IMetaDataTables.GetColumnInfo](imetadatatables-getcolumninfo-method.md).</span></span>

- <span data-ttu-id="80c7e-113">**GetColumn** 方法自动将 **Rid** 或 **CodedToken** 类型的列转换为完整的32位 `mdToken` 值。</span><span class="sxs-lookup"><span data-stu-id="80c7e-113">The **GetColumn** method automatically converts columns of type **Rid** or **CodedToken** to full 32-bit `mdToken` values.</span></span>
- <span data-ttu-id="80c7e-114">它还会自动将8位或16位值转换为完整的32位值。</span><span class="sxs-lookup"><span data-stu-id="80c7e-114">It also automatically converts 8-bit or 16-bit values to full 32-bit values.</span></span>
- <span data-ttu-id="80c7e-115">对于 *堆* 类型列，返回的 *pVal* 将是对应堆中的索引。</span><span class="sxs-lookup"><span data-stu-id="80c7e-115">For *heap* type columns, the returned *pVal* will be an index into the corresponding heap.</span></span>

| <span data-ttu-id="80c7e-116">列类型</span><span class="sxs-lookup"><span data-stu-id="80c7e-116">Column type</span></span>              | <span data-ttu-id="80c7e-117">pVal 包含</span><span class="sxs-lookup"><span data-stu-id="80c7e-117">pVal contains</span></span> | <span data-ttu-id="80c7e-118">注释</span><span class="sxs-lookup"><span data-stu-id="80c7e-118">Comment</span></span>                          |
|--------------------------|---------------|-----------------------------------|
| <span data-ttu-id="80c7e-119">`0`..`iRidMax`</span><span class="sxs-lookup"><span data-stu-id="80c7e-119">`0`..`iRidMax`</span></span><br><span data-ttu-id="80c7e-120"> (0. 63) </span><span class="sxs-lookup"><span data-stu-id="80c7e-120">(0..63)</span></span>  | <span data-ttu-id="80c7e-121">mdToken</span><span class="sxs-lookup"><span data-stu-id="80c7e-121">mdToken</span></span>     | <span data-ttu-id="80c7e-122">*pVal* 将包含一个完整的令牌。</span><span class="sxs-lookup"><span data-stu-id="80c7e-122">*pVal* will contain a full Token.</span></span> <span data-ttu-id="80c7e-123">函数自动将 Rid 转换为完整的标记。</span><span class="sxs-lookup"><span data-stu-id="80c7e-123">The function automatically converts the Rid into a full token.</span></span> |
| <span data-ttu-id="80c7e-124">`iCodedToken`..`iCodedTokenMax`</span><span class="sxs-lookup"><span data-stu-id="80c7e-124">`iCodedToken`..`iCodedTokenMax`</span></span><br><span data-ttu-id="80c7e-125"> (64.. 95) </span><span class="sxs-lookup"><span data-stu-id="80c7e-125">(64..95)</span></span> | <span data-ttu-id="80c7e-126">mdToken</span><span class="sxs-lookup"><span data-stu-id="80c7e-126">mdToken</span></span> | <span data-ttu-id="80c7e-127">返回后， *pVal* 将包含一个完整的令牌。</span><span class="sxs-lookup"><span data-stu-id="80c7e-127">Upon return, *pVal* will contain a full Token.</span></span> <span data-ttu-id="80c7e-128">函数自动将 CodedToken 解压缩到完整的令牌中。</span><span class="sxs-lookup"><span data-stu-id="80c7e-128">The function automatically decompresses the CodedToken into a full token.</span></span> |
| <span data-ttu-id="80c7e-129">`iSHORT` (96) </span><span class="sxs-lookup"><span data-stu-id="80c7e-129">`iSHORT` (96)</span></span>            | <span data-ttu-id="80c7e-130">Int16</span><span class="sxs-lookup"><span data-stu-id="80c7e-130">Int16</span></span>         | <span data-ttu-id="80c7e-131">自动将符号扩展为32位。</span><span class="sxs-lookup"><span data-stu-id="80c7e-131">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="80c7e-132">`iUSHORT` (97) </span><span class="sxs-lookup"><span data-stu-id="80c7e-132">`iUSHORT` (97)</span></span>           | <span data-ttu-id="80c7e-133">UInt16</span><span class="sxs-lookup"><span data-stu-id="80c7e-133">UInt16</span></span>        | <span data-ttu-id="80c7e-134">自动将符号扩展为32位。</span><span class="sxs-lookup"><span data-stu-id="80c7e-134">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="80c7e-135">`iLONG` (98) </span><span class="sxs-lookup"><span data-stu-id="80c7e-135">`iLONG` (98)</span></span>             | <span data-ttu-id="80c7e-136">Int32</span><span class="sxs-lookup"><span data-stu-id="80c7e-136">Int32</span></span>         |                                        |
| <span data-ttu-id="80c7e-137">`iULONG` (99) </span><span class="sxs-lookup"><span data-stu-id="80c7e-137">`iULONG` (99)</span></span>            | <span data-ttu-id="80c7e-138">UInt32</span><span class="sxs-lookup"><span data-stu-id="80c7e-138">UInt32</span></span>        |                                        |
| <span data-ttu-id="80c7e-139">`iBYTE` (100) </span><span class="sxs-lookup"><span data-stu-id="80c7e-139">`iBYTE` (100)</span></span>            | <span data-ttu-id="80c7e-140">Byte</span><span class="sxs-lookup"><span data-stu-id="80c7e-140">Byte</span></span>          | <span data-ttu-id="80c7e-141">自动将符号扩展为32位。</span><span class="sxs-lookup"><span data-stu-id="80c7e-141">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="80c7e-142">`iSTRING` (101) </span><span class="sxs-lookup"><span data-stu-id="80c7e-142">`iSTRING` (101)</span></span>          | <span data-ttu-id="80c7e-143">字符串堆索引</span><span class="sxs-lookup"><span data-stu-id="80c7e-143">String heap index</span></span> | <span data-ttu-id="80c7e-144">*pVal* 是字符串堆中的索引。</span><span class="sxs-lookup"><span data-stu-id="80c7e-144">*pVal* is an index into the String heap.</span></span> <span data-ttu-id="80c7e-145">使用 [IMetadataTables：： GetString](imetadatatables-getstring-method.md) 获取实际的列字符串值。</span><span class="sxs-lookup"><span data-stu-id="80c7e-145">Use [IMetadataTables::GetString](imetadatatables-getstring-method.md) to get the actual column String value.</span></span> |
| <span data-ttu-id="80c7e-146">`iGUID` (102) </span><span class="sxs-lookup"><span data-stu-id="80c7e-146">`iGUID` (102)</span></span>            | <span data-ttu-id="80c7e-147">Guid 堆索引</span><span class="sxs-lookup"><span data-stu-id="80c7e-147">Guid heap index</span></span> | <span data-ttu-id="80c7e-148">*pVal* 是 Guid 堆中的索引。</span><span class="sxs-lookup"><span data-stu-id="80c7e-148">*pVal* is an index into the Guid heap.</span></span> <span data-ttu-id="80c7e-149">使用 [IMetadataTables：： GetGuid](imetadatatables-getguid-method.md) 获取实际的列 Guid 值。</span><span class="sxs-lookup"><span data-stu-id="80c7e-149">Use [IMetadataTables::GetGuid](imetadatatables-getguid-method.md) to get the actual column Guid value.</span></span> |
| <span data-ttu-id="80c7e-150">`iBLOB` (103) </span><span class="sxs-lookup"><span data-stu-id="80c7e-150">`iBLOB` (103)</span></span>            | <span data-ttu-id="80c7e-151">Blob 堆索引</span><span class="sxs-lookup"><span data-stu-id="80c7e-151">Blob heap index</span></span> | <span data-ttu-id="80c7e-152">*pVal* 是 Blob 堆中的索引。</span><span class="sxs-lookup"><span data-stu-id="80c7e-152">*pVal* is an index into the Blob heap.</span></span> <span data-ttu-id="80c7e-153">使用 [IMetadataTables：： GetBlob](imetadatatables-getblob-method.md) 获取实际的列 Blob 值。</span><span class="sxs-lookup"><span data-stu-id="80c7e-153">Use [IMetadataTables::GetBlob](imetadatatables-getblob-method.md) to get the actual column Blob value.</span></span> |
  
## <a name="requirements"></a><span data-ttu-id="80c7e-154">要求</span><span class="sxs-lookup"><span data-stu-id="80c7e-154">Requirements</span></span>  

 <span data-ttu-id="80c7e-155">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="80c7e-155">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80c7e-156">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="80c7e-156">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="80c7e-157">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="80c7e-157">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="80c7e-158">**.NET Framework 版本**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80c7e-158">**.NET Framework Versions** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80c7e-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="80c7e-159">See also</span></span>

- [<span data-ttu-id="80c7e-160">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="80c7e-160">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="80c7e-161">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="80c7e-161">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
