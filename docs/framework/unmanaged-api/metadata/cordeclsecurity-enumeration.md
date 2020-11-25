---
title: CorDeclSecurity 枚举
ms.date: 03/30/2017
api_name:
- CorDeclSecurity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorDeclSecurity
helpviewer_keywords:
- CorDeclSecurity enumeration [.NET Framework metadata]
ms.assetid: 864f1267-d267-4696-8df7-1f83f8444d6f
topic_type:
- apiref
ms.openlocfilehash: dd599ce8c63fa94e1a18b4e2d18fa334238728bd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718873"
---
# <a name="cordeclsecurity-enumeration"></a><span data-ttu-id="00e79-102">CorDeclSecurity 枚举</span><span class="sxs-lookup"><span data-stu-id="00e79-102">CorDeclSecurity Enumeration</span></span>

<span data-ttu-id="00e79-103">指定可以使用声明性安全执行的安全操作。</span><span class="sxs-lookup"><span data-stu-id="00e79-103">Specifies the security actions that can be performed using declarative security.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00e79-104">语法</span><span class="sxs-lookup"><span data-stu-id="00e79-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDeclSecurity {  
  
    dclActionMask               =   0x001f,  
    dclActionNil                =   0x0000,  
    dclRequest                  =   0x0001,  
    dclDemand                   =   0x0002,  
    dclAssert                   =   0x0003,  
    dclDeny                     =   0x0004,  
    dclPermitOnly               =   0x0005,  
    dclLinktimeCheck            =   0x0006,  
    dclInheritanceCheck         =   0x0007,  
    dclRequestMinimum           =   0x0008,  
    dclRequestOptional          =   0x0009,  
    dclRequestRefuse            =   0x000a,  
    dclPrejitGrant              =   0x000b,  
    dclPrejitDenied             =   0x000c,  
    dclNonCasDemand             =   0x000d,  
    dclNonCasLinkDemand         =   0x000e,  
    dclNonCasInheritance        =   0x000f,  
    dclLinkDemandChoice         =   0x0010,  
    dclInheritanceDemandChoice  =   0x0011,  
    dclDemandChoice             =   0x0012,  
    dclMaximumValue             =   0x0012  
  
} CorDeclSecurity;  
```  
  
## <a name="members"></a><span data-ttu-id="00e79-105">成员</span><span class="sxs-lookup"><span data-stu-id="00e79-105">Members</span></span>  
  
|<span data-ttu-id="00e79-106">成员</span><span class="sxs-lookup"><span data-stu-id="00e79-106">Member</span></span>|<span data-ttu-id="00e79-107">说明</span><span class="sxs-lookup"><span data-stu-id="00e79-107">Description</span></span>|  
|------------|-----------------|  
|`dclActionMask`|<span data-ttu-id="00e79-108">保留。</span><span class="sxs-lookup"><span data-stu-id="00e79-108">Reserved.</span></span>|  
|`dclActionNil`|<span data-ttu-id="00e79-109">保留。</span><span class="sxs-lookup"><span data-stu-id="00e79-109">Reserved.</span></span>|  
|`dclRequest`|<span data-ttu-id="00e79-110">保留。</span><span class="sxs-lookup"><span data-stu-id="00e79-110">Reserved.</span></span>|  
|`dclDemand`|<span data-ttu-id="00e79-111">要求调用堆栈中的所有高级调用方已被授予当前权限对象所指定的权限。</span><span class="sxs-lookup"><span data-stu-id="00e79-111">All callers higher in the call stack are required to have been granted the permission specified by the current permission object.</span></span>|  
|`dclAssert`|<span data-ttu-id="00e79-112">调用代码可以访问当前权限对象所标识的资源，即使堆栈中的高级调用方未被授予访问该资源的权限</span><span class="sxs-lookup"><span data-stu-id="00e79-112">The calling code can access the resource identified by the current permission object, even if callers higher in the stack have not been granted permission to access the resource</span></span>|  
|`dclDeny`|<span data-ttu-id="00e79-113">即使调用方已被授予访问当前权限对象所指定的资源的权限，也会拒绝这些调用方访问该资源。</span><span class="sxs-lookup"><span data-stu-id="00e79-113">The ability to access the resource specified by the current permission object is denied to callers, even if they have been granted permission to access it.</span></span>|  
|`dclPermitOnly`|<span data-ttu-id="00e79-114">仅可以访问此权限对象所指定的资源，即使代码已被授予访问其他资源的权限。</span><span class="sxs-lookup"><span data-stu-id="00e79-114">Only the resources specified by this permission object can be accessed, even if the code has been granted permission to access other resources.</span></span>|  
|`dclLinktimeCheck`|<span data-ttu-id="00e79-115">需要在给定的时间段内向直接调用方授予指定的权限。</span><span class="sxs-lookup"><span data-stu-id="00e79-115">The immediate caller is required to have been granted the specified permission for a given period of time.</span></span>|  
|`dclInheritanceCheck`|<span data-ttu-id="00e79-116">需要继承另一个类或重写方法的派生类已被授予指定的权限。</span><span class="sxs-lookup"><span data-stu-id="00e79-116">The derived class inheriting another class or overriding a method is required to have been granted the specified permission.</span></span>|  
|`dclRequestMinimum`|<span data-ttu-id="00e79-117">调用方可以请求运行代码所需的最小权限。</span><span class="sxs-lookup"><span data-stu-id="00e79-117">The caller can request for the minimum permissions required for code to run.</span></span> <span data-ttu-id="00e79-118">此操作仅可以在程序集的作用域内使用。</span><span class="sxs-lookup"><span data-stu-id="00e79-118">This action can only be used within the scope of the assembly.</span></span>|  
|`dclRequestOptional`|<span data-ttu-id="00e79-119">调用方可以请求其他可选权限，这 (不需要运行) 。</span><span class="sxs-lookup"><span data-stu-id="00e79-119">The caller can request for additional permissions that are optional (not required to run).</span></span> <span data-ttu-id="00e79-120">此请求隐式拒绝所有未明确请求的其他权限。</span><span class="sxs-lookup"><span data-stu-id="00e79-120">This request implicitly refuses all other permissions not specifically requested.</span></span> <span data-ttu-id="00e79-121">此操作仅可以在程序集的作用域内使用。</span><span class="sxs-lookup"><span data-stu-id="00e79-121">This action can only be used within the scope of the assembly.</span></span>|  
|`dclRequestRefuse`|<span data-ttu-id="00e79-122">调用方对可能被误用的权限的请求将不会被授予。</span><span class="sxs-lookup"><span data-stu-id="00e79-122">The caller's request for permissions that might be misused will not be granted.</span></span> <span data-ttu-id="00e79-123">此操作仅可以在程序集的作用域内使用。</span><span class="sxs-lookup"><span data-stu-id="00e79-123">This action can only be used within the scope of the assembly.</span></span>|  
|`dclPrejitGrant`|<span data-ttu-id="00e79-124">保留。</span><span class="sxs-lookup"><span data-stu-id="00e79-124">Reserved.</span></span>|  
|`dclPrejitDenied`|<span data-ttu-id="00e79-125">保留。</span><span class="sxs-lookup"><span data-stu-id="00e79-125">Reserved.</span></span>|  
|`dclNonCasDemand`|<span data-ttu-id="00e79-126">保留。</span><span class="sxs-lookup"><span data-stu-id="00e79-126">Reserved.</span></span>|  
|`dclNonCasLinkDemand`|<span data-ttu-id="00e79-127">要求直接调用方已被授予指定的权限。</span><span class="sxs-lookup"><span data-stu-id="00e79-127">The immediate caller is required to have been granted the specified permission.</span></span>|  
|`dclNonCasInheritance`|<span data-ttu-id="00e79-128">保留。</span><span class="sxs-lookup"><span data-stu-id="00e79-128">Reserved.</span></span>|  
|`dclLinkDemandChoice`|<span data-ttu-id="00e79-129">保留。</span><span class="sxs-lookup"><span data-stu-id="00e79-129">Reserved.</span></span>|  
|`dclInheritanceDemandChoice`|<span data-ttu-id="00e79-130">保留。</span><span class="sxs-lookup"><span data-stu-id="00e79-130">Reserved.</span></span>|  
|`dclDemandChoice`|<span data-ttu-id="00e79-131">保留。</span><span class="sxs-lookup"><span data-stu-id="00e79-131">Reserved.</span></span>|  
|`dclMaximumValue`|<span data-ttu-id="00e79-132">保留。</span><span class="sxs-lookup"><span data-stu-id="00e79-132">Reserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="00e79-133">要求</span><span class="sxs-lookup"><span data-stu-id="00e79-133">Requirements</span></span>  

 <span data-ttu-id="00e79-134">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="00e79-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00e79-135">**标头：** Corhdr。h</span><span class="sxs-lookup"><span data-stu-id="00e79-135">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="00e79-136">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00e79-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00e79-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00e79-137">See also</span></span>

- [<span data-ttu-id="00e79-138">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="00e79-138">Metadata Enumerations</span></span>](metadata-enumerations.md)
