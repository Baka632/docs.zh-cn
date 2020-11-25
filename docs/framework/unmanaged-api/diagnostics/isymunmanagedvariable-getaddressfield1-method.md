---
title: ISymUnmanagedVariable::GetAddressField1 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField1
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField1
helpviewer_keywords:
- GetAddressField1 method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressField1 method [.NET Framework debugging]
ms.assetid: 25788ed1-0ce3-4b97-96fc-88f8997812a3
topic_type:
- apiref
ms.openlocfilehash: e3ea3c0fd65750d52c0cfb10edbe18b1512f724b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729013"
---
# <a name="isymunmanagedvariablegetaddressfield1-method"></a><span data-ttu-id="05b12-102">ISymUnmanagedVariable::GetAddressField1 方法</span><span class="sxs-lookup"><span data-stu-id="05b12-102">ISymUnmanagedVariable::GetAddressField1 Method</span></span>

<span data-ttu-id="05b12-103">获取此变量的第一个地址字段。</span><span class="sxs-lookup"><span data-stu-id="05b12-103">Gets the first address field for this variable.</span></span> <span data-ttu-id="05b12-104">其含义取决于地址的类型。</span><span class="sxs-lookup"><span data-stu-id="05b12-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05b12-105">语法</span><span class="sxs-lookup"><span data-stu-id="05b12-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressField1(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05b12-106">参数</span><span class="sxs-lookup"><span data-stu-id="05b12-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="05b12-107">弄指向的指针 `ULONG32` ，该指针接收第一个地址字段。</span><span class="sxs-lookup"><span data-stu-id="05b12-107">[out] A pointer to a `ULONG32` that receives the first address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="05b12-108">返回值</span><span class="sxs-lookup"><span data-stu-id="05b12-108">Return Value</span></span>  

 <span data-ttu-id="05b12-109">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="05b12-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05b12-110">要求</span><span class="sxs-lookup"><span data-stu-id="05b12-110">Requirements</span></span>  

 <span data-ttu-id="05b12-111">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="05b12-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05b12-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="05b12-112">See also</span></span>

- [<span data-ttu-id="05b12-113">ISymUnmanagedVariable 接口</span><span class="sxs-lookup"><span data-stu-id="05b12-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="05b12-114">GetAddressField2 方法</span><span class="sxs-lookup"><span data-stu-id="05b12-114">GetAddressField2 Method</span></span>](isymunmanagedvariable-getaddressfield2-method.md)
- [<span data-ttu-id="05b12-115">GetAddressField3 方法</span><span class="sxs-lookup"><span data-stu-id="05b12-115">GetAddressField3 Method</span></span>](isymunmanagedvariable-getaddressfield3-method.md)
- [<span data-ttu-id="05b12-116">GetAddressKind 方法</span><span class="sxs-lookup"><span data-stu-id="05b12-116">GetAddressKind Method</span></span>](isymunmanagedvariable-getaddresskind-method.md)
