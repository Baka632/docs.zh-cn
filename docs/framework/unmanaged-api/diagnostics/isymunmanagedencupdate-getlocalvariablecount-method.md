---
title: ISymUnmanagedENCUpdate::GetLocalVariableCount 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariableCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariableCount
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariableCount method [.NET Framework debugging]
- GetLocalVariableCount method [.NET Framework debugging]
ms.assetid: 9777d8bb-4abc-4be8-aa7c-34f853eceb9c
topic_type:
- apiref
ms.openlocfilehash: 19e07fb181f631335a0c56bd59b6fc8e14e2f36d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726920"
---
# <a name="isymunmanagedencupdategetlocalvariablecount-method"></a><span data-ttu-id="05eeb-102">ISymUnmanagedENCUpdate::GetLocalVariableCount 方法</span><span class="sxs-lookup"><span data-stu-id="05eeb-102">ISymUnmanagedENCUpdate::GetLocalVariableCount Method</span></span>

<span data-ttu-id="05eeb-103">获取局部变量的数目。</span><span class="sxs-lookup"><span data-stu-id="05eeb-103">Gets the number of local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05eeb-104">语法</span><span class="sxs-lookup"><span data-stu-id="05eeb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariableCount(  
    [in]  mdMethodDef  mdMethodToken,  
    [out] ULONG        *pcLocals);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05eeb-105">参数</span><span class="sxs-lookup"><span data-stu-id="05eeb-105">Parameters</span></span>  

 `mdMethodToken`  
 <span data-ttu-id="05eeb-106">中方法的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="05eeb-106">[in] The metadata token of methods.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="05eeb-107">弄指向的指针， `ULONG32` 该指针接收包含局部变量数所需的缓冲区大小（以字符数表示）。</span><span class="sxs-lookup"><span data-stu-id="05eeb-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the number of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="05eeb-108">返回值</span><span class="sxs-lookup"><span data-stu-id="05eeb-108">Return Value</span></span>  

 <span data-ttu-id="05eeb-109">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="05eeb-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05eeb-110">要求</span><span class="sxs-lookup"><span data-stu-id="05eeb-110">Requirements</span></span>  

 <span data-ttu-id="05eeb-111">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="05eeb-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05eeb-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="05eeb-112">See also</span></span>

- [<span data-ttu-id="05eeb-113">ISymUnmanagedENCUpdate 接口</span><span class="sxs-lookup"><span data-stu-id="05eeb-113">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)
