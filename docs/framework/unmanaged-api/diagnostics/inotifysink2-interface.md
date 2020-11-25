---
title: INotifySink2 接口
ms.date: 03/30/2017
api_name:
- INotifySink2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2
helpviewer_keywords:
- INotifySink2 interface [.NET Framework debugging]
ms.assetid: c1018789-4206-455d-aacc-2d876fc0d0bb
topic_type:
- apiref
ms.openlocfilehash: 255fe51f86157842a5807145bf7c58ae1ff5ba8a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720017"
---
# <a name="inotifysink2-interface"></a><span data-ttu-id="1f824-102">INotifySink2 接口</span><span class="sxs-lookup"><span data-stu-id="1f824-102">INotifySink2 Interface</span></span>

<span data-ttu-id="1f824-103">声明接收器通知的方法。</span><span class="sxs-lookup"><span data-stu-id="1f824-103">Declares methods for sink notification.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1f824-104">方法</span><span class="sxs-lookup"><span data-stu-id="1f824-104">Methods</span></span>  
  
|<span data-ttu-id="1f824-105">方法</span><span class="sxs-lookup"><span data-stu-id="1f824-105">Method</span></span>|<span data-ttu-id="1f824-106">说明</span><span class="sxs-lookup"><span data-stu-id="1f824-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1f824-107">OnSyncCallEnter 方法</span><span class="sxs-lookup"><span data-stu-id="1f824-107">OnSyncCallEnter Method</span></span>](inotifysink2-onsynccallenter-method.md)|<span data-ttu-id="1f824-108">在输入调用时调用。</span><span class="sxs-lookup"><span data-stu-id="1f824-108">Gets invoked when entering a call.</span></span>|  
|[<span data-ttu-id="1f824-109">OnSyncCallExit 方法</span><span class="sxs-lookup"><span data-stu-id="1f824-109">OnSyncCallExit Method</span></span>](inotifysink2-onsynccallexit-method.md)|<span data-ttu-id="1f824-110">在退出调用时调用。</span><span class="sxs-lookup"><span data-stu-id="1f824-110">Gets invoked when exiting a call.</span></span>|  
|[<span data-ttu-id="1f824-111">OnSyncCallOut 方法</span><span class="sxs-lookup"><span data-stu-id="1f824-111">OnSyncCallOut Method</span></span>](inotifysink2-onsynccallout-method.md)|<span data-ttu-id="1f824-112">在调用时调用。</span><span class="sxs-lookup"><span data-stu-id="1f824-112">Gets invoked when a call is out.</span></span>|  
|[<span data-ttu-id="1f824-113">OnSyncCallReturn 方法</span><span class="sxs-lookup"><span data-stu-id="1f824-113">OnSyncCallReturn Method</span></span>](inotifysink2-onsynccallreturn-method.md)|<span data-ttu-id="1f824-114">当调用返回时调用。</span><span class="sxs-lookup"><span data-stu-id="1f824-114">Gets invoked when a call returns.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1f824-115">要求</span><span class="sxs-lookup"><span data-stu-id="1f824-115">Requirements</span></span>  

 <span data-ttu-id="1f824-116">**标头：** ProtocolNotify2 .idl</span><span class="sxs-lookup"><span data-stu-id="1f824-116">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f824-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f824-117">See also</span></span>

- [<span data-ttu-id="1f824-118">INotifyConnection2 接口</span><span class="sxs-lookup"><span data-stu-id="1f824-118">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
- [<span data-ttu-id="1f824-119">INotifySource2 接口</span><span class="sxs-lookup"><span data-stu-id="1f824-119">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="1f824-120">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="1f824-120">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
