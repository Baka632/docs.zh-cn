---
title: ICorDebugProcess6::DecodeEvent 方法
ms.date: 03/30/2017
ms.assetid: 1453bc0c-6e0d-4d5a-b176-22607f8a3e6c
ms.openlocfilehash: ed75b3c5657fed805f187285a576b81598be331c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690273"
---
# <a name="icordebugprocess6decodeevent-method"></a><span data-ttu-id="fe7fd-102">ICorDebugProcess6::DecodeEvent 方法</span><span class="sxs-lookup"><span data-stu-id="fe7fd-102">ICorDebugProcess6::DecodeEvent Method</span></span>

<span data-ttu-id="fe7fd-103">对封装于特殊构造的本机异常调试事件有效载荷中的托管调试事件进行解码。</span><span class="sxs-lookup"><span data-stu-id="fe7fd-103">Decodes managed debug events that have been encapsulated in the payload of specially crafted native exception debug events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe7fd-104">语法</span><span class="sxs-lookup"><span data-stu-id="fe7fd-104">Syntax</span></span>  
  
```cpp  
HRESULT DecodeEvent(  
        [in, length_is(countBytes), size_is(countBytes)]  const BYTE pRecord[],  
        [in] DWORD countBytes,  
        [in] CorDebugRecordFormat format,  
        [in] DWORD dwFlags,
        [in] DWORD dwThreadId,
        [out] ICorDebugDebugEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe7fd-105">参数</span><span class="sxs-lookup"><span data-stu-id="fe7fd-105">Parameters</span></span>  

 `pRecord`  
 <span data-ttu-id="fe7fd-106">[输入] 包含托管调试事件相关信息的本机异常调试事件中的字节数组指针。</span><span class="sxs-lookup"><span data-stu-id="fe7fd-106">[in] A pointer to a byte array from a native exception debug event that includes information about a managed debug event.</span></span>  
  
 `countBytes`  
 <span data-ttu-id="fe7fd-107">[输入] `pRecord` 字节数组中的元素数量。</span><span class="sxs-lookup"><span data-stu-id="fe7fd-107">[in] The number of elements in the `pRecord` byte array.</span></span>  
  
 `format`  
 <span data-ttu-id="fe7fd-108">中 [CorDebugRecordFormat](cordebugrecordformat-enumeration.md) 枚举成员，用于指定非托管调试事件的格式。</span><span class="sxs-lookup"><span data-stu-id="fe7fd-108">[in] A [CorDebugRecordFormat](cordebugrecordformat-enumeration.md) enumeration member that specifies the format of the unmanaged debug event.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="fe7fd-109">[输入] 位域依赖于目标体系结构并指定调试事件相关的其他信息。</span><span class="sxs-lookup"><span data-stu-id="fe7fd-109">[in] A bit field that depends on the target architecture and that specifies additional information about the debug event.</span></span> <span data-ttu-id="fe7fd-110">对于 Windows 系统，它可以是 [CorDebugDecodeEventFlagsWindows](cordebugdecodeeventflagswindows-enumeration.md) 枚举的成员。</span><span class="sxs-lookup"><span data-stu-id="fe7fd-110">For Windows systems, it can be a member of the [CorDebugDecodeEventFlagsWindows](cordebugdecodeeventflagswindows-enumeration.md) enumeration.</span></span>  
  
 `dwThreadId`  
 <span data-ttu-id="fe7fd-111">[输入] 引发异常的线程的操作系统识别符。</span><span class="sxs-lookup"><span data-stu-id="fe7fd-111">[in] The operating system identifier of the thread on which the exception was thrown.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="fe7fd-112">弄指向表示已解码的托管调试事件的 [ICorDebugDebugEvent](icordebugdebugevent-interface.md) 对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="fe7fd-112">[out] A pointer to the address of an [ICorDebugDebugEvent](icordebugdebugevent-interface.md) object that represents a decoded managed debug event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe7fd-113">注解</span><span class="sxs-lookup"><span data-stu-id="fe7fd-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fe7fd-114">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="fe7fd-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe7fd-115">要求</span><span class="sxs-lookup"><span data-stu-id="fe7fd-115">Requirements</span></span>  

 <span data-ttu-id="fe7fd-116">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fe7fd-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe7fd-117">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fe7fd-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fe7fd-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe7fd-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe7fd-119">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe7fd-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe7fd-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fe7fd-120">See also</span></span>

- [<span data-ttu-id="fe7fd-121">“ICor调试进程6”接口</span><span class="sxs-lookup"><span data-stu-id="fe7fd-121">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="fe7fd-122">调试接口</span><span class="sxs-lookup"><span data-stu-id="fe7fd-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
