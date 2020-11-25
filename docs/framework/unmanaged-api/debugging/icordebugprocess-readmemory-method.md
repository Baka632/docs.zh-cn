---
title: ICorDebugProcess::ReadMemory 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ReadMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ReadMemory
helpviewer_keywords:
- ReadMemory method [.NET Framework debugging]
- ICorDebugProcess::ReadMemory method [.NET Framework debugging]
ms.assetid: 28e4b2f6-9589-445c-be24-24a3306795e7
topic_type:
- apiref
ms.openlocfilehash: a0abc7168ff7bffdbb835c1c1bc93de9df6e381c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95694862"
---
# <a name="icordebugprocessreadmemory-method"></a><span data-ttu-id="d58ae-102">ICorDebugProcess::ReadMemory 方法</span><span class="sxs-lookup"><span data-stu-id="d58ae-102">ICorDebugProcess::ReadMemory Method</span></span>

<span data-ttu-id="d58ae-103">读取此进程的指定内存区域。</span><span class="sxs-lookup"><span data-stu-id="d58ae-103">Reads a specified area of memory for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d58ae-104">语法</span><span class="sxs-lookup"><span data-stu-id="d58ae-104">Syntax</span></span>  
  
```cpp  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d58ae-105">参数</span><span class="sxs-lookup"><span data-stu-id="d58ae-105">Parameters</span></span>  

 `address`  
 <span data-ttu-id="d58ae-106">中一个 `CORDB_ADDRESS` 值，该值指定要读取的内存的基址。</span><span class="sxs-lookup"><span data-stu-id="d58ae-106">[in] A `CORDB_ADDRESS` value that specifies the base address of the memory to be read.</span></span>  
  
 `size`  
 <span data-ttu-id="d58ae-107">中要从内存中读取的字节数。</span><span class="sxs-lookup"><span data-stu-id="d58ae-107">[in] The number of bytes to be read from memory.</span></span>  
  
 `buffer`  
 <span data-ttu-id="d58ae-108">弄接收内存内容的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="d58ae-108">[out] A buffer that receives the contents of the memory.</span></span>  
  
 `read`  
 <span data-ttu-id="d58ae-109">弄一个指针，指向到指定缓冲区中传输的字节数。</span><span class="sxs-lookup"><span data-stu-id="d58ae-109">[out] A pointer to the number of bytes transferred into the specified buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d58ae-110">注解</span><span class="sxs-lookup"><span data-stu-id="d58ae-110">Remarks</span></span>  

 <span data-ttu-id="d58ae-111">此 `ReadMemory` 方法主要用于互操作调试，用于检查调试对象的非托管部分所使用的内存区域。</span><span class="sxs-lookup"><span data-stu-id="d58ae-111">The `ReadMemory` method is primarily intended to be used by interop debugging to inspect memory regions that are being used by the unmanaged portion of the debuggee.</span></span> <span data-ttu-id="d58ae-112">此方法还可用于读取 Microsoft 中间语言 (MSIL) 代码和本机 JIT 编译代码。</span><span class="sxs-lookup"><span data-stu-id="d58ae-112">This method can also be used to read Microsoft intermediate language (MSIL) code and native JIT-compiled code.</span></span>  
  
 <span data-ttu-id="d58ae-113">将从参数中返回的数据删除所有托管断点 `buffer` 。</span><span class="sxs-lookup"><span data-stu-id="d58ae-113">Any managed breakpoints will be removed from the data that is returned in the `buffer` parameter.</span></span> <span data-ttu-id="d58ae-114">不会对 [ICorDebugProcess2：： SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md)设置的本机断点进行任何调整。</span><span class="sxs-lookup"><span data-stu-id="d58ae-114">No adjustments will be made for native breakpoints set by [ICorDebugProcess2::SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="d58ae-115">不会执行进程内存缓存。</span><span class="sxs-lookup"><span data-stu-id="d58ae-115">No caching of process memory is performed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d58ae-116">要求</span><span class="sxs-lookup"><span data-stu-id="d58ae-116">Requirements</span></span>  

 <span data-ttu-id="d58ae-117">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d58ae-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d58ae-118">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d58ae-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d58ae-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d58ae-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d58ae-120">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d58ae-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
