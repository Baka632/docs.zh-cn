---
title: 如何：加载和卸载程序集
description: CLR 会自动加载程序引用的 .NET 程序集。 你还可以将特定程序集动态加载到当前应用程序域。
ms.date: 08/19/2019
ms.assetid: 6a4f490f-3576-471f-9533-003737cad4a3
ms.openlocfilehash: fe1a5fe63361620f8ab99ec8469169ed2213c0ee
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731483"
---
# <a name="how-to-load-and-unload-assemblies"></a><span data-ttu-id="c4c34-104">如何：加载和卸载程序集</span><span class="sxs-lookup"><span data-stu-id="c4c34-104">How to: Load and unload assemblies</span></span>

<span data-ttu-id="c4c34-105">公共语言运行时会自动加载程序所引用的程序集，但也可以将特定的程序集动态加载到当前的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="c4c34-105">The assemblies referenced by your program will automatically be loaded by the common language runtime, but it is also possible to dynamically load specific assemblies into the current application domain.</span></span> <span data-ttu-id="c4c34-106">有关详细信息，请参阅[如何：将程序集加载到应用程序域中](../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)。</span><span class="sxs-lookup"><span data-stu-id="c4c34-106">For more information, see [How to: Load assemblies into an application domain](../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span></span>

<span data-ttu-id="c4c34-107">在 .NET Framework 中，只有在卸载完所有包含单个程序集的应用程序域之后，才能卸载此程序集。</span><span class="sxs-lookup"><span data-stu-id="c4c34-107">In .NET Framework, there is no way to unload an individual assembly without unloading all of the application domains that contain it.</span></span> <span data-ttu-id="c4c34-108">即使程序集不在范围之内，在卸载包含它的所有应用程序域之前，实际的程序集文件都将保持加载状态。</span><span class="sxs-lookup"><span data-stu-id="c4c34-108">Even if the assembly goes out of scope, the actual assembly file will remain loaded until all application domains that contain it are unloaded.</span></span> <span data-ttu-id="c4c34-109">在 .NET Core 中，<xref:System.Runtime.Loader.AssemblyLoadContext?displayProperty=nameWithType> 类处理程序集的卸载。</span><span class="sxs-lookup"><span data-stu-id="c4c34-109">In .NET Core, the <xref:System.Runtime.Loader.AssemblyLoadContext?displayProperty=nameWithType> class handles the unloading of assemblies.</span></span> <span data-ttu-id="c4c34-110">有关详细信息，请参阅[如何在 .NET Core 中使用和调试程序集可卸载性](unloadability.md)。</span><span class="sxs-lookup"><span data-stu-id="c4c34-110">For more information, see [How to use and debug assembly unloadability in .NET Core](unloadability.md).</span></span>

## <a name="load-and-unload-assemblies"></a><span data-ttu-id="c4c34-111">加载和卸载程序集</span><span class="sxs-lookup"><span data-stu-id="c4c34-111">Load and unload assemblies</span></span>

<span data-ttu-id="c4c34-112">要将程序集加载到应用程序域中，请使用 <xref:System.AppDomain> 和 <xref:System.Reflection.Assembly> 类中包含的几种加载方法中的一种。</span><span class="sxs-lookup"><span data-stu-id="c4c34-112">To load an assembly into an application domain, use one of the several load methods contained in the classes <xref:System.AppDomain> and <xref:System.Reflection.Assembly>.</span></span> <span data-ttu-id="c4c34-113">有关详细信息，请参阅[如何：将程序集加载到应用程序域中](../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)。</span><span class="sxs-lookup"><span data-stu-id="c4c34-113">For more information, see [How to: Load assemblies into an application domain](../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span></span> <span data-ttu-id="c4c34-114">请注意，.NET Core 仅支持单个应用程序域。</span><span class="sxs-lookup"><span data-stu-id="c4c34-114">Note that .NET Core supports only a single application domain.</span></span>

<span data-ttu-id="c4c34-115">若要在 .NET Framework 中卸载程序集，必须卸载包含它的所有应用程序域。</span><span class="sxs-lookup"><span data-stu-id="c4c34-115">To unload an assembly in the .NET Framework, you must unload all of the application domains that contain it.</span></span> <span data-ttu-id="c4c34-116">要卸载应用程序域，请使用 <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="c4c34-116">To unload an application domain, use the <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="c4c34-117">有关详细信息，请参阅[如何：卸载应用程序域](../../framework/app-domains/how-to-unload-an-application-domain.md)。</span><span class="sxs-lookup"><span data-stu-id="c4c34-117">For more information, see [How to: Unload an application domain](../../framework/app-domains/how-to-unload-an-application-domain.md).</span></span>

<span data-ttu-id="c4c34-118">如果想要卸载 .NET Framework 应用程序中的某些程序集而不是其他程序集，请考虑创建一个新的应用程序域，在此域中执行代码，然后卸载此应用程序域。</span><span class="sxs-lookup"><span data-stu-id="c4c34-118">If you want to unload some assemblies but not others in a .NET Framework application, consider creating a new application domain, executing the code inside that domain, and then unloading that application domain.</span></span> <span data-ttu-id="c4c34-119">有关详细信息，请参阅[如何：卸载应用程序域](../../framework/app-domains/how-to-unload-an-application-domain.md)。</span><span class="sxs-lookup"><span data-stu-id="c4c34-119">For more information, see [How to: Unload an application domain](../../framework/app-domains/how-to-unload-an-application-domain.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="c4c34-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="c4c34-120">See also</span></span>

- [<span data-ttu-id="c4c34-121">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="c4c34-121">C# programming guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="c4c34-122">编程概念 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c4c34-122">Programming concepts (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/index.md)
- [<span data-ttu-id="c4c34-123">.NET 中的程序集</span><span class="sxs-lookup"><span data-stu-id="c4c34-123">Assemblies in .NET</span></span>](index.md)
- [<span data-ttu-id="c4c34-124">如何：将程序集加载到应用程序域中</span><span class="sxs-lookup"><span data-stu-id="c4c34-124">How to: Load assemblies into an application domain</span></span>](../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)
