---
title: IManagedObject::GetSerializedBuffer 方法
ms.date: 03/30/2017
api_name:
- IManagedObject.GetSerializedBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetSerializedBuffer
helpviewer_keywords:
- IManagedObject::GetSerializedBuffer method [.NET Framework hosting]
- GetSerializedBuffer method [.NET Framework hosting]
ms.assetid: c17105bb-b49f-434e-8f9b-77f8c85b9220
topic_type:
- apiref
ms.openlocfilehash: 159ece09ae0b6a67780639da8aae8c0e4b412bb8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730683"
---
# <a name="imanagedobjectgetserializedbuffer-method"></a><span data-ttu-id="e0dbc-102">IManagedObject::GetSerializedBuffer 方法</span><span class="sxs-lookup"><span data-stu-id="e0dbc-102">IManagedObject::GetSerializedBuffer Method</span></span>

<span data-ttu-id="e0dbc-103">获取此托管对象的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="e0dbc-103">Gets the string representation of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0dbc-104">语法</span><span class="sxs-lookup"><span data-stu-id="e0dbc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSerializedBuffer (  
    [out] BSTR *pBSTR  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0dbc-105">参数</span><span class="sxs-lookup"><span data-stu-id="e0dbc-105">Parameters</span></span>  

 `pBSTR`  
 <span data-ttu-id="e0dbc-106">弄指向字符串的指针，该字符串是序列化的对象。</span><span class="sxs-lookup"><span data-stu-id="e0dbc-106">[out] A pointer to a string that is the serialized object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0dbc-107">注解</span><span class="sxs-lookup"><span data-stu-id="e0dbc-107">Remarks</span></span>  

 <span data-ttu-id="e0dbc-108">`GetSerializedBuffer`方法会序列化对象，以便将其封送到客户端。</span><span class="sxs-lookup"><span data-stu-id="e0dbc-108">The `GetSerializedBuffer` method serializes the object so it can be marshaled to the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0dbc-109">要求</span><span class="sxs-lookup"><span data-stu-id="e0dbc-109">Requirements</span></span>  

 <span data-ttu-id="e0dbc-110">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e0dbc-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0dbc-111">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e0dbc-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e0dbc-112">**库：** 作为中的资源包含 MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e0dbc-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e0dbc-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0dbc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0dbc-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0dbc-114">See also</span></span>

- [<span data-ttu-id="e0dbc-115">IManagedObject 接口</span><span class="sxs-lookup"><span data-stu-id="e0dbc-115">IManagedObject Interface</span></span>](imanagedobject-interface.md)
