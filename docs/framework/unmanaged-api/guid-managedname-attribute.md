---
title: GUID_ManagedName 特性
ms.date: 03/30/2017
api_name:
- GUID_ManagedName
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GUID_ManagedName
helpviewer_keywords:
- GUID_ManagedName attribute
ms.assetid: 11e18095-e444-47bc-aff6-b887ac5dc01e
topic_type:
- apiref
ms.openlocfilehash: 0127b6894f1095521f1b24fc8c0424dc7db824b3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721044"
---
# <a name="guid_managedname-attribute"></a><span data-ttu-id="53746-102">GUID_ManagedName 特性</span><span class="sxs-lookup"><span data-stu-id="53746-102">GUID_ManagedName Attribute</span></span>

<span data-ttu-id="53746-103">定义一个自定义接口特性，该特性指定组件对象模型 (COM) 库的托管命名空间名称。</span><span class="sxs-lookup"><span data-stu-id="53746-103">Defines a custom interface attribute that specifies the managed namespace name for a component object model (COM) library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53746-104">语法</span><span class="sxs-lookup"><span data-stu-id="53746-104">Syntax</span></span>  
  
```idl
[  
   custom(GUID_ManagedName, value)  
]  
```  
  
## <a name="parameters"></a><span data-ttu-id="53746-105">参数</span><span class="sxs-lookup"><span data-stu-id="53746-105">Parameters</span></span>  

 `value`  
 <span data-ttu-id="53746-106">库的托管命名空间名称。</span><span class="sxs-lookup"><span data-stu-id="53746-106">The managed namespace name for the library.</span></span>  
  
## <a name="definition"></a><span data-ttu-id="53746-107">定义</span><span class="sxs-lookup"><span data-stu-id="53746-107">Definition</span></span>  

 <span data-ttu-id="53746-108">`GUID_ManagedName` 在 Cor 中定义，如下所示：</span><span class="sxs-lookup"><span data-stu-id="53746-108">`GUID_ManagedName` is defined in Cor.h as follows:</span></span>  
  
```cpp
// {0F21F359-AB84-41e8-9A78-36D110E6D2F9}  
EXTERN_GUID(GUID_ManagedName, 0xf21f359, 0xab84, 0x41e8, 0x9a, 0x78, 0x36, 0xd1, 0x10, 0xe6, 0xd2, 0xf9);  
```  
  
## <a name="remarks"></a><span data-ttu-id="53746-109">注解</span><span class="sxs-lookup"><span data-stu-id="53746-109">Remarks</span></span>  

 <span data-ttu-id="53746-110">自定义接口特性为类型库中的对象定义元数据。</span><span class="sxs-lookup"><span data-stu-id="53746-110">A custom interface attribute defines metadata for an object in the type library.</span></span>  
  
 <span data-ttu-id="53746-111">使用 <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType> 或 <xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType> 从属性中检索托管名称。</span><span class="sxs-lookup"><span data-stu-id="53746-111">Use <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType> or <xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType> to retrieve the managed name from the attribute.</span></span>  
  
 <span data-ttu-id="53746-112">有关详细信息，请参阅 Visual C++ 参考文档中的 [接口特性](/cpp/windows/attributes/interface-attributes) 。</span><span class="sxs-lookup"><span data-stu-id="53746-112">For more information, see [Interface Attributes](/cpp/windows/attributes/interface-attributes) in the Visual C++ reference documentation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53746-113">示例</span><span class="sxs-lookup"><span data-stu-id="53746-113">Example</span></span>  

 <span data-ttu-id="53746-114">下面的示例演示了一个使用属性的库定义 `GUID_ManagedName` 。</span><span class="sxs-lookup"><span data-stu-id="53746-114">The following example shows a library definition using the `GUID_ManagedName` attribute.</span></span>  
  
```idl
[  
   ...  
   custom(GUID_ManagedName, Microsoft.VisualStudio.CommandBars.dll")  
]  
library Microsoft_VisualStudio_CommandBars  
{  
   ...  
}  
```  
  
## <a name="requirements"></a><span data-ttu-id="53746-115">要求</span><span class="sxs-lookup"><span data-stu-id="53746-115">Requirements</span></span>  

 <span data-ttu-id="53746-116">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="53746-116">**Header:** Cor.h</span></span>
