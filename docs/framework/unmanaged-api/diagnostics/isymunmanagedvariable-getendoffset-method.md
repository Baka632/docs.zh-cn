---
title: ISymUnmanagedVariable::GetEndOffset 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedVariable::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: e5d777c5-d450-4c0f-999c-b3953ee22cfb
topic_type:
- apiref
ms.openlocfilehash: cf4179f839b62409d5b2185f3e11e8e732c29187
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721863"
---
# <a name="isymunmanagedvariablegetendoffset-method"></a><span data-ttu-id="3df36-102">ISymUnmanagedVariable::GetEndOffset 方法</span><span class="sxs-lookup"><span data-stu-id="3df36-102">ISymUnmanagedVariable::GetEndOffset Method</span></span>

<span data-ttu-id="3df36-103">获取此变量在其父级内的结束偏移量。</span><span class="sxs-lookup"><span data-stu-id="3df36-103">Gets the end offset of this variable within its parent.</span></span> <span data-ttu-id="3df36-104">如果这是一个作用域内的本地变量，则结束偏移量将在为该作用域定义的偏移量内。</span><span class="sxs-lookup"><span data-stu-id="3df36-104">If this is a local variable within a scope, the end offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3df36-105">语法</span><span class="sxs-lookup"><span data-stu-id="3df36-105">Syntax</span></span>  
  
```cpp  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3df36-106">参数</span><span class="sxs-lookup"><span data-stu-id="3df36-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="3df36-107">弄指向的指针 `ULONG32` ，该指针接收结束偏移量。</span><span class="sxs-lookup"><span data-stu-id="3df36-107">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3df36-108">返回值</span><span class="sxs-lookup"><span data-stu-id="3df36-108">Return Value</span></span>  

 <span data-ttu-id="3df36-109">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="3df36-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3df36-110">要求</span><span class="sxs-lookup"><span data-stu-id="3df36-110">Requirements</span></span>  

 <span data-ttu-id="3df36-111">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="3df36-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3df36-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3df36-112">See also</span></span>

- [<span data-ttu-id="3df36-113">ISymUnmanagedVariable 接口</span><span class="sxs-lookup"><span data-stu-id="3df36-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="3df36-114">GetStartOffset 方法</span><span class="sxs-lookup"><span data-stu-id="3df36-114">GetStartOffset Method</span></span>](isymunmanagedvariable-getstartoffset-method.md)
