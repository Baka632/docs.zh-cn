---
title: XML 数据类型的转换
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a2aa99ba-8239-4818-9281-f1d72ee40bde
ms.openlocfilehash: d7ee7447ab7a8be1bad0d087dba5fc2afaa878e8
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830969"
---
# <a name="conversion-of-xml-data-types"></a><span data-ttu-id="e176d-102">XML 数据类型的转换</span><span class="sxs-lookup"><span data-stu-id="e176d-102">Conversion of XML Data Types</span></span>
<span data-ttu-id="e176d-103">XmlConvert 类中的大多数方法都可用于在字符串和强类型格式之间转换数据。</span><span class="sxs-lookup"><span data-stu-id="e176d-103">The majority of the methods found in an **XmlConvert** class are used to convert data between strings and strongly typed formats.</span></span> <span data-ttu-id="e176d-104">这些方法与区域设置无关。</span><span class="sxs-lookup"><span data-stu-id="e176d-104">Methods are locale independent.</span></span> <span data-ttu-id="e176d-105">这意味着它们在执行转换时不考虑任何区域设置。</span><span class="sxs-lookup"><span data-stu-id="e176d-105">This means that they do not take into account any locale settings when doing conversion.</span></span>  
  
## <a name="reading-string-as-types"></a><span data-ttu-id="e176d-106">将字符串作为类型读取</span><span class="sxs-lookup"><span data-stu-id="e176d-106">Reading String as types</span></span>  
 <span data-ttu-id="e176d-107">下面的示例读取字符串，并将它转换为 DateTime 类型。</span><span class="sxs-lookup"><span data-stu-id="e176d-107">The following sample reads a string and converts it to a **DateTime** type.</span></span>  
  
 <span data-ttu-id="e176d-108">给定以下 XML 输入：</span><span class="sxs-lookup"><span data-stu-id="e176d-108">Given the following XML input:</span></span>  
  
 <span data-ttu-id="e176d-109">**输入**</span><span class="sxs-lookup"><span data-stu-id="e176d-109">**Input**</span></span>  
  
```xml  
<Element>2001-02-27T11:13:23</Element>  
```  
  
 <span data-ttu-id="e176d-110">下面的代码将字符串转换为 DateTime 格式：</span><span class="sxs-lookup"><span data-stu-id="e176d-110">This code converts the string to the **DateTime** format:</span></span>  
  
```vb  
reader.ReadStartElement()  
Dim vDateTime As DateTime = XmlConvert.ToDateTime(reader.ReadString())  
Console.WriteLine(vDateTime)  
```  
  
```csharp  
reader.ReadStartElement();  
DateTime vDateTime = XmlConvert.ToDateTime(reader.ReadString());  
Console.WriteLine(vDateTime);  
```  
  
## <a name="writing-strings-as-types"></a><span data-ttu-id="e176d-111">将字符串作为类型写入</span><span class="sxs-lookup"><span data-stu-id="e176d-111">Writing Strings as types</span></span>  
 <span data-ttu-id="e176d-112">下面的示例读取 Int32，并将它转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="e176d-112">The following sample reads an **Int32** and converts it to a string.</span></span>  
  
 <span data-ttu-id="e176d-113">给定以下 XML 输入：</span><span class="sxs-lookup"><span data-stu-id="e176d-113">Given the following XML input:</span></span>  
  
 <span data-ttu-id="e176d-114">**输入**</span><span class="sxs-lookup"><span data-stu-id="e176d-114">**Input**</span></span>  
  
```xml  
<TestInt32>-2147483648</TestInt32>  
```  
  
 <span data-ttu-id="e176d-115">下面的代码将 Int32 转换为 String：</span><span class="sxs-lookup"><span data-stu-id="e176d-115">This code converts the **Int32** into a **String**:</span></span>  
  
```vb  
Dim vInt32 As Int32 = -2147483648  
writer.WriteElementString("TestInt32", XmlConvert.ToString(vInt32))  
```  
  
```csharp  
Int32 vInt32=-2147483648;  
writer.WriteElementString("TestInt32",XmlConvert.ToString(vInt32));  
```  
  
## <a name="see-also"></a><span data-ttu-id="e176d-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="e176d-116">See also</span></span>

- [<span data-ttu-id="e176d-117">将字符串转换为 .NET Framework 数据类型</span><span class="sxs-lookup"><span data-stu-id="e176d-117">Converting Strings to .NET Framework Data Types</span></span>](converting-strings-to-dotnet-data-types.md)
- [<span data-ttu-id="e176d-118">将 .NET Framework 类型转换为字符串</span><span class="sxs-lookup"><span data-stu-id="e176d-118">Converting .NET Framework Types to Strings</span></span>](converting-dotnet-types-to-strings.md)
