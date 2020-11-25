---
title: ICLRDataTarget2::FreeVirtual 方法
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2.FreeVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2::FreeVirtual
helpviewer_keywords:
- ICLRDataTarget::FreeVirtual method [.NET Framework debugging]
- FreeVirtual method [.NET Framework debugging]
ms.assetid: 26fb69f8-1467-4711-bd24-cb117c63938f
topic_type:
- apiref
ms.openlocfilehash: 1fb701a40abe2dc6e51443837c07ee5ba05ddfbe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723644"
---
# <a name="iclrdatatarget2freevirtual-method"></a><span data-ttu-id="8b9f2-102">ICLRDataTarget2::FreeVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="8b9f2-102">ICLRDataTarget2::FreeVirtual Method</span></span>

<span data-ttu-id="8b9f2-103">由公共语言运行时 (CLR) 数据访问服务调用，以释放以前在目标进程的地址空间中分配的内存。</span><span class="sxs-lookup"><span data-stu-id="8b9f2-103">Called by the common language runtime (CLR) data access services to free memory that was previously allocated in the address space of the target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b9f2-104">语法</span><span class="sxs-lookup"><span data-stu-id="8b9f2-104">Syntax</span></span>  
  
```cpp  
HRESULT FreeVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b9f2-105">参数</span><span class="sxs-lookup"><span data-stu-id="8b9f2-105">Parameters</span></span>  

 `addr`  
 <span data-ttu-id="8b9f2-106">中一个 `CLRDATA_ADDRESS` 值，该值指定要释放的内存的起始地址。</span><span class="sxs-lookup"><span data-stu-id="8b9f2-106">[in] A `CLRDATA_ADDRESS` value that specifies the starting address of the memory to be freed.</span></span>  
  
 `size`  
 <span data-ttu-id="8b9f2-107">中要释放的内存的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="8b9f2-107">[in] The size, in bytes, of the memory to be freed.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="8b9f2-108">中控制释放内存的标志。</span><span class="sxs-lookup"><span data-stu-id="8b9f2-108">[in] Flags that control the freeing of memory.</span></span> <span data-ttu-id="8b9f2-109">请参阅 Win32 `VirtualFree` 函数。</span><span class="sxs-lookup"><span data-stu-id="8b9f2-109">See the Win32 `VirtualFree` function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b9f2-110">注解</span><span class="sxs-lookup"><span data-stu-id="8b9f2-110">Remarks</span></span>  

 <span data-ttu-id="8b9f2-111">`FreeVirtual`方法用作 Win32 函数的逻辑包装 `VirtualFree` 。</span><span class="sxs-lookup"><span data-stu-id="8b9f2-111">The `FreeVirtual` method serves as a logical wrapper for the Win32 `VirtualFree` function.</span></span>  
  
 <span data-ttu-id="8b9f2-112">此方法由调试应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="8b9f2-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b9f2-113">要求</span><span class="sxs-lookup"><span data-stu-id="8b9f2-113">Requirements</span></span>  

 <span data-ttu-id="8b9f2-114">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8b9f2-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b9f2-115">**标头：** ClrData，ClrData</span><span class="sxs-lookup"><span data-stu-id="8b9f2-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="8b9f2-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b9f2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b9f2-117">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b9f2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b9f2-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b9f2-118">See also</span></span>

- [<span data-ttu-id="8b9f2-119">ICLRDataTarget2 接口</span><span class="sxs-lookup"><span data-stu-id="8b9f2-119">ICLRDataTarget2 Interface</span></span>](iclrdatatarget2-interface.md)
- [<span data-ttu-id="8b9f2-120">AllocVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="8b9f2-120">AllocVirtual Method</span></span>](iclrdatatarget2-allocvirtual-method.md)
