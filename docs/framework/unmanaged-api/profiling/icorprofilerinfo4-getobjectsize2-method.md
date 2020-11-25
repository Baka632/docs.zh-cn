---
title: ICorProfilerInfo4::GetObjectSize2 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetObjectSize2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetObjectSize2
helpviewer_keywords:
- GetObjectSize2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetObjectSize2 method [.NET Framework profiling]
ms.assetid: 4a3e43ed-3ee3-4395-ab14-f78b903be13e
topic_type:
- apiref
ms.openlocfilehash: 960f8f1fe2315e068d599aa5a31e03f521b235a8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733862"
---
# <a name="icorprofilerinfo4getobjectsize2-method"></a><span data-ttu-id="5b388-102">ICorProfilerInfo4::GetObjectSize2 方法</span><span class="sxs-lookup"><span data-stu-id="5b388-102">ICorProfilerInfo4::GetObjectSize2 Method</span></span>

<span data-ttu-id="5b388-103">返回指定的对象的大小。</span><span class="sxs-lookup"><span data-stu-id="5b388-103">Returns the size of a specified object.</span></span> <span data-ttu-id="5b388-104">通过报告大于可在中表示的对象的大小来替换 [ICorProfilerInfo：： GetObjectSize](icorprofilerinfo-getobjectsize-method.md) 方法 `ULONG` 。</span><span class="sxs-lookup"><span data-stu-id="5b388-104">Replaces the [ICorProfilerInfo::GetObjectSize](icorprofilerinfo-getobjectsize-method.md) method by reporting sizes of objects that are larger than what can be expressed in a `ULONG`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b388-105">语法</span><span class="sxs-lookup"><span data-stu-id="5b388-105">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize2(  
    [in]  ObjectID objectId,  
    [out] SIZE_T *pcSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b388-106">参数</span><span class="sxs-lookup"><span data-stu-id="5b388-106">Parameters</span></span>  

 `objectId`  
 <span data-ttu-id="5b388-107">中对象的 ID。</span><span class="sxs-lookup"><span data-stu-id="5b388-107">[in] The ID of the object.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="5b388-108">弄一个指针，指向对象的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="5b388-108">[out] A pointer to the object's size, in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b388-109">注解</span><span class="sxs-lookup"><span data-stu-id="5b388-109">Remarks</span></span>  

 <span data-ttu-id="5b388-110">相同类型的不同对象通常具有相同的大小。</span><span class="sxs-lookup"><span data-stu-id="5b388-110">Different objects of the same types often have the same size.</span></span> <span data-ttu-id="5b388-111">但是，某些类型（例如数组或字符串）对于每个对象可能有不同的大小。</span><span class="sxs-lookup"><span data-stu-id="5b388-111">However, some types, such as arrays or strings, may have a different size for each object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b388-112">要求</span><span class="sxs-lookup"><span data-stu-id="5b388-112">Requirements</span></span>  

 <span data-ttu-id="5b388-113">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5b388-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b388-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5b388-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5b388-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b388-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b388-116">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b388-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b388-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b388-117">See also</span></span>

- [<span data-ttu-id="5b388-118">ICorProfilerInfo4 接口</span><span class="sxs-lookup"><span data-stu-id="5b388-118">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
