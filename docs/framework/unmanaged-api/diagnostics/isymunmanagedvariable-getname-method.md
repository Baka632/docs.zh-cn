---
title: ISymUnmanagedVariable::GetName 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetName
helpviewer_keywords:
- GetName method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetName method [.NET Framework debugging]
ms.assetid: eedf1ef0-9d4a-4847-a201-4e99572dfe5e
topic_type:
- apiref
ms.openlocfilehash: f9da3ca8684da3bbc87146b3b52effdc4f91393d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726881"
---
# <a name="isymunmanagedvariablegetname-method"></a><span data-ttu-id="80b0d-102">ISymUnmanagedVariable::GetName 方法</span><span class="sxs-lookup"><span data-stu-id="80b0d-102">ISymUnmanagedVariable::GetName Method</span></span>

<span data-ttu-id="80b0d-103">获取此变量的名称。</span><span class="sxs-lookup"><span data-stu-id="80b0d-103">Gets the name of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80b0d-104">语法</span><span class="sxs-lookup"><span data-stu-id="80b0d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80b0d-105">参数</span><span class="sxs-lookup"><span data-stu-id="80b0d-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="80b0d-106">中参数指向的缓冲区的长度 `pcchName` 。</span><span class="sxs-lookup"><span data-stu-id="80b0d-106">[in] The length of the buffer that the `pcchName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="80b0d-107">弄指向的指针， `ULONG32` 该指针接收包含名称（包括 null 终止）所需的缓冲区的大小（以字符数表示）。</span><span class="sxs-lookup"><span data-stu-id="80b0d-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="80b0d-108">弄存储名称的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="80b0d-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80b0d-109">返回值</span><span class="sxs-lookup"><span data-stu-id="80b0d-109">Return Value</span></span>  

 <span data-ttu-id="80b0d-110">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="80b0d-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80b0d-111">要求</span><span class="sxs-lookup"><span data-stu-id="80b0d-111">Requirements</span></span>  

 <span data-ttu-id="80b0d-112">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="80b0d-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80b0d-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="80b0d-113">See also</span></span>

- [<span data-ttu-id="80b0d-114">ISymUnmanagedVariable 接口</span><span class="sxs-lookup"><span data-stu-id="80b0d-114">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
