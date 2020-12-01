---
title: 如何：在独立存储中读取和写入文件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- files, isolated storage
- reading data
- storing data using isolated storage, reading and writing to files
- writing to files within store
- data storage using isolated storage, reading and writing to files
- reading files within store
- isolated storage, reading and writing to files
- data stores, reading and writing to files
- stores, reading and writing to files
ms.assetid: f977ebdc-1b55-475a-bc3d-3376470b08ae
ms.openlocfilehash: 3a8b783cf2cce93cb26b11823d9f565961376ca3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734590"
---
# <a name="how-to-read-and-write-to-files-in-isolated-storage"></a><span data-ttu-id="a496c-102">如何：在独立存储中读取和写入文件</span><span class="sxs-lookup"><span data-stu-id="a496c-102">How to: Read and Write to Files in Isolated Storage</span></span>

<span data-ttu-id="a496c-103">若要读取或写入独立存储区的文件，请使用包含流读取器（<xref:System.IO.IsolatedStorage.IsolatedStorageFileStream> 对象）或流编写器（<xref:System.IO.StreamReader> 对象）的 <xref:System.IO.StreamWriter> 对象。</span><span class="sxs-lookup"><span data-stu-id="a496c-103">To read from, or write to, a file in an isolated store, use an <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream> object with a stream reader (<xref:System.IO.StreamReader> object) or stream writer (<xref:System.IO.StreamWriter> object).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a496c-104">示例</span><span class="sxs-lookup"><span data-stu-id="a496c-104">Example</span></span>  

 <span data-ttu-id="a496c-105">下面的代码示例获取独立存储区，并检查存储区中是否存在 TestStore.txt 文件。</span><span class="sxs-lookup"><span data-stu-id="a496c-105">The following code example obtains an isolated store and checks whether a file named TestStore.txt exists in the store.</span></span> <span data-ttu-id="a496c-106">如果不存在，则创建该文件并将“Hello Isolated Storage”写入该文件。</span><span class="sxs-lookup"><span data-stu-id="a496c-106">If it doesn't exist, it creates the file and writes "Hello Isolated Storage" to the file.</span></span> <span data-ttu-id="a496c-107">如果 TestStore.txt 已存在，则示例代码会读取该文件。</span><span class="sxs-lookup"><span data-stu-id="a496c-107">If TestStore.txt already exists, the example code reads from the file.</span></span>  
  
 [!code-csharp[Conceptual.IsolatedStorage#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source5.cs#5)]
 [!code-vb[Conceptual.IsolatedStorage#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source5.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="a496c-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a496c-108">See also</span></span>

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>
- <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>
- <xref:System.IO.FileMode?displayProperty=nameWithType>
- <xref:System.IO.FileAccess?displayProperty=nameWithType>
- <xref:System.IO.StreamReader?displayProperty=nameWithType>
- <xref:System.IO.StreamWriter?displayProperty=nameWithType>
- [<span data-ttu-id="a496c-109">文件和流 I/O</span><span class="sxs-lookup"><span data-stu-id="a496c-109">File and Stream I/O</span></span>](index.md)
- [<span data-ttu-id="a496c-110">独立存储</span><span class="sxs-lookup"><span data-stu-id="a496c-110">Isolated Storage</span></span>](isolated-storage.md)
