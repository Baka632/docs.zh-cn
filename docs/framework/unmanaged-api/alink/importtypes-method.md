---
title: ImportTypes 方法
ms.date: 03/30/2017
api_name:
- IALink.ImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes
helpviewer_keywords:
- ImportTypes method
ms.assetid: 351d4b4c-c939-486d-9471-51914a55f471
topic_type:
- apiref
ms.openlocfilehash: 762f78900add70238971978ceecda089d0c725ce
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705106"
---
# <a name="importtypes-method"></a><span data-ttu-id="db4dc-102">ImportTypes 方法</span><span class="sxs-lookup"><span data-stu-id="db4dc-102">ImportTypes Method</span></span>

<span data-ttu-id="db4dc-103">开始从通过 [ImportFile 方法](importfile-method.md)导入的每个范围导入类型。</span><span class="sxs-lookup"><span data-stu-id="db4dc-103">Initiates the importing of types from each scope imported via [ImportFile Method](importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db4dc-104">语法</span><span class="sxs-lookup"><span data-stu-id="db4dc-104">Syntax</span></span>  
  
```cpp  
HRESULT ImportTypes(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="db4dc-105">参数</span><span class="sxs-lookup"><span data-stu-id="db4dc-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="db4dc-106">要导入到的程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="db4dc-106">ID of the assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="db4dc-107">要从中导入的文件的 ID。</span><span class="sxs-lookup"><span data-stu-id="db4dc-107">ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="db4dc-108">要导入的从零开始的范围。</span><span class="sxs-lookup"><span data-stu-id="db4dc-108">Zero-based scope to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="db4dc-109">接收此范围内的类型的枚举器句柄。</span><span class="sxs-lookup"><span data-stu-id="db4dc-109">Receives enumerator handle for the types in this scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="db4dc-110">可以选择接收 [IMetaDataImport 接口](../metadata/imetadataimport-interface.md) 接口。</span><span class="sxs-lookup"><span data-stu-id="db4dc-110">Optionally receives [IMetaDataImport Interface](../metadata/imetadataimport-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="db4dc-111">可以选择接收指定范围内的类型的计数。</span><span class="sxs-lookup"><span data-stu-id="db4dc-111">Optionally receives count of types in the indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="db4dc-112">返回值</span><span class="sxs-lookup"><span data-stu-id="db4dc-112">Return Value</span></span>  

 <span data-ttu-id="db4dc-113">如果方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="db4dc-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db4dc-114">要求</span><span class="sxs-lookup"><span data-stu-id="db4dc-114">Requirements</span></span>  

 <span data-ttu-id="db4dc-115">需要 alink</span><span class="sxs-lookup"><span data-stu-id="db4dc-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db4dc-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db4dc-116">See also</span></span>

- [<span data-ttu-id="db4dc-117">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="db4dc-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="db4dc-118">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="db4dc-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="db4dc-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="db4dc-119">ALink API</span></span>](index.md)
