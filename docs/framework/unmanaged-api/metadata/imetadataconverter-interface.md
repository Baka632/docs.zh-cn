---
title: IMetaDataConverter 接口
ms.date: 03/30/2017
api_name:
- IMetaDataConverter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter
helpviewer_keywords:
- IMetaDataConverter interface [.NET Framework metadata]
ms.assetid: 9caea662-0167-4267-b14a-2fa42c3be4ea
topic_type:
- apiref
ms.openlocfilehash: 74804cdc9dc04c3ede5cc26a6310dbb3948cd78a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729481"
---
# <a name="imetadataconverter-interface"></a><span data-ttu-id="e7a90-102">IMetaDataConverter 接口</span><span class="sxs-lookup"><span data-stu-id="e7a90-102">IMetaDataConverter Interface</span></span>

<span data-ttu-id="e7a90-103">提供将类型库映射到其元数据签名并进行相互转换的方法。</span><span class="sxs-lookup"><span data-stu-id="e7a90-103">Provides methods to map type libraries to their metadata signatures, and to convert from one to the other.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e7a90-104">方法</span><span class="sxs-lookup"><span data-stu-id="e7a90-104">Methods</span></span>  
  
|<span data-ttu-id="e7a90-105">方法</span><span class="sxs-lookup"><span data-stu-id="e7a90-105">Method</span></span>|<span data-ttu-id="e7a90-106">说明</span><span class="sxs-lookup"><span data-stu-id="e7a90-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e7a90-107">GetMetaDataFromTypeInfo 方法</span><span class="sxs-lookup"><span data-stu-id="e7a90-107">GetMetaDataFromTypeInfo Method</span></span>](imetadataconverter-getmetadatafromtypeinfo-method.md)|<span data-ttu-id="e7a90-108">获取一个指针，该指针指向表示指定实例引用的类型库的元数据签名的 [IMetaDataImport](imetadataimport-interface.md) 实例 `ITypeInfo` 。</span><span class="sxs-lookup"><span data-stu-id="e7a90-108">Gets a pointer to an [IMetaDataImport](imetadataimport-interface.md) instance that represents the metadata signature for the type library referenced by the specified `ITypeInfo` instance.</span></span>|  
|[<span data-ttu-id="e7a90-109">GetMetaDataFromTypeLib 方法</span><span class="sxs-lookup"><span data-stu-id="e7a90-109">GetMetaDataFromTypeLib Method</span></span>](imetadataconverter-getmetadatafromtypelib-method.md)|<span data-ttu-id="e7a90-110">获取一个指针，该指针指向 `IMetaDataImport` 表示指定实例所表示的类型库的元数据签名的实例 `ITypeLib` 。</span><span class="sxs-lookup"><span data-stu-id="e7a90-110">Gets a pointer to an `IMetaDataImport` instance that represents the metadata signature for the type library represented by the specified `ITypeLib` instance.</span></span>|  
|[<span data-ttu-id="e7a90-111">GetTypeLibFromMetaData 方法</span><span class="sxs-lookup"><span data-stu-id="e7a90-111">GetTypeLibFromMetaData Method</span></span>](imetadataconverter-gettypelibfrommetadata-method.md)|<span data-ttu-id="e7a90-112">获取一个指向实例的指针，该 `ITypeLib` 对象表示具有指定模块和库名称的类型库。</span><span class="sxs-lookup"><span data-stu-id="e7a90-112">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified module and library names.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e7a90-113">要求</span><span class="sxs-lookup"><span data-stu-id="e7a90-113">Requirements</span></span>  

 <span data-ttu-id="e7a90-114">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e7a90-114">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7a90-115">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="e7a90-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e7a90-116">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e7a90-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e7a90-117">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7a90-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7a90-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e7a90-118">See also</span></span>

- [<span data-ttu-id="e7a90-119">元数据接口</span><span class="sxs-lookup"><span data-stu-id="e7a90-119">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="e7a90-120">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="e7a90-120">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
