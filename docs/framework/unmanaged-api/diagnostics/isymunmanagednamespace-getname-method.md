---
title: ISymUnmanagedNamespace::GetName 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetName
helpviewer_keywords:
- ISymUnmanagedNamespace::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 657bf91d-005a-4ea4-9298-04d1291c0bc3
topic_type:
- apiref
ms.openlocfilehash: eca1137fb607d64e8645de5b0afc7ca391eac763
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699256"
---
# <a name="isymunmanagednamespacegetname-method"></a><span data-ttu-id="3d87b-102">ISymUnmanagedNamespace::GetName 方法</span><span class="sxs-lookup"><span data-stu-id="3d87b-102">ISymUnmanagedNamespace::GetName Method</span></span>

<span data-ttu-id="3d87b-103">获取此命名空间的名称。</span><span class="sxs-lookup"><span data-stu-id="3d87b-103">Gets the name of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d87b-104">语法</span><span class="sxs-lookup"><span data-stu-id="3d87b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d87b-105">参数</span><span class="sxs-lookup"><span data-stu-id="3d87b-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="3d87b-106">中 `ULONG32` 指示缓冲区大小的 `szName` 。</span><span class="sxs-lookup"><span data-stu-id="3d87b-106">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="3d87b-107">弄指向的指针， `ULONG32` 该指针接收包含命名空间名称（包括 null 终止）所需的缓冲区大小（以字符数表示）。</span><span class="sxs-lookup"><span data-stu-id="3d87b-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespace name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="3d87b-108">弄指向包含命名空间名称的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="3d87b-108">[out] A pointer to a buffer that contains the namespace name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3d87b-109">返回值</span><span class="sxs-lookup"><span data-stu-id="3d87b-109">Return Value</span></span>  

 <span data-ttu-id="3d87b-110">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="3d87b-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d87b-111">要求</span><span class="sxs-lookup"><span data-stu-id="3d87b-111">Requirements</span></span>  

 <span data-ttu-id="3d87b-112">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="3d87b-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d87b-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3d87b-113">See also</span></span>

- [<span data-ttu-id="3d87b-114">ISymUnmanagedNamespace 接口</span><span class="sxs-lookup"><span data-stu-id="3d87b-114">ISymUnmanagedNamespace Interface</span></span>](isymunmanagednamespace-interface.md)
