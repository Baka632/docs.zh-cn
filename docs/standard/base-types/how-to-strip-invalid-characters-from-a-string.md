---
title: 如何：从字符串中剥离无效字符
description: 阅读示例，了解如何使用静态 Regex.Replace 方法剥离字符串中可能有害的字符。
ms.date: 06/30/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regular expressions, examples
- cleaning input
- user input, examples
- .NET regular expressions, examples
- regular expressions [.NET], examples
- Regex.Replace method
- stripping invalid characters
- Replace method
- validating user input
ms.assetid: b4319c8a-9032-4129-a9d5-6f6fc28e7f32
ms.openlocfilehash: d6422556ab9c7d2100ea66e6b0dae1ee01e0e434
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683844"
---
# <a name="how-to-strip-invalid-characters-from-a-string"></a><span data-ttu-id="d28fa-103">如何：从字符串中剥离无效字符</span><span class="sxs-lookup"><span data-stu-id="d28fa-103">How to: Strip Invalid Characters from a String</span></span>

<span data-ttu-id="d28fa-104">下面的示例使用静态 <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> 方法，从字符串中剥离无效字符。</span><span class="sxs-lookup"><span data-stu-id="d28fa-104">The following example uses the static <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> method to strip invalid characters from a string.</span></span>  

[!INCLUDE [regex](../../../includes/regex.md)]

## <a name="example"></a><span data-ttu-id="d28fa-105">示例</span><span class="sxs-lookup"><span data-stu-id="d28fa-105">Example</span></span>  

 <span data-ttu-id="d28fa-106">可以使用此示例中定义的 `CleanInput` 方法来剥离在接受用户输入的文本字段中输入的可能有害的字符。</span><span class="sxs-lookup"><span data-stu-id="d28fa-106">You can use the `CleanInput` method defined in this example to strip potentially harmful characters that have been entered into a text field that accepts user input.</span></span> <span data-ttu-id="d28fa-107">在此情况下，`CleanInput` 会剥离所有非字母数字字符（句点 (.)、at 符号 (@) 和连字符 (-) 除外），并返回剩余字符串。</span><span class="sxs-lookup"><span data-stu-id="d28fa-107">In this case, `CleanInput` strips out all nonalphanumeric characters except periods (.), at symbols (@), and hyphens (-), and returns the remaining string.</span></span> <span data-ttu-id="d28fa-108">但是，可以修改正则表达式模式，使其剥离不应包含在输入字符串内的所有字符。</span><span class="sxs-lookup"><span data-stu-id="d28fa-108">However, you can modify the regular expression pattern so that it strips out any characters that should not be included in an input string.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.StripChars#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.StripChars/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.StripChars#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.StripChars/vb/Example.vb#1)]  
  
 <span data-ttu-id="d28fa-109">正则表达式模式 `[^\w\.@-]` 与非单词字符、句点、@ 符号或连字符的任何字符相匹配。</span><span class="sxs-lookup"><span data-stu-id="d28fa-109">The regular expression pattern `[^\w\.@-]` matches any character that is not a word character, a period, an @ symbol, or a hyphen.</span></span> <span data-ttu-id="d28fa-110">单词字符可以是任何字母、十进制数字或标点连接符（如下划线符号）。</span><span class="sxs-lookup"><span data-stu-id="d28fa-110">A word character is any letter, decimal digit, or punctuation connector such as an underscore.</span></span> <span data-ttu-id="d28fa-111">与此模式匹配的任何字符被替换为 <xref:System.String.Empty?displayProperty=nameWithType>（即替换模式定义的字符串）。</span><span class="sxs-lookup"><span data-stu-id="d28fa-111">Any character that matches this pattern is replaced by <xref:System.String.Empty?displayProperty=nameWithType>, which is the string defined by the replacement pattern.</span></span> <span data-ttu-id="d28fa-112">若要允许用户输入中出现其他字符，请将该字符添加到正则表达式模式中的字符类。</span><span class="sxs-lookup"><span data-stu-id="d28fa-112">To allow additional characters in user input, add those characters to the character class in the regular expression pattern.</span></span> <span data-ttu-id="d28fa-113">例如，正则表达式模式 `[^\w\.@-\\%]` 还允许输入字符串中包含百分号和反斜杠。</span><span class="sxs-lookup"><span data-stu-id="d28fa-113">For example, the regular expression pattern `[^\w\.@-\\%]` also allows a percentage symbol and a backslash in an input string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d28fa-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="d28fa-114">See also</span></span>

- [<span data-ttu-id="d28fa-115">.NET 正则表达式</span><span class="sxs-lookup"><span data-stu-id="d28fa-115">.NET Regular Expressions</span></span>](regular-expressions.md)
