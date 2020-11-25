---
title: ISymUnmanagedENCUpdate::GetLocalVariables 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables method [.NET Framework debugging]
- GetLocalVariables method [.NET Framework debugging]
ms.assetid: 5c8840be-ffea-447f-9c8d-178f1eaf8d06
topic_type:
- apiref
ms.openlocfilehash: 9e907450b4ae985ee30d9958eec8baba797b495a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728597"
---
# <a name="isymunmanagedencupdategetlocalvariables-method"></a><span data-ttu-id="80c10-102">ISymUnmanagedENCUpdate::GetLocalVariables 方法</span><span class="sxs-lookup"><span data-stu-id="80c10-102">ISymUnmanagedENCUpdate::GetLocalVariables Method</span></span>

<span data-ttu-id="80c10-103">获取局部变量。</span><span class="sxs-lookup"><span data-stu-id="80c10-103">Gets the local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80c10-104">语法</span><span class="sxs-lookup"><span data-stu-id="80c10-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariables(  
    [in]  mdMethodDef  mdMethodToken,  
    [in]  ULONG        cLocals,  
    [out, size_is(cLocals), length_is(*pceltFetched)]  
        ISymUnmanagedVariable *rgLocals[],  
    [out] ULONG        *pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80c10-105">参数</span><span class="sxs-lookup"><span data-stu-id="80c10-105">Parameters</span></span>  

 `mdMethodToken`  
 <span data-ttu-id="80c10-106">中方法的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="80c10-106">[in] The metadata token of the method.</span></span>  
  
 `cLocals`  
 <span data-ttu-id="80c10-107">中 `ULONG` 指示参数大小的 `rgLocals` 。</span><span class="sxs-lookup"><span data-stu-id="80c10-107">[in] A `ULONG` that indicates the size of the `rgLocals` parameter.</span></span>  
  
 `rgLocals`  
 <span data-ttu-id="80c10-108">弄返回的 [ISymUnmanagedVariable](isymunmanagedvariable-interface.md) 实例的数组。</span><span class="sxs-lookup"><span data-stu-id="80c10-108">[out] The returned array of [ISymUnmanagedVariable](isymunmanagedvariable-interface.md) instances.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="80c10-109">弄指向的指针 `ULONG` ，该指针接收 `rgLocals` 包含局部变量所需的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="80c10-109">[out] A pointer to a `ULONG` that receives the size of the `rgLocals` buffer required to contain the locals.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80c10-110">返回值</span><span class="sxs-lookup"><span data-stu-id="80c10-110">Return Value</span></span>  

 <span data-ttu-id="80c10-111">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="80c10-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80c10-112">要求</span><span class="sxs-lookup"><span data-stu-id="80c10-112">Requirements</span></span>  

 <span data-ttu-id="80c10-113">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="80c10-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80c10-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="80c10-114">See also</span></span>

- [<span data-ttu-id="80c10-115">ISymUnmanagedENCUpdate 接口</span><span class="sxs-lookup"><span data-stu-id="80c10-115">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)
