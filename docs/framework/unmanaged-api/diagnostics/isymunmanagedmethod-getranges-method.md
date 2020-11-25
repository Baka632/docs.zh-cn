---
title: ISymUnmanagedMethod::GetRanges 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetRanges
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetRanges
helpviewer_keywords:
- ISymUnmanagedMethod::GetRanges method [.NET Framework debugging]
- GetRanges method [.NET Framework debugging]
ms.assetid: a85283d8-379c-417a-9736-ddeeef9bcf50
topic_type:
- apiref
ms.openlocfilehash: 8ed492b573215736c82ab6c231cc5f2e188ea013
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732146"
---
# <a name="isymunmanagedmethodgetranges-method"></a><span data-ttu-id="3830f-102">ISymUnmanagedMethod::GetRanges 方法</span><span class="sxs-lookup"><span data-stu-id="3830f-102">ISymUnmanagedMethod::GetRanges Method</span></span>

<span data-ttu-id="3830f-103">给定文档中的某个位置后，将返回与 Microsoft 中间语言 (MSIL 范围对应的起始和结束偏移量对的数组，) 该位置涵盖在此方法中。</span><span class="sxs-lookup"><span data-stu-id="3830f-103">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span> <span data-ttu-id="3830f-104">数组是整数数组，格式为 [开始、结束、启动、结束]。</span><span class="sxs-lookup"><span data-stu-id="3830f-104">The array is an array of integers and has the format [start, end, start, end].</span></span> <span data-ttu-id="3830f-105">范围对的数目是数组的长度除以2。</span><span class="sxs-lookup"><span data-stu-id="3830f-105">The number of range pairs is the length of the array divided by 2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3830f-106">语法</span><span class="sxs-lookup"><span data-stu-id="3830f-106">Syntax</span></span>  
  
```cpp  
HRESULT GetRanges(  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32                line,  
    [in]  ULONG32                column,  
    [in]  ULONG32                cRanges,  
    [out] ULONG32                *pcRanges,  
    [out, size_is(cRanges),  
        length_is(*pcRanges)] ULONG32 ranges[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3830f-107">参数</span><span class="sxs-lookup"><span data-stu-id="3830f-107">Parameters</span></span>  

 `document`  
 <span data-ttu-id="3830f-108">中为其请求偏移量的文档。</span><span class="sxs-lookup"><span data-stu-id="3830f-108">[in] The document for which the offset is requested.</span></span>  
  
 `line`  
 <span data-ttu-id="3830f-109">中与范围对应的文档行。</span><span class="sxs-lookup"><span data-stu-id="3830f-109">[in] The document line corresponding to the ranges.</span></span>  
  
 `column`  
 <span data-ttu-id="3830f-110">中与范围对应的文档列。</span><span class="sxs-lookup"><span data-stu-id="3830f-110">[in] The document column corresponding to the ranges.</span></span>  
  
 `cRanges`  
 <span data-ttu-id="3830f-111">[in] `ranges` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="3830f-111">[in] The size of the `ranges` array.</span></span>  
  
 `pcRanges`  
 <span data-ttu-id="3830f-112">弄指向的指针 `ULONG32` ，该指针接收包含范围所需的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="3830f-112">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the ranges.</span></span>  
  
 `ranges`  
 <span data-ttu-id="3830f-113">弄指向接收范围的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="3830f-113">[out] A pointer to the buffer that receives the ranges.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3830f-114">返回值</span><span class="sxs-lookup"><span data-stu-id="3830f-114">Return Value</span></span>  

 <span data-ttu-id="3830f-115">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="3830f-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3830f-116">要求</span><span class="sxs-lookup"><span data-stu-id="3830f-116">Requirements</span></span>  

 <span data-ttu-id="3830f-117">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="3830f-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3830f-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3830f-118">See also</span></span>

- [<span data-ttu-id="3830f-119">ISymUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="3830f-119">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
