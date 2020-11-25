---
title: ICLRDataTarget 接口
ms.date: 03/30/2017
api_name:
- ICLRDataTarget
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget
helpviewer_keywords:
- ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: e2f05155-9bef-4e11-b703-7f05890665ca
topic_type:
- apiref
ms.openlocfilehash: 0d3e6a95d8fd71a67b97923dac53c1f615dfe666
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703416"
---
# <a name="iclrdatatarget-interface"></a><span data-ttu-id="5d426-102">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="5d426-102">ICLRDataTarget Interface</span></span>

<span data-ttu-id="5d426-103">提供与公共语言运行时的目标项 (CLR) 交互的方法。</span><span class="sxs-lookup"><span data-stu-id="5d426-103">Provides methods for interaction with a target item of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5d426-104">方法</span><span class="sxs-lookup"><span data-stu-id="5d426-104">Methods</span></span>  
  
|<span data-ttu-id="5d426-105">方法</span><span class="sxs-lookup"><span data-stu-id="5d426-105">Method</span></span>|<span data-ttu-id="5d426-106">说明</span><span class="sxs-lookup"><span data-stu-id="5d426-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5d426-107">GetCurrentThreadID 方法</span><span class="sxs-lookup"><span data-stu-id="5d426-107">GetCurrentThreadID Method</span></span>](iclrdatatarget-getcurrentthreadid-method.md)|<span data-ttu-id="5d426-108">获取当前线程的操作系统标识符。</span><span class="sxs-lookup"><span data-stu-id="5d426-108">Gets the operating system identifier for the current thread.</span></span>|  
|[<span data-ttu-id="5d426-109">GetImageBase 方法</span><span class="sxs-lookup"><span data-stu-id="5d426-109">GetImageBase Method</span></span>](iclrdatatarget-getimagebase-method.md)|<span data-ttu-id="5d426-110">获取指定的图像的基本内存地址。</span><span class="sxs-lookup"><span data-stu-id="5d426-110">Gets the base memory address for the specified image.</span></span>|  
|[<span data-ttu-id="5d426-111">GetMachineType 方法</span><span class="sxs-lookup"><span data-stu-id="5d426-111">GetMachineType Method</span></span>](iclrdatatarget-getmachinetype-method.md)|<span data-ttu-id="5d426-112">获取目标进程正在使用的指令集类型的标识符。</span><span class="sxs-lookup"><span data-stu-id="5d426-112">Gets an identifier for the kind of instruction set that the target process is using.</span></span>|  
|[<span data-ttu-id="5d426-113">GetPointerSize 方法</span><span class="sxs-lookup"><span data-stu-id="5d426-113">GetPointerSize Method</span></span>](iclrdatatarget-getpointersize-method.md)|<span data-ttu-id="5d426-114">获取指向当前目标的指针的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="5d426-114">Gets the size, in bytes, of a pointer to the current target.</span></span>|  
|[<span data-ttu-id="5d426-115">GetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="5d426-115">GetThreadContext Method</span></span>](iclrdatatarget-getthreadcontext-method.md)|<span data-ttu-id="5d426-116">获取一个指针，该指针指向具有指定标识符的线程的上下文。</span><span class="sxs-lookup"><span data-stu-id="5d426-116">Gets a pointer to the context of the thread with the specified identifier.</span></span>|  
|[<span data-ttu-id="5d426-117">GetTLSValue 方法</span><span class="sxs-lookup"><span data-stu-id="5d426-117">GetTLSValue Method</span></span>](iclrdatatarget-gettlsvalue-method.md)|<span data-ttu-id="5d426-118">在线程本地存储区中获取指定线程 (TLS) 中的值。</span><span class="sxs-lookup"><span data-stu-id="5d426-118">Gets a value in thread local storage (TLS) at the specified index for the specified thread.</span></span>|  
|[<span data-ttu-id="5d426-119">ReadVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="5d426-119">ReadVirtual Method</span></span>](iclrdatatarget-readvirtual-method.md)|<span data-ttu-id="5d426-120">将数据从指定的虚拟内存地址读入指定的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="5d426-120">Reads data from the specified virtual memory address into the specified buffer.</span></span>|  
|[<span data-ttu-id="5d426-121">Request 方法</span><span class="sxs-lookup"><span data-stu-id="5d426-121">Request Method</span></span>](iclrdatatarget-request-method.md)|<span data-ttu-id="5d426-122">由公共语言运行时调用 (CLR) 数据访问服务请求操作，如实现所定义。</span><span class="sxs-lookup"><span data-stu-id="5d426-122">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>|  
|[<span data-ttu-id="5d426-123">SetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="5d426-123">SetThreadContext Method</span></span>](iclrdatatarget-setthreadcontext-method.md)|<span data-ttu-id="5d426-124">设置目标进程中指定线程的当前上下文。</span><span class="sxs-lookup"><span data-stu-id="5d426-124">Sets the current context of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="5d426-125">SetTLSValue 方法</span><span class="sxs-lookup"><span data-stu-id="5d426-125">SetTLSValue Method</span></span>](iclrdatatarget-settlsvalue-method.md)|<span data-ttu-id="5d426-126">在目标进程中指定线程 (TLS) 中设置一个值。</span><span class="sxs-lookup"><span data-stu-id="5d426-126">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="5d426-127">WriteVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="5d426-127">WriteVirtual Method</span></span>](iclrdatatarget-writevirtual-method.md)|<span data-ttu-id="5d426-128">将数据从指定的缓冲区写入指定的虚拟内存地址。</span><span class="sxs-lookup"><span data-stu-id="5d426-128">Writes data from the specified buffer to the specified virtual memory address.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d426-129">注解</span><span class="sxs-lookup"><span data-stu-id="5d426-129">Remarks</span></span>  

 <span data-ttu-id="5d426-130">API 客户端 (即，调试器) 必须根据特定目标项实现此接口。</span><span class="sxs-lookup"><span data-stu-id="5d426-130">The API client (that is, the debugger) must implement this interface as appropriate for the particular target item.</span></span> <span data-ttu-id="5d426-131">例如，活动进程的实现将不同于内存转储的。</span><span class="sxs-lookup"><span data-stu-id="5d426-131">For example, a live process would have an implementation different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d426-132">要求</span><span class="sxs-lookup"><span data-stu-id="5d426-132">Requirements</span></span>  

 <span data-ttu-id="5d426-133">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5d426-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d426-134">**标头：** ClrData，ClrData</span><span class="sxs-lookup"><span data-stu-id="5d426-134">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="5d426-135">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d426-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d426-136">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d426-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d426-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5d426-137">See also</span></span>

- [<span data-ttu-id="5d426-138">ICLRDataTarget2 接口</span><span class="sxs-lookup"><span data-stu-id="5d426-138">ICLRDataTarget2 Interface</span></span>](iclrdatatarget2-interface.md)
- [<span data-ttu-id="5d426-139">调试接口</span><span class="sxs-lookup"><span data-stu-id="5d426-139">Debugging Interfaces</span></span>](debugging-interfaces.md)
