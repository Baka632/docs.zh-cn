---
title: IAppIdAuthority 接口
ms.date: 03/30/2017
api_name:
- IAppIdAuthority
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAppIdAuthority
helpviewer_keywords:
- IAppIdAuthority interface [.NET Framework fusion]
ms.assetid: ec354fa1-1efd-41b0-bc43-b90597b6e253
topic_type:
- apiref
ms.openlocfilehash: a344f2ab5d9a7aa92018c47ee7a162cd1721aeb5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732107"
---
# <a name="iappidauthority-interface"></a><span data-ttu-id="8897b-102">IAppIdAuthority 接口</span><span class="sxs-lookup"><span data-stu-id="8897b-102">IAppIdAuthority Interface</span></span>

<span data-ttu-id="8897b-103">提供一些方法，这些方法可为应用程序标识和引用生成和比较键。</span><span class="sxs-lookup"><span data-stu-id="8897b-103">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8897b-104">方法</span><span class="sxs-lookup"><span data-stu-id="8897b-104">Methods</span></span>  
  
|<span data-ttu-id="8897b-105">方法</span><span class="sxs-lookup"><span data-stu-id="8897b-105">Method</span></span>|<span data-ttu-id="8897b-106">说明</span><span class="sxs-lookup"><span data-stu-id="8897b-106">Description</span></span>|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|<span data-ttu-id="8897b-107">获取一个值，该值指示两个指定的 [IDefinitionAppId](idefinitionappid-interface.md) 实例是否相等。</span><span class="sxs-lookup"><span data-stu-id="8897b-107">Gets a value that indicates whether the two specified [IDefinitionAppId](idefinitionappid-interface.md) instances are equal.</span></span> <span data-ttu-id="8897b-108">可以将标志值 IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION 传递给，以忽略其各自的版本信息。</span><span class="sxs-lookup"><span data-stu-id="8897b-108">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreReferencesEqual`|<span data-ttu-id="8897b-109">获取一个值，该值指示两个指定的 [IReferenceAppId](ireferenceappid-interface.md) 实例是否相等。</span><span class="sxs-lookup"><span data-stu-id="8897b-109">Gets a value that indicates whether the two specified [IReferenceAppId](ireferenceappid-interface.md) instances are equal.</span></span> <span data-ttu-id="8897b-110">可以将标志值 IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION 传递给，以忽略其各自的版本信息。</span><span class="sxs-lookup"><span data-stu-id="8897b-110">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="8897b-111">获取一个值，该值指示两个指定的字符串定义是否相等。</span><span class="sxs-lookup"><span data-stu-id="8897b-111">Gets a value that indicates whether the two specified string definitions are equal.</span></span> <span data-ttu-id="8897b-112">可以将标志值 IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION 传递给，以忽略其各自的版本信息。</span><span class="sxs-lookup"><span data-stu-id="8897b-112">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualReferencesEqual`|<span data-ttu-id="8897b-113">获取一个值，该值指示两个指定的字符串引用是否相等。</span><span class="sxs-lookup"><span data-stu-id="8897b-113">Gets a value that indicates whether the two specified string references are equal.</span></span> <span data-ttu-id="8897b-114">可以将标志值 IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION 传递给，以忽略其各自的版本信息。</span><span class="sxs-lookup"><span data-stu-id="8897b-114">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::CreateDefinition`|<span data-ttu-id="8897b-115">获取一个接口指针，该指针指向 `IDefinitionAppId` 表示当前范围内的程序集的新生成的实例。</span><span class="sxs-lookup"><span data-stu-id="8897b-115">Gets an interface pointer to a newly generated `IDefinitionAppId` instance that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::CreateReference`|<span data-ttu-id="8897b-116">获取一个接口指针，该指针指向 `IReferenceAppId` 表示当前范围内的程序集的新创建的。</span><span class="sxs-lookup"><span data-stu-id="8897b-116">Gets an interface pointer to a newly created `IReferenceAppId` that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::DefinitionToText`|<span data-ttu-id="8897b-117">使用指定的标志值获取指定的的字符串版本 `IDefinitionAppId` 。</span><span class="sxs-lookup"><span data-stu-id="8897b-117">Gets a string version of the specified `IDefinitionAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="8897b-118">获取一个值，该值指示指定的 `IDefinitionAppId` 是否 `IReferenceAppId` 表示相同的程序集。</span><span class="sxs-lookup"><span data-stu-id="8897b-118">Gets a value that indicates whether the specified `IDefinitionAppId` and `IReferenceAppId` represent the same assembly.</span></span>|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="8897b-119">获取一个值，该值指示指定的定义字符串和引用字符串是否表示相同的程序集。</span><span class="sxs-lookup"><span data-stu-id="8897b-119">Gets a value that indicates whether the specified definition string and reference string represent the same assembly.</span></span>|  
|`IAppIdAuthority::GenerateDefinitionKey`|<span data-ttu-id="8897b-120">获取表示指定实例的字符串键 `IDefinitionAppId` 。</span><span class="sxs-lookup"><span data-stu-id="8897b-120">Gets a string key that represents the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::GenerateReferenceKey`|<span data-ttu-id="8897b-121">获取表示指定实例的字符串键 `IReferenceAppId` 。</span><span class="sxs-lookup"><span data-stu-id="8897b-121">Gets a string key that represents the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::HashDefinition`|<span data-ttu-id="8897b-122">获取指定实例的哈希键 `IDefinitionAppId` 。</span><span class="sxs-lookup"><span data-stu-id="8897b-122">Gets a hash key for the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::HashReference`|<span data-ttu-id="8897b-123">获取指定实例的哈希键 `IReferenceAppId` 。</span><span class="sxs-lookup"><span data-stu-id="8897b-123">Gets a hash key for the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::ReferenceToText`|<span data-ttu-id="8897b-124">使用指定的标志值获取指定的的字符串版本 `IReferenceAppId` 。</span><span class="sxs-lookup"><span data-stu-id="8897b-124">Gets a string version of the specified `IReferenceAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::TextToDefinition`|<span data-ttu-id="8897b-125">获取一个接口指针，该指针指向 `IDefinitionAppId` 表示指定字符串键所引用的程序集的实例。</span><span class="sxs-lookup"><span data-stu-id="8897b-125">Gets an interface pointer to an `IDefinitionAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
|`IAppIdAuthority::TextToReference`|<span data-ttu-id="8897b-126">获取一个接口指针，该指针指向 `IReferenceAppId` 表示指定字符串键所引用的程序集的实例。</span><span class="sxs-lookup"><span data-stu-id="8897b-126">Gets an interface pointer to an `IReferenceAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8897b-127">要求</span><span class="sxs-lookup"><span data-stu-id="8897b-127">Requirements</span></span>  

 <span data-ttu-id="8897b-128">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8897b-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8897b-129">**标头：** 隔离。h</span><span class="sxs-lookup"><span data-stu-id="8897b-129">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="8897b-130">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8897b-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8897b-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8897b-131">See also</span></span>

- [<span data-ttu-id="8897b-132">合成接口</span><span class="sxs-lookup"><span data-stu-id="8897b-132">Fusion Interfaces</span></span>](fusion-interfaces.md)
