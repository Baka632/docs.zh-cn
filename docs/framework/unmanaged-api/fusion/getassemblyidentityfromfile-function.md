---
title: GetAssemblyIdentityFromFile 函数
ms.date: 03/30/2017
api_name:
- GetAssemblyIdentityFromFile
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- COM
f1_keywords:
- GetAssemblyIdentityFromFile
helpviewer_keywords:
- GetAssemblyIdentityFromFile function [.NET Framework fusion]
ms.assetid: 2c32da53-76c7-4048-84d0-d05207333004
topic_type:
- apiref
ms.openlocfilehash: 9580dd3bc5a7279549e8deadac95d35a33da74f8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724476"
---
# <a name="getassemblyidentityfromfile-function"></a><span data-ttu-id="dd4f2-102">GetAssemblyIdentityFromFile 函数</span><span class="sxs-lookup"><span data-stu-id="dd4f2-102">GetAssemblyIdentityFromFile Function</span></span>

<span data-ttu-id="dd4f2-103">获取一个指针，该指针指向在 `IUnknown` `IID` 指定文件路径的程序集中具有指定的对象。</span><span class="sxs-lookup"><span data-stu-id="dd4f2-103">Gets a pointer to an `IUnknown` object with the specified `IID` in the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd4f2-104">语法</span><span class="sxs-lookup"><span data-stu-id="dd4f2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd4f2-105">参数</span><span class="sxs-lookup"><span data-stu-id="dd4f2-105">Parameters</span></span>  

 `pwzFilePath`  
 <span data-ttu-id="dd4f2-106">中请求的程序集的有效路径。</span><span class="sxs-lookup"><span data-stu-id="dd4f2-106">[in] A valid path to the requested assembly.</span></span>  
  
 `riid`  
 <span data-ttu-id="dd4f2-107">中 `IID` 要返回的接口的。</span><span class="sxs-lookup"><span data-stu-id="dd4f2-107">[in] The `IID` of the interface to return.</span></span>  
  
 `ppIdentity`  
 <span data-ttu-id="dd4f2-108">弄返回的接口指针。</span><span class="sxs-lookup"><span data-stu-id="dd4f2-108">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd4f2-109">要求</span><span class="sxs-lookup"><span data-stu-id="dd4f2-109">Requirements</span></span>  

 <span data-ttu-id="dd4f2-110">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dd4f2-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd4f2-111">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="dd4f2-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="dd4f2-112">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd4f2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd4f2-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dd4f2-113">See also</span></span>

- [<span data-ttu-id="dd4f2-114">IUnknown</span><span class="sxs-lookup"><span data-stu-id="dd4f2-114">IUnknown</span></span>](/cpp/atl/iunknown)
- [<span data-ttu-id="dd4f2-115">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="dd4f2-115">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
