---
title: ISymENCUnmanagedMethod::GetLineFromOffset 方法
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetLineFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetLineFromOffset
helpviewer_keywords:
- GetLineFromOffset method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetLineFromOffset method [.NET Framework debugging]
ms.assetid: cc09bad2-fb34-4d13-a521-6ec7b1a1d915
topic_type:
- apiref
ms.openlocfilehash: 196993df9058d3eb8167e0144255c5fe366c54f8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707355"
---
# <a name="isymencunmanagedmethodgetlinefromoffset-method"></a><span data-ttu-id="a80c2-102">ISymENCUnmanagedMethod::GetLineFromOffset 方法</span><span class="sxs-lookup"><span data-stu-id="a80c2-102">ISymENCUnmanagedMethod::GetLineFromOffset Method</span></span>

<span data-ttu-id="a80c2-103">获取与偏移量关联的行信息。</span><span class="sxs-lookup"><span data-stu-id="a80c2-103">Gets the line information associated with an offset.</span></span> <span data-ttu-id="a80c2-104">如果 offset 参数 (`dwOffset`) 不是序列点，则此方法将获取与上一个偏移量关联的行信息。</span><span class="sxs-lookup"><span data-stu-id="a80c2-104">If the offset parameter (`dwOffset`) is not a sequence point, this method gets the line information associated with the previous offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a80c2-105">语法</span><span class="sxs-lookup"><span data-stu-id="a80c2-105">Syntax</span></span>  
  
```cpp  
HRESULT GetLineFromOffset(  
     [in]  ULONG32   dwOffset,  
     [out] ULONG32*  pline,  
     [out] ULONG32*  pcolumn,  
     [out] ULONG32*  pendLine,  
     [out] ULONG32*  pendColumn,  
     [out] ULONG32*  pdwStartOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a80c2-106">参数</span><span class="sxs-lookup"><span data-stu-id="a80c2-106">Parameters</span></span>  

 `dwOffset`  
 <span data-ttu-id="a80c2-107">中一个 `ULONG32` 包含偏移量的。</span><span class="sxs-lookup"><span data-stu-id="a80c2-107">[in] A `ULONG32` that contains the offset.</span></span>  
  
 `pline`  
 <span data-ttu-id="a80c2-108">弄指向接收行的的指针 `ULONG32` 。</span><span class="sxs-lookup"><span data-stu-id="a80c2-108">[out] A pointer to a `ULONG32` that receives the line.</span></span>  
  
 `pcolumn`  
 <span data-ttu-id="a80c2-109">弄指向接收列的的指针 `ULONG32` 。</span><span class="sxs-lookup"><span data-stu-id="a80c2-109">[out] A pointer to a `ULONG32` that receives the column.</span></span>  
  
 `pendLine`  
 <span data-ttu-id="a80c2-110">弄指向 `ULONG32` 的指针，该指针接收结束行。</span><span class="sxs-lookup"><span data-stu-id="a80c2-110">[out] A pointer to a `ULONG32` that receives the end line.</span></span>  
  
 `pendColumn`  
 <span data-ttu-id="a80c2-111">弄指向的指针 `ULONG32` ，该指针接收结束列。</span><span class="sxs-lookup"><span data-stu-id="a80c2-111">[out] A pointer to a `ULONG32` that receives the end column.</span></span>  
  
 `pdwStartOffset`  
 <span data-ttu-id="a80c2-112">弄指向 `ULONG32` 的指针，该指针接收关联的序列点。</span><span class="sxs-lookup"><span data-stu-id="a80c2-112">[out] A pointer to a `ULONG32` that receives the associated sequence point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a80c2-113">返回值</span><span class="sxs-lookup"><span data-stu-id="a80c2-113">Return Value</span></span>  

 <span data-ttu-id="a80c2-114">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="a80c2-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a80c2-115">要求</span><span class="sxs-lookup"><span data-stu-id="a80c2-115">Requirements</span></span>  

 <span data-ttu-id="a80c2-116">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="a80c2-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a80c2-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a80c2-117">See also</span></span>

- [<span data-ttu-id="a80c2-118">ISymENCUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="a80c2-118">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)
