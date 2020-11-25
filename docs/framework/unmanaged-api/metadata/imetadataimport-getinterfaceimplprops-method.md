---
title: IMetaDataImport::GetInterfaceImplProps 方法
ms.date: 02/25/2019
api_name:
- IMetaDataImport.GetInterfaceImplProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetInterfaceImplProps
helpviewer_keywords:
- IMetaDataImport::GetInterfaceImplProps method [.NET Framework metadata]
- GetInterfaceImpProps method [.NET Framework metadata]
ms.assetid: be3f5985-b1e4-4036-8602-c16e8508d4af
topic_type:
- apiref
ms.openlocfilehash: e81816ce2194c2c1862cb997ad2c6e5baf301231
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703991"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a><span data-ttu-id="1e780-102">IMetaDataImport::GetInterfaceImplProps 方法</span><span class="sxs-lookup"><span data-stu-id="1e780-102">IMetaDataImport::GetInterfaceImplProps Method</span></span>

<span data-ttu-id="1e780-103">获取一个指针，该指针指向实现指定方法的的元数据标记 <xref:System.Type> 和声明该方法的接口。</span><span class="sxs-lookup"><span data-stu-id="1e780-103">Gets a pointer to the metadata tokens for the <xref:System.Type> that implements the specified method, and for the interface that declares that method.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="1e780-104">语法</span><span class="sxs-lookup"><span data-stu-id="1e780-104">Syntax</span></span>  
  
```cpp  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e780-105">参数</span><span class="sxs-lookup"><span data-stu-id="1e780-105">Parameters</span></span>  

 `iiImpl`  
 <span data-ttu-id="1e780-106">中表示要为其返回类和接口标记的方法的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="1e780-106">[in] The metadata token representing the method to return the class and interface tokens for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="1e780-107">弄表示实现方法的类的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="1e780-107">[out] The metadata token representing the class that implements the method.</span></span>  
  
 `ptkIface`  
 <span data-ttu-id="1e780-108">弄表示用于定义实现的方法的接口的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="1e780-108">[out] The metadata token representing the interface that defines the implemented method.</span></span>  

## <a name="remarks"></a><span data-ttu-id="1e780-109">注解</span><span class="sxs-lookup"><span data-stu-id="1e780-109">Remarks</span></span>

 <span data-ttu-id="1e780-110">可以 `iImpl` 通过调用 [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) 方法来获取的值。</span><span class="sxs-lookup"><span data-stu-id="1e780-110">You obtain the value for `iImpl` by calling the [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) method.</span></span>

 <span data-ttu-id="1e780-111">例如，假设某个类的 `mdTypeDef` 标记值为0x02000007，并且它实现了三个类型具有标记的接口：</span><span class="sxs-lookup"><span data-stu-id="1e780-111">For example, suppose that a class has an `mdTypeDef` token value of 0x02000007 and that it implements three interfaces whose types have tokens:</span></span>

- <span data-ttu-id="1e780-112">0x02000003 (TypeDef) </span><span class="sxs-lookup"><span data-stu-id="1e780-112">0x02000003 (TypeDef)</span></span>
- <span data-ttu-id="1e780-113">0x0100000A (TypeRef) </span><span class="sxs-lookup"><span data-stu-id="1e780-113">0x0100000A (TypeRef)</span></span>
- <span data-ttu-id="1e780-114">0x0200001C (TypeDef) </span><span class="sxs-lookup"><span data-stu-id="1e780-114">0x0200001C (TypeDef)</span></span>

<span data-ttu-id="1e780-115">从概念上讲，此信息存储到接口实现表中，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1e780-115">Conceptually, this information is stored into an interface implementation table as:</span></span>

| <span data-ttu-id="1e780-116">行号</span><span class="sxs-lookup"><span data-stu-id="1e780-116">Row number</span></span> | <span data-ttu-id="1e780-117">类标记</span><span class="sxs-lookup"><span data-stu-id="1e780-117">Class token</span></span> | <span data-ttu-id="1e780-118">接口令牌</span><span class="sxs-lookup"><span data-stu-id="1e780-118">Interface token</span></span> |
|------------|-------------|-----------------|
| <span data-ttu-id="1e780-119">4</span><span class="sxs-lookup"><span data-stu-id="1e780-119">4</span></span>          |             |                 |
| <span data-ttu-id="1e780-120">5</span><span class="sxs-lookup"><span data-stu-id="1e780-120">5</span></span>          | <span data-ttu-id="1e780-121">02000007</span><span class="sxs-lookup"><span data-stu-id="1e780-121">02000007</span></span>    | <span data-ttu-id="1e780-122">02000003</span><span class="sxs-lookup"><span data-stu-id="1e780-122">02000003</span></span>        |
| <span data-ttu-id="1e780-123">6</span><span class="sxs-lookup"><span data-stu-id="1e780-123">6</span></span>          | <span data-ttu-id="1e780-124">02000007</span><span class="sxs-lookup"><span data-stu-id="1e780-124">02000007</span></span>    | <span data-ttu-id="1e780-125">0100000A</span><span class="sxs-lookup"><span data-stu-id="1e780-125">0100000A</span></span>        |
| <span data-ttu-id="1e780-126">7</span><span class="sxs-lookup"><span data-stu-id="1e780-126">7</span></span>          |             |                 |
| <span data-ttu-id="1e780-127">8</span><span class="sxs-lookup"><span data-stu-id="1e780-127">8</span></span>          | <span data-ttu-id="1e780-128">02000007</span><span class="sxs-lookup"><span data-stu-id="1e780-128">02000007</span></span>    | <span data-ttu-id="1e780-129">0200001C</span><span class="sxs-lookup"><span data-stu-id="1e780-129">0200001C</span></span>        |

<span data-ttu-id="1e780-130">请记住，该令牌是一个4字节的值：</span><span class="sxs-lookup"><span data-stu-id="1e780-130">Recall, the token is a 4-byte value:</span></span>

- <span data-ttu-id="1e780-131">下3个字节保存行号或 RID。</span><span class="sxs-lookup"><span data-stu-id="1e780-131">The lower 3 bytes hold the row number, or RID.</span></span>
- <span data-ttu-id="1e780-132">上部字节保留标记类型– 0x09 `mdtInterfaceImpl` 。</span><span class="sxs-lookup"><span data-stu-id="1e780-132">The upper byte holds the token type – 0x09 for `mdtInterfaceImpl`.</span></span>

<span data-ttu-id="1e780-133">`GetInterfaceImplProps` 返回在参数中提供其标记的行中保存的信息 `iImpl` 。</span><span class="sxs-lookup"><span data-stu-id="1e780-133">`GetInterfaceImplProps` returns the information held in the row whose token you provide in the `iImpl` argument.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="1e780-134">要求</span><span class="sxs-lookup"><span data-stu-id="1e780-134">Requirements</span></span>  

 <span data-ttu-id="1e780-135">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1e780-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e780-136">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="1e780-136">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1e780-137">**库：** 作为中的资源包含 MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1e780-137">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1e780-138">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e780-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e780-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1e780-139">See also</span></span>

- [<span data-ttu-id="1e780-140">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="1e780-140">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="1e780-141">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="1e780-141">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
