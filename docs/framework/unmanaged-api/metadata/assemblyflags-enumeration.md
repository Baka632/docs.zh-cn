---
title: AssemblyFlags 枚举
ms.date: 03/30/2017
api_name:
- AssemblyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyFlags
helpviewer_keywords:
- AssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: 40f9bd9e-16ec-447e-81b0-168c875e9866
topic_type:
- apiref
ms.openlocfilehash: 561b4d68a574a2859286fb5f2e2d950518a9d29d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732770"
---
# <a name="assemblyflags-enumeration"></a><span data-ttu-id="b28b2-102">AssemblyFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="b28b2-102">AssemblyFlags Enumeration</span></span>

<span data-ttu-id="b28b2-103">包含用于描述程序集的运行时功能的值。</span><span class="sxs-lookup"><span data-stu-id="b28b2-103">Contains values that describe run-time features of an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b28b2-104">语法</span><span class="sxs-lookup"><span data-stu-id="b28b2-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    afImplicitExportedTypes = 0x0001,  
    afImplicitResources = 0x0002,  
    afNonSideBySideAppDomain = 0x0010,  
    afNonSideBySideProcess = 0x0020,  
    afNonSideBySideMachine = 0x0030  
} AssemblyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="b28b2-105">成员</span><span class="sxs-lookup"><span data-stu-id="b28b2-105">Members</span></span>  
  
|<span data-ttu-id="b28b2-106">成员</span><span class="sxs-lookup"><span data-stu-id="b28b2-106">Member</span></span>|<span data-ttu-id="b28b2-107">说明</span><span class="sxs-lookup"><span data-stu-id="b28b2-107">Description</span></span>|  
|------------|-----------------|  
|`afImplicitExportedTypes`|<span data-ttu-id="b28b2-108">指定导出的类型定义在构成程序集的文件中是隐式的。</span><span class="sxs-lookup"><span data-stu-id="b28b2-108">Specifies that exported type definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="b28b2-109">在 .NET Framework 版本1.0 和1.1 中，始终假定此值已设置。</span><span class="sxs-lookup"><span data-stu-id="b28b2-109">In the .NET Framework versions 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afImplicitResources`|<span data-ttu-id="b28b2-110">指定资源定义在构成程序集的文件中是隐式的。</span><span class="sxs-lookup"><span data-stu-id="b28b2-110">Specifies that resource definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="b28b2-111">在 .NET Framework 1.0 和1.1 中，始终假定此值已设置。</span><span class="sxs-lookup"><span data-stu-id="b28b2-111">In the .NET Framework 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afNonSideBySideAppDomain`|<span data-ttu-id="b28b2-112">指定程序集不能与其他版本在同一应用程序域中一起执行。</span><span class="sxs-lookup"><span data-stu-id="b28b2-112">Specifies that the assembly cannot execute with other versions if they are running in the same application domain.</span></span>|  
|`afNonSideBySideProcess`|<span data-ttu-id="b28b2-113">指定程序集不能与其他版本在同一进程中一起执行。</span><span class="sxs-lookup"><span data-stu-id="b28b2-113">Specifies that the assembly cannot execute with other versions if they are running in the same process.</span></span>|  
|`afNonSideBySideMachine`|<span data-ttu-id="b28b2-114">如果程序集在同一台计算机上运行，则指定该程序集无法与其他版本一起执行。</span><span class="sxs-lookup"><span data-stu-id="b28b2-114">Specifies that the assembly cannot execute with other versions if they are running on the same computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b28b2-115">注解</span><span class="sxs-lookup"><span data-stu-id="b28b2-115">Remarks</span></span>  

 <span data-ttu-id="b28b2-116">0x0010 和0x0070 （含）之间的值用于描述所引用程序集的并行兼容性功能。</span><span class="sxs-lookup"><span data-stu-id="b28b2-116">The values between 0x0010 and 0x0070, inclusive, are used to describe side-by-side compatibility features of the referenced assembly.</span></span> <span data-ttu-id="b28b2-117">如果未设置这些值，则假定程序集是并行兼容的。</span><span class="sxs-lookup"><span data-stu-id="b28b2-117">If none of these values are set, the assembly is assumed to be side-by-side compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b28b2-118">要求</span><span class="sxs-lookup"><span data-stu-id="b28b2-118">Requirements</span></span>  

 <span data-ttu-id="b28b2-119">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b28b2-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b28b2-120">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b28b2-120">**Header:** MsCorEE.h</span></span>  
  
 <span data-ttu-id="b28b2-121">**库：** 作为中的资源包含 MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b28b2-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b28b2-122">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b28b2-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b28b2-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b28b2-123">See also</span></span>

- [<span data-ttu-id="b28b2-124">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="b28b2-124">Metadata Enumerations</span></span>](metadata-enumerations.md)
- [<span data-ttu-id="b28b2-125">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="b28b2-125">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
