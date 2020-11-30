---
title: 如何：序列化对象
description: 本文演示如何序列化对象。 选择 XML 流的传输格式，即它是作为流还是作为文件进行存储。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
ms.assetid: a1207d05-32b2-4953-8582-959607991227
ms.openlocfilehash: ce8510a987f75ed4110a44ffa9f2ac813d36a5be
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678891"
---
# <a name="how-to-serialize-an-object"></a><span data-ttu-id="22d08-104">如何：序列化对象</span><span class="sxs-lookup"><span data-stu-id="22d08-104">How to: Serialize an Object</span></span>

<span data-ttu-id="22d08-105">要序列化对象，首先应创建要序列化的对象，然后设置其公共属性和字段。</span><span class="sxs-lookup"><span data-stu-id="22d08-105">To serialize an object, first create the object that is to be serialized and set its public properties and fields.</span></span> <span data-ttu-id="22d08-106">为此，必须确定 XML 流的传输格式，即它是作为流还是作为文件进行存储。</span><span class="sxs-lookup"><span data-stu-id="22d08-106">To do this, you must determine the transport format in which the XML stream is to be stored, either as a stream or as a file.</span></span> <span data-ttu-id="22d08-107">例如，如果 XML 流必须以永久形式保存，则应创建 <xref:System.IO.FileStream> 对象。</span><span class="sxs-lookup"><span data-stu-id="22d08-107">For example, if the XML stream must be saved in a permanent form, create a <xref:System.IO.FileStream> object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="22d08-108">有关 XML 序列化的更多示例，请参见 [XML 序列化示例](examples-of-xml-serialization.md)。</span><span class="sxs-lookup"><span data-stu-id="22d08-108">For more examples of XML serialization, see [Examples of XML Serialization](examples-of-xml-serialization.md).</span></span>  
  
### <a name="to-serialize-an-object"></a><span data-ttu-id="22d08-109">序列化对象</span><span class="sxs-lookup"><span data-stu-id="22d08-109">To serialize an object</span></span>  
  
1. <span data-ttu-id="22d08-110">创建对象并设置其公共字段和属性。</span><span class="sxs-lookup"><span data-stu-id="22d08-110">Create the object and set its public fields and properties.</span></span>  
  
2. <span data-ttu-id="22d08-111">使用对象的类型构造 <xref:System.Xml.Serialization.XmlSerializer>。</span><span class="sxs-lookup"><span data-stu-id="22d08-111">Construct a <xref:System.Xml.Serialization.XmlSerializer> using the type of the object.</span></span> <span data-ttu-id="22d08-112">有关更多信息，请参见 <xref:System.Xml.Serialization.XmlSerializer> 类构造函数。</span><span class="sxs-lookup"><span data-stu-id="22d08-112">For more information, see the <xref:System.Xml.Serialization.XmlSerializer> class constructors.</span></span>  
  
3. <span data-ttu-id="22d08-113">调用 <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> 方法生成对象的公共属性和字段的 XML 流或文件表示形式。</span><span class="sxs-lookup"><span data-stu-id="22d08-113">Call the <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> method to generate either an XML stream or a file representation of the object's public properties and fields.</span></span> <span data-ttu-id="22d08-114">下面的示例将创建一个文件。</span><span class="sxs-lookup"><span data-stu-id="22d08-114">The following example creates a file.</span></span>  
  
    ```vb  
    Dim myObject As MySerializableClass = New MySerializableClass()  
    ' Insert code to set properties and fields of the object.  
    Dim mySerializer As XmlSerializer = New XmlSerializer(GetType(MySerializableClass))  
    ' To write to a file, create a StreamWriter object.  
    Dim myWriter As StreamWriter = New StreamWriter("myFileName.xml")  
    mySerializer.Serialize(myWriter, myObject)  
    myWriter.Close()  
    ```  
  
    ```csharp  
    MySerializableClass myObject = new MySerializableClass();  
    // Insert code to set properties and fields of the object.  
    XmlSerializer mySerializer = new
    XmlSerializer(typeof(MySerializableClass));  
    // To write to a file, create a StreamWriter object.  
    StreamWriter myWriter = new StreamWriter("myFileName.xml");  
    mySerializer.Serialize(myWriter, myObject);  
    myWriter.Close();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="22d08-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="22d08-115">See also</span></span>

- [<span data-ttu-id="22d08-116">XML 序列化简介</span><span class="sxs-lookup"><span data-stu-id="22d08-116">Introducing XML Serialization</span></span>](introducing-xml-serialization.md)
- [<span data-ttu-id="22d08-117">如何：反序列化对象</span><span class="sxs-lookup"><span data-stu-id="22d08-117">How to: Deserialize an Object</span></span>](how-to-deserialize-an-object.md)
