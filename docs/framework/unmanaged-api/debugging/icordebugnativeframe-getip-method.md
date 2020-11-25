---
title: ICorDebugNativeFrame::GetIP 方法
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
- ICorDebugNativeFrame::GetIP method [.NET Framework debugging]
ms.assetid: 99f693f3-d3b9-4fd8-9d09-b8efd03f7b67
topic_type:
- apiref
ms.openlocfilehash: c9c0598f8e7b3e8654124f50663c912f3cd61659
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709294"
---
# <a name="icordebugnativeframegetip-method"></a><span data-ttu-id="a82f5-102">ICorDebugNativeFrame::GetIP 方法</span><span class="sxs-lookup"><span data-stu-id="a82f5-102">ICorDebugNativeFrame::GetIP Method</span></span>

<span data-ttu-id="a82f5-103">获取指令指针当前所设置到的本机代码偏移位置。</span><span class="sxs-lookup"><span data-stu-id="a82f5-103">Gets the native code offset location to which the instruction pointer is currently set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a82f5-104">语法</span><span class="sxs-lookup"><span data-stu-id="a82f5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32           *pnOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a82f5-105">参数</span><span class="sxs-lookup"><span data-stu-id="a82f5-105">Parameters</span></span>  

 `pnOffset`  
 <span data-ttu-id="a82f5-106">弄指向本机代码中的偏移位置的指针。</span><span class="sxs-lookup"><span data-stu-id="a82f5-106">[out] A pointer to the offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a82f5-107">注解</span><span class="sxs-lookup"><span data-stu-id="a82f5-107">Remarks</span></span>  

 <span data-ttu-id="a82f5-108">如果此 "ICorDebugNativeFrame" 表示的堆栈帧处于活动状态，则偏移量是要执行的下一条指令的地址。</span><span class="sxs-lookup"><span data-stu-id="a82f5-108">If the stack frame that is represented by this "ICorDebugNativeFrame" is active, the offset is the address of the next instruction to be executed.</span></span> <span data-ttu-id="a82f5-109">如果此堆栈帧不处于活动状态，则偏移量是在重新激活堆栈帧时要执行的下一条指令的地址。</span><span class="sxs-lookup"><span data-stu-id="a82f5-109">If this stack frame is not active, the offset is the address of the next instruction to be executed when the stack frame is reactivated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a82f5-110">要求</span><span class="sxs-lookup"><span data-stu-id="a82f5-110">Requirements</span></span>  

 <span data-ttu-id="a82f5-111">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a82f5-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a82f5-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a82f5-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a82f5-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a82f5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a82f5-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a82f5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a82f5-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a82f5-115">See also</span></span>
