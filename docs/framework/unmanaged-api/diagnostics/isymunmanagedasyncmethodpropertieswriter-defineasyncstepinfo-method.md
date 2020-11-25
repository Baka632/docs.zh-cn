---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo 方法
ms.date: 03/30/2017
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
ms.openlocfilehash: f8c77e44183fd92704aa91ca1cfd7e3fa68aa27f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719614"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="38ea1-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo 方法</span><span class="sxs-lookup"><span data-stu-id="38ea1-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>

<span data-ttu-id="38ea1-103">在当前方法中定义一组异步等待操作。</span><span class="sxs-lookup"><span data-stu-id="38ea1-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="38ea1-104">每个 yield 偏移均与 await 的返回指令匹配，确定潜在的收益率。</span><span class="sxs-lookup"><span data-stu-id="38ea1-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="38ea1-105">每个 `breakpointMethod` / `breakpointOffset` 对都告诉我们异步操作将恢复到的位置，这可能在不同的方法中。</span><span class="sxs-lookup"><span data-stu-id="38ea1-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38ea1-106">语法</span><span class="sxs-lookup"><span data-stu-id="38ea1-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38ea1-107">参数</span><span class="sxs-lookup"><span data-stu-id="38ea1-107">Parameters</span></span>  
  
|<span data-ttu-id="38ea1-108">参数</span><span class="sxs-lookup"><span data-stu-id="38ea1-108">Parameter</span></span>|<span data-ttu-id="38ea1-109">说明</span><span class="sxs-lookup"><span data-stu-id="38ea1-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="38ea1-110">返回值</span><span class="sxs-lookup"><span data-stu-id="38ea1-110">Return Value</span></span>  

 <span data-ttu-id="38ea1-111">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="38ea1-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38ea1-112">要求</span><span class="sxs-lookup"><span data-stu-id="38ea1-112">Requirements</span></span>  

 <span data-ttu-id="38ea1-113">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="38ea1-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38ea1-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38ea1-114">See also</span></span>

- [<span data-ttu-id="38ea1-115">ISymUnmanagedAsyncMethodPropertiesWriter 接口</span><span class="sxs-lookup"><span data-stu-id="38ea1-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)
