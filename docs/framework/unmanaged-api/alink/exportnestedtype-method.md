---
title: ExportNestedType 方法
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedType
- ExportNestedType
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedType
helpviewer_keywords:
- ExportNestedType method
ms.assetid: dec7df60-4d30-47c8-99db-72e0419e5f76
topic_type:
- apiref
ms.openlocfilehash: 69c99e2facfcb9077c3fc4131186ba3882c7cef6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684832"
---
# <a name="exportnestedtype-method"></a><span data-ttu-id="86f50-102">ExportNestedType 方法</span><span class="sxs-lookup"><span data-stu-id="86f50-102">ExportNestedType Method</span></span>

<span data-ttu-id="86f50-103">指定嵌套类型为可导出。</span><span class="sxs-lookup"><span data-stu-id="86f50-103">Specifies nested types as exportable.</span></span> <span data-ttu-id="86f50-104">[ExportType 方法](exporttype-method.md)还可以导出嵌套类型，但此方法的速度更快。</span><span class="sxs-lookup"><span data-stu-id="86f50-104">The [ExportType Method](exporttype-method.md) can also export nested types, but this method is faster.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86f50-105">语法</span><span class="sxs-lookup"><span data-stu-id="86f50-105">Syntax</span></span>  
  
```cpp  
HRESULT ExportNestedType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;
```  
  
## <a name="parameters"></a><span data-ttu-id="86f50-106">参数</span><span class="sxs-lookup"><span data-stu-id="86f50-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="86f50-107">要从中导出的程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="86f50-107">ID of assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="86f50-108">定义要导出的类型的文件标记或文件的程序集。</span><span class="sxs-lookup"><span data-stu-id="86f50-108">File token or Assembly of file that defines the type to be made exportable.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="86f50-109">要使其可导出的类型的类型标记。</span><span class="sxs-lookup"><span data-stu-id="86f50-109">Type token of type to be made exportable.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="86f50-110">父类型的标记。</span><span class="sxs-lookup"><span data-stu-id="86f50-110">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="86f50-111">要导出的完全限定的类型名称。</span><span class="sxs-lookup"><span data-stu-id="86f50-111">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="86f50-112">`ComType` 标志，如 `tdPublic` 或 `tdNested` 。</span><span class="sxs-lookup"><span data-stu-id="86f50-112">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="86f50-113">此值可传递给 [DefineExportedType 方法](../metadata/imetadataassemblyemit-defineexportedtype-method.md)。</span><span class="sxs-lookup"><span data-stu-id="86f50-113">This value may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="86f50-114">接收导出类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="86f50-114">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="86f50-115">返回值</span><span class="sxs-lookup"><span data-stu-id="86f50-115">Return Value</span></span>  

 <span data-ttu-id="86f50-116">如果方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="86f50-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86f50-117">要求</span><span class="sxs-lookup"><span data-stu-id="86f50-117">Requirements</span></span>  

 <span data-ttu-id="86f50-118">需要 alink</span><span class="sxs-lookup"><span data-stu-id="86f50-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86f50-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86f50-119">See also</span></span>

- [<span data-ttu-id="86f50-120">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="86f50-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="86f50-121">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="86f50-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="86f50-122">ALink API</span><span class="sxs-lookup"><span data-stu-id="86f50-122">ALink API</span></span>](index.md)
