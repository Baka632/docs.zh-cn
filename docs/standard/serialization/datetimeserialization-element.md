---
title: <dateTimeSerialization> 元素
description: 本文介绍 <dateTimeSerialization> 元素，该元素可确定 DateTime 对象的序列化模式。
ms.date: 03/30/2017
helpviewer_keywords:
- dateTimeSerialization element
- XML serialization, configuration
- <dateTimeSerialization> element
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
ms.openlocfilehash: 1623517e66955c14b7e738c860ec16086fe30429
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678969"
---
# <a name="datetimeserialization-element"></a><span data-ttu-id="950c1-103">\<dateTimeSerialization> 元素</span><span class="sxs-lookup"><span data-stu-id="950c1-103">\<dateTimeSerialization> Element</span></span>

<span data-ttu-id="950c1-104">确定 <xref:System.DateTime> 对象的序列化模式。</span><span class="sxs-lookup"><span data-stu-id="950c1-104">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>  
  
 \<configuration>  
\<dateTimeSerialization>  
  
## <a name="syntax"></a><span data-ttu-id="950c1-105">语法</span><span class="sxs-lookup"><span data-stu-id="950c1-105">Syntax</span></span>  
  
```xml  
<dateTimeSerialization  
    mode = "Roundtrip|Local"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="950c1-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="950c1-106">Attributes and Elements</span></span>  

 <span data-ttu-id="950c1-107">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="950c1-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="950c1-108">特性</span><span class="sxs-lookup"><span data-stu-id="950c1-108">Attributes</span></span>  
  
|<span data-ttu-id="950c1-109">特性</span><span class="sxs-lookup"><span data-stu-id="950c1-109">Attributes</span></span>|<span data-ttu-id="950c1-110">描述</span><span class="sxs-lookup"><span data-stu-id="950c1-110">Description</span></span>|  
|----------------|-----------------|  
|`mode`|<span data-ttu-id="950c1-111">可选。</span><span class="sxs-lookup"><span data-stu-id="950c1-111">Optional.</span></span> <span data-ttu-id="950c1-112">指定序列化模式。</span><span class="sxs-lookup"><span data-stu-id="950c1-112">Specifies the serialization mode.</span></span> <span data-ttu-id="950c1-113">设置为 <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> 值之一。</span><span class="sxs-lookup"><span data-stu-id="950c1-113">Set to one of the <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> values.</span></span> <span data-ttu-id="950c1-114">默认值为 RoundTrip。</span><span class="sxs-lookup"><span data-stu-id="950c1-114">The default is **RoundTrip**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="950c1-115">子元素</span><span class="sxs-lookup"><span data-stu-id="950c1-115">Child Elements</span></span>  

 <span data-ttu-id="950c1-116">无。</span><span class="sxs-lookup"><span data-stu-id="950c1-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="950c1-117">父元素</span><span class="sxs-lookup"><span data-stu-id="950c1-117">Parent Elements</span></span>  
  
|<span data-ttu-id="950c1-118">元素</span><span class="sxs-lookup"><span data-stu-id="950c1-118">Element</span></span>|<span data-ttu-id="950c1-119">描述</span><span class="sxs-lookup"><span data-stu-id="950c1-119">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="950c1-120">system.xml.serialization</span><span class="sxs-lookup"><span data-stu-id="950c1-120">system.xml.serialization</span></span>|<span data-ttu-id="950c1-121">用于控制 XML 序列化的顶级元素。</span><span class="sxs-lookup"><span data-stu-id="950c1-121">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="950c1-122">备注</span><span class="sxs-lookup"><span data-stu-id="950c1-122">Remarks</span></span>  

<span data-ttu-id="950c1-123">将此属性设置为 Local 时，<xref:System.DateTime> 对象始终设置为本地时间格式。</span><span class="sxs-lookup"><span data-stu-id="950c1-123">When this property is set to **Local**, <xref:System.DateTime> objects are always formatted as the local time.</span></span> <span data-ttu-id="950c1-124">即，序列化的数据中总是包含本地时区信息。</span><span class="sxs-lookup"><span data-stu-id="950c1-124">That is, local time zone information is always included with the serialized data.</span></span>
  
<span data-ttu-id="950c1-125">将此属性设置为 Roundtrip 时，系统会检查 <xref:System.DateTime> 对象以确定这些对象位于本地时区、UTC 时区还是未指定的时区中。</span><span class="sxs-lookup"><span data-stu-id="950c1-125">When this property is set to **Roundtrip**, <xref:System.DateTime> objects are examined to determine whether they are in the local, UTC, or an unspecified time zone.</span></span> <span data-ttu-id="950c1-126">随后会序列化 <xref:System.DateTime> 对象并保留该信息。</span><span class="sxs-lookup"><span data-stu-id="950c1-126">The <xref:System.DateTime> objects are then serialized in such a way that this information is preserved.</span></span> <span data-ttu-id="950c1-127">这是默认行为，建议为所有不与 Framework 的较早版本通信的新应用程序使用此行为。</span><span class="sxs-lookup"><span data-stu-id="950c1-127">This is the default behavior and is the recommended behavior for all new applications that do not communicate with older versions of the framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="950c1-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="950c1-128">See also</span></span>

- <xref:System.DateTime>
- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="950c1-129">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="950c1-129">Configuration File Schema</span></span>](../../framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="950c1-130">\<schemaImporterExtensions> 元素</span><span class="sxs-lookup"><span data-stu-id="950c1-130">\<schemaImporterExtensions> Element</span></span>](schemaimporterextensions-element.md)
- <span data-ttu-id="950c1-131">[\<add> 的 \<schemaImporterExtensions>](add-element-for-schemaimporterextensions.md) 元素</span><span class="sxs-lookup"><span data-stu-id="950c1-131">[\<add> Element for \<schemaImporterExtensions>](add-element-for-schemaimporterextensions.md)</span></span>
- [<span data-ttu-id="950c1-132">\<system.xml.serialization> 元素</span><span class="sxs-lookup"><span data-stu-id="950c1-132">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)
