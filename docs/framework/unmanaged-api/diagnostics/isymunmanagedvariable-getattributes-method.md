---
title: ISymUnmanagedVariable::GetAttributes 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAttributes
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAttributes
helpviewer_keywords:
- GetAttributes method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAttributes method [.NET Framework debugging]
ms.assetid: 80f168af-a6a6-4c8f-b9e6-8a82dc834ed5
topic_type:
- apiref
ms.openlocfilehash: 1142dbb83693f6104ba6e22e174ce02fb92997a6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726894"
---
# <a name="isymunmanagedvariablegetattributes-method"></a><span data-ttu-id="fc84f-102">ISymUnmanagedVariable::GetAttributes 方法</span><span class="sxs-lookup"><span data-stu-id="fc84f-102">ISymUnmanagedVariable::GetAttributes Method</span></span>

<span data-ttu-id="fc84f-103">获取此变量的特性标志。</span><span class="sxs-lookup"><span data-stu-id="fc84f-103">Gets the attribute flags for this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc84f-104">语法</span><span class="sxs-lookup"><span data-stu-id="fc84f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAttributes(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc84f-105">参数</span><span class="sxs-lookup"><span data-stu-id="fc84f-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="fc84f-106">弄指向接收特性的的指针 `ULONG32` 。</span><span class="sxs-lookup"><span data-stu-id="fc84f-106">[out] A pointer to a `ULONG32` that receives the attributes.</span></span> <span data-ttu-id="fc84f-107">返回的值将是 [CorSymVarFlag](corsymvarflag-enumeration.md) 枚举中定义的值之一。</span><span class="sxs-lookup"><span data-stu-id="fc84f-107">The returned value will be one of the values defined in the [CorSymVarFlag](corsymvarflag-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fc84f-108">返回值</span><span class="sxs-lookup"><span data-stu-id="fc84f-108">Return Value</span></span>  

 <span data-ttu-id="fc84f-109">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="fc84f-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc84f-110">要求</span><span class="sxs-lookup"><span data-stu-id="fc84f-110">Requirements</span></span>  

 <span data-ttu-id="fc84f-111">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="fc84f-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc84f-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fc84f-112">See also</span></span>

- [<span data-ttu-id="fc84f-113">ISymUnmanagedVariable 接口</span><span class="sxs-lookup"><span data-stu-id="fc84f-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
