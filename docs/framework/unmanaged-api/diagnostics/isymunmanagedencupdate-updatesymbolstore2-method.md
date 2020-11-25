---
title: ISymUnmanagedENCUpdate::UpdateSymbolStore2 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.UpdateSymbolStore2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2
helpviewer_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2 method [.NET Framework debugging]
- UpdateSymbolStore2 method [.NET Framework debugging]
ms.assetid: 35588317-6184-485c-ab41-4b15fc1765d9
topic_type:
- apiref
ms.openlocfilehash: c68cf632b789a523b19cc78d8d919c2278b1befa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699568"
---
# <a name="isymunmanagedencupdateupdatesymbolstore2-method"></a><span data-ttu-id="d2174-102">ISymUnmanagedENCUpdate::UpdateSymbolStore2 方法</span><span class="sxs-lookup"><span data-stu-id="d2174-102">ISymUnmanagedENCUpdate::UpdateSymbolStore2 Method</span></span>

<span data-ttu-id="d2174-103">如果行信息满足要求，则允许编译器省略未从程序数据库 (PDB) 流中修改的函数。</span><span class="sxs-lookup"><span data-stu-id="d2174-103">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided the line information meets the requirements.</span></span> <span data-ttu-id="d2174-104">可以通过旧的 PDB 行信息和函数中所有行的一个增量来确定正确的行信息。</span><span class="sxs-lookup"><span data-stu-id="d2174-104">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2174-105">语法</span><span class="sxs-lookup"><span data-stu-id="d2174-105">Syntax</span></span>  
  
```cpp  
HRESULT UpdateSymbolStore2(  
    [in]  IStream      *pIStream,  
    [in]  SYMLINEDELTA* pDeltaLines,  
    [in]  ULONG         cDeltaLines);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2174-106">参数</span><span class="sxs-lookup"><span data-stu-id="d2174-106">Parameters</span></span>  

 `pIStream`  
 <span data-ttu-id="d2174-107">中一个指针，指向包含行信息的 [IStream](/windows/desktop/api/objidl/nn-objidl-istream) 。</span><span class="sxs-lookup"><span data-stu-id="d2174-107">[in] A pointer to an [IStream](/windows/desktop/api/objidl/nn-objidl-istream) that contains the line information.</span></span>  
  
 `pDeltaLines`  
 <span data-ttu-id="d2174-108">中指向 [SYMLINEDELTA](symlinedelta-structure.md) 结构的指针，该结构包含已更改的行。</span><span class="sxs-lookup"><span data-stu-id="d2174-108">[in] A pointer to a [SYMLINEDELTA](symlinedelta-structure.md) structure that contains the lines that have changed.</span></span>  
  
 `cDeltaLines`  
 <span data-ttu-id="d2174-109">中 `ULONG` ，它表示已更改的行数。</span><span class="sxs-lookup"><span data-stu-id="d2174-109">[in] A `ULONG` that represents the number of lines that have changed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d2174-110">返回值</span><span class="sxs-lookup"><span data-stu-id="d2174-110">Return Value</span></span>  

 <span data-ttu-id="d2174-111">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="d2174-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2174-112">要求</span><span class="sxs-lookup"><span data-stu-id="d2174-112">Requirements</span></span>  

 <span data-ttu-id="d2174-113">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="d2174-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2174-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d2174-114">See also</span></span>

- [<span data-ttu-id="d2174-115">ISymUnmanagedENCUpdate 接口</span><span class="sxs-lookup"><span data-stu-id="d2174-115">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)
