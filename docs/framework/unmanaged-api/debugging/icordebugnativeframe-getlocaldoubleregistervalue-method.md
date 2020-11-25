---
title: ICorDebugNativeFrame::GetLocalDoubleRegisterValue 方法
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalDoubleRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue method [.NET Framework debugging]
- GetLocalDoubleRegisterValue method [.NET Framework debugging]
ms.assetid: 1f838215-ac8a-434f-8ce6-03021d3098d9
topic_type:
- apiref
ms.openlocfilehash: 10f06fb04099ef947711bc7c5641e5a7f1fa36b7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695694"
---
# <a name="icordebugnativeframegetlocaldoubleregistervalue-method"></a><span data-ttu-id="2522c-102">ICorDebugNativeFrame::GetLocalDoubleRegisterValue 方法</span><span class="sxs-lookup"><span data-stu-id="2522c-102">ICorDebugNativeFrame::GetLocalDoubleRegisterValue Method</span></span>

<span data-ttu-id="2522c-103">获取此本机帧存储在两个指定寄存器中的参数或局部变量的值。</span><span class="sxs-lookup"><span data-stu-id="2522c-103">Gets the value of an argument or local variable that is stored in the two specified registers for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2522c-104">语法</span><span class="sxs-lookup"><span data-stu-id="2522c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalDoubleRegisterValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CorDebugRegister   lowWordReg,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2522c-105">参数</span><span class="sxs-lookup"><span data-stu-id="2522c-105">Parameters</span></span>  

 `highWordReg`  
 <span data-ttu-id="2522c-106">中"CorDebugRegister" 枚举的一个值，它指定包含值高位字的寄存器。</span><span class="sxs-lookup"><span data-stu-id="2522c-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the high word of the value.</span></span>  
  
 `lowWordReg`  
 <span data-ttu-id="2522c-107">中枚举的一个值 `CorDebugRegister` ，该值指定包含值的低位字的寄存器。</span><span class="sxs-lookup"><span data-stu-id="2522c-107">[in] A value of the `CorDebugRegister` enumeration that specifies the register containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="2522c-108">中一个整数，指定参数引用的二进制元数据签名的大小 `pvSigBlob` 。</span><span class="sxs-lookup"><span data-stu-id="2522c-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="2522c-109">中一个 `PCCOR_SIGNATURE` 值，该值指向值类型的二进制元数据签名。</span><span class="sxs-lookup"><span data-stu-id="2522c-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="2522c-110">弄一个指向 "ICorDebugValue" 对象地址的指针，该对象表示存储在指定寄存器中的检索到的值。</span><span class="sxs-lookup"><span data-stu-id="2522c-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified registers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2522c-111">注解</span><span class="sxs-lookup"><span data-stu-id="2522c-111">Remarks</span></span>  

 <span data-ttu-id="2522c-112">`GetLocalDoubleRegisterValue`方法既可以在本机框架中使用，也可以在实时 (JIT) 编译的框架中使用。</span><span class="sxs-lookup"><span data-stu-id="2522c-112">The `GetLocalDoubleRegisterValue` method can be used either in a native frame or a just-in-time (JIT)-compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2522c-113">要求</span><span class="sxs-lookup"><span data-stu-id="2522c-113">Requirements</span></span>  

 <span data-ttu-id="2522c-114">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2522c-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2522c-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2522c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2522c-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2522c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2522c-117">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2522c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2522c-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2522c-118">See also</span></span>
