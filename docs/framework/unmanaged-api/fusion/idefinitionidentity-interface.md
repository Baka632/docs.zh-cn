---
title: IDefinitionIdentity 接口
ms.date: 03/30/2017
api_name:
- IDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionIdentity
helpviewer_keywords:
- IDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: ce5ba888-5fbe-4efd-91cf-f0ff94d8428b
topic_type:
- apiref
ms.openlocfilehash: 4f08fbbf9c8be16dff092327713e731c5aa14661
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732859"
---
# <a name="idefinitionidentity-interface"></a><span data-ttu-id="deb9f-102">IDefinitionIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="deb9f-102">IDefinitionIdentity Interface</span></span>

<span data-ttu-id="deb9f-103">表示定义当前作用域中的应用程序的代码的唯一签名。</span><span class="sxs-lookup"><span data-stu-id="deb9f-103">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="deb9f-104">方法</span><span class="sxs-lookup"><span data-stu-id="deb9f-104">Methods</span></span>  
  
|<span data-ttu-id="deb9f-105">方法</span><span class="sxs-lookup"><span data-stu-id="deb9f-105">Method</span></span>|<span data-ttu-id="deb9f-106">说明</span><span class="sxs-lookup"><span data-stu-id="deb9f-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|<span data-ttu-id="deb9f-107">获取一个接口指针，该指针指向与 `IDefinitionIdentity` 此相同的新对象 `IDefinitionIdentity` ，但指定的特性更改除外。</span><span class="sxs-lookup"><span data-stu-id="deb9f-107">Gets an interface pointer to a new `IDefinitionIdentity` object that is identical to this `IDefinitionIdentity`, except for the specified attribute changes.</span></span>|  
|`IDefinitionIdentity::EnumAttributes`|<span data-ttu-id="deb9f-108">获取一个指向 [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) 对象的接口指针，该对象包含与此关联的特性 `IDefinitionIdentity` 。</span><span class="sxs-lookup"><span data-stu-id="deb9f-108">Gets an interface pointer to an [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) object that contains the attributes associated with this `IDefinitionIdentity`.</span></span>|  
|`IDefinitionIdentity::GetAttribute`|<span data-ttu-id="deb9f-109">获取指定命名空间中具有指定名称的属性的值。</span><span class="sxs-lookup"><span data-stu-id="deb9f-109">Gets the value of the attribute with the specified name in the specified namespace.</span></span>|  
|`IDefinitionIdentity::SetAttribute`|<span data-ttu-id="deb9f-110">将指定命名空间中具有指定名称的特性设置为指定值。</span><span class="sxs-lookup"><span data-stu-id="deb9f-110">Sets the attribute that has the specified name in the specified namespace to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="deb9f-111">要求</span><span class="sxs-lookup"><span data-stu-id="deb9f-111">Requirements</span></span>  

 <span data-ttu-id="deb9f-112">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="deb9f-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="deb9f-113">**标头：** 隔离。h</span><span class="sxs-lookup"><span data-stu-id="deb9f-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="deb9f-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="deb9f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="deb9f-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="deb9f-115">See also</span></span>

- [<span data-ttu-id="deb9f-116">合成接口</span><span class="sxs-lookup"><span data-stu-id="deb9f-116">Fusion Interfaces</span></span>](fusion-interfaces.md)
