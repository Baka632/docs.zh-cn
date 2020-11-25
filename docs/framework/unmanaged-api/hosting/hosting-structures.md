---
title: 承载结构
ms.date: 03/30/2017
helpviewer_keywords:
- hosting structures [.NET Framework]
- unmanaged structures [.NET Framework], hosting
- structures [.NET Framework hosting]
ms.assetid: 492e010f-7493-4134-9505-f7008ccdaae6
ms.openlocfilehash: 9d0349e4801c550731b6d126197003917c4a46e8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721785"
---
# <a name="hosting-structures"></a><span data-ttu-id="5f16e-102">承载结构</span><span class="sxs-lookup"><span data-stu-id="5f16e-102">Hosting Structures</span></span>

<span data-ttu-id="5f16e-103">本节介绍宿主 API 使用的非托管结构。</span><span class="sxs-lookup"><span data-stu-id="5f16e-103">This section describes the unmanaged structures that the hosting API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5f16e-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="5f16e-104">In This Section</span></span>  

 [<span data-ttu-id="5f16e-105">AssemblyBindInfo 结构</span><span class="sxs-lookup"><span data-stu-id="5f16e-105">AssemblyBindInfo Structure</span></span>](assemblybindinfo-structure.md)  
 <span data-ttu-id="5f16e-106">提供有关所引用程序集的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5f16e-106">Provides detailed information about the referenced assembly.</span></span>  
  
 [<span data-ttu-id="5f16e-107">BucketParameters 结构</span><span class="sxs-lookup"><span data-stu-id="5f16e-107">BucketParameters Structure</span></span>](bucketparameters-structure.md)  
 <span data-ttu-id="5f16e-108">存储事件的类型名称和与事件关联的当前异常的参数。</span><span class="sxs-lookup"><span data-stu-id="5f16e-108">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
 [<span data-ttu-id="5f16e-109">COR_GC_STATS 结构</span><span class="sxs-lookup"><span data-stu-id="5f16e-109">COR_GC_STATS Structure</span></span>](cor-gc-stats-structure.md)  
 <span data-ttu-id="5f16e-110">提供有关公共语言运行时 (CLR) 的垃圾回收机制的统计信息。</span><span class="sxs-lookup"><span data-stu-id="5f16e-110">Provides statistics about the garbage collection mechanism of the common language runtime (CLR).</span></span>  
  
 [<span data-ttu-id="5f16e-111">COR_GC_THREAD_STATS 结构</span><span class="sxs-lookup"><span data-stu-id="5f16e-111">COR_GC_THREAD_STATS Structure</span></span>](cor-gc-thread-stats-structure.md)  
 <span data-ttu-id="5f16e-112">包含与垃圾回收相关的每个线程的统计信息。</span><span class="sxs-lookup"><span data-stu-id="5f16e-112">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
 [<span data-ttu-id="5f16e-113">CustomDumpItem 结构</span><span class="sxs-lookup"><span data-stu-id="5f16e-113">CustomDumpItem Structure</span></span>](customdumpitem-structure.md)  
 <span data-ttu-id="5f16e-114">描述要添加到错误报告中的自定义转储的项。</span><span class="sxs-lookup"><span data-stu-id="5f16e-114">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
 [<span data-ttu-id="5f16e-115">MDAInfo 结构</span><span class="sxs-lookup"><span data-stu-id="5f16e-115">MDAInfo Structure</span></span>](mdainfo-structure.md)  
 <span data-ttu-id="5f16e-116">提供有关事件的详细信息 `Event_MDAFired` ，该事件会触发)  (MDA 创建托管调试助手。</span><span class="sxs-lookup"><span data-stu-id="5f16e-116">Provides details about the `Event_MDAFired` event, which triggers the creation of a managed debugging assistant (MDA).</span></span>  
  
 [<span data-ttu-id="5f16e-117">ModuleBindInfo 结构</span><span class="sxs-lookup"><span data-stu-id="5f16e-117">ModuleBindInfo Structure</span></span>](modulebindinfo-structure.md)  
 <span data-ttu-id="5f16e-118">提供有关被引用模块和包含它的程序集的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5f16e-118">Provides detailed information about the referenced module and the assembly that contains it.</span></span>  
  
 [<span data-ttu-id="5f16e-119">StackOverflowInfo 结构</span><span class="sxs-lookup"><span data-stu-id="5f16e-119">StackOverflowInfo Structure</span></span>](stackoverflowinfo-structure.md)  
 <span data-ttu-id="5f16e-120">存储发生的溢出的类型以及因溢出而引发的异常的信息。</span><span class="sxs-lookup"><span data-stu-id="5f16e-120">Stores the type of overflow that occurred and information on the exception that was thrown due to the overflow.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5f16e-121">相关章节</span><span class="sxs-lookup"><span data-stu-id="5f16e-121">Related Sections</span></span>  

 [<span data-ttu-id="5f16e-122">承载组件类</span><span class="sxs-lookup"><span data-stu-id="5f16e-122">Hosting Coclasses</span></span>](hosting-coclasses.md)  
  
 [<span data-ttu-id="5f16e-123">承载接口</span><span class="sxs-lookup"><span data-stu-id="5f16e-123">Hosting Interfaces</span></span>](hosting-interfaces.md)  
  
 [<span data-ttu-id="5f16e-124">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="5f16e-124">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)  
  
 [<span data-ttu-id="5f16e-125">承载枚举</span><span class="sxs-lookup"><span data-stu-id="5f16e-125">Hosting Enumerations</span></span>](hosting-enumerations.md)
