---
title: ICorProfilerInfo2::GetStaticFieldInfo 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetStaticFieldInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo method [.NET Framework profiling]
- GetStaticFieldInfo method [.NET Framework profiling]
ms.assetid: fc663e76-e23f-49a8-bdd5-52cdf1a3b2b3
topic_type:
- apiref
ms.openlocfilehash: ff84bdfb8bbd5331fb94eed766f09137adf9e62c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703832"
---
# <a name="icorprofilerinfo2getstaticfieldinfo-method"></a><span data-ttu-id="f2b90-102">ICorProfilerInfo2::GetStaticFieldInfo 方法</span><span class="sxs-lookup"><span data-stu-id="f2b90-102">ICorProfilerInfo2::GetStaticFieldInfo Method</span></span>

<span data-ttu-id="f2b90-103">获取一个值，该值指示应用于指定字段的静态类型。</span><span class="sxs-lookup"><span data-stu-id="f2b90-103">Gets a value that indicates the kind of static that applies to the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2b90-104">语法</span><span class="sxs-lookup"><span data-stu-id="f2b90-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldInfo (  
    [in] ClassID               classId,  
    [in] mdFieldDef            fieldToken,  
    [out] COR_PRF_STATIC_TYPE  *pFieldInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2b90-105">参数</span><span class="sxs-lookup"><span data-stu-id="f2b90-105">Parameters</span></span>  

 `classId`  
 <span data-ttu-id="f2b90-106">中在其中定义静态字段的类的 ID。</span><span class="sxs-lookup"><span data-stu-id="f2b90-106">[in] The ID of the class in which the static field is defined.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="f2b90-107">中静态字段的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="f2b90-107">[in] The metadata token for the static field.</span></span>  
  
 `pFieldInfo`  
 <span data-ttu-id="f2b90-108">弄一个指针，指向 [COR_PRF_STATIC_TYPE](cor-prf-static-type-enumeration.md) 枚举的值，该值指示指定字段是否为静态的，如果为，则为应用于该字段的静态类型。</span><span class="sxs-lookup"><span data-stu-id="f2b90-108">[out] A pointer to a value of the [COR_PRF_STATIC_TYPE](cor-prf-static-type-enumeration.md) enumeration that indicates whether the specified field is static, and if so, the kind of static that applies to the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2b90-109">注解</span><span class="sxs-lookup"><span data-stu-id="f2b90-109">Remarks</span></span>  

 <span data-ttu-id="f2b90-110">此信息可用于确定要调用哪个函数以获取静态字段的地址。</span><span class="sxs-lookup"><span data-stu-id="f2b90-110">This information can be used to determine which function to call to get the address of the static field.</span></span>  
  
 <span data-ttu-id="f2b90-111">探查器代码仍应检查静态字段的元数据，以确保它实际具有地址。</span><span class="sxs-lookup"><span data-stu-id="f2b90-111">The profiler code should still check the metadata for a static field to ensure that it actually has an address.</span></span> <span data-ttu-id="f2b90-112">静态文本 (也就是说，常量) 只存在于元数据中，并且没有地址。</span><span class="sxs-lookup"><span data-stu-id="f2b90-112">Static literals (that is, constants) exist only in the metadata and do not have an address.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2b90-113">要求</span><span class="sxs-lookup"><span data-stu-id="f2b90-113">Requirements</span></span>  

 <span data-ttu-id="f2b90-114">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f2b90-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2b90-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f2b90-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f2b90-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2b90-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2b90-117">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2b90-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2b90-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f2b90-118">See also</span></span>

- [<span data-ttu-id="f2b90-119">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="f2b90-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="f2b90-120">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="f2b90-120">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
