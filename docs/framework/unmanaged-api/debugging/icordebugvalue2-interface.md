---
title: ICorDebugValue2 接口
ms.date: 03/30/2017
api_name:
- ICorDebugValue2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2
helpviewer_keywords:
- ICorDebugValue2 interface [.NET Framework debugging]
ms.assetid: 3ff2ad2a-da5a-461b-8627-1a8eba49df9c
topic_type:
- apiref
ms.openlocfilehash: 7aca5fcb5a55331756b4f98c08eb46fc4db1e289
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720329"
---
# <a name="icordebugvalue2-interface"></a><span data-ttu-id="01184-102">ICorDebugValue2 接口</span><span class="sxs-lookup"><span data-stu-id="01184-102">ICorDebugValue2 Interface</span></span>

<span data-ttu-id="01184-103">扩展 "ICorDebugValue" 接口，以提供对 "ICorDebugType" 对象的支持。</span><span class="sxs-lookup"><span data-stu-id="01184-103">Extends the "ICorDebugValue" interface to provide support for "ICorDebugType" objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="01184-104">方法</span><span class="sxs-lookup"><span data-stu-id="01184-104">Methods</span></span>  
  
|<span data-ttu-id="01184-105">方法</span><span class="sxs-lookup"><span data-stu-id="01184-105">Method</span></span>|<span data-ttu-id="01184-106">说明</span><span class="sxs-lookup"><span data-stu-id="01184-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="01184-107">GetExactType 方法</span><span class="sxs-lookup"><span data-stu-id="01184-107">GetExactType Method</span></span>](icordebugvalue2-getexacttype-method.md)|<span data-ttu-id="01184-108">获取一个接口指针，该指针指向 `ICorDebugType` 表示 <xref:System.Type> 此值的的对象。</span><span class="sxs-lookup"><span data-stu-id="01184-108">Gets an interface pointer to an `ICorDebugType` object that represents the <xref:System.Type> of this value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01184-109">注解</span><span class="sxs-lookup"><span data-stu-id="01184-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="01184-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="01184-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01184-111">要求</span><span class="sxs-lookup"><span data-stu-id="01184-111">Requirements</span></span>  

 <span data-ttu-id="01184-112">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="01184-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01184-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="01184-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="01184-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="01184-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="01184-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01184-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01184-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01184-116">See also</span></span>

- [<span data-ttu-id="01184-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="01184-117">Debugging Interfaces</span></span>](debugging-interfaces.md)

- [<span data-ttu-id="01184-118">ICorDebugValue3 接口</span><span class="sxs-lookup"><span data-stu-id="01184-118">ICorDebugValue3 Interface</span></span>](icordebugvalue3-interface.md)
