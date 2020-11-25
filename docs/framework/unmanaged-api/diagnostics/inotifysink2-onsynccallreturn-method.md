---
title: INotifySink2::OnSyncCallReturn 方法
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallReturn
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallReturn
helpviewer_keywords:
- OnSyncCallReturn method [.NET Framework debugging]
- INotifySink2::OnSyncCallReturn method [.NET Framework debugging]
ms.assetid: c1bda761-6292-4750-a14b-7d5db8f33456
topic_type:
- apiref
ms.openlocfilehash: fe2db3df688f91ec6e1aadd8cc3bb43726e5c30f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719952"
---
# <a name="inotifysink2onsynccallreturn-method"></a><span data-ttu-id="a186b-102">INotifySink2::OnSyncCallReturn 方法</span><span class="sxs-lookup"><span data-stu-id="a186b-102">INotifySink2::OnSyncCallReturn Method</span></span>

<span data-ttu-id="a186b-103">当调用返回时调用。</span><span class="sxs-lookup"><span data-stu-id="a186b-103">Gets invoked when a call returns.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a186b-104">语法</span><span class="sxs-lookup"><span data-stu-id="a186b-104">Syntax</span></span>  
  
```cpp  
HRESULT OnSyncCallReturn  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a186b-105">参数</span><span class="sxs-lookup"><span data-stu-id="a186b-105">Parameters</span></span>  

 `in_CallID`  
 <span data-ttu-id="a186b-106">中从其返回的调用的 ID。</span><span class="sxs-lookup"><span data-stu-id="a186b-106">[in] ID of the call being returned from.</span></span> <span data-ttu-id="a186b-107">请参阅 [CALL_ID 结构](call-id-structure.md)。</span><span class="sxs-lookup"><span data-stu-id="a186b-107">See [CALL_ID Structure](call-id-structure.md).</span></span>  
  
 `in_pBuffer`  
 <span data-ttu-id="a186b-108">中调用缓冲区。</span><span class="sxs-lookup"><span data-stu-id="a186b-108">[in] Call buffer.</span></span>  
  
 `in_BufferSize`  
 <span data-ttu-id="a186b-109">中调用缓冲区的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="a186b-109">[in] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a186b-110">返回值</span><span class="sxs-lookup"><span data-stu-id="a186b-110">Return Value</span></span>  

 <span data-ttu-id="a186b-111">如果方法成功，则 S_OK。</span><span class="sxs-lookup"><span data-stu-id="a186b-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a186b-112">要求</span><span class="sxs-lookup"><span data-stu-id="a186b-112">Requirements</span></span>  

 <span data-ttu-id="a186b-113">**标头：** ProtocolNotify2 .idl</span><span class="sxs-lookup"><span data-stu-id="a186b-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a186b-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a186b-114">See also</span></span>

- [<span data-ttu-id="a186b-115">INotifySink2 接口</span><span class="sxs-lookup"><span data-stu-id="a186b-115">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="a186b-116">INotifySource2 接口</span><span class="sxs-lookup"><span data-stu-id="a186b-116">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="a186b-117">INotifyConnection2 接口</span><span class="sxs-lookup"><span data-stu-id="a186b-117">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
