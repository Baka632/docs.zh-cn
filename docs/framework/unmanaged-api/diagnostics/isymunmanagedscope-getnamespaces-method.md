---
title: ISymUnmanagedScope::GetNamespaces 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetNamespaces
helpviewer_keywords:
- GetNamespaces method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetNamespaces method [.NET Framework debugging]
ms.assetid: c44b0440-04bd-460a-84fb-41afecf44503
topic_type:
- apiref
ms.openlocfilehash: 026ba35044bc7573dc54617dcade9cf3918a76ec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725919"
---
# <a name="isymunmanagedscopegetnamespaces-method"></a><span data-ttu-id="f1831-102">ISymUnmanagedScope::GetNamespaces 方法</span><span class="sxs-lookup"><span data-stu-id="f1831-102">ISymUnmanagedScope::GetNamespaces Method</span></span>

<span data-ttu-id="f1831-103">获取正在此范围内使用的命名空间。</span><span class="sxs-lookup"><span data-stu-id="f1831-103">Gets the namespaces that are being used within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1831-104">语法</span><span class="sxs-lookup"><span data-stu-id="f1831-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces),  
        length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1831-105">参数</span><span class="sxs-lookup"><span data-stu-id="f1831-105">Parameters</span></span>  

 `cNameSpaces`  
 <span data-ttu-id="f1831-106">[in] `namespaces` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="f1831-106">[in] The size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="f1831-107">弄指向的指针 `ULONG32` ，该指针接收包含命名空间所需的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="f1831-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="f1831-108">弄接收命名空间的数组。</span><span class="sxs-lookup"><span data-stu-id="f1831-108">[out] The array that receives the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f1831-109">返回值</span><span class="sxs-lookup"><span data-stu-id="f1831-109">Return Value</span></span>  

 <span data-ttu-id="f1831-110">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="f1831-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1831-111">要求</span><span class="sxs-lookup"><span data-stu-id="f1831-111">Requirements</span></span>  

 <span data-ttu-id="f1831-112">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="f1831-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1831-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f1831-113">See also</span></span>

- [<span data-ttu-id="f1831-114">ISymUnmanagedScope 接口</span><span class="sxs-lookup"><span data-stu-id="f1831-114">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
