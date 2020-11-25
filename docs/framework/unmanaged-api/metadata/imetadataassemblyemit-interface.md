---
title: IMetaDataAssemblyEmit 接口
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit
helpviewer_keywords:
- IMetaDataAssemblyEmit interface [.NET Framework metadata]
ms.assetid: 34fb03cc-2285-4a45-ac48-ad993b7a921a
topic_type:
- apiref
ms.openlocfilehash: 5d8bc54a94e1571ff8335c934407bbf235179ecc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728285"
---
# <a name="imetadataassemblyemit-interface"></a><span data-ttu-id="f1111-102">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="f1111-102">IMetaDataAssemblyEmit Interface</span></span>

<span data-ttu-id="f1111-103">提供支持公共语言运行时用于解析和使用资源的自描述模型的方法。</span><span class="sxs-lookup"><span data-stu-id="f1111-103">Provides methods that support the self-description model used by the common language runtime to resolve and consume resources.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f1111-104">方法</span><span class="sxs-lookup"><span data-stu-id="f1111-104">Methods</span></span>  
  
|<span data-ttu-id="f1111-105">方法</span><span class="sxs-lookup"><span data-stu-id="f1111-105">Method</span></span>|<span data-ttu-id="f1111-106">说明</span><span class="sxs-lookup"><span data-stu-id="f1111-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f1111-107">DefineAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="f1111-107">DefineAssembly Method</span></span>](imetadataassemblyemit-defineassembly-method.md)|<span data-ttu-id="f1111-108">创建包含指定程序集的元数据的程序集数据结构，并返回关联的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="f1111-108">Creates an assembly data structure containing metadata for the specified assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="f1111-109">DefineAssemblyRef 方法</span><span class="sxs-lookup"><span data-stu-id="f1111-109">DefineAssemblyRef Method</span></span>](imetadataassemblyemit-defineassemblyref-method.md)|<span data-ttu-id="f1111-110">创建包含此程序集引用的程序集的元数据的 `AssemblyRef` 结构，并返回关联的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="f1111-110">Creates an `AssemblyRef` structure containing metadata for the assembly that this assembly references, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="f1111-111">DefineExportedType 方法</span><span class="sxs-lookup"><span data-stu-id="f1111-111">DefineExportedType Method</span></span>](imetadataassemblyemit-defineexportedtype-method.md)|<span data-ttu-id="f1111-112">创建包含指定导出类型的元数据的 `ExportedType` 结构，并返回关联的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="f1111-112">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="f1111-113">DefineFile 方法</span><span class="sxs-lookup"><span data-stu-id="f1111-113">DefineFile Method</span></span>](imetadataassemblyemit-definefile-method.md)|<span data-ttu-id="f1111-114">创建包含此程序集引用的程序集的元数据的 `File` 元数据结构，并返回关联的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="f1111-114">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="f1111-115">DefineManifestResource 方法</span><span class="sxs-lookup"><span data-stu-id="f1111-115">DefineManifestResource Method</span></span>](imetadataassemblyemit-definemanifestresource-method.md)|<span data-ttu-id="f1111-116">创建包含指定清单资源的元数据的 `ManifestResource` 结构，并返回关联的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="f1111-116">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="f1111-117">SetAssemblyProps 方法</span><span class="sxs-lookup"><span data-stu-id="f1111-117">SetAssemblyProps Method</span></span>](imetadataassemblyemit-setassemblyprops-method.md)|<span data-ttu-id="f1111-118">修改指定的 `Assembly` 元数据结构。</span><span class="sxs-lookup"><span data-stu-id="f1111-118">Modifies the specified `Assembly` metadata structure.</span></span>|  
|[<span data-ttu-id="f1111-119">SetAssemblyRefProps 方法</span><span class="sxs-lookup"><span data-stu-id="f1111-119">SetAssemblyRefProps Method</span></span>](imetadataassemblyemit-setassemblyrefprops-method.md)|<span data-ttu-id="f1111-120">修改指定的 `AssemblyRef` 元数据结构。</span><span class="sxs-lookup"><span data-stu-id="f1111-120">Modifies the specified `AssemblyRef` metadata structure.</span></span>|  
|[<span data-ttu-id="f1111-121">SetExportedTypeProps 方法</span><span class="sxs-lookup"><span data-stu-id="f1111-121">SetExportedTypeProps Method</span></span>](imetadataassemblyemit-setexportedtypeprops-method.md)|<span data-ttu-id="f1111-122">修改指定的 `ExportedType` 元数据结构。</span><span class="sxs-lookup"><span data-stu-id="f1111-122">Modifies the specified `ExportedType` metadata structure.</span></span>|  
|[<span data-ttu-id="f1111-123">SetFileProps 方法</span><span class="sxs-lookup"><span data-stu-id="f1111-123">SetFileProps Method</span></span>](imetadataassemblyemit-setfileprops-method.md)|<span data-ttu-id="f1111-124">修改指定的 `File` 元数据结构。</span><span class="sxs-lookup"><span data-stu-id="f1111-124">Modifies the specified `File` metadata structure.</span></span>|  
|[<span data-ttu-id="f1111-125">SetManifestResourceProps 方法</span><span class="sxs-lookup"><span data-stu-id="f1111-125">SetManifestResourceProps Method</span></span>](imetadataassemblyemit-setmanifestresourceprops-method.md)|<span data-ttu-id="f1111-126">修改指定的 `ManifestResource` 元数据结构。</span><span class="sxs-lookup"><span data-stu-id="f1111-126">Modifies the specified `ManifestResource` metadata structure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1111-127">备注</span><span class="sxs-lookup"><span data-stu-id="f1111-127">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1111-128">要求</span><span class="sxs-lookup"><span data-stu-id="f1111-128">Requirements</span></span>  

 <span data-ttu-id="f1111-129">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f1111-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1111-130">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="f1111-130">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f1111-131">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f1111-131">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f1111-132">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1111-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1111-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f1111-133">See also</span></span>

- [<span data-ttu-id="f1111-134">元数据接口</span><span class="sxs-lookup"><span data-stu-id="f1111-134">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="f1111-135">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="f1111-135">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
