---
title: IDebugAutoAttach::AutoAttach 方法
ms.date: 03/30/2017
api_name:
- IDebugAutoAttach.AutoAttach
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IDebugAutoAttach::AutoAttach
helpviewer_keywords:
- AutoAttach method [.NET Framework debugging]
- IDebugAutoAttach::AutoAttach method [.NET Framework debugging]
ms.assetid: 3cf3bd9c-7d88-4afa-a476-94cdc7609aa6
topic_type:
- apiref
ms.openlocfilehash: 64dd653bb0d4e383075a999e0803e4acfd0fae3d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720095"
---
# <a name="idebugautoattachautoattach-method"></a><span data-ttu-id="a31b0-102">IDebugAutoAttach::AutoAttach 方法</span><span class="sxs-lookup"><span data-stu-id="a31b0-102">IDebugAutoAttach::AutoAttach Method</span></span>

<span data-ttu-id="a31b0-103">执行服务器调用的调试器自动附加。</span><span class="sxs-lookup"><span data-stu-id="a31b0-103">Performs server-invoked debugger auto attach.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a31b0-104">语法</span><span class="sxs-lookup"><span data-stu-id="a31b0-104">Syntax</span></span>  
  
```cpp  
HRESULT AutoAttach  
(  
    [in]  REFGUID   guidPort,  
    [in]  DWORD     dwPid,  
    [in]  AUTOATTACH_PROGRAM_TYPE dwProgramType,  
    [in]  DWORD     dwProgramId,  
    [in]  LPCWSTR   pszSessionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a31b0-105">参数</span><span class="sxs-lookup"><span data-stu-id="a31b0-105">Parameters</span></span>  

 `guidPort`  
 <span data-ttu-id="a31b0-106">中始终设置为 `GUID_NULL` 。</span><span class="sxs-lookup"><span data-stu-id="a31b0-106">[in] Always set to `GUID_NULL`.</span></span>  
  
 `dwPid`  
 <span data-ttu-id="a31b0-107">中进程 ID，通常通过函数检索 `GetCurrentProcessId` 。</span><span class="sxs-lookup"><span data-stu-id="a31b0-107">[in] Process ID, normally retrieved with the `GetCurrentProcessId` function.</span></span>  
  
 `dwProgramType`  
 <span data-ttu-id="a31b0-108">中程序类型： `AUTOATTACH_PROGRAM_WIN32` 、 `AUTOATTACH_PROGRAM_COMPLUS` 或 `AUTOATTACH_PROGRAM_UNKNOWN` 。</span><span class="sxs-lookup"><span data-stu-id="a31b0-108">[in] Program type: `AUTOATTACH_PROGRAM_WIN32`, `AUTOATTACH_PROGRAM_COMPLUS`, or `AUTOATTACH_PROGRAM_UNKNOWN`.</span></span>  
  
 `dwProgramId`  
 <span data-ttu-id="a31b0-109">中程序 ID。</span><span class="sxs-lookup"><span data-stu-id="a31b0-109">[in] Program ID.</span></span>  
  
 `pszSessionId`  
 <span data-ttu-id="a31b0-110">中调试谓词传递的字符串。</span><span class="sxs-lookup"><span data-stu-id="a31b0-110">[in] String passed by the debug verb.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a31b0-111">返回值</span><span class="sxs-lookup"><span data-stu-id="a31b0-111">Return Value</span></span>  

 <span data-ttu-id="a31b0-112">如果方法成功，则 S_OK。</span><span class="sxs-lookup"><span data-stu-id="a31b0-112">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a31b0-113">要求</span><span class="sxs-lookup"><span data-stu-id="a31b0-113">Requirements</span></span>  

 <span data-ttu-id="a31b0-114">**标头：** DbgAutoAttach</span><span class="sxs-lookup"><span data-stu-id="a31b0-114">**Header:** DbgAutoAttach.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a31b0-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a31b0-115">See also</span></span>

- [<span data-ttu-id="a31b0-116">IDebugAutoAttach 接口</span><span class="sxs-lookup"><span data-stu-id="a31b0-116">IDebugAutoAttach Interface</span></span>](idebugautoattach-interface.md)
