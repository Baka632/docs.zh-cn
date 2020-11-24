---
title: _EFN_GetManagedObjectName 函数
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedObjectName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedObjectName
helpviewer_keywords:
- _EFN_GetManagedObjectName function [.NET Framework debugging]
ms.assetid: 6e7c6bee-7ced-495f-bf6c-2a5f0c716f7e
topic_type:
- apiref
ms.openlocfilehash: 0fb694cf85256c0f3ac5ae179e53ff504ab707e9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676200"
---
# <a name="_efn_getmanagedobjectname-function"></a><span data-ttu-id="3ca8a-102">\_EFN \_ GetManagedObjectName 函数</span><span class="sxs-lookup"><span data-stu-id="3ca8a-102">\_EFN\_GetManagedObjectName Function</span></span>

<span data-ttu-id="3ca8a-103">使用提供的托管对象指针获取类型的名称。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-103">Gets the name of a type using the provided managed object pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ca8a-104">语法</span><span class="sxs-lookup"><span data-stu-id="3ca8a-104">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedObjectName(  
    [in]  PDEBUG_CLIENT  Client,  
    [in]  ULONG64        objAddr,  
    [out] __out_ecount(cbName) PSTR szName,  
    [out] ULONG          cbName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ca8a-105">参数</span><span class="sxs-lookup"><span data-stu-id="3ca8a-105">Parameters</span></span>  

 `Client`  
 <span data-ttu-id="3ca8a-106">中指向调试客户端的指针。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="3ca8a-107">中托管对象指针。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="3ca8a-108">szName</span><span class="sxs-lookup"><span data-stu-id="3ca8a-108">szName</span></span>  
 <span data-ttu-id="3ca8a-109">弄类型的名称。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-109">[out] The name of the type.</span></span>  
  
 `cbName`  
 <span data-ttu-id="3ca8a-110">弄字符串缓冲区中的可用字符数。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ca8a-111">注解</span><span class="sxs-lookup"><span data-stu-id="3ca8a-111">Remarks</span></span>  

 <span data-ttu-id="3ca8a-112">如果当前上下文中的线程上没有托管代码，则该函数将返回具有0xa0 的工具值的 HRESULT SOS_E_NOMANAGEDCODE 和错误代码0x1000。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ca8a-113">要求</span><span class="sxs-lookup"><span data-stu-id="3ca8a-113">Requirements</span></span>  

 <span data-ttu-id="3ca8a-114">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3ca8a-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ca8a-115">**标头：** SOS_Stacktrace。h</span><span class="sxs-lookup"><span data-stu-id="3ca8a-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="3ca8a-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ca8a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ca8a-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3ca8a-117">See also</span></span>

- [<span data-ttu-id="3ca8a-118">调试全局静态函数</span><span class="sxs-lookup"><span data-stu-id="3ca8a-118">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
