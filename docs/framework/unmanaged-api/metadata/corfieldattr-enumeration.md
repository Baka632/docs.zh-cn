---
title: CorFieldAttr 枚举
ms.date: 03/30/2017
api_name:
- CorFieldAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFieldAttr
helpviewer_keywords:
- CorFieldAttr enumeration [.NET Framework metadata]
ms.assetid: 6ae2c4be-212c-4e74-9288-40a11dc26522
topic_type:
- apiref
ms.openlocfilehash: 4e40f684cc1578672cb8ff474972ce9cdc39efb2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718821"
---
# <a name="corfieldattr-enumeration"></a><span data-ttu-id="0b7cb-102">CorFieldAttr 枚举</span><span class="sxs-lookup"><span data-stu-id="0b7cb-102">CorFieldAttr Enumeration</span></span>

<span data-ttu-id="0b7cb-103">包含一些值，用于描述字段的相应元数据。</span><span class="sxs-lookup"><span data-stu-id="0b7cb-103">Contains values that describe metadata about a field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b7cb-104">语法</span><span class="sxs-lookup"><span data-stu-id="0b7cb-104">Syntax</span></span>  
  
```cpp  
typedef enum CorFieldAttr {  
  
    fdFieldAccessMask           =   0x0007,  
    fdPrivateScope              =   0x0000,  
    fdPrivate                   =   0x0001,  
    fdFamANDAssem               =   0x0002,  
    fdAssembly                  =   0x0003,  
    fdFamily                    =   0x0004,  
    fdFamORAssem                =   0x0005,  
    fdPublic                    =   0x0006,  
  
    fdStatic                    =   0x0010,  
    fdInitOnly                  =   0x0020,  
    fdLiteral                   =   0x0040,  
    fdNotSerialized             =   0x0080,  
  
    fdSpecialName               =   0x0200,  
  
    fdPinvokeImpl               =   0x2000,  
  
    fdReservedMask              =   0x9500,  
    fdRTSpecialName             =   0x0400,  
    fdHasFieldMarshal           =   0x1000,  
    fdHasDefault                =   0x8000,  
    fdHasFieldRVA               =   0x0100  
  
} CorFieldAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="0b7cb-105">成员</span><span class="sxs-lookup"><span data-stu-id="0b7cb-105">Members</span></span>  
  
|<span data-ttu-id="0b7cb-106">成员</span><span class="sxs-lookup"><span data-stu-id="0b7cb-106">Member</span></span>|<span data-ttu-id="0b7cb-107">说明</span><span class="sxs-lookup"><span data-stu-id="0b7cb-107">Description</span></span>|  
|------------|-----------------|  
|`fdFieldAccessMask`|<span data-ttu-id="0b7cb-108">指定辅助功能信息。</span><span class="sxs-lookup"><span data-stu-id="0b7cb-108">Specifies accessibility information.</span></span>|  
|`fdPrivateScope`|<span data-ttu-id="0b7cb-109">指定该字段不能被引用。</span><span class="sxs-lookup"><span data-stu-id="0b7cb-109">Specifies that the field cannot be referenced.</span></span>|  
|`fdPrivate`|<span data-ttu-id="0b7cb-110">指定该字段只能由其父类型访问。</span><span class="sxs-lookup"><span data-stu-id="0b7cb-110">Specifies that the field is accessible only by its parent type.</span></span>|  
|`fdFamANDAssem`|<span data-ttu-id="0b7cb-111">指定该字段可由其程序集中的派生类访问。</span><span class="sxs-lookup"><span data-stu-id="0b7cb-111">Specifies that the field is accessible by derived classes in its assembly.</span></span>|  
|`fdAssembly`|<span data-ttu-id="0b7cb-112">指定该字段可由其程序集中的所有类型进行访问。</span><span class="sxs-lookup"><span data-stu-id="0b7cb-112">Specifies that the field is accessible by all types in its assembly.</span></span>|  
|`fdFamily`|<span data-ttu-id="0b7cb-113">指定该字段只能由其类型和派生类访问。</span><span class="sxs-lookup"><span data-stu-id="0b7cb-113">Specifies that the field is accessible only by its type and derived classes.</span></span>|  
|`fdFamORAssem`|<span data-ttu-id="0b7cb-114">指定该字段可由派生类和其程序集中的所有类型进行访问。</span><span class="sxs-lookup"><span data-stu-id="0b7cb-114">Specifies that the field is accessible by derived classes and by all types in its assembly.</span></span>|  
|`fdPublic`|<span data-ttu-id="0b7cb-115">指定该字段可由具有此范围可见性的所有类型进行访问。</span><span class="sxs-lookup"><span data-stu-id="0b7cb-115">Specifies that the field is accessible by all types with visibility of this scope.</span></span>|  
|`fdStatic`|<span data-ttu-id="0b7cb-116">指定该字段是其类型的成员而不是实例成员。</span><span class="sxs-lookup"><span data-stu-id="0b7cb-116">Specifies that the field is a member of its type rather than an instance member.</span></span>|  
|`fdInitOnly`|<span data-ttu-id="0b7cb-117">指定字段在初始化之后不能更改。</span><span class="sxs-lookup"><span data-stu-id="0b7cb-117">Specifies that the field cannot be changed after it is initialized.</span></span>|  
|`fdLiteral`|<span data-ttu-id="0b7cb-118">指定字段值是编译时常量。</span><span class="sxs-lookup"><span data-stu-id="0b7cb-118">Specifies that the field value is a compile-time constant.</span></span>|  
|`fdNotSerialized`|<span data-ttu-id="0b7cb-119">指定当字段的类型为 "远程" 时不对其进行序列化。</span><span class="sxs-lookup"><span data-stu-id="0b7cb-119">Specifies that the field is not serialized when its type is remoted.</span></span>|  
|`fdSpecialName`|<span data-ttu-id="0b7cb-120">指定该字段为特殊字段，并且其名称描述了操作方法。</span><span class="sxs-lookup"><span data-stu-id="0b7cb-120">Specifies that the field is special, and that its name describes how.</span></span>|  
|`fdPinvokeImpl`|<span data-ttu-id="0b7cb-121">指定通过 PInvoke 转发字段实现。</span><span class="sxs-lookup"><span data-stu-id="0b7cb-121">Specifies that the field implementation is forwarded through PInvoke.</span></span>|  
|`fdReservedMask`|<span data-ttu-id="0b7cb-122">保留供公共语言运行时内部使用。</span><span class="sxs-lookup"><span data-stu-id="0b7cb-122">Reserved for internal use by the common language runtime.</span></span>|  
|`fdRTSpecialName`|<span data-ttu-id="0b7cb-123">指定公共语言运行时元数据内部 Api 应检查名称的编码。</span><span class="sxs-lookup"><span data-stu-id="0b7cb-123">Specifies that the common language runtime metadata internal APIs should check the encoding of the name.</span></span>|  
|`fdHasFieldMarshal`|<span data-ttu-id="0b7cb-124">指定该字段包含封送处理信息。</span><span class="sxs-lookup"><span data-stu-id="0b7cb-124">Specifies that the field contains marshaling information.</span></span>|  
|`fdHasDefault`|<span data-ttu-id="0b7cb-125">指定该字段具有默认值。</span><span class="sxs-lookup"><span data-stu-id="0b7cb-125">Specifies that the field has a default value.</span></span>|  
|`fdHasFieldRVA`|<span data-ttu-id="0b7cb-126">指定该字段具有相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="0b7cb-126">Specifies that the field has a relative virtual address.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0b7cb-127">要求</span><span class="sxs-lookup"><span data-stu-id="0b7cb-127">Requirements</span></span>  

 <span data-ttu-id="0b7cb-128">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0b7cb-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b7cb-129">**标头：** Corhdr。h</span><span class="sxs-lookup"><span data-stu-id="0b7cb-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="0b7cb-130">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b7cb-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b7cb-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0b7cb-131">See also</span></span>

- [<span data-ttu-id="0b7cb-132">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="0b7cb-132">Metadata Enumerations</span></span>](metadata-enumerations.md)
