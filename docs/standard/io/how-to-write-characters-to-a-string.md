---
title: 如何：向字符串写入字符
ms.date: 01/21/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data streams, writing characters to string
- writing characters to strings
- streams, writing characters to strings
- I/O [.NET], writing characters to strings
ms.assetid: 1222cbeb-0760-44bf-9888-914a2a37174b
ms.openlocfilehash: d4a6bbc77a9feb16293fc88e1598d124d8d2d75d
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829721"
---
# <a name="how-to-write-characters-to-a-string"></a><span data-ttu-id="318ea-102">如何：向字符串写入字符</span><span class="sxs-lookup"><span data-stu-id="318ea-102">How to: Write characters to a string</span></span>

<span data-ttu-id="318ea-103">下面的代码示例从字符数组以同步或异步方式向字符串写入字符。</span><span class="sxs-lookup"><span data-stu-id="318ea-103">The following code examples write characters synchronously or asynchronously from a character array into a string.</span></span>  
  
## <a name="example-write-characters-synchronously-in-a-console-app"></a><span data-ttu-id="318ea-104">示例：在控制台应用中以同步方式编写字符</span><span class="sxs-lookup"><span data-stu-id="318ea-104">Example: Write characters synchronously in a console app</span></span>  
 <span data-ttu-id="318ea-105">下面的示例使用 <xref:System.IO.StringWriter> 将五个字符同步写入 <xref:System.Text.StringBuilder> 对象。</span><span class="sxs-lookup"><span data-stu-id="318ea-105">The following example uses a <xref:System.IO.StringWriter> to write five characters synchronously to a <xref:System.Text.StringBuilder> object.</span></span>
  
 [!code-csharp[Conceptual.StringBuilder#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/example2.cs#9)]
 [!code-vb[Conceptual.StringBuilder#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/example2.vb#9)]  
  
## <a name="example-write-characters-asynchronously-in-a-wpf-app"></a><span data-ttu-id="318ea-106">示例：在 WPF 应用中异步写入字符</span><span class="sxs-lookup"><span data-stu-id="318ea-106">Example: Write characters asynchronously in a WPF app</span></span>
 <span data-ttu-id="318ea-107">下一个示例是 WPF 应用背后的代码。</span><span class="sxs-lookup"><span data-stu-id="318ea-107">The next example is the code behind a WPF app.</span></span> <span data-ttu-id="318ea-108">在窗口加载时，示例从 <xref:System.Windows.Controls.TextBox> 控件异步读取所有字符，并将其存储在数组中。</span><span class="sxs-lookup"><span data-stu-id="318ea-108">On window load, the example asynchronously reads all characters from a <xref:System.Windows.Controls.TextBox> control and stores them in an array.</span></span> <span data-ttu-id="318ea-109">随后，它以异步方式将每个字母或空格字符写入单独的 <xref:System.Windows.Controls.TextBlock> 控件行。</span><span class="sxs-lookup"><span data-stu-id="318ea-109">It then asynchronously writes each letter or white-space character to a separate line of a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
 [!code-csharp[StreamReaderWriter](../../../samples/snippets/csharp/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.cs)]
 [!code-vb[StreamReaderWriter](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="318ea-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="318ea-110">See also</span></span>

- <xref:System.IO.StringWriter>  
- <xref:System.IO.StringWriter.Write%2A?displayProperty=nameWithType>  
- <xref:System.Text.StringBuilder>  
- [<span data-ttu-id="318ea-111">文件和流 I/O</span><span class="sxs-lookup"><span data-stu-id="318ea-111">File and stream I/O</span></span>](index.md)  
- [<span data-ttu-id="318ea-112">异步文件 I/O</span><span class="sxs-lookup"><span data-stu-id="318ea-112">Asynchronous file I/O</span></span>](asynchronous-file-i-o.md)  
- [<span data-ttu-id="318ea-113">如何：枚举目录和文件</span><span class="sxs-lookup"><span data-stu-id="318ea-113">How to: Enumerate directories and files</span></span>](how-to-enumerate-directories-and-files.md)  
- [<span data-ttu-id="318ea-114">如何：对新建的数据文件进行读取和写入</span><span class="sxs-lookup"><span data-stu-id="318ea-114">How to: Read and write to a newly created data file</span></span>](how-to-read-and-write-to-a-newly-created-data-file.md)  
- [<span data-ttu-id="318ea-115">如何：打开并追加到日志文件</span><span class="sxs-lookup"><span data-stu-id="318ea-115">How to: Open and append to a log file</span></span>](how-to-open-and-append-to-a-log-file.md)  
- [<span data-ttu-id="318ea-116">如何：从文件中读取文本</span><span class="sxs-lookup"><span data-stu-id="318ea-116">How to: Read text from a file</span></span>](how-to-read-text-from-a-file.md)  
- [<span data-ttu-id="318ea-117">如何：将文本写入文件</span><span class="sxs-lookup"><span data-stu-id="318ea-117">How to: Write text to a file</span></span>](how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="318ea-118">如何：从字符串中读取字符</span><span class="sxs-lookup"><span data-stu-id="318ea-118">How to: Read characters from a string</span></span>](how-to-read-characters-from-a-string.md)
