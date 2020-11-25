---
title: ICorDebugProcess::IsTransitionStub 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.IsTransitionStub
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsTransitionStub
helpviewer_keywords:
- ICorDebugProcess::IsTransitionStub method [.NET Framework debugging]
- IsTransitionStub method [.NET Framework debugging]
ms.assetid: f7653317-7e48-4163-be03-f50f1a4b0f70
topic_type:
- apiref
ms.openlocfilehash: 2996c219ccf4e975c45fb531807abc4a608bae73
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95694771"
---
# <a name="icordebugprocessistransitionstub-method"></a><span data-ttu-id="2d0cb-102">ICorDebugProcess::IsTransitionStub 方法</span><span class="sxs-lookup"><span data-stu-id="2d0cb-102">ICorDebugProcess::IsTransitionStub Method</span></span>

<span data-ttu-id="2d0cb-103">获取一个值，该值指示地址是否在将导致转换到托管代码的存根内。</span><span class="sxs-lookup"><span data-stu-id="2d0cb-103">Gets a value that indicates whether an address is inside a stub that will cause a transition to managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d0cb-104">语法</span><span class="sxs-lookup"><span data-stu-id="2d0cb-104">Syntax</span></span>  
  
```cpp  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d0cb-105">参数</span><span class="sxs-lookup"><span data-stu-id="2d0cb-105">Parameters</span></span>  

 `address`  
 <span data-ttu-id="2d0cb-106">中一个 `CORDB_ADDRESS` 值，该值指定相关的地址。</span><span class="sxs-lookup"><span data-stu-id="2d0cb-106">[in] A `CORDB_ADDRESS` value that specifies the address in question.</span></span>  
  
 `pbTransitionStub`  
 <span data-ttu-id="2d0cb-107">弄指向布尔值的指针， `true` 如果指定的地址在将导致转换到托管代码的存根内，则为; 否则 `pbTransitionStub` 为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="2d0cb-107">[out] A pointer to a Boolean value that is `true` if the specified address is inside a stub that will cause a transition to managed code; otherwise \*`pbTransitionStub` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d0cb-108">注解</span><span class="sxs-lookup"><span data-stu-id="2d0cb-108">Remarks</span></span>  

 <span data-ttu-id="2d0cb-109">`IsTransitionStub`非托管的单步执行代码可以使用方法来确定何时将单步执行控件返回给托管分档器。</span><span class="sxs-lookup"><span data-stu-id="2d0cb-109">The `IsTransitionStub` method can be used by unmanaged stepping code to decide when to return stepping control to the managed stepper.</span></span>  
  
 <span data-ttu-id="2d0cb-110">还可以通过查看可移植可执行文件 (PE) 文件中的信息来标识转换存根。</span><span class="sxs-lookup"><span data-stu-id="2d0cb-110">You can also identity transition stubs by looking at information in the portable executable (PE) file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d0cb-111">要求</span><span class="sxs-lookup"><span data-stu-id="2d0cb-111">Requirements</span></span>  

 <span data-ttu-id="2d0cb-112">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2d0cb-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d0cb-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2d0cb-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2d0cb-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d0cb-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d0cb-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d0cb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
