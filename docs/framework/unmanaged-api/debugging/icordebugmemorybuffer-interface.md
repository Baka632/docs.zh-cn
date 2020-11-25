---
title: ICorDebugMemoryBuffer 接口
ms.date: 03/30/2017
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
ms.openlocfilehash: 2765852309401d2aa30f91b506ba55156cd8a3e2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710724"
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="c933a-102">ICorDebugMemoryBuffer 接口</span><span class="sxs-lookup"><span data-stu-id="c933a-102">ICorDebugMemoryBuffer Interface</span></span>

<span data-ttu-id="c933a-103">表示内存中缓冲区。</span><span class="sxs-lookup"><span data-stu-id="c933a-103">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c933a-104">方法</span><span class="sxs-lookup"><span data-stu-id="c933a-104">Methods</span></span>  
  
|<span data-ttu-id="c933a-105">方法</span><span class="sxs-lookup"><span data-stu-id="c933a-105">Method</span></span>|<span data-ttu-id="c933a-106">说明</span><span class="sxs-lookup"><span data-stu-id="c933a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c933a-107">GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="c933a-107">GetSize Method</span></span>](icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="c933a-108">获取内存缓冲区的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="c933a-108">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="c933a-109">GetStartAddress 方法</span><span class="sxs-lookup"><span data-stu-id="c933a-109">GetStartAddress Method</span></span>](icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="c933a-110">获取内存缓冲区的起始地址。</span><span class="sxs-lookup"><span data-stu-id="c933a-110">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c933a-111">注解</span><span class="sxs-lookup"><span data-stu-id="c933a-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c933a-112">此接口仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="c933a-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="c933a-113">如果在 .NET Native 外为 ICorDebug 方案实现此接口，则公共语言运行时将忽略此接口。</span><span class="sxs-lookup"><span data-stu-id="c933a-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c933a-114">要求</span><span class="sxs-lookup"><span data-stu-id="c933a-114">Requirements</span></span>  

 <span data-ttu-id="c933a-115">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c933a-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c933a-116">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c933a-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c933a-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c933a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c933a-118">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c933a-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c933a-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c933a-119">See also</span></span>

- [<span data-ttu-id="c933a-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="c933a-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c933a-121">调试</span><span class="sxs-lookup"><span data-stu-id="c933a-121">Debugging</span></span>](index.md)
