---
title: ICorDebugVariableHome：： GetOffset 方法
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetOffset
helpviewer_keywords:
- ICorDebugVariableHome::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: f025c2e5-3f6c-4be8-9ffe-c8b214617dfe
topic_type:
- apiref
ms.openlocfilehash: c5d491b66e4ec64dffa4e19dabff876c9c473036
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711788"
---
# <a name="icordebugvariablehomegetoffset-method"></a><span data-ttu-id="668e4-102">ICorDebugVariableHome：： GetOffset 方法</span><span class="sxs-lookup"><span data-stu-id="668e4-102">ICorDebugVariableHome::GetOffset Method</span></span>

<span data-ttu-id="668e4-103">获取与基寄存器相对应的偏移量。</span><span class="sxs-lookup"><span data-stu-id="668e4-103">Gets the offset from the base register for a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="668e4-104">语法</span><span class="sxs-lookup"><span data-stu-id="668e4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="668e4-105">参数</span><span class="sxs-lookup"><span data-stu-id="668e4-105">Parameters</span></span>  

 `pOffset`  
 <span data-ttu-id="668e4-106">弄基寄存器的偏移量。</span><span class="sxs-lookup"><span data-stu-id="668e4-106">[out] The offset from the base register.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="668e4-107">返回值</span><span class="sxs-lookup"><span data-stu-id="668e4-107">Return Value</span></span>  

 <span data-ttu-id="668e4-108">方法返回以下值：</span><span class="sxs-lookup"><span data-stu-id="668e4-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="668e4-109">Value</span><span class="sxs-lookup"><span data-stu-id="668e4-109">Value</span></span>|<span data-ttu-id="668e4-110">说明</span><span class="sxs-lookup"><span data-stu-id="668e4-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="668e4-111">变量在寄存器相对内存位置。</span><span class="sxs-lookup"><span data-stu-id="668e4-111">The variable is in a register-relative memory location.</span></span>|  
|`E_FAIL`|<span data-ttu-id="668e4-112">变量不在寄存器相对内存位置中。</span><span class="sxs-lookup"><span data-stu-id="668e4-112">The variable is not in a register-relative memory location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="668e4-113">要求</span><span class="sxs-lookup"><span data-stu-id="668e4-113">Requirements</span></span>  

 <span data-ttu-id="668e4-114">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="668e4-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="668e4-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="668e4-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="668e4-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="668e4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="668e4-117">**.NET Framework 版本：**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="668e4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="668e4-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="668e4-118">See also</span></span>

- [<span data-ttu-id="668e4-119">ICorDebugVariableHome 接口</span><span class="sxs-lookup"><span data-stu-id="668e4-119">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
