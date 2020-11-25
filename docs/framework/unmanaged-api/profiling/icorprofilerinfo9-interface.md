---
title: ICorProfilerInfo9 接口
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 3d1cdfa56e6bb20f08370aa76b87d516f7b51cda
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732952"
---
# <a name="icorprofilerinfo9-interface"></a><span data-ttu-id="3ff1b-102">ICorProfilerInfo9 接口</span><span class="sxs-lookup"><span data-stu-id="3ff1b-102">ICorProfilerInfo9 Interface</span></span>

<span data-ttu-id="3ff1b-103">[ICorProfilerInfo8](icorprofilerinfo8-interface.md)的子类，提供用于查询有关具有多个本机代码版本的函数的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="3ff1b-103">A subclass of [ICorProfilerInfo8](icorprofilerinfo8-interface.md) that provides methods to query information about functions with multiple native code versions.</span></span>  

## <a name="methods"></a><span data-ttu-id="3ff1b-104">方法</span><span class="sxs-lookup"><span data-stu-id="3ff1b-104">Methods</span></span>  

| <span data-ttu-id="3ff1b-105">方法</span><span class="sxs-lookup"><span data-stu-id="3ff1b-105">Method</span></span>|<span data-ttu-id="3ff1b-106">说明</span><span class="sxs-lookup"><span data-stu-id="3ff1b-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="3ff1b-107">GetNativeCodeStartAddresses 方法</span><span class="sxs-lookup"><span data-stu-id="3ff1b-107">GetNativeCodeStartAddresses Method</span></span>](icorprofilerinfo9-getnativecodestartaddresses-method.md)| <span data-ttu-id="3ff1b-108">给定一个 functionId 和 rejitId，枚举此代码当前存在的所有实时编译版本的本机代码起始地址。</span><span class="sxs-lookup"><span data-stu-id="3ff1b-108">Given a functionId and rejitId, enumerates the native code start address of all jitted versions of this code that currently exist.</span></span> |
|[<span data-ttu-id="3ff1b-109">GetILToNativeMapping3 方法</span><span class="sxs-lookup"><span data-stu-id="3ff1b-109">GetILToNativeMapping3 Method</span></span>](icorprofilerinfo9-getiltonativemapping3-method.md)| <span data-ttu-id="3ff1b-110">给定本机代码起始地址，返回此实时编译版本的代码的本机到 IL 映射信息。</span><span class="sxs-lookup"><span data-stu-id="3ff1b-110">Given the native code start address, returns the native to IL mapping information for this jitted version of the code.</span></span> |
|[<span data-ttu-id="3ff1b-111">GetCodeInfo4 方法</span><span class="sxs-lookup"><span data-stu-id="3ff1b-111">GetCodeInfo4 Method</span></span>](icorprofilerinfo9-getcodeinfo4-method.md)| <span data-ttu-id="3ff1b-112">给定本机代码起始地址，返回存储此代码的虚拟内存块。</span><span class="sxs-lookup"><span data-stu-id="3ff1b-112">Given the native code start address, returns the blocks of virtual memory that store this code.</span></span> |

## <a name="requirements"></a><span data-ttu-id="3ff1b-113">要求</span><span class="sxs-lookup"><span data-stu-id="3ff1b-113">Requirements</span></span>  

<span data-ttu-id="3ff1b-114">**平台：** 请参阅 [支持 .Net Core 的操作系统](../../../core/install/windows.md?pivots=os-windows)。</span><span class="sxs-lookup"><span data-stu-id="3ff1b-114">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>  
<span data-ttu-id="3ff1b-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3ff1b-115">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="3ff1b-116">**.Net 版本：**[!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ff1b-116">**.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="3ff1b-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3ff1b-117">See also</span></span>

- [<span data-ttu-id="3ff1b-118">分析接口</span><span class="sxs-lookup"><span data-stu-id="3ff1b-118">Profiling Interfaces</span></span>](profiling-interfaces.md)
