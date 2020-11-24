---
title: ISymUnmanagedWriter5::OpenMapTokensToSourceSpans 方法
ms.date: 03/30/2017
ms.assetid: 93ad2517-b0dc-464c-8688-a58a30eda18d
ms.openlocfilehash: 95976e2f331252c88eab717e184abc284842e3b3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683259"
---
# <a name="isymunmanagedwriter5openmaptokenstosourcespans-method"></a><span data-ttu-id="ed207-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans 方法</span><span class="sxs-lookup"><span data-stu-id="ed207-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans Method</span></span>

<span data-ttu-id="ed207-103">打开一个特殊的自定义数据部分，将令牌到源范围的映射信息发送到。</span><span class="sxs-lookup"><span data-stu-id="ed207-103">Open a special custom data section to emit token-to-source span mapping information into.</span></span> <span data-ttu-id="ed207-104">如果方法已打开（或相反），则打开此节是错误的。</span><span class="sxs-lookup"><span data-stu-id="ed207-104">Opening this section when a method is already open, or vice versa, is an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed207-105">语法</span><span class="sxs-lookup"><span data-stu-id="ed207-105">Syntax</span></span>  
  
```idl  
HRESULT OpenMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ed207-106">返回值</span><span class="sxs-lookup"><span data-stu-id="ed207-106">Return Value</span></span>  

 <span data-ttu-id="ed207-107">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="ed207-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed207-108">要求</span><span class="sxs-lookup"><span data-stu-id="ed207-108">Requirements</span></span>  

 <span data-ttu-id="ed207-109">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="ed207-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed207-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed207-110">See also</span></span>

- [<span data-ttu-id="ed207-111">ISymUnmanagedWriter5 接口</span><span class="sxs-lookup"><span data-stu-id="ed207-111">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)
