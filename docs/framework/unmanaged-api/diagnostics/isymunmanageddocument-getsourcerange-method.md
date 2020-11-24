---
title: ISymUnmanagedDocument::GetSourceRange 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetSourceRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetSourceRange
helpviewer_keywords:
- ISymUnmanagedDocument::GetSourceRange method [.NET Framework debugging]
- GetSourceRange method [.NET Framework debugging]
ms.assetid: 20fefee7-1040-41ba-93dc-bd42f68b90c2
topic_type:
- apiref
ms.openlocfilehash: f5d7df60a7b9c728b73fe6592226a8b6734b1e66
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95692145"
---
# <a name="isymunmanageddocumentgetsourcerange-method"></a><span data-ttu-id="620fc-102">ISymUnmanagedDocument::GetSourceRange 方法</span><span class="sxs-lookup"><span data-stu-id="620fc-102">ISymUnmanagedDocument::GetSourceRange Method</span></span>

<span data-ttu-id="620fc-103">将嵌入源的指定范围返回到给定缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="620fc-103">Returns the specified range of the embedded source into the given buffer.</span></span> <span data-ttu-id="620fc-104">缓冲区必须足够大才能容纳源。</span><span class="sxs-lookup"><span data-stu-id="620fc-104">The buffer must be large enough to hold the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="620fc-105">语法</span><span class="sxs-lookup"><span data-stu-id="620fc-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceRange(  
    [in]  ULONG32  startLine,  
    [in]  ULONG32  startColumn,  
    [in]  ULONG32  endLine,  
    [in]  ULONG32  endColumn,  
    [in]  ULONG32  cSourceBytes,  
    [out] ULONG32  *pcSourceBytes,  
    [out, size_is(cSourceBytes),  
        length_is(*pcSourceBytes)] BYTE source[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="620fc-106">参数</span><span class="sxs-lookup"><span data-stu-id="620fc-106">Parameters</span></span>  

 `startLine`  
 <span data-ttu-id="620fc-107">中当前文档中的起始行。</span><span class="sxs-lookup"><span data-stu-id="620fc-107">[in] The starting line in the current document.</span></span>  
  
 `startColumn`  
 <span data-ttu-id="620fc-108">中当前文档中的起始列。</span><span class="sxs-lookup"><span data-stu-id="620fc-108">[in] The starting column in the current document.</span></span>  
  
 `endLine`  
 <span data-ttu-id="620fc-109">中当前文档中的最后一行。</span><span class="sxs-lookup"><span data-stu-id="620fc-109">[in] The final line in the current document.</span></span>  
  
 `endColumn`  
 <span data-ttu-id="620fc-110">中当前文档中的最后一列。</span><span class="sxs-lookup"><span data-stu-id="620fc-110">[in] The final column in the current document.</span></span>  
  
 `cSourceBytes`  
 <span data-ttu-id="620fc-111">中源的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="620fc-111">[in] The size of the source, in bytes.</span></span>  
  
 `pcSourceBytes`  
 <span data-ttu-id="620fc-112">弄指向接收源大小的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="620fc-112">[out] A pointer to a variable that receives the source size.</span></span>  
  
 `source`  
 <span data-ttu-id="620fc-113">弄源文档的指定范围的大小和长度（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="620fc-113">[out] The size and length of the specified range of the source document, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="620fc-114">返回值</span><span class="sxs-lookup"><span data-stu-id="620fc-114">Return Value</span></span>  

 <span data-ttu-id="620fc-115">如果方法成功，则 S_OK。</span><span class="sxs-lookup"><span data-stu-id="620fc-115">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="620fc-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="620fc-116">See also</span></span>

- [<span data-ttu-id="620fc-117">ISymUnmanagedDocument 接口</span><span class="sxs-lookup"><span data-stu-id="620fc-117">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
