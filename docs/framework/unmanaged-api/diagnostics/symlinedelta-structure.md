---
title: SYMLINEDELTA 结构
ms.date: 03/30/2017
api_name:
- SYMLINEDELTA
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SYMLINEDELTA
helpviewer_keywords:
- SYMLINEDELTA structure [.NET Framework debugging]
ms.assetid: 9634e995-d46d-4397-ab66-cc5781d11e4e
topic_type:
- apiref
ms.openlocfilehash: dd45703540f8dc41b746ca03b4f09d74186aa9aa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690936"
---
# <a name="symlinedelta-structure"></a><span data-ttu-id="f42ea-102">SYMLINEDELTA 结构</span><span class="sxs-lookup"><span data-stu-id="f42ea-102">SYMLINEDELTA Structure</span></span>

<span data-ttu-id="f42ea-103">向符号处理程序提供有关因编辑而移动的方法的信息。</span><span class="sxs-lookup"><span data-stu-id="f42ea-103">Provides information to the symbol handler about methods that were moved as a result of edits.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f42ea-104">语法</span><span class="sxs-lookup"><span data-stu-id="f42ea-104">Syntax</span></span>  
  
```cpp  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a><span data-ttu-id="f42ea-105">成员</span><span class="sxs-lookup"><span data-stu-id="f42ea-105">Members</span></span>  
  
|<span data-ttu-id="f42ea-106">成员</span><span class="sxs-lookup"><span data-stu-id="f42ea-106">Member</span></span>|<span data-ttu-id="f42ea-107">说明</span><span class="sxs-lookup"><span data-stu-id="f42ea-107">Description</span></span>|  
|------------|-----------------|  
|`mdMethod`|<span data-ttu-id="f42ea-108">方法的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="f42ea-108">The method's metadata token.</span></span>|  
|`delta`|<span data-ttu-id="f42ea-109">此方法已移动的行数。</span><span class="sxs-lookup"><span data-stu-id="f42ea-109">The number of lines the method was moved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f42ea-110">要求</span><span class="sxs-lookup"><span data-stu-id="f42ea-110">Requirements</span></span>  

 <span data-ttu-id="f42ea-111">**标头：** CorSym .idl</span><span class="sxs-lookup"><span data-stu-id="f42ea-111">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f42ea-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f42ea-112">See also</span></span>

- [<span data-ttu-id="f42ea-113">诊断符号存储区结构</span><span class="sxs-lookup"><span data-stu-id="f42ea-113">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)
