---
title: ISymUnmanagedDocument::HasEmbeddedSource 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.HasEmbeddedSource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::HasEmbeddedSource
helpviewer_keywords:
- HasEmbeddedSource method [.NET Framework debugging]
- ISymUnmanagedDocument::HasEmbeddedSource method [.NET Framework debugging]
ms.assetid: 385fc4d3-365c-4645-b7b0-6c4c5344b79f
topic_type:
- apiref
ms.openlocfilehash: 09bc0f87cd35f12a15566fb525c2ce42990ac69b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688193"
---
# <a name="isymunmanageddocumenthasembeddedsource-method"></a><span data-ttu-id="9622f-102">ISymUnmanagedDocument::HasEmbeddedSource 方法</span><span class="sxs-lookup"><span data-stu-id="9622f-102">ISymUnmanagedDocument::HasEmbeddedSource Method</span></span>

<span data-ttu-id="9622f-103">`true`如果文档在调试符号中嵌入了源，则返回; 否则返回 `false` 。</span><span class="sxs-lookup"><span data-stu-id="9622f-103">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9622f-104">语法</span><span class="sxs-lookup"><span data-stu-id="9622f-104">Syntax</span></span>  
  
```cpp  
HRESULT HasEmbeddedSource(  
   [out, retval]  BOOL  *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9622f-105">参数</span><span class="sxs-lookup"><span data-stu-id="9622f-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="9622f-106">弄指向一个变量的指针，该变量指示文档是否将源嵌入调试符号。</span><span class="sxs-lookup"><span data-stu-id="9622f-106">[out] A pointer to a variable that indicates whether the document has source embedded in the debugging symbols.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9622f-107">返回值</span><span class="sxs-lookup"><span data-stu-id="9622f-107">Return Value</span></span>  

 <span data-ttu-id="9622f-108">如果方法成功，则 S_OK。</span><span class="sxs-lookup"><span data-stu-id="9622f-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9622f-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9622f-109">See also</span></span>

- [<span data-ttu-id="9622f-110">ISymUnmanagedDocument 接口</span><span class="sxs-lookup"><span data-stu-id="9622f-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
