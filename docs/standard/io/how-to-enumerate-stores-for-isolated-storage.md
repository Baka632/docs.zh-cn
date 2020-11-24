---
title: 如何：枚举独立存储的存储区
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- enumerating stores
- data storage using isolated storage, enumerating stores
- storing data using isolated storage, enumerating stores
- stores, enumerating
- isolated storage, enumerating stores
- data stores, enumerating
ms.assetid: 0fcf279a-f241-48f0-8034-2e3d331f1fcb
ms.openlocfilehash: 9c7163dda34f254320ab7da86856d8731cd39426
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830761"
---
# <a name="how-to-enumerate-stores-for-isolated-storage"></a><span data-ttu-id="44e43-102">如何：枚举独立存储的存储区</span><span class="sxs-lookup"><span data-stu-id="44e43-102">How to: Enumerate Stores for Isolated Storage</span></span>
<span data-ttu-id="44e43-103">您可以使用 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A?displayProperty=nameWithType> 静态方法枚举当前用户的所有独立存储区。</span><span class="sxs-lookup"><span data-stu-id="44e43-103">You can enumerate all isolated stores for the current user by using the  <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A?displayProperty=nameWithType> static method.</span></span> <span data-ttu-id="44e43-104">该方法采用 <xref:System.IO.IsolatedStorage.IsolatedStorageScope> 值并且返回 <xref:System.IO.IsolatedStorage.IsolatedStorageFile> 枚举器。</span><span class="sxs-lookup"><span data-stu-id="44e43-104">This  method takes an <xref:System.IO.IsolatedStorage.IsolatedStorageScope> value and returns an <xref:System.IO.IsolatedStorage.IsolatedStorageFile> enumerator.</span></span> <span data-ttu-id="44e43-105">若要枚举存储区，您必须具有指定<xref:System.Security.Permissions.IsolatedStorageFilePermission> 值的 <xref:System.Security.Permissions.IsolatedStorageContainment.AdministerIsolatedStorageByUser> 权限。</span><span class="sxs-lookup"><span data-stu-id="44e43-105">To enumerate stores, you must have the <xref:System.Security.Permissions.IsolatedStorageFilePermission> permission that specifies the <xref:System.Security.Permissions.IsolatedStorageContainment.AdministerIsolatedStorageByUser> value.</span></span> <span data-ttu-id="44e43-106">如果调用采用 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> 值的 <xref:System.IO.IsolatedStorage.IsolatedStorageScope.User> 方法，它将返回一组为当前用户定义的 <xref:System.IO.IsolatedStorage.IsolatedStorageFile> 对象。</span><span class="sxs-lookup"><span data-stu-id="44e43-106">If you call the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> method with the <xref:System.IO.IsolatedStorage.IsolatedStorageScope.User> value, it returns an array of <xref:System.IO.IsolatedStorage.IsolatedStorageFile> objects that are defined for the current user.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44e43-107">示例</span><span class="sxs-lookup"><span data-stu-id="44e43-107">Example</span></span>  
 <span data-ttu-id="44e43-108">下面的代码示例使用 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> 方法获取按用户和程序集隔离的存储区，创建一些文件，并检索这些文件。</span><span class="sxs-lookup"><span data-stu-id="44e43-108">The following code example obtains a store that is isolated by user and assembly, creates a few files, and retrieves those files by using the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> method.</span></span>  
  
 [!code-csharp[Conceptual.IsolatedStorage#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source2.cs#2)]
 [!code-vb[Conceptual.IsolatedStorage#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="44e43-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="44e43-109">See also</span></span>

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>
- [<span data-ttu-id="44e43-110">独立存储</span><span class="sxs-lookup"><span data-stu-id="44e43-110">Isolated Storage</span></span>](isolated-storage.md)
