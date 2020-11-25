---
title: IHostMemoryManager::NeedsVirtualAddressSpace 方法
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.NeedsVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::NeedsVirtualAddressSpace
helpviewer_keywords:
- IHostMemoryManager::NeedsVirtualAddressSpace method [.NET Framework hosting]
- NeedsVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: 71f0eab5-0170-46f8-9f88-1df5abdeb34a
topic_type:
- apiref
ms.openlocfilehash: 74fbb2f162fbb68871f1bb4e1a1de32f5f913cd7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731314"
---
# <a name="ihostmemorymanagerneedsvirtualaddressspace-method"></a><span data-ttu-id="5b5cb-102">IHostMemoryManager::NeedsVirtualAddressSpace 方法</span><span class="sxs-lookup"><span data-stu-id="5b5cb-102">IHostMemoryManager::NeedsVirtualAddressSpace Method</span></span>

<span data-ttu-id="5b5cb-103">向宿主通知公共语言运行时 (CLR) 将要尝试使用指定的内存。</span><span class="sxs-lookup"><span data-stu-id="5b5cb-103">Notifies the host that the common language runtime (CLR) is going to attempt to use the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b5cb-104">语法</span><span class="sxs-lookup"><span data-stu-id="5b5cb-104">Syntax</span></span>  
  
```cpp  
HRESULT NeedsVirtualAddressSpace (  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b5cb-105">参数</span><span class="sxs-lookup"><span data-stu-id="5b5cb-105">Parameters</span></span>  

 `startAddress`  
 <span data-ttu-id="5b5cb-106">中内存的起始地址。</span><span class="sxs-lookup"><span data-stu-id="5b5cb-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="5b5cb-107">中内存的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="5b5cb-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b5cb-108">注解</span><span class="sxs-lookup"><span data-stu-id="5b5cb-108">Remarks</span></span>  

 <span data-ttu-id="5b5cb-109">`NeedsVirtualAddressSpace`方法是一个回调方法，必须由宿主应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="5b5cb-109">The `NeedsVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="5b5cb-110">它由 CLR 调用。</span><span class="sxs-lookup"><span data-stu-id="5b5cb-110">It is called by the CLR.</span></span>  
  
 <span data-ttu-id="5b5cb-111">如果主机不希望 CLR 使用指定的内存，则它可能会返回 E_OUTOFMEMORY HRESULT。</span><span class="sxs-lookup"><span data-stu-id="5b5cb-111">If the host does not want the CLR to use the specified memory, it may return an E_OUTOFMEMORY HRESULT.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b5cb-112">要求</span><span class="sxs-lookup"><span data-stu-id="5b5cb-112">Requirements</span></span>  

 <span data-ttu-id="5b5cb-113">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5b5cb-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b5cb-114">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5b5cb-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5b5cb-115">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5b5cb-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5b5cb-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b5cb-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b5cb-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b5cb-117">See also</span></span>

- [<span data-ttu-id="5b5cb-118">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="5b5cb-118">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
