---
title: ISymUnmanagedNamespace::GetNamespaces 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedNamespace::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 0ea9d9af-8709-4a46-872b-f54d9e840088
topic_type:
- apiref
ms.openlocfilehash: 8eef973c4c054b704b7c3f798e5dc1aa455dda96
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707765"
---
# <a name="isymunmanagednamespacegetnamespaces-method"></a><span data-ttu-id="7d5c1-102">ISymUnmanagedNamespace::GetNamespaces 方法</span><span class="sxs-lookup"><span data-stu-id="7d5c1-102">ISymUnmanagedNamespace::GetNamespaces Method</span></span>

<span data-ttu-id="7d5c1-103">获取此命名空间的子级。</span><span class="sxs-lookup"><span data-stu-id="7d5c1-103">Gets the children of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d5c1-104">语法</span><span class="sxs-lookup"><span data-stu-id="7d5c1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces), length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d5c1-105">参数</span><span class="sxs-lookup"><span data-stu-id="7d5c1-105">Parameters</span></span>  

 `cNameSpaces`  
 <span data-ttu-id="7d5c1-106">中 `ULONG32` 指示数组大小的 `namespaces` 。</span><span class="sxs-lookup"><span data-stu-id="7d5c1-106">[in] A `ULONG32` that indicates the size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="7d5c1-107">弄指向的指针， `ULONG32` 该指针接收包含命名空间所需的缓冲区大小（以字符数表示）。</span><span class="sxs-lookup"><span data-stu-id="7d5c1-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="7d5c1-108">弄指向包含命名空间的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="7d5c1-108">[out] A pointer to the buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7d5c1-109">返回值</span><span class="sxs-lookup"><span data-stu-id="7d5c1-109">Return Value</span></span>  

 <span data-ttu-id="7d5c1-110">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="7d5c1-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d5c1-111">要求</span><span class="sxs-lookup"><span data-stu-id="7d5c1-111">Requirements</span></span>  

 <span data-ttu-id="7d5c1-112">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="7d5c1-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d5c1-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d5c1-113">See also</span></span>

- [<span data-ttu-id="7d5c1-114">ISymUnmanagedNamespace 接口</span><span class="sxs-lookup"><span data-stu-id="7d5c1-114">ISymUnmanagedNamespace Interface</span></span>](isymunmanagednamespace-interface.md)
