---
title: ISymUnmanagedWriter::Initialize 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Initialize
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Initialize
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: e0ebd793-3764-4df0-8f12-0e95f60b9eae
topic_type:
- apiref
ms.openlocfilehash: c702aa32e8c8d6d5c137f7968d1578715102180f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726856"
---
# <a name="isymunmanagedwriterinitialize-method"></a><span data-ttu-id="a094e-102">ISymUnmanagedWriter::Initialize 方法</span><span class="sxs-lookup"><span data-stu-id="a094e-102">ISymUnmanagedWriter::Initialize Method</span></span>

<span data-ttu-id="a094e-103">设置此编写器将与之关联的元数据发射器接口，并设置调试符号将写入的输出文件名。</span><span class="sxs-lookup"><span data-stu-id="a094e-103">Sets the metadata emitter interface with which this writer will be associated, and sets the output file name to which the debugging symbols will be written.</span></span>  
  
 <span data-ttu-id="a094e-104">此方法只能调用一次，并且必须在任何其他编写器方法之前调用此方法。</span><span class="sxs-lookup"><span data-stu-id="a094e-104">This method can be called only once, and it must be called before any other writer methods.</span></span> <span data-ttu-id="a094e-105">某些编写器可能需要文件名。</span><span class="sxs-lookup"><span data-stu-id="a094e-105">Some writers may require a file name.</span></span> <span data-ttu-id="a094e-106">但是，您始终可以将文件名传递给此方法，而不会对不使用文件名的编写器产生任何负面影响。</span><span class="sxs-lookup"><span data-stu-id="a094e-106">However, you can always pass a file name to this method without any negative effect on writers that do not use the file name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a094e-107">语法</span><span class="sxs-lookup"><span data-stu-id="a094e-107">Syntax</span></span>  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *filename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a094e-108">参数</span><span class="sxs-lookup"><span data-stu-id="a094e-108">Parameters</span></span>  

 `emitter`  
 <span data-ttu-id="a094e-109">中指向元数据发射器接口的指针。</span><span class="sxs-lookup"><span data-stu-id="a094e-109">[in] A pointer to the metadata emitter interface.</span></span>  
  
 `filename`  
 <span data-ttu-id="a094e-110">中向其中写入调试符号的文件名。</span><span class="sxs-lookup"><span data-stu-id="a094e-110">[in] The file name to which the debugging symbols are written.</span></span> <span data-ttu-id="a094e-111">如果为不使用文件名的编写器指定文件名，则忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="a094e-111">If a file name is specified for a writer that does not use file names, this parameter is ignored.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="a094e-112">中如果已指定，则符号编写器会将符号发送到给定的 <xref:System.Runtime.InteropServices.ComTypes.IStream> （而不是参数中指定的文件） `filename` 。</span><span class="sxs-lookup"><span data-stu-id="a094e-112">[in] If specified, the symbol writer will emit the symbols into the given <xref:System.Runtime.InteropServices.ComTypes.IStream> rather than to the file specified in the `filename` parameter.</span></span> <span data-ttu-id="a094e-113">`pIStream` 参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="a094e-113">The `pIStream` parameter is optional.</span></span>  
  
 `fFullBuild`  
 <span data-ttu-id="a094e-114">[in] `true` 如果这是完全重新生成，则为; `false` 如果这是增量编译，则为。</span><span class="sxs-lookup"><span data-stu-id="a094e-114">[in] `true` if this is a full rebuild; `false` if this is an incremental compilation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a094e-115">返回值</span><span class="sxs-lookup"><span data-stu-id="a094e-115">Return Value</span></span>  

 <span data-ttu-id="a094e-116">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="a094e-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a094e-117">要求</span><span class="sxs-lookup"><span data-stu-id="a094e-117">Requirements</span></span>  

 <span data-ttu-id="a094e-118">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="a094e-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a094e-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a094e-119">See also</span></span>

- [<span data-ttu-id="a094e-120">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="a094e-120">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="a094e-121">Initialize2 方法</span><span class="sxs-lookup"><span data-stu-id="a094e-121">Initialize2 Method</span></span>](isymunmanagedwriter-initialize2-method.md)
