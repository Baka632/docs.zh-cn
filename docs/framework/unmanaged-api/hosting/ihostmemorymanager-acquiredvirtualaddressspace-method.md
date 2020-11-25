---
title: IHostMemoryManager::AcquiredVirtualAddressSpace 方法
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.AcquiredVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::AcquiredVirtualAddressSpace
helpviewer_keywords:
- IHostMemoryManager::AcquiredVirtualAddressSpace method [.NET Framework hosting]
- AcquiredVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: ef2f83c2-127e-4c38-8385-306c03cd2167
topic_type:
- apiref
ms.openlocfilehash: 58fce616ae05dcc622369a706f010f91d657389f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700621"
---
# <a name="ihostmemorymanageracquiredvirtualaddressspace-method"></a><span data-ttu-id="d477a-102">IHostMemoryManager::AcquiredVirtualAddressSpace 方法</span><span class="sxs-lookup"><span data-stu-id="d477a-102">IHostMemoryManager::AcquiredVirtualAddressSpace Method</span></span>

<span data-ttu-id="d477a-103">向宿主通知公共语言运行时 (CLR) 已从操作系统中获取指定内存。</span><span class="sxs-lookup"><span data-stu-id="d477a-103">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d477a-104">语法</span><span class="sxs-lookup"><span data-stu-id="d477a-104">Syntax</span></span>  
  
```cpp  
HRESULT AcquiredVirtualAddressSpace(  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d477a-105">参数</span><span class="sxs-lookup"><span data-stu-id="d477a-105">Parameters</span></span>  

 `startAddress`  
 <span data-ttu-id="d477a-106">中内存的起始地址。</span><span class="sxs-lookup"><span data-stu-id="d477a-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="d477a-107">中内存的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="d477a-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d477a-108">注解</span><span class="sxs-lookup"><span data-stu-id="d477a-108">Remarks</span></span>  

 <span data-ttu-id="d477a-109">`AcquiredVirtualAddressSpace`方法是一个回调方法，必须由宿主应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="d477a-109">The `AcquiredVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="d477a-110">它由 CLR 调用。</span><span class="sxs-lookup"><span data-stu-id="d477a-110">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d477a-111">要求</span><span class="sxs-lookup"><span data-stu-id="d477a-111">Requirements</span></span>  

 <span data-ttu-id="d477a-112">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d477a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d477a-113">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d477a-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d477a-114">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d477a-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d477a-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d477a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d477a-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d477a-116">See also</span></span>

- [<span data-ttu-id="d477a-117">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="d477a-117">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
