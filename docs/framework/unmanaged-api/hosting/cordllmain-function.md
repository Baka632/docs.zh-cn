---
title: _CorDllMain 函数
ms.date: 03/30/2017
api_name:
- _CorDllMain
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorDllMain
helpviewer_keywords:
- _CorDllMain function [.NET Framework hosting]
ms.assetid: bc7b51cf-39d3-48ec-a5cb-2f179fbefff8
topic_type:
- apiref
ms.openlocfilehash: 1b3ebcabc66ee7ca29245bb02d958be311bc65fa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673691"
---
# <a name="_cordllmain-function"></a><span data-ttu-id="58e79-102">\_CorDllMain 函数</span><span class="sxs-lookup"><span data-stu-id="58e79-102">\_CorDllMain Function</span></span>

<span data-ttu-id="58e79-103"> (CLR) 初始化公共语言运行时，查找 DLL 程序集的 CLR 头中的托管入口点，然后开始执行。</span><span class="sxs-lookup"><span data-stu-id="58e79-103">Initializes the common language runtime (CLR), locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58e79-104">语法</span><span class="sxs-lookup"><span data-stu-id="58e79-104">Syntax</span></span>  
  
```cpp  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58e79-105">参数</span><span class="sxs-lookup"><span data-stu-id="58e79-105">Parameters</span></span>  

 `hInst`  
 <span data-ttu-id="58e79-106">中加载的模块的实例句柄。</span><span class="sxs-lookup"><span data-stu-id="58e79-106">[in] The instance handle of the loaded module.</span></span>  
  
 `dwReason`  
 <span data-ttu-id="58e79-107">中指示调用 DLL 入口点函数的原因。</span><span class="sxs-lookup"><span data-stu-id="58e79-107">[in]Indicates why the DLL entry-point function is being called.</span></span> <span data-ttu-id="58e79-108">此参数可以是下列值之一： DLL \_ PROCESS_ATTACH、dll \_ 线程 \_ 附加、dll \_ 线程 \_ 附加或 dll \_ 进程 \_ 分离。</span><span class="sxs-lookup"><span data-stu-id="58e79-108">This parameter can be one of the following values: DLL\_PROCESS_ATTACH, DLL\_THREAD\_ATTACH, DLL\_THREAD\_ATTACH, or DLL\_PROCESS\_DETACH.</span></span> <span data-ttu-id="58e79-109">有关这些值的说明，请参阅 `DllMain` PLATFORM SDK 中的文档。</span><span class="sxs-lookup"><span data-stu-id="58e79-109">For descriptions of these values, see the `DllMain` documentation in the Platform SDK.</span></span>  
  
 `lpReserved`  
 <span data-ttu-id="58e79-110">中用.</span><span class="sxs-lookup"><span data-stu-id="58e79-110">[in] Unused.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="58e79-111">返回值</span><span class="sxs-lookup"><span data-stu-id="58e79-111">Return Value</span></span>  

 <span data-ttu-id="58e79-112">`true`如果发生错误，则此方法将返回成功 `false` 。</span><span class="sxs-lookup"><span data-stu-id="58e79-112">This method returns `true` for success and `false` if an error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58e79-113">注解</span><span class="sxs-lookup"><span data-stu-id="58e79-113">Remarks</span></span>  

 <span data-ttu-id="58e79-114">此函数由 DLL 程序集的操作系统加载程序调用。</span><span class="sxs-lookup"><span data-stu-id="58e79-114">This function is called by the operating system loader for DLL assemblies.</span></span> <span data-ttu-id="58e79-115">对于可执行程序集，加载程序将调用[ \_ CorExeMain](corexemain-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="58e79-115">For executable assemblies, the loader calls the [\_CorExeMain](corexemain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="58e79-116">操作系统加载程序将调用此方法，而不考虑 DLL 文件中指定的入口点。</span><span class="sxs-lookup"><span data-stu-id="58e79-116">The operating system loader calls this method regardless of the entry point specified in the DLL file.</span></span>  
  
<span data-ttu-id="58e79-117">`_CorDllMain`函数由操作系统加载程序直接调用。</span><span class="sxs-lookup"><span data-stu-id="58e79-117">The `_CorDllMain` function is called directly by the operating system loader.</span></span>
  
 <span data-ttu-id="58e79-118">有关其他信息，请参阅[ \_ CorValidateImage](corvalidateimage-function.md)主题中的 "备注" 部分。</span><span class="sxs-lookup"><span data-stu-id="58e79-118">For additional information, see the Remarks section in the [\_CorValidateImage](corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58e79-119">要求</span><span class="sxs-lookup"><span data-stu-id="58e79-119">Requirements</span></span>  

 <span data-ttu-id="58e79-120">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="58e79-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58e79-121">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="58e79-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="58e79-122">**库：** 作为中的资源包含 MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="58e79-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="58e79-123">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58e79-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58e79-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58e79-124">See also</span></span>

- [<span data-ttu-id="58e79-125">元数据全局静态函数</span><span class="sxs-lookup"><span data-stu-id="58e79-125">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
