---
title: 调试接口
ms.date: 02/07/2019
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
ms.openlocfilehash: a3dd81ceaab2ba467d4c8ca091c1c2219040a273
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676291"
---
# <a name="debugging-interfaces"></a><span data-ttu-id="ffcaa-102">调试接口</span><span class="sxs-lookup"><span data-stu-id="ffcaa-102">Debugging Interfaces</span></span>

<span data-ttu-id="ffcaa-103">本节描述进行程序调试处理的非托管接口，所调试的程序在公共语言运行时 (CLR) 中执行。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-103">This section describes the unmanaged interfaces that handle the debugging of a program that is executing in the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ffcaa-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="ffcaa-104">In This Section</span></span>  

 <span data-ttu-id="ffcaa-105">[ICLRDataEnumMemoryRegions 接口](iclrdataenummemoryregions-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-105">[ICLRDataEnumMemoryRegions Interface](iclrdataenummemoryregions-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-106">提供对由调用方指定的内存区域进行枚举的方法。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-106">Provides a method to enumerate regions of memory that are specified by callers.</span></span>  
  
 <span data-ttu-id="ffcaa-107">[ICLRDataEnumMemoryRegionsCallback 接口](iclrdataenummemoryregionscallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-107">[ICLRDataEnumMemoryRegionsCallback Interface](iclrdataenummemoryregionscallback-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-108">为 `EnumMemoryRegions` 提供一种回调方法，用于向调试器报告尝试枚举指定内存区域的结果。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-108">Provides a callback method for `EnumMemoryRegions` to report to the debugger, the result of an attempt to enumerate a specified region of memory.</span></span>  
  
 <span data-ttu-id="ffcaa-109">[ICLRDataTarget 接口](iclrdatatarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-109">[ICLRDataTarget Interface](iclrdatatarget-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-110">提供与目标 CLR 进程进行交互的方法。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-110">Provides methods for interaction with a target CLR process.</span></span>  
  
 <span data-ttu-id="ffcaa-111">[ICLRDataTarget2 接口](iclrdatatarget2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-111">[ICLRDataTarget2 Interface](iclrdatatarget2-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-112">数据访问服务层在目标进程中操作虚拟内存区域时所用的 `ICLRDataTarget` 的子类。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-112">A subclass of `ICLRDataTarget` that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
 <span data-ttu-id="ffcaa-113">[ICLRDataTarget3 接口](iclrdatatarget3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-113">[ICLRDataTarget3 Interface](iclrdatatarget3-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-114">提供对异常信息的访问的 [ICLRDataTarget2](iclrdatatarget2-interface.md) 的子类。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-114">A subclass of [ICLRDataTarget2](iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
 <span data-ttu-id="ffcaa-115">[ICLRDebugging 接口](iclrdebugging-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-115">[ICLRDebugging Interface](iclrdebugging-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-116">提供一些方法，用于处理模块的加载和卸载以进行调试。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-116">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
 <span data-ttu-id="ffcaa-117">[ICLRDebuggingLibraryProvider 接口](iclrdebugginglibraryprovider-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-117">[ICLRDebuggingLibraryProvider Interface](iclrdebugginglibraryprovider-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-118">包括 [ProvideLibrary 方法](iclrdebugginglibraryprovider-providelibrary-method.md) 方法，该方法可获取一个库提供程序回调接口，该接口允许根据需要定位和加载特定于公共语言运行时版本的调试库。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-118">Includes the [ProvideLibrary Method](iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
 <span data-ttu-id="ffcaa-119">[ICLRMetadataLocator 接口](iclrmetadatalocator-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-119">[ICLRMetadataLocator Interface](iclrmetadatalocator-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-120">数据访问服务层用于在目标进程中定位程序集的元数据的接口。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-120">Interface used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
 <span data-ttu-id="ffcaa-121">[ICorDebug 接口](icordebug-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-121">[ICorDebug Interface](icordebug-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-122">提供允许开发人员在 CLR 环境中调试应用程序的方法。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-122">Provides methods that allow developers to debug applications in the CLR environment.</span></span>  
  
 <span data-ttu-id="ffcaa-123">[ICorDebugAppDomain 接口](icordebugappdomain-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-123">[ICorDebugAppDomain Interface](icordebugappdomain-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-124">提供用于调试应用程序域的方法。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-124">Provides methods for debugging application domains.</span></span>  
  
 <span data-ttu-id="ffcaa-125">[ICorDebugAppDomain2 接口](icordebugappdomain2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-125">[ICorDebugAppDomain2 Interface](icordebugappdomain2-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-126">提供处理数组、指针、函数指针和 ByRef 类型的方法。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-126">Provides methods to work with arrays, pointers, function pointers, and ByRef types.</span></span> <span data-ttu-id="ffcaa-127">此接口是 `ICorDebugAppDomain` 接口的扩展。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-127">This interface is an extension of the `ICorDebugAppDomain` interface.</span></span>  
  
 <span data-ttu-id="ffcaa-128">[ICorDebugAppDomain3 接口](icordebugappdomain3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-128">[ICorDebugAppDomain3 Interface](icordebugappdomain3-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-129">提供用于在应用程序域中使用 Windows 运行时类型的方法。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-129">Provides methods to work with the Windows Runtime types in an application domain.</span></span> <span data-ttu-id="ffcaa-130">此接口是 `ICorDebugAppDomain` 和 `ICorDebugAppDomain2` 接口的扩展。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-130">This interface is an extension of the `ICorDebugAppDomain` and `ICorDebugAppDomain2` interfaces.</span></span>  
  
 <span data-ttu-id="ffcaa-131">[ICorDebugAppDomain4 接口](icordebugappdomain4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-131">[ICorDebugAppDomain4 Interface](icordebugappdomain4-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-132">对 [ICorDebugAppDomain](icordebugappdomain-interface.md) 接口进行逻辑扩展，以从 COM 可调用包装器获取托管对象。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-132">Logically extends the [ICorDebugAppDomain](icordebugappdomain-interface.md) interface to get a managed object from a COM callable wrapper.</span></span>  
  
 <span data-ttu-id="ffcaa-133">[ICorDebugAppDomainEnum 接口](icordebugappdomainenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-133">[ICorDebugAppDomainEnum Interface](icordebugappdomainenum-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-134">提供一种方法，此方法从枚举中的下一个位置开始，返回指定数目的 `ICorDebugAppDomain` 值。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-134">Provides a method that returns a specified number of `ICorDebugAppDomain` values starting at the next location in the enumeration.</span></span>  
  
 <span data-ttu-id="ffcaa-135">[ICorDebugArrayValue 接口](icordebugarrayvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-135">[ICorDebugArrayValue Interface](icordebugarrayvalue-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-136">表示一维或多维数组的 `ICorDebugHeapValue` 的子类。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-136">A subclass of `ICorDebugHeapValue` that represents a single-dimensional or multi-dimensional array.</span></span>  
  
 <span data-ttu-id="ffcaa-137">[ICorDebugAssembly 接口](icordebugassembly-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-137">[ICorDebugAssembly Interface](icordebugassembly-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-138">表示一个程序集。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-138">Represents an assembly.</span></span>  
  
 <span data-ttu-id="ffcaa-139">[ICorDebugAssembly2 接口](icordebugassembly2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-139">[ICorDebugAssembly2 Interface](icordebugassembly2-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-140">表示一个程序集。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-140">Represents an assembly.</span></span> <span data-ttu-id="ffcaa-141">此接口是 `ICorDebugAssembly` 接口的扩展。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-141">This interface is an extension of the `ICorDebugAssembly` interface.</span></span>  
  
 <span data-ttu-id="ffcaa-142">[ICorDebugAssembly3 接口](icordebugassembly3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-142">[ICorDebugAssembly3 Interface](icordebugassembly3-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-143">对 [ICorDebugAssembly](icordebugassembly-interface.md) 接口进行逻辑扩展，以便为容器程序集及其包含的程序集提供支持。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-143">Logically extends the [ICorDebugAssembly](icordebugassembly-interface.md) interface to provide support for container assemblies and their contained assemblies.</span></span> <span data-ttu-id="ffcaa-144">**仅在 .NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="ffcaa-144">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="ffcaa-145">[ICorDebugAssemblyEnum 接口](icordebugassemblyenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-145">[ICorDebugAssemblyEnum Interface](icordebugassemblyenum-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-146">实现 `ICorDebugEnum` 方法，并枚举 `ICorDebugAssembly` 数组。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-146">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugAssembly` arrays.</span></span>  
  
 <span data-ttu-id="ffcaa-147">[ICorDebugBlockingObjectEnum 接口](icordebugblockingobjectenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-147">[ICorDebugBlockingObjectEnum Interface](icordebugblockingobjectenum-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-148">为 [CorDebugBlockingObject](cordebugblockingobject-structure.md) 结构的列表提供枚举器。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-148">Provides an enumerator for a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>  
  
 <span data-ttu-id="ffcaa-149">[ICorDebugBoxValue 接口](icordebugboxvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-149">[ICorDebugBoxValue Interface](icordebugboxvalue-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-150">表示装箱的值类对象的 `ICorDebugHeapValue` 的子类。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-150">A subclass of `ICorDebugHeapValue` that represents a boxed value class object.</span></span>  
  
 <span data-ttu-id="ffcaa-151">[ICorDebugBreakpoint 接口](icordebugbreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-151">[ICorDebugBreakpoint Interface](icordebugbreakpoint-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-152">表示函数中的断点，或值的观察点。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-152">Represents a breakpoint in a function or a watch point on a value.</span></span>  
  
 <span data-ttu-id="ffcaa-153">[ICorDebugBreakpointEnum 接口](icordebugbreakpointenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-153">[ICorDebugBreakpointEnum Interface](icordebugbreakpointenum-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-154">实现 `ICorDebugEnum` 方法，并枚举 `ICorDebugBreakpoint` 数组。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-154">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugBreakpoint` arrays.</span></span>  
  
 <span data-ttu-id="ffcaa-155">[ICorDebugChain 接口](icordebugchain-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-155">[ICorDebugChain Interface](icordebugchain-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-156">表示一个物理或逻辑调用堆栈段。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-156">Represents a segment of a physical or logical call stack.</span></span>  
  
 <span data-ttu-id="ffcaa-157">[ICorDebugChainEnum 接口](icordebugchainenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-157">[ICorDebugChainEnum Interface](icordebugchainenum-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-158">实现 `ICorDebugEnum` 方法，并枚举 `ICorDebugChain` 数组。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-158">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugChain` arrays.</span></span>  
  
 <span data-ttu-id="ffcaa-159">[ICorDebugClass 接口](icordebugclass-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-159">[ICorDebugClass Interface](icordebugclass-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-160">表示基类型或复杂类型（即用户定义的类型）。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-160">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="ffcaa-161">如果该类型为泛型类型，则 `ICorDebugClass` 表示实例化的泛型类型。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-161">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
 <span data-ttu-id="ffcaa-162">[ICorDebugClass2 接口](icordebugclass2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-162">[ICorDebugClass2 Interface](icordebugclass2-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-163">表示泛型类或具有 <xref:System.Type> 类型的方法参数的类。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-163">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="ffcaa-164">此接口扩展了 `ICorDebugClass`。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-164">This interface extends `ICorDebugClass`.</span></span>  
  
 <span data-ttu-id="ffcaa-165">[ICorDebugCode 接口](icordebugcode-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-165">[ICorDebugCode Interface](icordebugcode-interface1.md)</span></span>\
 <span data-ttu-id="ffcaa-166">表示 Microsoft 中间语言 (MSIL) 代码段或本机代码段。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-166">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
 <span data-ttu-id="ffcaa-167">[ICorDebugCode2 接口](icordebugcode2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-167">[ICorDebugCode2 Interface](icordebugcode2-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-168">提供扩展 `ICorDebugCode` 的功能的方法。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-168">Provides methods that extend the capabilities of `ICorDebugCode`.</span></span>  
  
 <span data-ttu-id="ffcaa-169">[ICorDebugCode3 接口](icordebugcode3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-169">[ICorDebugCode3 Interface](icordebugcode3-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-170">提供扩展 [ICorDebugCode](icordebugcode-interface1.md) 和 [ICorDebugCode2](icordebugcode2-interface.md) 的方法，以提供有关托管返回值的信息。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-170">Provides a method that extends [ICorDebugCode](icordebugcode-interface1.md) and [ICorDebugCode2](icordebugcode2-interface.md) to provide information about a managed return value.</span></span>  
  
 <span data-ttu-id="ffcaa-171">[ICorDebugCode4 接口](icordebugcode4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-171">[ICorDebugCode4 Interface](icordebugcode4-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-172">提供一个方法，该方法使调试器可以枚举函数中的局部变量和参数。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-172">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
 <span data-ttu-id="ffcaa-173">[ICorDebugCodeEnum 接口](icordebugcodeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-173">[ICorDebugCodeEnum Interface](icordebugcodeenum-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-174">实现 `ICorDebugEnum` 方法，并枚举 `ICorDebugCode` 数组。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-174">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugCode` arrays.</span></span>  
  
 <span data-ttu-id="ffcaa-175">[ICorDebugComObjectValue 接口](icordebugcomobjectvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-175">[ICorDebugComObjectValue Interface](icordebugcomobjectvalue-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-176">提供用来检索缓存的接口对象的方法。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-176">Provides methods to retrieve cached interface objects.</span></span>  
  
 <span data-ttu-id="ffcaa-177">[ICorDebugContext 接口](icordebugcontext-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-177">[ICorDebugContext Interface](icordebugcontext-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-178">表示一个上下文对象。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-178">Represents a context object.</span></span> <span data-ttu-id="ffcaa-179">此接口尚未实现。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-179">This interface has not been implemented yet.</span></span>  
  
 <span data-ttu-id="ffcaa-180">[ICorDebugController 接口](icordebugcontroller-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-180">[ICorDebugController Interface](icordebugcontroller-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-181">表示可以控制代码执行上下文的 <xref:System.Diagnostics.Process> 或 <xref:System.AppDomain> 范围。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-181">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
 <span data-ttu-id="ffcaa-182">[ICorDebugDataTarget 接口](icordebugdatatarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-182">[ICorDebugDataTarget Interface](icordebugdatatarget-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-183">提供一个回调接口，该接口可提供对特定目标进程的访问。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-183">Provides a callback interface that provides access to a particular target process.</span></span>  
  
 <span data-ttu-id="ffcaa-184">[ICorDebugDataTarget2 接口](icordebugdatatarget2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-184">[ICorDebugDataTarget2 Interface](icordebugdatatarget2-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-185">对 [ICorDebugDataTarget](icordebugdatatarget-interface.md) 接口进行逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-185">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="ffcaa-186">**仅在 .NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="ffcaa-186">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="ffcaa-187">[ICorDebugDataTarget3 接口](icordebugdatatarget3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-187">[ICorDebugDataTarget3 Interface](icordebugdatatarget3-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-188">对 [ICorDebugDataTarget](icordebugdatatarget-interface.md) 接口进行逻辑扩展，以提供有关已加载模块的信息。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-188">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span> <span data-ttu-id="ffcaa-189">**仅在 .NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="ffcaa-189">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="ffcaa-190">[ICorDebugDebugEvent 接口](icordebugdebugevent-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-190">[ICorDebugDebugEvent Interface](icordebugdebugevent-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-191">定义所有 `ICorDebug` 调试事件派生的基接口。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-191">Defines the base interface from which all `ICorDebug` debug events derive.</span></span> <span data-ttu-id="ffcaa-192">**仅在 .NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="ffcaa-192">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="ffcaa-193">[ICorDebugEditAndContinueErrorInfo 接口](icordebugeditandcontinueerrorinfo-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-193">[ICorDebugEditAndContinueErrorInfo Interface](icordebugeditandcontinueerrorinfo-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-194">已过时。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-194">Obsolete.</span></span> <span data-ttu-id="ffcaa-195">不要使用此接口。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-195">Do not use this interface.</span></span>  
  
 <span data-ttu-id="ffcaa-196">[ICorDebugEditAndContinueSnapshot 接口](icordebugeditandcontinuesnapshot-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-196">[ICorDebugEditAndContinueSnapshot Interface](icordebugeditandcontinuesnapshot-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-197">已过时。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-197">Obsolete.</span></span> <span data-ttu-id="ffcaa-198">不要使用此接口。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-198">Do not use this interface.</span></span>  
  
 <span data-ttu-id="ffcaa-199">[ICorDebugEnum 接口](icordebugenum-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-199">[ICorDebugEnum Interface](icordebugenum-interface1.md)</span></span>\
 <span data-ttu-id="ffcaa-200">作为调试枚举器的抽象基接口。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-200">Serves as the abstract base interface for debugging enumerators.</span></span>  
  
 <span data-ttu-id="ffcaa-201">[ICorDebugErrorInfoEnum 接口](icordebugerrorinfoenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-201">[ICorDebugErrorInfoEnum Interface](icordebugerrorinfoenum-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-202">已过时。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-202">Obsolete.</span></span> <span data-ttu-id="ffcaa-203">不要使用此接口。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-203">Do not use this interface.</span></span>  
  
 <span data-ttu-id="ffcaa-204">[ICorDebugEval 接口](icordebugeval-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-204">[ICorDebugEval Interface](icordebugeval-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-205">提供使调试器能够在正在调试的代码的上下文中执行代码的方法。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-205">Provides methods to enable the debugger to execute code within the context of the code being debugged.</span></span>  
  
 <span data-ttu-id="ffcaa-206">[ICorDebugEval2 接口](icordebugeval2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-206">[ICorDebugEval2 Interface](icordebugeval2-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-207">扩展 `ICorDebugEval` 以对泛型类型提供支持。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-207">Extends `ICorDebugEval` to provide support for generic types.</span></span>  
  
 <span data-ttu-id="ffcaa-208">[ICorDebugExceptionDebugEvent 接口](icordebugexceptiondebugevent-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-208">[ICorDebugExceptionDebugEvent Interface](icordebugexceptiondebugevent-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-209">扩展 [ICorDebugDebugEvent](icordebugdebugevent-interface.md) 接口以支持异常事件。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-209">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support exception events.</span></span> <span data-ttu-id="ffcaa-210">**仅在 .NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="ffcaa-210">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="ffcaa-211">[ICorDebugExceptionObjectCallStackEnum 接口](icordebugexceptionobjectcallstackenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-211">[ICorDebugExceptionObjectCallStackEnum Interface](icordebugexceptionobjectcallstackenum-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-212">为嵌入在异常对象中的调用堆栈信息提供枚举器。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-212">Provides an enumerator for call stack information that is embedded in an exception object.</span></span>  
  
 <span data-ttu-id="ffcaa-213">[ICorDebugExceptionObjectValue 接口](icordebugexceptionobjectvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-213">[ICorDebugExceptionObjectValue Interface](icordebugexceptionobjectvalue-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-214">扩展 [ICorDebugObjectValue](icordebugobjectvalue-interface.md) 接口以提供来自托管异常对象的堆栈跟踪信息。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-214">Extends the [ICorDebugObjectValue](icordebugobjectvalue-interface.md) interface to provide stack trace information from a managed exception object.</span></span>  
  
 <span data-ttu-id="ffcaa-215">[ICorDebugFrame 接口](icordebugframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-215">[ICorDebugFrame Interface](icordebugframe-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-216">表示当前堆栈上的帧。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-216">Represents a frame on the current stack.</span></span>  
  
 <span data-ttu-id="ffcaa-217">[ICorDebugFrameEnum 接口](icordebugframeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-217">[ICorDebugFrameEnum Interface](icordebugframeenum-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-218">实现 `ICorDebugEnum` 方法，并枚举 `ICorDebugFrame` 数组。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-218">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugFrame` arrays.</span></span>  
  
 <span data-ttu-id="ffcaa-219">[ICorDebugFunction 接口](icordebugfunction-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-219">[ICorDebugFunction Interface](icordebugfunction-interface1.md)</span></span>\
 <span data-ttu-id="ffcaa-220">表示一个托管函数或方法。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-220">Represents a managed function or method.</span></span>  
  
 <span data-ttu-id="ffcaa-221">[ICorDebugFunction2 接口](icordebugfunction2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-221">[ICorDebugFunction2 Interface](icordebugfunction2-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-222">对 `ICorDebugFunction` 进行逻辑扩展，以支持“仅我的代码”的单步执行调试。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-222">Logically extends `ICorDebugFunction` to provide support for Just My Code step-through debugging.</span></span>  
  
 <span data-ttu-id="ffcaa-223">[ICorDebugFunction3 接口](icordebugfunction3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-223">[ICorDebugFunction3 Interface](icordebugfunction3-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-224">对 [ICorDebugFunction](icordebugfunction-interface1.md) 接口进行逻辑扩展，以提供对 ReJIT 请求中的代码的访问。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-224">Logically extends the [ICorDebugFunction](icordebugfunction-interface1.md) interface to provide access to code from a ReJIT request.</span></span>  
  
 <span data-ttu-id="ffcaa-225">[ICorDebugFunctionBreakpoint 接口](icordebugfunctionbreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-225">[ICorDebugFunctionBreakpoint Interface](icordebugfunctionbreakpoint-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-226">扩展 `ICorDebugBreakpoint` 以支持函数中的断点。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-226">Extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
 <span data-ttu-id="ffcaa-227">[ICorDebugGCReferenceEnum 接口](icordebuggcreferenceenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-227">[ICorDebugGCReferenceEnum Interface](icordebuggcreferenceenum-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-228">提供针对将进行垃圾回收的对象的枚举器。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-228">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
 <span data-ttu-id="ffcaa-229">[ICorDebugGenericValue 接口](icordebuggenericvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-229">[ICorDebugGenericValue Interface](icordebuggenericvalue-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-230">应用于所有值的 `ICorDebugValue` 的子类。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-230">A subclass of `ICorDebugValue` that applies to all values.</span></span> <span data-ttu-id="ffcaa-231">此接口可为值提供 Get 和 Set 方法。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-231">This interface provides Get and Set methods for the value.</span></span>  
  
 <span data-ttu-id="ffcaa-232">[ICorDebugGuidToTypeEnum 接口](icordebugguidtotypeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-232">[ICorDebugGuidToTypeEnum Interface](icordebugguidtotypeenum-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-233">提供针对映射 GUID 的对象及其相应的 `ICorDebugType` 对象的枚举器。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-233">Provides an enumerator for an object that maps GUIDs and their corresponding `ICorDebugType` objects.</span></span>  
  
 <span data-ttu-id="ffcaa-234">[ICorDebugHandleValue 接口](icordebughandlevalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-234">[ICorDebugHandleValue Interface](icordebughandlevalue-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-235">`ICorDebugReferenceValue` 的一个子类，前者表示调试器已为其创建了垃圾回收句柄的引用值。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-235">A subclass of `ICorDebugReferenceValue` that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
 <span data-ttu-id="ffcaa-236">[ICorDebugHeapEnum 接口](icordebugheapenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-236">[ICorDebugHeapEnum Interface](icordebugheapenum-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-237">提供针对托管堆上的对象的枚举器。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-237">Provides an enumerator for objects on the managed heap.</span></span>  
  
 <span data-ttu-id="ffcaa-238">[ICorDebugHeapSegmentEnum 接口](icordebugheapsegmentenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-238">[ICorDebugHeapSegmentEnum Interface](icordebugheapsegmentenum-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-239">提供针对托管堆的内存区域的枚举器。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-239">Provides an enumerator for the memory regions of the managed heap.</span></span>  
  
 <span data-ttu-id="ffcaa-240">[ICorDebugHeapValue 接口](icordebugheapvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-240">[ICorDebugHeapValue Interface](icordebugheapvalue-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-241">表示 CLR 垃圾回收器已收集的对象的 `ICorDebugValue` 的子类。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-241">A subclass of `ICorDebugValue` that represents an object that has been collected by the CLR garbage collector.</span></span>  
  
 <span data-ttu-id="ffcaa-242">[ICorDebugHeapValue2 接口](icordebugheapvalue2-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-242">[ICorDebugHeapValue2 Interface](icordebugheapvalue2-interface1.md)</span></span>\
 <span data-ttu-id="ffcaa-243">对运行时句柄提供支持的 `ICorDebugHeapValue` 的扩展。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-243">An extension of `ICorDebugHeapValue` that provides support for runtime handles.</span></span>  
  
 <span data-ttu-id="ffcaa-244">[ICorDebugHeapValue3 接口](icordebugheapvalue3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-244">[ICorDebugHeapValue3 Interface](icordebugheapvalue3-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-245">公开对象的监视器锁属性。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-245">Exposes the monitor lock properties of objects.</span></span>  
  
 <span data-ttu-id="ffcaa-246">[ICorDebugILCode 接口](icordebugilcode-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-246">[ICorDebugILCode Interface](icordebugilcode-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-247">表示中间语言 (IL) 代码段。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-247">Represents a segment of intermediate language (IL) code.</span></span>  
  
 <span data-ttu-id="ffcaa-248">[ICorDebugILCode2 接口](icordebugilcode2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-248">[ICorDebugILCode2 Interface](icordebugilcode2-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-249">对 [ICorDebugILCode](icordebugilcode-interface.md) 接口进行逻辑扩展，以提供返回函数的局部变量签名的标记的方法，并将探查器检测到的中间语言 (il) 偏移量映射到原始方法的 il 偏移量。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-249">Logically extends the [ICorDebugILCode](icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
 <span data-ttu-id="ffcaa-250">[ICorDebugILFrame 接口](icordebugilframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-250">[ICorDebugILFrame Interface](icordebugilframe-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-251">表示 MSIL 代码的堆栈帧。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-251">Represents a stack frame of MSIL code.</span></span>  
  
 <span data-ttu-id="ffcaa-252">[ICorDebugILFrame2 接口](icordebugilframe2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-252">[ICorDebugILFrame2 Interface](icordebugilframe2-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-253">`ICorDebugILFrame` 的逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-253">A logical extension of `ICorDebugILFrame`.</span></span>  
  
 <span data-ttu-id="ffcaa-254">[ICorDebugILFrame3 接口](icordebugilframe3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-254">[ICorDebugILFrame3 Interface](icordebugilframe3-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-255">提供用于封装函数的返回值的方法。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-255">Provides a method that encapsulates the return value of a function.</span></span>  
  
 <span data-ttu-id="ffcaa-256">[ICorDebugILFrame4 接口](icordebugilframe4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-256">[ICorDebugILFrame4 Interface](icordebugilframe4-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-257">提供使你能够访问中间语言 (IL) 代码的堆栈帧中的局部变量和代码的方法。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-257">Provides methods that allow you to access the local variables and code in a stack frame of intermediate language (IL) code.</span></span> <span data-ttu-id="ffcaa-258">一个用于指定调试器是否可以访问在探查器 ReJIT 检测中添加的变量和代码的参数。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-258">A parameter specifies whether the debugger has access to variables and code added in profiler ReJIT instrumentation.</span></span>  
  
 <span data-ttu-id="ffcaa-259">[ICorDebugInstanceFieldSymbol 接口](icordebuginstancefieldsymbol-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-259">[ICorDebugInstanceFieldSymbol Interface](icordebuginstancefieldsymbol-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-260">表示某一实例字段的调试符号信息。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-260">Represents the debug symbol information for an instance field.</span></span> <span data-ttu-id="ffcaa-261">**仅在 .NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="ffcaa-261">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="ffcaa-262">[ICorDebugInternalFrame 接口](icordebuginternalframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-262">[ICorDebugInternalFrame Interface](icordebuginternalframe-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-263">标识调试器的帧类型。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-263">Identifies frame types for the debugger.</span></span>  
  
 <span data-ttu-id="ffcaa-264">[ICorDebugInternalFrame2 接口](icordebuginternalframe2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-264">[ICorDebugInternalFrame2 Interface](icordebuginternalframe2-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-265">提供有关内部帧的信息，包括堆栈地址和相对于 [ICorDebugFrame](icordebugframe-interface.md) 对象的位置。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-265">Provides information about internal frames, including stack address and position in relation to [ICorDebugFrame](icordebugframe-interface.md) objects.</span></span>  
  
 <span data-ttu-id="ffcaa-266">[ICorDebugLoadedModule 接口](icordebugloadedmodule-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-266">[ICorDebugLoadedModule Interface](icordebugloadedmodule-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-267">提供有关已加载模块的信息。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-267">Provides information about a loaded module.</span></span> <span data-ttu-id="ffcaa-268">**仅在 .NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="ffcaa-268">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="ffcaa-269">[ICorDebugManagedCallback 接口](icordebugmanagedcallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-269">[ICorDebugManagedCallback Interface](icordebugmanagedcallback-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-270">提供用于处理调试器回调的方法。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-270">Provides methods to process debugger callbacks.</span></span>  
  
 <span data-ttu-id="ffcaa-271">[ICorDebugManagedCallback2 接口](icordebugmanagedcallback2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-271">[ICorDebugManagedCallback2 Interface](icordebugmanagedcallback2-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-272">提供支持调试器异常处理和托管调试助手 (MDA) 的方法。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-272">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="ffcaa-273">`ICorDebugManagedCallback2` 是 `ICorDebugManagedCallback` 的逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-273">`ICorDebugManagedCallback2` is a logical extension of `ICorDebugManagedCallback`.</span></span>  
  
 <span data-ttu-id="ffcaa-274">[ICorDebugManagedCallback3 接口](icordebugmanagedcallback3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-274">[ICorDebugManagedCallback3 Interface](icordebugmanagedcallback3-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-275">提供一个回调方法，该方法指示已发出启用的自定义调试器通知。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-275">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
 <span data-ttu-id="ffcaa-276">[ICorDebugMDA 接口](icordebugmda-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-276">[ICorDebugMDA Interface](icordebugmda-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-277">表示托管调试助手 (MDA) 消息。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-277">Represents a managed debugging assistant (MDA) message.</span></span>  
  
 <span data-ttu-id="ffcaa-278">[ICorDebugMemoryBuffer 接口](icordebugmemorybuffer-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-278">[ICorDebugMemoryBuffer Interface](icordebugmemorybuffer-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-279">表示内存中缓冲区。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-279">Represents an in-memory buffer.</span></span> <span data-ttu-id="ffcaa-280">**仅在 .NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="ffcaa-280">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="ffcaa-281">[ICorDebugMergedAssemblyRecord 接口](icordebugmergedassemblyrecord-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-281">[ICorDebugMergedAssemblyRecord Interface](icordebugmergedassemblyrecord-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-282">提供有关合并的程序集的信息。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-282">Provides information about a merged assembly.</span></span> <span data-ttu-id="ffcaa-283">**仅在 .NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="ffcaa-283">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="ffcaa-284">[ICorDebugMetaDataLocator 接口](icordebugmetadatalocator-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-284">[ICorDebugMetaDataLocator Interface](icordebugmetadatalocator-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-285">向调试器提供元数据信息。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-285">Provides metadata information to the debugger.</span></span>  
  
 <span data-ttu-id="ffcaa-286">[ICorDebugModule 接口](icordebugmodule-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-286">[ICorDebugModule Interface](icordebugmodule-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-287">表示 CLR 模块，它是可执行文件或动态链接库 (DLL)。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-287">Represents a CLR module, which is either an executable or a dynamic-link library (DLL).</span></span>  
  
 <span data-ttu-id="ffcaa-288">[ICorDebugModule2 接口](icordebugmodule2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-288">[ICorDebugModule2 Interface](icordebugmodule2-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-289">用作 `ICorDebugModule` 的逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-289">Serves as a logical extension to `ICorDebugModule`.</span></span>  
  
 <span data-ttu-id="ffcaa-290">[ICorDebugModule3 接口](icordebugmodule3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-290">[ICorDebugModule3 Interface](icordebugmodule3-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-291">为动态模块创建符号读取器。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-291">Creates a symbol reader for a dynamic module.</span></span>  
  
 <span data-ttu-id="ffcaa-292">[ICorDebugModuleBreakpoint 接口](icordebugmodulebreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-292">[ICorDebugModuleBreakpoint Interface](icordebugmodulebreakpoint-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-293">扩展 `ICorDebugBreakpoint` 以提供对特定模块的访问。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-293">Extends `ICorDebugBreakpoint` to provide access to specific modules.</span></span>  
  
 <span data-ttu-id="ffcaa-294">[ICorDebugModuleDebugEvent 接口](icordebugmoduledebugevent-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-294">[ICorDebugModuleDebugEvent Interface](icordebugmoduledebugevent-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-295">扩展 [ICorDebugDebugEvent](icordebugdebugevent-interface.md) 接口以支持模块级事件。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-295">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support module-level events.</span></span> <span data-ttu-id="ffcaa-296">**仅在 .NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="ffcaa-296">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="ffcaa-297">[ICorDebugModuleEnum 接口](icordebugmoduleenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-297">[ICorDebugModuleEnum Interface](icordebugmoduleenum-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-298">实现 `ICorDebugEnum` 方法，并枚举 `ICorDebugModule` 数组。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-298">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugModule` arrays.</span></span>  
  
 <span data-ttu-id="ffcaa-299">[ICorDebugMutableDataTarget 接口](icordebugmutabledatatarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-299">[ICorDebugMutableDataTarget Interface](icordebugmutabledatatarget-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-300">扩展 [ICorDebugDataTarget](icordebugdatatarget-interface.md) 接口以支持可变数据目标。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-300">Extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to support mutable data targets.</span></span>  
  
 <span data-ttu-id="ffcaa-301">[ICorDebugNativeFrame 接口](icordebugnativeframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-301">[ICorDebugNativeFrame Interface](icordebugnativeframe-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-302">用于本机帧的 `ICorDebugFrame` 的专用实现。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-302">A specialized implementation of `ICorDebugFrame` used for native frames.</span></span>  
  
 <span data-ttu-id="ffcaa-303">[ICorDebugNativeFrame2 接口](icordebugnativeframe2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-303">[ICorDebugNativeFrame2 Interface](icordebugnativeframe2-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-304">提供用于测试子帧与父帧关系的方法。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-304">Provides methods that test for child and parent frame relationships.</span></span>  
  
 <span data-ttu-id="ffcaa-305">[ICorDebugObjectEnum 接口](icordebugobjectenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-305">[ICorDebugObjectEnum Interface](icordebugobjectenum-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-306">实现 `ICorDebugEnum` 方法，并通过对象数组的相对虚拟地址 (RVA) 对其进行枚举。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-306">Implements `ICorDebugEnum` methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
 <span data-ttu-id="ffcaa-307">[ICorDebugObjectValue 接口](icordebugobjectvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-307">[ICorDebugObjectValue Interface](icordebugobjectvalue-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-308">表示包含对象的值的 `ICorDebugValue` 的子类。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-308">A subclass of `ICorDebugValue` that represents a value that contains an object.</span></span>  
  
 <span data-ttu-id="ffcaa-309">[ICorDebugObjectValue2 接口](icordebugobjectvalue2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-309">[ICorDebugObjectValue2 Interface](icordebugobjectvalue2-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-310">扩展 `ICorDebugObjectValue` 以支持继承和重写。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-310">Extends `ICorDebugObjectValue` to support inheritance and overrides.</span></span>  
  
 <span data-ttu-id="ffcaa-311">[ICorDebugProcess 接口](icordebugprocess-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-311">[ICorDebugProcess Interface](icordebugprocess-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-312">表示正在执行托管代码的进程。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-312">Represents a process that is executing managed code.</span></span>  
  
 <span data-ttu-id="ffcaa-313">[ICorDebugProcess2 接口](icordebugprocess2-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-313">[ICorDebugProcess2 Interface](icordebugprocess2-interface1.md)</span></span>\
 <span data-ttu-id="ffcaa-314">`ICorDebugProcess` 的逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-314">A logical extension of `ICorDebugProcess`.</span></span>  
  
 <span data-ttu-id="ffcaa-315">[ICorDebugProcess3 接口](icordebugprocess3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-315">[ICorDebugProcess3 Interface](icordebugprocess3-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-316">控制自定义调试器通知。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-316">Controls custom debugger notifications.</span></span>

 <span data-ttu-id="ffcaa-317">[ICorDebugProcess4 接口](icordebugprocess4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-317">[ICorDebugProcess4 Interface](icordebugprocess4-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-318">为进程外执行控制提供支持。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-318">Provides support for out of process execution control.</span></span>
  
 <span data-ttu-id="ffcaa-319">[ICorDebugProcess5 接口](icordebugprocess5-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-319">[ICorDebugProcess5 Interface](icordebugprocess5-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-320">扩展 [ICorDebugProcess](icordebugprocess-interface.md) 接口以支持对托管堆的访问，以提供有关托管对象的垃圾回收的信息，以及确定调试器是否从应用程序的本地本机映像缓存中加载图像。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-320">Extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application's local native image cache.</span></span>  
  
 <span data-ttu-id="ffcaa-321">[ICorDebugProcess6 接口](icordebugprocess6-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-321">[ICorDebugProcess6 Interface](icordebugprocess6-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-322">对 [ICorDebugProcess](icordebugprocess-interface.md) 接口进行逻辑扩展，以启用一些功能，如对以本机异常调试事件和虚拟模块拆分方式编码的托管调试事件进行解码。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-322">Logically extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to enable features such as decoding managed debug events that are encoded in native exception debug events and virtual module splitting.</span></span> <span data-ttu-id="ffcaa-323">**仅在 .NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="ffcaa-323">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="ffcaa-324">[ICorDebugProcess7 接口](icordebugprocess7-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-324">[ICorDebugProcess7 Interface](icordebugprocess7-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-325">提供了一种方法，用于配置调试器以处理目标进程中的内存中元数据更新。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-325">Provides a method that configures the debugger to handle in-memory metadata updates in the target process.</span></span>  
  
 <span data-ttu-id="ffcaa-326">[ICorDebugProcess8 接口](icordebugprocess8-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-326">[ICorDebugProcess8 Interface](icordebugprocess8-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-327">对 [ICorDebugProcess](icordebugprocess-interface.md) 接口进行逻辑扩展，以启用或禁用某些类型的 [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) 异常回调。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-327">Logically extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to enable or disable certain types of [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
 <span data-ttu-id="ffcaa-328">[ICorDebugProcessEnum 接口](icordebugprocessenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-328">[ICorDebugProcessEnum Interface](icordebugprocessenum-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-329">实现 `ICorDebugEnum` 方法，并枚举 `ICorDebugProcess` 数组。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-329">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugProcess` arrays.</span></span>  
  
 <span data-ttu-id="ffcaa-330">[ICorDebugReferenceValue 接口](icordebugreferencevalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-330">[ICorDebugReferenceValue Interface](icordebugreferencevalue-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-331">`ICorDebugValue` 的子类，它支持引用类型。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-331">A subclass of `ICorDebugValue` that supports reference types.</span></span>  
  
 <span data-ttu-id="ffcaa-332">[ICorDebugRegisterSet 接口](icordebugregisterset-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-332">[ICorDebugRegisterSet Interface](icordebugregisterset-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-333">表示在当前正在执行代码的计算机上可用的寄存器组。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-333">Represents the set of registers available on the machine that is currently executing code.</span></span>  
  
 <span data-ttu-id="ffcaa-334">[ICorDebugRegisterSet2 接口](icordebugregisterset2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-334">[ICorDebugRegisterSet2 Interface](icordebugregisterset2-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-335">为具有 64 个以上寄存器的硬件平台扩展 `ICorDebugRegisterSet` 的功能。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-335">Extends the capabilities of `ICorDebugRegisterSet` for hardware platforms that have more than 64 registers.</span></span>  
  
 <span data-ttu-id="ffcaa-336">[ICorDebugRemote 接口](icordebugremote-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-336">[ICorDebugRemote Interface](icordebugremote-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-337">提供启动托管调试器或将其附加到远程目标进程的能力。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-337">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
 <span data-ttu-id="ffcaa-338">[ICorDebugRemoteTarget 接口](icordebugremotetarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-338">[ICorDebugRemoteTarget Interface](icordebugremotetarget-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-339">提供使你能够在 CLR 环境中调试基于 Silverlight 的应用程序的方法。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-339">Provides methods that enable you to debug Silverlight-based applications in the CLR environment.</span></span>  
  
 <span data-ttu-id="ffcaa-340">[ICorDebugRuntimeUnwindableFrame 接口](icordebugruntimeunwindableframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-340">[ICorDebugRuntimeUnwindableFrame Interface](icordebugruntimeunwindableframe-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-341">提供对非托管方法的支持，这些方法需要公共语言运行时 (CLR) 来展开帧。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-341">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
 <span data-ttu-id="ffcaa-342">[ICorDebugStackWalk 接口](icordebugstackwalk-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-342">[ICorDebugStackWalk Interface](icordebugstackwalk-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-343">提供用于获取线程堆栈上的托管方法或帧的方法。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-343">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
 <span data-ttu-id="ffcaa-344">[ICorDebugStaticFieldSymbol 接口](icordebugstaticfieldsymbol-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-344">[ICorDebugStaticFieldSymbol Interface](icordebugstaticfieldsymbol-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-345">表示某个静态字段的调试符号信息。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-345">Represents the debug symbol information for a static field.</span></span> <span data-ttu-id="ffcaa-346">**仅在 .NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="ffcaa-346">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="ffcaa-347">[ICorDebugStepper 接口](icordebugstepper-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-347">[ICorDebugStepper Interface](icordebugstepper-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-348">表示在代码执行过程中由调试器执行的一个步骤。此步骤作为命令颁发和完成之间的标识符使用，可以实现取消对某个步骤的执行。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-348">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
 <span data-ttu-id="ffcaa-349">[ICorDebugStepper2 接口](icordebugstepper2-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-349">[ICorDebugStepper2 Interface](icordebugstepper2-interface1.md)</span></span>\
 <span data-ttu-id="ffcaa-350">提供对“仅我的代码”(JMC) 调试的支持。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-350">Provides support for Just My Code (JMC) debugging.</span></span>  
  
 <span data-ttu-id="ffcaa-351">[ICorDebugStepperEnum 接口](icordebugstepperenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-351">[ICorDebugStepperEnum Interface](icordebugstepperenum-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-352">实现 `ICorDebugEnum` 方法，并枚举 `ICorDebugStepper` 数组。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-352">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugStepper` arrays.</span></span>  
  
 <span data-ttu-id="ffcaa-353">[ICorDebugStringValue 接口](icordebugstringvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-353">[ICorDebugStringValue Interface](icordebugstringvalue-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-354">应用于字符串值的 `ICorDebugHeapValue` 的子类。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-354">A subclass of `ICorDebugHeapValue` that applies to string values.</span></span>  
  
 <span data-ttu-id="ffcaa-355">[ICorDebugSymbolProvider 接口](icordebugsymbolprovider-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-355">[ICorDebugSymbolProvider Interface](icordebugsymbolprovider-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-356">提供可用于检索调试符号信息的方法。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-356">Provides methods that can be used to retrieve debug symbol information.</span></span> <span data-ttu-id="ffcaa-357">**仅在 .NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="ffcaa-357">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="ffcaa-358">[ICorDebugSymbolProvider2 接口](icordebugsymbolprovider2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-358">[ICorDebugSymbolProvider2 Interface](icordebugsymbolprovider2-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-359">以逻辑方式扩展 [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) 接口以检索其他调试符号信息。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-359">Logically extends the [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span> <span data-ttu-id="ffcaa-360">**仅在 .NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="ffcaa-360">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="ffcaa-361">[ICorDebugThread 接口](icordebugthread-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-361">[ICorDebugThread Interface](icordebugthread-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-362">表示进程中的线程。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-362">Represents a thread in a process.</span></span> <span data-ttu-id="ffcaa-363">`ICorDebugThread` 实例的生存期与它表示的线程的生存期相同。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-363">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
 <span data-ttu-id="ffcaa-364">[ICorDebugThread2 接口](icordebugthread2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-364">[ICorDebugThread2 Interface](icordebugthread2-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-365">用作 `ICorDebugThread` 的逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-365">Serves as a logical extension to `ICorDebugThread`.</span></span>  
  
 <span data-ttu-id="ffcaa-366">[ICorDebugThread3 接口](icordebugthread3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-366">[ICorDebugThread3 Interface](icordebugthread3-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-367">提供 [ICorDebugStackWalk](icordebugstackwalk-interface.md) 和相应接口的入口点。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-367">Provides the entry point to the [ICorDebugStackWalk](icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
 <span data-ttu-id="ffcaa-368">[ICorDebugThread4 接口](icordebugthread4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-368">[ICorDebugThread4 Interface](icordebugthread4-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-369">提供线程阻塞信息。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-369">Provides thread blocking information.</span></span>  
  
 <span data-ttu-id="ffcaa-370">[ICorDebugThreadEnum 接口](icordebugthreadenum-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-370">[ICorDebugThreadEnum Interface](icordebugthreadenum-interface1.md)</span></span>\
 <span data-ttu-id="ffcaa-371">实现 `ICorDebugEnum` 方法，并枚举 `ICorDebugThread` 数组。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-371">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugThread` arrays.</span></span>  
  
 <span data-ttu-id="ffcaa-372">[ICorDebugType 接口](icordebugtype-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-372">[ICorDebugType Interface](icordebugtype-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-373">表示基类型或复杂类型（即用户定义的类型）。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-373">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="ffcaa-374">如果该类型是泛型类型，则 `ICorDebugType` 表示未实例化的泛型类型。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-374">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
 <span data-ttu-id="ffcaa-375">[ICorDebugType2 接口](icordebugtype2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-375">[ICorDebugType2 Interface](icordebugtype2-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-376">扩展 [ICorDebugType](icordebugtype-interface.md) 接口以检索基类型或复杂 (用户定义的) 类型的类型标识符。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-376">Extends the [ICorDebugType](icordebugtype-interface.md) interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
 <span data-ttu-id="ffcaa-377">[ICorDebugTypeEnum 接口](icordebugtypeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-377">[ICorDebugTypeEnum Interface](icordebugtypeenum-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-378">实现 `ICorDebugEnum` 方法，并枚举 `ICorDebugType` 数组。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-378">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugType` arrays.</span></span>  
  
 <span data-ttu-id="ffcaa-379">[ICorDebugUnmanagedCallback 接口](icordebugunmanagedcallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-379">[ICorDebugUnmanagedCallback Interface](icordebugunmanagedcallback-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-380">提供与 CLR 没有直接关系的本机事件的通知。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-380">Provides notification of native events that are not directly related to the CLR.</span></span>  
  
 <span data-ttu-id="ffcaa-381">[ICorDebugValue](icordebugvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-381">[ICorDebugValue](icordebugvalue-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-382">表示正在调试的进程中的读取或写入值。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-382">Represents a read or write value in the process being debugged.</span></span>  
  
 <span data-ttu-id="ffcaa-383">[ICorDebugValue2](icordebugvalue2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-383">[ICorDebugValue2](icordebugvalue2-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-384">扩展 `ICorDebugValue` 以提供对 `ICorDebugType` 的支持。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-384">Extends `ICorDebugValue` to provide support for `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="ffcaa-385">[ICorDebugValue3 接口](icordebugvalue3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-385">[ICorDebugValue3 Interface](icordebugvalue3-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-386">扩展了 "ICorDebugValue" 和 "ICorDebugValue2" 接口，为大于 2 GB 的数组提供支持。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-386">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
 <span data-ttu-id="ffcaa-387">[ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-387">[ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-388">扩展 `ICorDebugBreakpoint` 以提供对特定值的访问。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-388">Extends `ICorDebugBreakpoint` to provide access to specific values.</span></span>  
  
 <span data-ttu-id="ffcaa-389">[ICorDebugValueEnum](icordebugvalueenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-389">[ICorDebugValueEnum](icordebugvalueenum-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-390">实现 `ICorDebugEnum` 方法，并枚举 `ICorDebugValue` 数组。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-390">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugValue` arrays.</span></span>  
  
 <span data-ttu-id="ffcaa-391">[ICorDebugVariableHome 接口](icordebugvariablehome-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-391">[ICorDebugVariableHome Interface](icordebugvariablehome-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-392">表示函数的局部变量或自变量。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-392">Represents a local variable or argument of a function.</span></span>  
  
 <span data-ttu-id="ffcaa-393">[ICorDebugVariableHomeEnum 接口](icordebugvariablehomeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-393">[ICorDebugVariableHomeEnum Interface](icordebugvariablehomeenum-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-394">提供对函数中的局部变量和参数的枚举器。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-394">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
 <span data-ttu-id="ffcaa-395">[ICorDebugVariableSymbol 接口](icordebugvariablesymbol-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-395">[ICorDebugVariableSymbol Interface](icordebugvariablesymbol-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-396">检索变量的调试符号信息。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-396">Retrieves the debug symbol information for a variable.</span></span> <span data-ttu-id="ffcaa-397">**仅在 .NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="ffcaa-397">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="ffcaa-398">[ICorDebugVirtualUnwinder 接口](icordebugvirtualunwinder-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-398">[ICorDebugVirtualUnwinder Interface](icordebugvirtualunwinder-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-399">提供帮助堆栈展开的方法。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-399">Provides methods to help in stack unwinding.</span></span> <span data-ttu-id="ffcaa-400">**仅在 .NET Native 上可用。**</span><span class="sxs-lookup"><span data-stu-id="ffcaa-400">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="ffcaa-401">[ICorPublish 接口](icorpublish-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-401">[ICorPublish Interface](icorpublish-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-402">用作发布进程的常规接口。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-402">Serves as the general interface for the publishing processes.</span></span>  
  
 <span data-ttu-id="ffcaa-403">[ICorPublishAppDomain 接口](icorpublishappdomain-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-403">[ICorPublishAppDomain Interface](icorpublishappdomain-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-404">表示并提供关于应用程序域的信息。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-404">Represents and provides information about an application domain.</span></span>  
  
 <span data-ttu-id="ffcaa-405">[ICorPublishAppDomainEnum 接口](icorpublishappdomainenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-405">[ICorPublishAppDomainEnum Interface](icorpublishappdomainenum-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-406">提供遍历进程中当前存在的 `ICorPublishAppDomain` 对象的集合的方法。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-406">Provides methods that traverse a collection of `ICorPublishAppDomain` objects that currently exist within a process.</span></span>  
  
 <span data-ttu-id="ffcaa-407">[ICorPublishEnum 接口](icorpublishenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-407">[ICorPublishEnum Interface](icorpublishenum-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-408">用作发布枚举器的抽象基。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-408">Serves as the abstract base for publishing enumerators.</span></span>  
  
 <span data-ttu-id="ffcaa-409">[ICorPublishProcess 接口](icorpublishprocess-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-409">[ICorPublishProcess Interface](icorpublishprocess-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-410">提供用于访问有关进程的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-410">Provides methods that access information about a process.</span></span>  
  
 <span data-ttu-id="ffcaa-411">[ICorPublishProcessEnum 接口](icorpublishprocessenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-411">[ICorPublishProcessEnum Interface](icorpublishprocessenum-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-412">提供遍历 `ICorPublishProcess` 对象的集合的方法。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-412">Provides methods that traverse a collection of `ICorPublishProcess` objects.</span></span>  

 <span data-ttu-id="ffcaa-413">[ISOSDacInterface 接口](isosdacinterface-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-413">[ISOSDacInterface Interface](isosdacinterface-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-414">提供用于访问中的数据的帮助器方法 `SOS` 。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-414">Provides helper methods to access data from `SOS`.</span></span>

 <span data-ttu-id="ffcaa-415">[IXCLRDataMethodDefinition 接口](ixclrdatamethoddefinition-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-415">[IXCLRDataMethodDefinition Interface](ixclrdatamethoddefinition-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-416">提供用于查询有关方法定义的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-416">Provides methods for querying information about a method definition.</span></span>

 <span data-ttu-id="ffcaa-417">[IXCLRDataMethodInstance 接口](ixclrdatamethodinstance-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-417">[IXCLRDataMethodInstance Interface](ixclrdatamethodinstance-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-418">提供用于查询有关方法实例的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-418">Provides methods for querying information about a method instance.</span></span>

 <span data-ttu-id="ffcaa-419">[IXCLRDataModule 接口](ixclrdatamodule-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-419">[IXCLRDataModule Interface](ixclrdatamodule-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-420">提供用于查询有关已加载模块的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-420">Provides methods for querying information about a loaded module.</span></span>

 <span data-ttu-id="ffcaa-421">[IXCLRDataProcess 接口](ixclrdataprocess-interface.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-421">[IXCLRDataProcess Interface](ixclrdataprocess-interface.md)</span></span>\
 <span data-ttu-id="ffcaa-422">提供用于查询有关进程的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="ffcaa-422">Provides methods for querying information about a process.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="ffcaa-423">相关章节</span><span class="sxs-lookup"><span data-stu-id="ffcaa-423">Related Sections</span></span>  

 <span data-ttu-id="ffcaa-424">[调试组件类](debugging-coclasses.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-424">[Debugging Coclasses](debugging-coclasses.md)</span></span>\
 <span data-ttu-id="ffcaa-425">[调试全局静态函数](debugging-global-static-functions.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-425">[Debugging Global Static Functions](debugging-global-static-functions.md)</span></span>\
 <span data-ttu-id="ffcaa-426">[调试枚举](debugging-enumerations.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-426">[Debugging Enumerations](debugging-enumerations.md)</span></span>\
 <span data-ttu-id="ffcaa-427">[调试结构](debugging-structures.md)</span><span class="sxs-lookup"><span data-stu-id="ffcaa-427">[Debugging Structures](debugging-structures.md)</span></span>\
