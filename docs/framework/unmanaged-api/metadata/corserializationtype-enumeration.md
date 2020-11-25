---
title: CorSerializationType 枚举
ms.date: 03/30/2017
api_name:
- CorSerializationType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSerializationType
helpviewer_keywords:
- CorSerializationType enumeration [.NET Framework metadata]
ms.assetid: 6b1fcd11-c7fb-4be2-8910-abc862d4caf4
topic_type:
- apiref
ms.openlocfilehash: e9c9674bfe0e5a8006a4881e103b633ee8f2af1d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706042"
---
# <a name="corserializationtype-enumeration"></a><span data-ttu-id="f7878-102">CorSerializationType 枚举</span><span class="sxs-lookup"><span data-stu-id="f7878-102">CorSerializationType Enumeration</span></span>

<span data-ttu-id="f7878-103">指定公共语言运行时序列化对象的方式。</span><span class="sxs-lookup"><span data-stu-id="f7878-103">Specifies how an object is serialized by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7878-104">语法</span><span class="sxs-lookup"><span data-stu-id="f7878-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSerializationType {  
  
    SERIALIZATION_TYPE_UNDEFINED     = 0,  
    SERIALIZATION_TYPE_BOOLEAN       = ELEMENT_TYPE_BOOLEAN,  
    SERIALIZATION_TYPE_CHAR          = ELEMENT_TYPE_CHAR,  
    SERIALIZATION_TYPE_I1            = ELEMENT_TYPE_I1,  
    SERIALIZATION_TYPE_U1            = ELEMENT_TYPE_U1,  
    SERIALIZATION_TYPE_I2            = ELEMENT_TYPE_I2,  
    SERIALIZATION_TYPE_U2            = ELEMENT_TYPE_U2,  
    SERIALIZATION_TYPE_I4            = ELEMENT_TYPE_I4,  
    SERIALIZATION_TYPE_U4            = ELEMENT_TYPE_U4,  
    SERIALIZATION_TYPE_I8            = ELEMENT_TYPE_I8,  
    SERIALIZATION_TYPE_U8            = ELEMENT_TYPE_U8,  
    SERIALIZATION_TYPE_R4            = ELEMENT_TYPE_R4,  
    SERIALIZATION_TYPE_R8            = ELEMENT_TYPE_R8,  
    SERIALIZATION_TYPE_STRING        = ELEMENT_TYPE_STRING,  
    SERIALIZATION_TYPE_SZARRAY       = ELEMENT_TYPE_SZARRAY,  
    SERIALIZATION_TYPE_TYPE          = 0x50,  
    SERIALIZATION_TYPE_TAGGED_OBJECT = 0x51,  
    SERIALIZATION_TYPE_FIELD         = 0x53,  
    SERIALIZATION_TYPE_PROPERTY      = 0x54,  
    SERIALIZATION_TYPE_ENUM          = 0x55  
  
} CorSerializationType;  
```  
  
## <a name="members"></a><span data-ttu-id="f7878-105">成员</span><span class="sxs-lookup"><span data-stu-id="f7878-105">Members</span></span>  
  
|<span data-ttu-id="f7878-106">成员</span><span class="sxs-lookup"><span data-stu-id="f7878-106">Member</span></span>|<span data-ttu-id="f7878-107">说明</span><span class="sxs-lookup"><span data-stu-id="f7878-107">Description</span></span>|  
|------------|-----------------|  
|`SERIALIZATION_TYPE_UNDEFINED`|<span data-ttu-id="f7878-108">对象的序列化未定义。</span><span class="sxs-lookup"><span data-stu-id="f7878-108">Serialization of the object is undefined.</span></span>|  
|`SERIALIZATION_TYPE_BOOLEAN`|<span data-ttu-id="f7878-109">将对象序列化为布尔类型</span><span class="sxs-lookup"><span data-stu-id="f7878-109">Object is serialized as a Boolean type</span></span>|  
|`SERIALIZATION_TYPE_CHAR`|<span data-ttu-id="f7878-110">将对象序列化为字符类型。</span><span class="sxs-lookup"><span data-stu-id="f7878-110">Object is serialized as a character type.</span></span>|  
|`SERIALIZATION_TYPE_I1`|<span data-ttu-id="f7878-111">将对象序列化为有符号的1字节整数。</span><span class="sxs-lookup"><span data-stu-id="f7878-111">Object is serialized as a signed 1-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U1`|<span data-ttu-id="f7878-112">将对象序列化为无符号的1字节整数。</span><span class="sxs-lookup"><span data-stu-id="f7878-112">Object is serialized as an unsigned 1-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I2`|<span data-ttu-id="f7878-113">将对象序列化为有符号的2字节整数。</span><span class="sxs-lookup"><span data-stu-id="f7878-113">Object is serialized as a signed 2-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U2`|<span data-ttu-id="f7878-114">将对象序列化为无符号的2字节整数。</span><span class="sxs-lookup"><span data-stu-id="f7878-114">Object is serialized as an unsigned 2-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I4`|<span data-ttu-id="f7878-115">将对象序列化为有符号4字节整数。</span><span class="sxs-lookup"><span data-stu-id="f7878-115">Object is serialized as a signed 4-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U4`|<span data-ttu-id="f7878-116">将对象序列化为无符号4字节整数。</span><span class="sxs-lookup"><span data-stu-id="f7878-116">Object is serialized as an unsigned 4-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I8`|<span data-ttu-id="f7878-117">将对象序列化为有符号的8字节整数。</span><span class="sxs-lookup"><span data-stu-id="f7878-117">Object is serialized as a signed 8-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U8`|<span data-ttu-id="f7878-118">将对象序列化为无符号的8字节整数。</span><span class="sxs-lookup"><span data-stu-id="f7878-118">Object is serialized as an unsigned 8-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_R4`|<span data-ttu-id="f7878-119">将对象序列化为4字节浮点数。</span><span class="sxs-lookup"><span data-stu-id="f7878-119">Object is serialized as a 4-byte floating point.</span></span>|  
|`SERIALIZATION_TYPE_R8`|<span data-ttu-id="f7878-120">将对象序列化为8字节浮点。</span><span class="sxs-lookup"><span data-stu-id="f7878-120">Object is serialized as an 8-byte floating point.</span></span>|  
|`SERIALIZATION_TYPE_STRING`|<span data-ttu-id="f7878-121">将对象序列化为 System.string 类型。</span><span class="sxs-lookup"><span data-stu-id="f7878-121">Object is serialized as a System.String type.</span></span>|  
|`SERIALIZATION_TYPE_SZARRAY`|<span data-ttu-id="f7878-122">将对象序列化为一个一维的、零下限的数组。</span><span class="sxs-lookup"><span data-stu-id="f7878-122">Object is serialized as a single-dimensional, zero lower-bound array.</span></span>|  
|`SERIALIZATION_TYPE_TYPE`|<span data-ttu-id="f7878-123">将对象序列化为泛型类型。</span><span class="sxs-lookup"><span data-stu-id="f7878-123">Object is serialized as a generic type.</span></span>|  
|`SERIALIZATION_TYPE_TAGGED_OBJECT`|<span data-ttu-id="f7878-124">将对象序列化为标记的对象。</span><span class="sxs-lookup"><span data-stu-id="f7878-124">Object is serialized as a tagged object.</span></span>|  
|`SERIALIZATION_TYPE_FIELD`|<span data-ttu-id="f7878-125">将对象序列化为一个字段。</span><span class="sxs-lookup"><span data-stu-id="f7878-125">Object is serialized as a field.</span></span>|  
|`SERIALIZATION_TYPE_PROPERTY`|<span data-ttu-id="f7878-126">将对象序列化为属性。</span><span class="sxs-lookup"><span data-stu-id="f7878-126">Object is serialized as a property.</span></span>|  
|`SERIALIZATION_TYPE_ENUM`|<span data-ttu-id="f7878-127">将对象序列化为枚举。</span><span class="sxs-lookup"><span data-stu-id="f7878-127">Object is serialized as an enumeration.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f7878-128">要求</span><span class="sxs-lookup"><span data-stu-id="f7878-128">Requirements</span></span>  

 <span data-ttu-id="f7878-129">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f7878-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7878-130">**标头：** Corhdr。h</span><span class="sxs-lookup"><span data-stu-id="f7878-130">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="f7878-131">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7878-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7878-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f7878-132">See also</span></span>

- [<span data-ttu-id="f7878-133">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="f7878-133">Metadata Enumerations</span></span>](metadata-enumerations.md)
