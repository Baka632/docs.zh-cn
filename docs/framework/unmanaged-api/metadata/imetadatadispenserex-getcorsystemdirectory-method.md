---
title: IMetaDataDispenserEx::GetCORSystemDirectory 方法
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.GetCORSystemDirectory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::GetCORSystemDirectory
helpviewer_keywords:
- IMetaDataDispenserEx::GetCORSystemDirectory method [.NET Framework metadata]
- GetCORSystemDirectory method [.NET Framework metadata]
ms.assetid: d9e0f3b6-e106-4820-bada-5bfba34ce360
topic_type:
- apiref
ms.openlocfilehash: ea0e6f96028afc201f498119976eb87aa762a6eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681686"
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a><span data-ttu-id="560fb-102">IMetaDataDispenserEx::GetCORSystemDirectory 方法</span><span class="sxs-lookup"><span data-stu-id="560fb-102">IMetaDataDispenserEx::GetCORSystemDirectory Method</span></span>

<span data-ttu-id="560fb-103">获取 (CLR) 保存当前公共语言运行时的目录。</span><span class="sxs-lookup"><span data-stu-id="560fb-103">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="560fb-104">此方法仅支持在进程外调试器中使用。</span><span class="sxs-lookup"><span data-stu-id="560fb-104">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="560fb-105">如果从另一个组件调用，它将返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="560fb-105">If called from another component, it will return E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="560fb-106">语法</span><span class="sxs-lookup"><span data-stu-id="560fb-106">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,
    [in]  DWORD       cchBuffer,
    [out] DWORD*      pchBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="560fb-107">参数</span><span class="sxs-lookup"><span data-stu-id="560fb-107">Parameters</span></span>  

 `szBuffer`  
 <span data-ttu-id="560fb-108">弄要接收目录名称的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="560fb-108">[out] The buffer to receive the directory name.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="560fb-109">中的大小（以字节为单位） `szBuffer` 。</span><span class="sxs-lookup"><span data-stu-id="560fb-109">[in] The size, in bytes, of `szBuffer`.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="560fb-110">弄中实际返回的字节数 `szBuffer` 。</span><span class="sxs-lookup"><span data-stu-id="560fb-110">[out] The number of bytes actually returned in `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="560fb-111">要求</span><span class="sxs-lookup"><span data-stu-id="560fb-111">Requirements</span></span>  

 <span data-ttu-id="560fb-112">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="560fb-112">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="560fb-113">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="560fb-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="560fb-114">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="560fb-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="560fb-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="560fb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="560fb-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="560fb-116">See also</span></span>

- [<span data-ttu-id="560fb-117">IMetaDataDispenserEx 接口</span><span class="sxs-lookup"><span data-stu-id="560fb-117">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="560fb-118">IMetaDataDispenser 接口</span><span class="sxs-lookup"><span data-stu-id="560fb-118">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
