---
title: IMetaDataAssemblyEmit::SetAssemblyProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyProps method [.NET Framework metadata]
ms.assetid: 91b633d7-9e75-43c3-a8d2-2144984e5f9e
topic_type:
- apiref
ms.openlocfilehash: 3736e7279056e015b157758b1233cf6dc5aa6d8d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720199"
---
# <a name="imetadataassemblyemitsetassemblyprops-method"></a><span data-ttu-id="ed8fa-102">IMetaDataAssemblyEmit::SetAssemblyProps 方法</span><span class="sxs-lookup"><span data-stu-id="ed8fa-102">IMetaDataAssemblyEmit::SetAssemblyProps Method</span></span>

<span data-ttu-id="ed8fa-103">修改指定的 `Assembly` 元数据结构。</span><span class="sxs-lookup"><span data-stu-id="ed8fa-103">Modifies the specified `Assembly` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed8fa-104">语法</span><span class="sxs-lookup"><span data-stu-id="ed8fa-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyProps (  
    [in] mdAssembly               pma,  
    [in] const void               *pbPublicKey,  
    [in] ULONG                    cbPublicKey,  
    [in] ULONG                    ulHashAlgId,  
    [in] LPCWSTR                  szName,  
    [in] const ASSEMBLYMETADATA   *pMetaData,  
    [in] DWORD                    dwAssemblyFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed8fa-105">参数</span><span class="sxs-lookup"><span data-stu-id="ed8fa-105">Parameters</span></span>  

 `pma`  
 <span data-ttu-id="ed8fa-106">中 `Assembly` 用于指定要修改的元数据结构的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="ed8fa-106">[in] The metadata token that specifies the `Assembly` metadata structure to be modified.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="ed8fa-107">中指向程序集发布者的公钥的指针。</span><span class="sxs-lookup"><span data-stu-id="ed8fa-107">[in] A pointer to the public key of the publisher of the assembly.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="ed8fa-108">中的大小（以字节为单位） `pbPublicKey` 。</span><span class="sxs-lookup"><span data-stu-id="ed8fa-108">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `ulHashAlgId`  
 <span data-ttu-id="ed8fa-109">中用于对程序集文件进行哈希处理的哈希算法的标识符。</span><span class="sxs-lookup"><span data-stu-id="ed8fa-109">[in] The identifier for the hash algorithm used to hash the assembly files.</span></span>  
  
 `szName`  
 <span data-ttu-id="ed8fa-110">中程序集的用户可读文本名称。</span><span class="sxs-lookup"><span data-stu-id="ed8fa-110">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="ed8fa-111">中指向包含程序集的版本、平台和区域设置信息的 ASSEMBLYMETADATA 的指针。</span><span class="sxs-lookup"><span data-stu-id="ed8fa-111">[in] A pointer to the ASSEMBLYMETADATA that contains version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="ed8fa-112">中 [AssemblyFlags](assemblyflags-enumeration.md) 值的按位组合，用于指定程序集的各种属性。</span><span class="sxs-lookup"><span data-stu-id="ed8fa-112">[in] A bitwise combination of [AssemblyFlags](assemblyflags-enumeration.md) values that specify various attributes of the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed8fa-113">注解</span><span class="sxs-lookup"><span data-stu-id="ed8fa-113">Remarks</span></span>  

 <span data-ttu-id="ed8fa-114">若要创建 `Assembly` 元数据结构，请使用 [IMetaDataAssemblyEmit：:D efineassembly](imetadataassemblyemit-defineassembly-method.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="ed8fa-114">To create an `Assembly` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssembly](imetadataassemblyemit-defineassembly-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed8fa-115">要求</span><span class="sxs-lookup"><span data-stu-id="ed8fa-115">Requirements</span></span>  

 <span data-ttu-id="ed8fa-116">**平台：** 请参阅 [系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ed8fa-116">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed8fa-117">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="ed8fa-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ed8fa-118">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ed8fa-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ed8fa-119">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed8fa-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed8fa-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed8fa-120">See also</span></span>

- [<span data-ttu-id="ed8fa-121">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="ed8fa-121">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
