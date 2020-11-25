---
title: ICLRDataTarget::SetThreadContext 方法
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetThreadContext
helpviewer_keywords:
- SetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::SetThreadContext method [.NET Framework debugging]
ms.assetid: 103c8502-81fe-40d7-9c1e-9008d8fb19e1
topic_type:
- apiref
ms.openlocfilehash: c135c051637858682c22db58d562e1d50eea562b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723696"
---
# <a name="iclrdatatargetsetthreadcontext-method"></a><span data-ttu-id="2b44d-102">ICLRDataTarget::SetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="2b44d-102">ICLRDataTarget::SetThreadContext Method</span></span>

<span data-ttu-id="2b44d-103">设置目标进程中指定线程的当前上下文。</span><span class="sxs-lookup"><span data-stu-id="2b44d-103">Sets the current context of the specified thread in the target process.</span></span> <span data-ttu-id="2b44d-104">此方法由公共语言运行时 (CLR) 数据访问服务调用。</span><span class="sxs-lookup"><span data-stu-id="2b44d-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b44d-105">语法</span><span class="sxs-lookup"><span data-stu-id="2b44d-105">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextSize,  
    [in, size_is(contextSize)]
         BYTE               *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b44d-106">参数</span><span class="sxs-lookup"><span data-stu-id="2b44d-106">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="2b44d-107">中目标进程中的线程的操作系统标识符。</span><span class="sxs-lookup"><span data-stu-id="2b44d-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="2b44d-108">中上下文的大小。</span><span class="sxs-lookup"><span data-stu-id="2b44d-108">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="2b44d-109">中指向包含上下文的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="2b44d-109">[in] Pointer to a buffer containing the context.</span></span>  
  
 <span data-ttu-id="2b44d-110">缓冲区中的数据 `context` 将采用 Win32 结构的格式 `CONTEXT` 。</span><span class="sxs-lookup"><span data-stu-id="2b44d-110">The data in the `context` buffer will be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="2b44d-111">上下文指定处理器特定的寄存器数据，因此 Win32 结构的定义 `CONTEXT` 取决于处理器的体系结构。</span><span class="sxs-lookup"><span data-stu-id="2b44d-111">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="2b44d-112">有关 Win32 结构的定义，请参阅 WinNT. .h 头文件 `CONTEXT` 。</span><span class="sxs-lookup"><span data-stu-id="2b44d-112">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b44d-113">注解</span><span class="sxs-lookup"><span data-stu-id="2b44d-113">Remarks</span></span>  

 <span data-ttu-id="2b44d-114">此方法由调试应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="2b44d-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b44d-115">要求</span><span class="sxs-lookup"><span data-stu-id="2b44d-115">Requirements</span></span>  

 <span data-ttu-id="2b44d-116">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2b44d-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b44d-117">**标头：** ClrData，ClrData</span><span class="sxs-lookup"><span data-stu-id="2b44d-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="2b44d-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b44d-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b44d-119">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b44d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b44d-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2b44d-120">See also</span></span>

- [<span data-ttu-id="2b44d-121">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="2b44d-121">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
