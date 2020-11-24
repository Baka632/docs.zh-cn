---
title: CreateApplicationContext 函数
ms.date: 03/30/2017
api_name:
- CreateApplicationContext
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- CreateApplicationContext
helpviewer_keywords:
- CreateApplicationContext function [.NET Framework fusion]
ms.assetid: 7bf8a141-b2c0-4058-9885-1cef7dcaa811
topic_type:
- apiref
ms.openlocfilehash: 9418be85f5b72bac8eed7f5ea4af4fc42439b01f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683221"
---
# <a name="createapplicationcontext-function"></a><span data-ttu-id="a90b9-102">CreateApplicationContext 函数</span><span class="sxs-lookup"><span data-stu-id="a90b9-102">CreateApplicationContext Function</span></span>

<span data-ttu-id="a90b9-103">此函数支持 .NET Framework 基础结构，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="a90b9-103">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a90b9-104">语法</span><span class="sxs-lookup"><span data-stu-id="a90b9-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateApplicationContext (  
    [in]  IAssemblyName  *pName,  
    [out] LPPAPPLICATIONCONTEXT  *ppCtx  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="a90b9-105">参数</span><span class="sxs-lookup"><span data-stu-id="a90b9-105">Parameters</span></span>  

 `pName`  
 <span data-ttu-id="a90b9-106">中指向友好名称的指针。</span><span class="sxs-lookup"><span data-stu-id="a90b9-106">[in] A pointer to a friendly name.</span></span>  
  
 `ppCtx`  
 <span data-ttu-id="a90b9-107">弄指向应用程序上下文的指针。</span><span class="sxs-lookup"><span data-stu-id="a90b9-107">[out] A pointer to an application context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a90b9-108">要求</span><span class="sxs-lookup"><span data-stu-id="a90b9-108">Requirements</span></span>  

 <span data-ttu-id="a90b9-109">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a90b9-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a90b9-110">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="a90b9-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="a90b9-111">**库：** 作为中的资源包含 Fusion.dll</span><span class="sxs-lookup"><span data-stu-id="a90b9-111">**Library:** Included as a resource in Fusion.dll</span></span>  
  
 <span data-ttu-id="a90b9-112">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a90b9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a90b9-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a90b9-113">See also</span></span>

- [<span data-ttu-id="a90b9-114">IAssemblyCache 接口</span><span class="sxs-lookup"><span data-stu-id="a90b9-114">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
- [<span data-ttu-id="a90b9-115">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="a90b9-115">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
- [<span data-ttu-id="a90b9-116">全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="a90b9-116">Global Assembly Cache</span></span>](../../app-domains/gac.md)
