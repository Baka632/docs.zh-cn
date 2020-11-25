---
title: ICLRDataTarget::Request 方法
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.Request
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::Request
helpviewer_keywords:
- ICLRDataTarget::Request method [.NET Framework debugging]
- Request method [.NET Framework debugging]
ms.assetid: 4723bd1c-eddb-4ed2-897a-010024a47e01
topic_type:
- apiref
ms.openlocfilehash: 4d0cf22b4b0644d6b25d6b3ef884718cb9ca1e42
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723774"
---
# <a name="iclrdatatargetrequest-method"></a><span data-ttu-id="6d9df-102">ICLRDataTarget::Request 方法</span><span class="sxs-lookup"><span data-stu-id="6d9df-102">ICLRDataTarget::Request Method</span></span>

<span data-ttu-id="6d9df-103">由公共语言运行时调用 (CLR) 数据访问服务请求操作，如实现所定义。</span><span class="sxs-lookup"><span data-stu-id="6d9df-103">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d9df-104">语法</span><span class="sxs-lookup"><span data-stu-id="6d9df-104">Syntax</span></span>  
  
```cpp  
HRESULT Request (  
    [in] ULONG32            reqCode,  
    [in] ULONG32            inBufferSize,  
    [in, size_is(inBufferSize)]
        BYTE                *inBuffer,  
    [in] ULONG32            outBufferSize,  
    [out, size_is(outBufferSize)]
        BYTE                *outBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d9df-105">参数</span><span class="sxs-lookup"><span data-stu-id="6d9df-105">Parameters</span></span>  

 `reqCode`  
 <span data-ttu-id="6d9df-106">中用户定义的。</span><span class="sxs-lookup"><span data-stu-id="6d9df-106">[in] User-defined.</span></span>  
  
 `inBufferSize`  
 <span data-ttu-id="6d9df-107">中输入缓冲区的大小，该大小用于传入的请求。</span><span class="sxs-lookup"><span data-stu-id="6d9df-107">[in] The size of the input buffer, which is used for the incoming request.</span></span>  
  
 `inBuffer`  
 <span data-ttu-id="6d9df-108">中包含请求的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="6d9df-108">[in] A buffer containing the request.</span></span>  
  
 `outBufferSize`  
 <span data-ttu-id="6d9df-109">中用于响应的输出缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="6d9df-109">[in] The size of the output buffer, which is used for the response.</span></span>  
  
 `outBuffer`  
 <span data-ttu-id="6d9df-110">弄包含响应的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="6d9df-110">[out] A Buffer containing the response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d9df-111">注解</span><span class="sxs-lookup"><span data-stu-id="6d9df-111">Remarks</span></span>  

 <span data-ttu-id="6d9df-112">`Request`方法便于添加未指定的自定义操作。</span><span class="sxs-lookup"><span data-stu-id="6d9df-112">The `Request` method facilitates the addition of unspecified custom operations.</span></span> <span data-ttu-id="6d9df-113">也就是说，此方法提供了扩展性，无需版本的接口定义。</span><span class="sxs-lookup"><span data-stu-id="6d9df-113">That is, this method provides extensibility without requiring revision of the interface definition.</span></span>  
  
 <span data-ttu-id="6d9df-114">此方法由调试应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="6d9df-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d9df-115">要求</span><span class="sxs-lookup"><span data-stu-id="6d9df-115">Requirements</span></span>  

 <span data-ttu-id="6d9df-116">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6d9df-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d9df-117">**标头：** ClrData，ClrData</span><span class="sxs-lookup"><span data-stu-id="6d9df-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="6d9df-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d9df-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d9df-119">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d9df-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d9df-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6d9df-120">See also</span></span>

- [<span data-ttu-id="6d9df-121">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="6d9df-121">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
