---
title: 如何在十六进制字符串与数值类型之间转换 - C# 编程指南
description: 了解如何在十六进制字符串与数值类型之间转换。 查看代码示例和其他可用资源。
ms.date: 07/20/2015
helpviewer_keywords:
- hexadecimal strings [C#], converting to numeric type
- conversions [C#], hexidecimal strings
- strings [C#], converting hexadecimal strings
- hexadecimal strings [C#]
ms.topic: how-to
ms.custom: contperf-fy21q2
ms.assetid: 7115c49f-7d1d-40c3-8bd9-aae0cc1d46b6
ms.openlocfilehash: 35cf1af661071c70b8d68de2e47ce555be7b9fef
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2021
ms.locfileid: "98025402"
---
# <a name="how-to-convert-between-hexadecimal-strings-and-numeric-types-c-programming-guide"></a><span data-ttu-id="25045-104">如何在十六进制字符串与数值类型之间转换（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="25045-104">How to convert between hexadecimal strings and numeric types (C# Programming Guide)</span></span>

<span data-ttu-id="25045-105">以下示例演示如何执行下列任务：</span><span class="sxs-lookup"><span data-stu-id="25045-105">These examples show you how to perform the following tasks:</span></span>  
  
- <span data-ttu-id="25045-106">获取[字符串](../../language-reference/builtin-types/reference-types.md)中每个字符的十六进制值。</span><span class="sxs-lookup"><span data-stu-id="25045-106">Obtain the hexadecimal value of each character in a [string](../../language-reference/builtin-types/reference-types.md).</span></span>  
  
- <span data-ttu-id="25045-107">获取与十六进制字符串中的每个值对应的 [char](../../language-reference/builtin-types/char.md)。</span><span class="sxs-lookup"><span data-stu-id="25045-107">Obtain the [char](../../language-reference/builtin-types/char.md) that corresponds to each value in a hexadecimal string.</span></span>  
  
- <span data-ttu-id="25045-108">将十六进制 `string` 转换为 [int](../../language-reference/builtin-types/integral-numeric-types.md)。</span><span class="sxs-lookup"><span data-stu-id="25045-108">Convert a hexadecimal `string` to an [int](../../language-reference/builtin-types/integral-numeric-types.md).</span></span>  
  
- <span data-ttu-id="25045-109">将十六进制 `string` 转换为 [float](../../language-reference/builtin-types/floating-point-numeric-types.md)。</span><span class="sxs-lookup"><span data-stu-id="25045-109">Convert a hexadecimal `string` to a [float](../../language-reference/builtin-types/floating-point-numeric-types.md).</span></span>  
  
- <span data-ttu-id="25045-110">将[字节](../../language-reference/builtin-types/integral-numeric-types.md)数组转换为十六进制 `string`。</span><span class="sxs-lookup"><span data-stu-id="25045-110">Convert a [byte](../../language-reference/builtin-types/integral-numeric-types.md) array to a hexadecimal `string`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25045-111">示例</span><span class="sxs-lookup"><span data-stu-id="25045-111">Example</span></span>  

 <span data-ttu-id="25045-112">此示例输出 `string` 中每个字符的十六进制值。</span><span class="sxs-lookup"><span data-stu-id="25045-112">This example outputs the hexadecimal value of each character in a `string`.</span></span> <span data-ttu-id="25045-113">首先，将 `string` 分析为字符数组。</span><span class="sxs-lookup"><span data-stu-id="25045-113">First it parses the `string` to an array of characters.</span></span> <span data-ttu-id="25045-114">然后，对每个字符调用 <xref:System.Convert.ToInt32%28System.Char%29>获取相应的数值。</span><span class="sxs-lookup"><span data-stu-id="25045-114">Then it calls <xref:System.Convert.ToInt32%28System.Char%29> on each character to obtain its numeric value.</span></span> <span data-ttu-id="25045-115">最后，在 `string` 中将数字的格式设置为十六进制表示形式。</span><span class="sxs-lookup"><span data-stu-id="25045-115">Finally, it formats the number as its hexadecimal representation in a `string`.</span></span>  
  
 [!code-csharp[csProgGuideTypes#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#30)]  
  
## <a name="example"></a><span data-ttu-id="25045-116">示例</span><span class="sxs-lookup"><span data-stu-id="25045-116">Example</span></span>  

 <span data-ttu-id="25045-117">此示例分析十六进制值的 `string` 并输出对应于每个十六进制值的字符。</span><span class="sxs-lookup"><span data-stu-id="25045-117">This example parses a `string` of hexadecimal values and outputs the character corresponding to each hexadecimal value.</span></span> <span data-ttu-id="25045-118">首先，调用 [Split(Char\[\])](xref:System.String.Split(System.Char[])) 方法以获取每个十六进制值作为数组中的单个 `string`。</span><span class="sxs-lookup"><span data-stu-id="25045-118">First it calls the [Split(Char\[\])](xref:System.String.Split(System.Char[])) method to obtain each hexadecimal value as an individual `string` in an array.</span></span> <span data-ttu-id="25045-119">然后，调用 <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29>将十六进制值转换为表示为 [int](../../language-reference/builtin-types/integral-numeric-types.md) 的十进制值。示例中演示了 2 种不同方法，用于获取对应于该字符代码的字符。</span><span class="sxs-lookup"><span data-stu-id="25045-119">Then it calls <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29> to convert the hexadecimal value to a decimal value represented as an [int](../../language-reference/builtin-types/integral-numeric-types.md). It shows two different ways to obtain the character corresponding to that character code.</span></span> <span data-ttu-id="25045-120">第 1 种方法是使用 <xref:System.Char.ConvertFromUtf32%28System.Int32%29>，它将对应于整型参数的字符作为 `string` 返回。</span><span class="sxs-lookup"><span data-stu-id="25045-120">The first technique uses <xref:System.Char.ConvertFromUtf32%28System.Int32%29>, which returns the character corresponding to the integer argument as a `string`.</span></span> <span data-ttu-id="25045-121">第 2 种方法是将 `int` 显式转换为 [char](../../language-reference/builtin-types/char.md)。</span><span class="sxs-lookup"><span data-stu-id="25045-121">The second technique explicitly casts the `int` to a [char](../../language-reference/builtin-types/char.md).</span></span>  
  
 [!code-csharp[csProgGuideTypes#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#31)]  
  
## <a name="example"></a><span data-ttu-id="25045-122">示例</span><span class="sxs-lookup"><span data-stu-id="25045-122">Example</span></span>  

 <span data-ttu-id="25045-123">此示例演示了将十六进制 `string` 转换为整数的另一种方法，即调用 <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29> 方法。</span><span class="sxs-lookup"><span data-stu-id="25045-123">This example shows another way to convert a hexadecimal `string` to an integer, by calling the <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29> method.</span></span>  
  
 [!code-csharp[csProgGuideTypes#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#32)]  
  
## <a name="example"></a><span data-ttu-id="25045-124">示例</span><span class="sxs-lookup"><span data-stu-id="25045-124">Example</span></span>  

 <span data-ttu-id="25045-125">下面的示例演示了如何使用 <xref:System.BitConverter?displayProperty=nameWithType> 类和 <xref:System.UInt32.Parse%2A?displayProperty=nameWithType> 方法将十六进制 `string` 转换为 [float](../../language-reference/builtin-types/floating-point-numeric-types.md)。</span><span class="sxs-lookup"><span data-stu-id="25045-125">The following example shows how to convert a hexadecimal `string` to a [float](../../language-reference/builtin-types/floating-point-numeric-types.md) by using the <xref:System.BitConverter?displayProperty=nameWithType> class and the <xref:System.UInt32.Parse%2A?displayProperty=nameWithType> method.</span></span>  
  
 [!code-csharp[csProgGuideTypes#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#39)]  
  
## <a name="example"></a><span data-ttu-id="25045-126">示例</span><span class="sxs-lookup"><span data-stu-id="25045-126">Example</span></span>  

 <span data-ttu-id="25045-127">下面的示例演示了如何使用 <xref:System.BitConverter?displayProperty=nameWithType> 类将[字节](../../language-reference/builtin-types/integral-numeric-types.md)数组转换为十六进制字符串。</span><span class="sxs-lookup"><span data-stu-id="25045-127">The following example shows how to convert a [byte](../../language-reference/builtin-types/integral-numeric-types.md) array to a hexadecimal string by using the <xref:System.BitConverter?displayProperty=nameWithType> class.</span></span>  
  
 [!code-csharp[csProgGuideTypes#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#38)]  
  
## <a name="example"></a><span data-ttu-id="25045-128">示例</span><span class="sxs-lookup"><span data-stu-id="25045-128">Example</span></span>  

 <span data-ttu-id="25045-129">下面的示例演示如何通过调用 .NET 5.0 中引入的 <xref:System.Convert.ToHexString%2A?displayProperty=nameWithType> 方法，将[字节](../../language-reference/builtin-types/integral-numeric-types.md)数组转换为十六进制字符串。</span><span class="sxs-lookup"><span data-stu-id="25045-129">The following example shows how to convert a [byte](../../language-reference/builtin-types/integral-numeric-types.md) array to a hexadecimal string by calling the <xref:System.Convert.ToHexString%2A?displayProperty=nameWithType> method introduced in .NET 5.0.</span></span>
  
 [!code-csharp[csProgGuideTypes#47](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#47)]  
  
## <a name="see-also"></a><span data-ttu-id="25045-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="25045-130">See also</span></span>

- [<span data-ttu-id="25045-131">标准数字格式字符串</span><span class="sxs-lookup"><span data-stu-id="25045-131">Standard Numeric Format Strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
- [<span data-ttu-id="25045-132">类型</span><span class="sxs-lookup"><span data-stu-id="25045-132">Types</span></span>](./index.md)
- [<span data-ttu-id="25045-133">如何确定字符串是否表示数值</span><span class="sxs-lookup"><span data-stu-id="25045-133">How to determine whether a string represents a numeric value</span></span>](../strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)
