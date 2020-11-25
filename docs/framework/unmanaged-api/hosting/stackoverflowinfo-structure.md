---
title: StackOverflowInfo 结构
ms.date: 03/30/2017
api_name:
- StackOverflowInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowInfo
helpviewer_keywords:
- StackOverflowInfo structure [.NET Framework hosting]
ms.assetid: 519389f2-0217-436c-99d4-93a76ebce5b5
topic_type:
- apiref
ms.openlocfilehash: a8a57cfcaf36949d4d10c6ec267a5f55a2aee5eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729923"
---
# <a name="stackoverflowinfo-structure"></a><span data-ttu-id="bfd96-102">StackOverflowInfo 结构</span><span class="sxs-lookup"><span data-stu-id="bfd96-102">StackOverflowInfo Structure</span></span>

<span data-ttu-id="bfd96-103">存储发生的溢出的类型以及因溢出而引发的异常的信息。</span><span class="sxs-lookup"><span data-stu-id="bfd96-103">Stores the type of overflow that occurred and information on the exception that was thrown due to the overflow.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfd96-104">语法</span><span class="sxs-lookup"><span data-stu-id="bfd96-104">Syntax</span></span>  
  
```cpp  
typedef struct _StackOverflowInfo {  
    StackOverflowType   soType;  
    EXCEPTION_POINTERS  *pExceptionInfo;  
} StackOverflowInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="bfd96-105">成员</span><span class="sxs-lookup"><span data-stu-id="bfd96-105">Members</span></span>  
  
|<span data-ttu-id="bfd96-106">成员</span><span class="sxs-lookup"><span data-stu-id="bfd96-106">Member</span></span>|<span data-ttu-id="bfd96-107">说明</span><span class="sxs-lookup"><span data-stu-id="bfd96-107">Description</span></span>|  
|------------|-----------------|  
|`soType`|<span data-ttu-id="bfd96-108">指定溢出类型的 [StackOverflowType](stackoverflowtype-enumeration.md) 枚举的值。</span><span class="sxs-lookup"><span data-stu-id="bfd96-108">A value of the [StackOverflowType](stackoverflowtype-enumeration.md) enumeration that specifies the type of overflow.</span></span>|  
|`pExceptionInfo`|<span data-ttu-id="bfd96-109">一个指向 Win32 对象的指针 `EXCEPTION_POINTERS` ，该对象包含一个异常记录，其中包含与计算机无关的异常说明和一个上下文记录，其中包含发生异常时的处理器上下文的依赖于计算机的说明。</span><span class="sxs-lookup"><span data-stu-id="bfd96-109">A pointer to a Win32 `EXCEPTION_POINTERS` object, which contains an exception record with a machine-independent description of an exception and a context record with a machine-dependent description of the processor context at the time of the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bfd96-110">注解</span><span class="sxs-lookup"><span data-stu-id="bfd96-110">Remarks</span></span>  

 <span data-ttu-id="bfd96-111">`StackOverflowInfo`对象将传递到事件的[IActionOnCLREvent：： OnEvent](iactiononclrevent-onevent-method.md)方法 `Event_StackOverflow` 。</span><span class="sxs-lookup"><span data-stu-id="bfd96-111">A `StackOverflowInfo` object is passed to the [IActionOnCLREvent::OnEvent](iactiononclrevent-onevent-method.md) method for `Event_StackOverflow` events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfd96-112">要求</span><span class="sxs-lookup"><span data-stu-id="bfd96-112">Requirements</span></span>  

 <span data-ttu-id="bfd96-113">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bfd96-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfd96-114">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="bfd96-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="bfd96-115">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bfd96-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bfd96-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfd96-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfd96-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bfd96-117">See also</span></span>

- [<span data-ttu-id="bfd96-118">承载结构</span><span class="sxs-lookup"><span data-stu-id="bfd96-118">Hosting Structures</span></span>](hosting-structures.md)
