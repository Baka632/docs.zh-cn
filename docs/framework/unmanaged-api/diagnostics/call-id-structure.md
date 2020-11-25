---
title: CALL_ID 结构
ms.date: 03/30/2017
api_name:
- CALL_ID
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- CALL_ID
helpviewer_keywords:
- CALL_ID structure [.NET Framework debugging]
ms.assetid: bfd46324-afec-4782-9c18-586d81fb4740
topic_type:
- apiref
ms.openlocfilehash: 3f41dd969e25f7a42308ff0b7b2d617344284b38
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725243"
---
# <a name="call_id-structure"></a><span data-ttu-id="9bc39-102">CALL_ID 结构</span><span class="sxs-lookup"><span data-stu-id="9bc39-102">CALL_ID Structure</span></span>

<span data-ttu-id="9bc39-103">向调试器提供有关正在调用的函数的信息。</span><span class="sxs-lookup"><span data-stu-id="9bc39-103">Provides information to a debugger about a function that is being called.</span></span> <span data-ttu-id="9bc39-104">有关详细信息，请参阅 [INotifySink2](inotifysink2-interface.md) 接口。</span><span class="sxs-lookup"><span data-stu-id="9bc39-104">See the [INotifySink2](inotifysink2-interface.md) interface for more information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bc39-105">语法</span><span class="sxs-lookup"><span data-stu-id="9bc39-105">Syntax</span></span>  
  
```cpp  
typedef struct tagCALL_ID  
{  
    LPCOLESTR       szMachine;  
    DWORD           dwPid;  
    USER_THREAD     *pUserThread;  
    STACK_ADDRESS   addrStackPointer;  
    LPCOLESTR       szEntryPoint;  
    LPCOLESTR       szDestinationMachine;  
} CALL_ID;  
```  
  
## <a name="members"></a><span data-ttu-id="9bc39-106">成员</span><span class="sxs-lookup"><span data-stu-id="9bc39-106">Members</span></span>  
  
|<span data-ttu-id="9bc39-107">成员</span><span class="sxs-lookup"><span data-stu-id="9bc39-107">Member</span></span>|<span data-ttu-id="9bc39-108">说明</span><span class="sxs-lookup"><span data-stu-id="9bc39-108">Description</span></span>|  
|------------|-----------------|  
|`szMachine`|<span data-ttu-id="9bc39-109">标识正在进行调用的计算机。</span><span class="sxs-lookup"><span data-stu-id="9bc39-109">Identifies the machine that is making the call.</span></span>|  
|`dwPid`|<span data-ttu-id="9bc39-110">标识计算机处理器。</span><span class="sxs-lookup"><span data-stu-id="9bc39-110">Identifies the machine processor.</span></span>|  
|`pUserThread`|<span data-ttu-id="9bc39-111">标识正在执行调用的线程。</span><span class="sxs-lookup"><span data-stu-id="9bc39-111">Identifies the thread that is executing the call.</span></span>|  
|`addrStackPointer`|<span data-ttu-id="9bc39-112">指定调用堆栈的地址。</span><span class="sxs-lookup"><span data-stu-id="9bc39-112">Specifies the address of the call stack.</span></span>|  
|`szEntryPoint`|<span data-ttu-id="9bc39-113">指定调用的地址。</span><span class="sxs-lookup"><span data-stu-id="9bc39-113">Specifies the address of the call.</span></span>|  
|`szDestinationMachine`|<span data-ttu-id="9bc39-114">标识要执行调用的计算机。</span><span class="sxs-lookup"><span data-stu-id="9bc39-114">Identifies the machine that will execute the call.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9bc39-115">要求</span><span class="sxs-lookup"><span data-stu-id="9bc39-115">Requirements</span></span>  

 <span data-ttu-id="9bc39-116">**标头：** ProtocolNotify2 .idl</span><span class="sxs-lookup"><span data-stu-id="9bc39-116">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bc39-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9bc39-117">See also</span></span>

- [<span data-ttu-id="9bc39-118">INotifySink2 接口</span><span class="sxs-lookup"><span data-stu-id="9bc39-118">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="9bc39-119">诊断符号存储区结构</span><span class="sxs-lookup"><span data-stu-id="9bc39-119">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)
