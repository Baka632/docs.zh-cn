---
title: 合成全局静态函数
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged global static functions [.NET Framework], fusion
- fusion global static functions [.NET Framework]
- global static functions [.NET Framework fusion]
ms.assetid: 229b2188-9168-4b44-a987-e1f515494688
ms.openlocfilehash: 691fd50e05cadd3f82196fc6ba5df9bb84a66faa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688739"
---
# <a name="fusion-global-static-functions"></a><span data-ttu-id="8d2bb-102">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="8d2bb-102">Fusion Global Static Functions</span></span>

<span data-ttu-id="8d2bb-103">本部分介绍了合成 API 使用的非托管全局静态函数。</span><span class="sxs-lookup"><span data-stu-id="8d2bb-103">This section describes the unmanaged global static functions that the fusion API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8d2bb-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="8d2bb-104">In This Section</span></span>  

 [<span data-ttu-id="8d2bb-105">ClearDownloadCache 函数</span><span class="sxs-lookup"><span data-stu-id="8d2bb-105">ClearDownloadCache Function</span></span>](cleardownloadcache-function.md)  
 <span data-ttu-id="8d2bb-106">清除已下载程序集的全局程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="8d2bb-106">Clears the global assembly cache of downloaded assemblies.</span></span>  
  
 [<span data-ttu-id="8d2bb-107">CompareAssemblyIdentity 函数</span><span class="sxs-lookup"><span data-stu-id="8d2bb-107">CompareAssemblyIdentity Function</span></span>](compareassemblyidentity-function.md)  
 <span data-ttu-id="8d2bb-108">比较两个程序集标识以确定它们是否等效。</span><span class="sxs-lookup"><span data-stu-id="8d2bb-108">Compares two assembly identities to determine whether they are equivalent.</span></span>  
  
 [<span data-ttu-id="8d2bb-109">CreateApplicationContext 函数</span><span class="sxs-lookup"><span data-stu-id="8d2bb-109">CreateApplicationContext Function</span></span>](createapplicationcontext-function.md)  
 <span data-ttu-id="8d2bb-110">仅限内部。</span><span class="sxs-lookup"><span data-stu-id="8d2bb-110">Internal only.</span></span> <span data-ttu-id="8d2bb-111"> (此函数支持 .NET Framework 基础结构，不应在代码中直接使用。 ) </span><span class="sxs-lookup"><span data-stu-id="8d2bb-111">(This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="8d2bb-112">CreateAssemblyCache 函数</span><span class="sxs-lookup"><span data-stu-id="8d2bb-112">CreateAssemblyCache Function</span></span>](createassemblycache-function.md)  
 <span data-ttu-id="8d2bb-113">获取一个指针，该指针指向表示全局程序集缓存的新 [IAssemblyCache](iassemblycache-interface.md) 实例。</span><span class="sxs-lookup"><span data-stu-id="8d2bb-113">Gets a pointer to a new [IAssemblyCache](iassemblycache-interface.md) instance that represents the global assembly cache.</span></span>  
  
 [<span data-ttu-id="8d2bb-114">CreateAssemblyEnum 函数</span><span class="sxs-lookup"><span data-stu-id="8d2bb-114">CreateAssemblyEnum Function</span></span>](createassemblyenum-function.md)  
 <span data-ttu-id="8d2bb-115">获取一个指针，该指针指向表示存在于指定程序集中的对象的列表的 [IAssemblyEnum](iassemblyenum-interface.md) 实例。</span><span class="sxs-lookup"><span data-stu-id="8d2bb-115">Gets a pointer to an [IAssemblyEnum](iassemblyenum-interface.md) instance that represents a list of objects that exist in the specified assembly.</span></span>  
  
 [<span data-ttu-id="8d2bb-116">CreateAssemblyNameObject 函数</span><span class="sxs-lookup"><span data-stu-id="8d2bb-116">CreateAssemblyNameObject Function</span></span>](createassemblynameobject-function.md)  
 <span data-ttu-id="8d2bb-117">获取一个指针，该指针指向表示具有指定名称的程序集的唯一标识的 [IAssemblyName](iassemblyname-interface.md) 实例。</span><span class="sxs-lookup"><span data-stu-id="8d2bb-117">Gets a pointer to an [IAssemblyName](iassemblyname-interface.md) instance that represents the unique identity of the assembly with the specified name.</span></span>  
  
 [<span data-ttu-id="8d2bb-118">CreateHistoryReader 函数</span><span class="sxs-lookup"><span data-stu-id="8d2bb-118">CreateHistoryReader Function</span></span>](createhistoryreader-function.md)  
 <span data-ttu-id="8d2bb-119">为指定的文件创建历史记录读取器。</span><span class="sxs-lookup"><span data-stu-id="8d2bb-119">Creates a history reader for the specified file.</span></span>  
  
 [<span data-ttu-id="8d2bb-120">CreateInstallReferenceEnum 函数</span><span class="sxs-lookup"><span data-stu-id="8d2bb-120">CreateInstallReferenceEnum Function</span></span>](createinstallreferenceenum-function.md)  
 <span data-ttu-id="8d2bb-121">获取一个指针，该指针指向表示应用程序对指定程序集的引用列表的 [IInstallReferenceEnum](iinstallreferenceenum-interface.md) 实例。</span><span class="sxs-lookup"><span data-stu-id="8d2bb-121">Gets a pointer to an [IInstallReferenceEnum](iinstallreferenceenum-interface.md) instance that represents a list of an application's references to the specified assembly.</span></span>  
  
 [<span data-ttu-id="8d2bb-122">GetAppIdAuthority 函数</span><span class="sxs-lookup"><span data-stu-id="8d2bb-122">GetAppIdAuthority Function</span></span>](getappidauthority-function.md)  
 <span data-ttu-id="8d2bb-123">获取一个指针，该指针指向管理应用程序标识和引用的密钥的 [IAppIdAuthority](iappidauthority-interface.md) 实例。</span><span class="sxs-lookup"><span data-stu-id="8d2bb-123">Gets a pointer to an [IAppIdAuthority](iappidauthority-interface.md) instance that manages keys for application identities and references.</span></span>  
  
 [<span data-ttu-id="8d2bb-124">GetAssemblyIdentityFromFile 函数</span><span class="sxs-lookup"><span data-stu-id="8d2bb-124">GetAssemblyIdentityFromFile Function</span></span>](getassemblyidentityfromfile-function.md)  
 <span data-ttu-id="8d2bb-125">获取一个指针，该指针指向在 `IUnknown` `IID` 指定文件路径的程序集中具有指定的对象。</span><span class="sxs-lookup"><span data-stu-id="8d2bb-125">Gets a pointer to an `IUnknown` object with the specified `IID` in the assembly at the specified file path.</span></span>  
  
 [<span data-ttu-id="8d2bb-126">GetCachePath 函数</span><span class="sxs-lookup"><span data-stu-id="8d2bb-126">GetCachePath Function</span></span>](getcachepath-function.md)  
 <span data-ttu-id="8d2bb-127">使用指定的标志获取缓存的程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="8d2bb-127">Gets the path to the cached assembly, using the specified flags.</span></span>  
  
 [<span data-ttu-id="8d2bb-128">GetHistoryFileDirectory 函数</span><span class="sxs-lookup"><span data-stu-id="8d2bb-128">GetHistoryFileDirectory Function</span></span>](gethistoryfiledirectory-function.md)  
 <span data-ttu-id="8d2bb-129">检索应用程序历史记录目录的路径。</span><span class="sxs-lookup"><span data-stu-id="8d2bb-129">Retrieves the path of the application history directory.</span></span>  
  
 [<span data-ttu-id="8d2bb-130">GetIdentityAuthority 函数</span><span class="sxs-lookup"><span data-stu-id="8d2bb-130">GetIdentityAuthority Function</span></span>](getidentityauthority-function.md)  
 <span data-ttu-id="8d2bb-131">获取一个指针，该指针指向管理代码对象的键的 [IIdentityAuthority](iidentityauthority-interface.md) 实例。</span><span class="sxs-lookup"><span data-stu-id="8d2bb-131">Gets a pointer to an [IIdentityAuthority](iidentityauthority-interface.md) instance that manages keys for code objects.</span></span>  
  
 [<span data-ttu-id="8d2bb-132">IsFrameworkAssembly 函数</span><span class="sxs-lookup"><span data-stu-id="8d2bb-132">IsFrameworkAssembly Function</span></span>](isframeworkassembly-function.md)  
 <span data-ttu-id="8d2bb-133">获取一个值，该值指示是否托管指定的程序集。</span><span class="sxs-lookup"><span data-stu-id="8d2bb-133">Gets a value that indicates whether the specified assembly is managed.</span></span>  
  
 [<span data-ttu-id="8d2bb-134">NukeDownloadedCache 函数</span><span class="sxs-lookup"><span data-stu-id="8d2bb-134">NukeDownloadedCache Function</span></span>](nukedownloadedcache-function.md)  
 <span data-ttu-id="8d2bb-135">删除公共语言运行时下载缓存。</span><span class="sxs-lookup"><span data-stu-id="8d2bb-135">Deletes the common language runtime download cache.</span></span>  
  
 [<span data-ttu-id="8d2bb-136">PreBindAssemblyEx 函数</span><span class="sxs-lookup"><span data-stu-id="8d2bb-136">PreBindAssemblyEx Function</span></span>](prebindassemblyex-function.md)  
 <span data-ttu-id="8d2bb-137">获取程序集的策略后显示名称。</span><span class="sxs-lookup"><span data-stu-id="8d2bb-137">Gets the post-policy display name for an assembly.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8d2bb-138">相关章节</span><span class="sxs-lookup"><span data-stu-id="8d2bb-138">Related Sections</span></span>  

 [<span data-ttu-id="8d2bb-139">合成接口</span><span class="sxs-lookup"><span data-stu-id="8d2bb-139">Fusion Interfaces</span></span>](fusion-interfaces.md)  
  
 [<span data-ttu-id="8d2bb-140">合成枚举</span><span class="sxs-lookup"><span data-stu-id="8d2bb-140">Fusion Enumerations</span></span>](fusion-enumerations.md)  
  
 [<span data-ttu-id="8d2bb-141">合成结构</span><span class="sxs-lookup"><span data-stu-id="8d2bb-141">Fusion Structures</span></span>](fusion-structures.md)  
  
 [<span data-ttu-id="8d2bb-142">全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="8d2bb-142">Global Assembly Cache</span></span>](../../app-domains/gac.md)
