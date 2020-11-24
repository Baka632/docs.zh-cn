---
title: ISymUnmanagedReader::GetMethod 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethod
helpviewer_keywords:
- GetMethod method, ISymUnmanagedReader interface [.NET Framework debugging]
- ISymUnmanagedReader::GetMethod method [.NET Framework debugging]
ms.assetid: ae6cfb29-bc2c-4606-af86-1d32ebd31020
topic_type:
- apiref
ms.openlocfilehash: 3f0d0e060bba832080dd8fbfab62f3115fec0aab
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689636"
---
# <a name="isymunmanagedreadergetmethod-method"></a><span data-ttu-id="be0c0-102">ISymUnmanagedReader::GetMethod 方法</span><span class="sxs-lookup"><span data-stu-id="be0c0-102">ISymUnmanagedReader::GetMethod Method</span></span>

<span data-ttu-id="be0c0-103">在给定方法标记的情况下，获取符号读取器方法。</span><span class="sxs-lookup"><span data-stu-id="be0c0-103">Gets a symbol reader method, given a method token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be0c0-104">语法</span><span class="sxs-lookup"><span data-stu-id="be0c0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethod (  
    [in]  mdMethodDef  token,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be0c0-105">参数</span><span class="sxs-lookup"><span data-stu-id="be0c0-105">Parameters</span></span>  

 `token`  
 <span data-ttu-id="be0c0-106">中方法标记。</span><span class="sxs-lookup"><span data-stu-id="be0c0-106">[in] The method token.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="be0c0-107">弄指向返回的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="be0c0-107">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="be0c0-108">返回值</span><span class="sxs-lookup"><span data-stu-id="be0c0-108">Return Value</span></span>  

 <span data-ttu-id="be0c0-109">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="be0c0-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be0c0-110">要求</span><span class="sxs-lookup"><span data-stu-id="be0c0-110">Requirements</span></span>  

 <span data-ttu-id="be0c0-111">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="be0c0-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be0c0-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="be0c0-112">See also</span></span>

- [<span data-ttu-id="be0c0-113">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="be0c0-113">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
