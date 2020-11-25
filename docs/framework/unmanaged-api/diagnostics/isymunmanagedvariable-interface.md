---
title: ISymUnmanagedVariable 接口
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable
helpviewer_keywords:
- ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: 704c69ba-77bc-40d7-8c0c-400061686321
topic_type:
- apiref
ms.openlocfilehash: 93e1f8eb17f06e42ddb243f88c593979fcb28030
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733277"
---
# <a name="isymunmanagedvariable-interface"></a><span data-ttu-id="50221-102">ISymUnmanagedVariable 接口</span><span class="sxs-lookup"><span data-stu-id="50221-102">ISymUnmanagedVariable Interface</span></span>

<span data-ttu-id="50221-103">表示变量，如参数、局部变量或字段。</span><span class="sxs-lookup"><span data-stu-id="50221-103">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="50221-104">方法</span><span class="sxs-lookup"><span data-stu-id="50221-104">Methods</span></span>  
  
|<span data-ttu-id="50221-105">方法</span><span class="sxs-lookup"><span data-stu-id="50221-105">Method</span></span>|<span data-ttu-id="50221-106">说明</span><span class="sxs-lookup"><span data-stu-id="50221-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="50221-107">GetAddressField1 方法</span><span class="sxs-lookup"><span data-stu-id="50221-107">GetAddressField1 Method</span></span>](isymunmanagedvariable-getaddressfield1-method.md)|<span data-ttu-id="50221-108">获取此变量的第一个地址字段。</span><span class="sxs-lookup"><span data-stu-id="50221-108">Gets the first address field for this variable.</span></span> <span data-ttu-id="50221-109">其含义取决于地址的类型。</span><span class="sxs-lookup"><span data-stu-id="50221-109">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="50221-110">GetAddressField2 方法</span><span class="sxs-lookup"><span data-stu-id="50221-110">GetAddressField2 Method</span></span>](isymunmanagedvariable-getaddressfield2-method.md)|<span data-ttu-id="50221-111">获取此变量的第二个地址字段。</span><span class="sxs-lookup"><span data-stu-id="50221-111">Gets the second address field for this variable.</span></span> <span data-ttu-id="50221-112">其含义取决于地址的类型。</span><span class="sxs-lookup"><span data-stu-id="50221-112">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="50221-113">GetAddressField3 方法</span><span class="sxs-lookup"><span data-stu-id="50221-113">GetAddressField3 Method</span></span>](isymunmanagedvariable-getaddressfield3-method.md)|<span data-ttu-id="50221-114">获取此变量的第三个地址字段。</span><span class="sxs-lookup"><span data-stu-id="50221-114">Gets the third address field for this variable.</span></span> <span data-ttu-id="50221-115">其含义取决于地址的类型。</span><span class="sxs-lookup"><span data-stu-id="50221-115">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="50221-116">GetAddressKind 方法</span><span class="sxs-lookup"><span data-stu-id="50221-116">GetAddressKind Method</span></span>](isymunmanagedvariable-getaddresskind-method.md)|<span data-ttu-id="50221-117">获取此变量的地址类型。</span><span class="sxs-lookup"><span data-stu-id="50221-117">Gets the kind of address of this variable.</span></span>|  
|[<span data-ttu-id="50221-118">GetAttributes 方法</span><span class="sxs-lookup"><span data-stu-id="50221-118">GetAttributes Method</span></span>](isymunmanagedvariable-getattributes-method.md)|<span data-ttu-id="50221-119">获取此变量的特性标志。</span><span class="sxs-lookup"><span data-stu-id="50221-119">Gets the attribute flags for this variable.</span></span>|  
|[<span data-ttu-id="50221-120">GetEndOffset 方法</span><span class="sxs-lookup"><span data-stu-id="50221-120">GetEndOffset Method</span></span>](isymunmanagedvariable-getendoffset-method.md)|<span data-ttu-id="50221-121">获取此变量在其父级内的结束偏移量。</span><span class="sxs-lookup"><span data-stu-id="50221-121">Gets the end offset of this variable within its parent.</span></span>|  
|[<span data-ttu-id="50221-122">GetName 方法</span><span class="sxs-lookup"><span data-stu-id="50221-122">GetName Method</span></span>](isymunmanagedvariable-getname-method.md)|<span data-ttu-id="50221-123">获取此变量的名称。</span><span class="sxs-lookup"><span data-stu-id="50221-123">Gets the name of this variable.</span></span>|  
|[<span data-ttu-id="50221-124">GetSignature 方法</span><span class="sxs-lookup"><span data-stu-id="50221-124">GetSignature Method</span></span>](isymunmanagedvariable-getsignature-method.md)|<span data-ttu-id="50221-125">获取此变量的签名。</span><span class="sxs-lookup"><span data-stu-id="50221-125">Gets the signature of this variable.</span></span>|  
|[<span data-ttu-id="50221-126">GetStartOffset 方法</span><span class="sxs-lookup"><span data-stu-id="50221-126">GetStartOffset Method</span></span>](isymunmanagedvariable-getstartoffset-method.md)|<span data-ttu-id="50221-127">获取此变量在其父级内的起始偏移量。</span><span class="sxs-lookup"><span data-stu-id="50221-127">Gets the start offset of this variable within its parent.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="50221-128">要求</span><span class="sxs-lookup"><span data-stu-id="50221-128">Requirements</span></span>  

 <span data-ttu-id="50221-129">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="50221-129">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50221-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50221-130">See also</span></span>

- [<span data-ttu-id="50221-131">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="50221-131">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
