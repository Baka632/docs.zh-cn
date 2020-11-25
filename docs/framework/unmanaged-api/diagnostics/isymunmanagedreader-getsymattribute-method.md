---
title: ISymUnmanagedReader::GetSymAttribute 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetSymAttribute
helpviewer_keywords:
- GetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymAttribute method [.NET Framework debugging]
ms.assetid: c675ce7e-76e7-45ff-8273-3b6489a2767c
topic_type:
- apiref
ms.openlocfilehash: aa3b742babe4a94a43e4e6168dea67c0a0245eb0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720576"
---
# <a name="isymunmanagedreadergetsymattribute-method"></a><span data-ttu-id="cde91-102">ISymUnmanagedReader::GetSymAttribute 方法</span><span class="sxs-lookup"><span data-stu-id="cde91-102">ISymUnmanagedReader::GetSymAttribute Method</span></span>

<span data-ttu-id="cde91-103">根据名称获取自定义属性。</span><span class="sxs-lookup"><span data-stu-id="cde91-103">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="cde91-104">与元数据自定义属性不同，这些自定义属性保存在符号存储区中。</span><span class="sxs-lookup"><span data-stu-id="cde91-104">Unlike metadata custom attributes, these custom attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cde91-105">语法</span><span class="sxs-lookup"><span data-stu-id="cde91-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSymAttribute (  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is (cBuffer),  
        length_is (*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cde91-106">参数</span><span class="sxs-lookup"><span data-stu-id="cde91-106">Parameters</span></span>  

 `parent`  
 <span data-ttu-id="cde91-107">中请求其属性的对象的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="cde91-107">[in] The metadata token for the object for which the attribute is requested.</span></span>  
  
 `name`  
 <span data-ttu-id="cde91-108">中指向变量的指针，该变量指示要检索的属性。</span><span class="sxs-lookup"><span data-stu-id="cde91-108">[in] A pointer to the variable that indicates the attribute to retrieve.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="cde91-109">[in] `buffer` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="cde91-109">[in] The size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="cde91-110">弄指向接收属性数据长度的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="cde91-110">[out] A pointer to the variable that receives the length of the attribute data.</span></span>  
  
 `buffer`  
 <span data-ttu-id="cde91-111">弄指向接收特性数据的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="cde91-111">[out] A pointer to the variable that receives the attribute data.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cde91-112">返回值</span><span class="sxs-lookup"><span data-stu-id="cde91-112">Return Value</span></span>  

 <span data-ttu-id="cde91-113">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="cde91-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cde91-114">要求</span><span class="sxs-lookup"><span data-stu-id="cde91-114">Requirements</span></span>  

 <span data-ttu-id="cde91-115">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="cde91-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cde91-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cde91-116">See also</span></span>

- [<span data-ttu-id="cde91-117">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="cde91-117">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
