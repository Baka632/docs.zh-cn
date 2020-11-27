---
title: XmlDictionaryReaderQuotas
ms.date: 03/30/2017
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
ms.openlocfilehash: c5bb7813a680c89eb90f4ccf4ed6f09a831c8095
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262198"
---
# <a name="xmldictionaryreaderquotas"></a><span data-ttu-id="213a2-102">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="213a2-102">XmlDictionaryReaderQuotas</span></span>

<span data-ttu-id="213a2-103">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="213a2-103">XmlDictionaryReaderQuotas</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="213a2-104">语法</span><span class="sxs-lookup"><span data-stu-id="213a2-104">Syntax</span></span>  
  
```csharp
class XmlDictionaryReaderQuotas  
{  
  sint32 MaxArrayLength;  
  sint32 MaxBytesPerRead;  
  sint32 MaxDepth;  
  sint32 MaxNameTableCharCount;  
  sint32 MaxStringContentLength;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="213a2-105">方法</span><span class="sxs-lookup"><span data-stu-id="213a2-105">Methods</span></span>  

 <span data-ttu-id="213a2-106">XmlDictionaryReaderQuotas 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="213a2-106">The XmlDictionaryReaderQuotas class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="213a2-107">属性</span><span class="sxs-lookup"><span data-stu-id="213a2-107">Properties</span></span>  

 <span data-ttu-id="213a2-108">XmlDictionaryReaderQuotas 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="213a2-108">The XmlDictionaryReaderQuotas class has the following properties:</span></span>  
  
### <a name="maxarraylength"></a><span data-ttu-id="213a2-109">MaxArrayLength</span><span class="sxs-lookup"><span data-stu-id="213a2-109">MaxArrayLength</span></span>  

 <span data-ttu-id="213a2-110">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="213a2-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="213a2-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="213a2-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="213a2-112">允许的最大数组长度。</span><span class="sxs-lookup"><span data-stu-id="213a2-112">The maximum allowed array length.</span></span>  
  
### <a name="maxbytesperread"></a><span data-ttu-id="213a2-113">MaxBytesPerRead</span><span class="sxs-lookup"><span data-stu-id="213a2-113">MaxBytesPerRead</span></span>  

 <span data-ttu-id="213a2-114">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="213a2-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="213a2-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="213a2-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="213a2-116">允许为每次读取返回的最大字节数。</span><span class="sxs-lookup"><span data-stu-id="213a2-116">The maximum allowed bytes returned for each read.</span></span>  
  
### <a name="maxdepth"></a><span data-ttu-id="213a2-117">MaxDepth</span><span class="sxs-lookup"><span data-stu-id="213a2-117">MaxDepth</span></span>  

 <span data-ttu-id="213a2-118">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="213a2-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="213a2-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="213a2-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="213a2-120">每次读取的最大嵌套节点深度。</span><span class="sxs-lookup"><span data-stu-id="213a2-120">The maximum nested node depth for each read.</span></span>  
  
### <a name="maxnametablecharcount"></a><span data-ttu-id="213a2-121">MaxNameTableCharCount</span><span class="sxs-lookup"><span data-stu-id="213a2-121">MaxNameTableCharCount</span></span>  

 <span data-ttu-id="213a2-122">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="213a2-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="213a2-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="213a2-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="213a2-124">表名称中允许的最大字符数。</span><span class="sxs-lookup"><span data-stu-id="213a2-124">The maximum characters allowed in a table name.</span></span>  
  
### <a name="maxstringcontentlength"></a><span data-ttu-id="213a2-125">MaxStringContentLength</span><span class="sxs-lookup"><span data-stu-id="213a2-125">MaxStringContentLength</span></span>  

 <span data-ttu-id="213a2-126">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="213a2-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="213a2-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="213a2-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="213a2-128">XML 元素内容中允许包含的最大字符数。</span><span class="sxs-lookup"><span data-stu-id="213a2-128">The maximum characters allowed in XML element content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="213a2-129">要求</span><span class="sxs-lookup"><span data-stu-id="213a2-129">Requirements</span></span>  
  
|<span data-ttu-id="213a2-130">MOF</span><span class="sxs-lookup"><span data-stu-id="213a2-130">MOF</span></span>|<span data-ttu-id="213a2-131">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="213a2-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="213a2-132">命名空间</span><span class="sxs-lookup"><span data-stu-id="213a2-132">Namespace</span></span>|<span data-ttu-id="213a2-133">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="213a2-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="213a2-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="213a2-134">See also</span></span>

- <xref:System.Xml.XmlDictionaryReaderQuotas>
- <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
