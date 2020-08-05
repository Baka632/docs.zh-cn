---
title: 使用哈希代码确保数据完整性
description: 了解如何在 .NET 中使用哈希代码确保数据完整性。 哈希值是用于唯一标识数据的固定长度的数字值。
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- generating hash
- verifying hash codes
- cryptography [.NET], hash
- data integrity
- checking hash codes
- encryption [.NET], hash
- hash
ms.assetid: 33660f33-b70f-4dca-8c87-ab35cfc2961a
ms.openlocfilehash: 3205e37f283cb205f5edfc5948a9cb9f7256f752
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556951"
---
# <a name="ensuring-data-integrity-with-hash-codes"></a><span data-ttu-id="83eb7-104">使用哈希代码确保数据完整性</span><span class="sxs-lookup"><span data-stu-id="83eb7-104">Ensuring Data Integrity with Hash Codes</span></span>
<span data-ttu-id="83eb7-105">哈希值是用于唯一标识数据的固定长度的数字值。</span><span class="sxs-lookup"><span data-stu-id="83eb7-105">A hash value is a numeric value of a fixed length that uniquely identifies data.</span></span> <span data-ttu-id="83eb7-106">哈希值以小得多的数字值表示大量数据，因此与数字签名配合使用。</span><span class="sxs-lookup"><span data-stu-id="83eb7-106">Hash values represent large amounts of data as much smaller numeric values, so they are used with digital signatures.</span></span> <span data-ttu-id="83eb7-107">对哈希值进行签名比对较大的值进行签名更为高效。</span><span class="sxs-lookup"><span data-stu-id="83eb7-107">You can sign a hash value more efficiently than signing the larger value.</span></span> <span data-ttu-id="83eb7-108">对于验证通过不安全通道发送的数据的完整性，哈希值也很有用。</span><span class="sxs-lookup"><span data-stu-id="83eb7-108">Hash values are also useful for verifying the integrity of data sent through insecure channels.</span></span> <span data-ttu-id="83eb7-109">当被发送出去确定数据是否已更改时，将接收数据的哈希值与数据的哈希值相比较。</span><span class="sxs-lookup"><span data-stu-id="83eb7-109">The hash value of received data can be compared to the hash value of data as it was sent to determine whether the data was altered.</span></span>  
  
<span data-ttu-id="83eb7-110">本主题介绍如何通过使用 <xref:System.Security.Cryptography> 命名空间中的类生成和验证哈希代码。</span><span class="sxs-lookup"><span data-stu-id="83eb7-110">This topic describes how to generate and verify hash codes by using the classes in the <xref:System.Security.Cryptography> namespace.</span></span>  
  
## <a name="generating-a-hash"></a><span data-ttu-id="83eb7-111">生成哈希</span><span class="sxs-lookup"><span data-stu-id="83eb7-111">Generating a Hash</span></span>

 <span data-ttu-id="83eb7-112">托管哈希类可以对字节数组或托管流对象进行哈希处理。</span><span class="sxs-lookup"><span data-stu-id="83eb7-112">The managed hash classes can hash either an array of bytes or a managed stream object.</span></span> <span data-ttu-id="83eb7-113">以下示例使用 SHA1 哈希算法为字符串创建哈希值。</span><span class="sxs-lookup"><span data-stu-id="83eb7-113">The following example uses the SHA1 hash algorithm to create a hash value for a string.</span></span> <span data-ttu-id="83eb7-114">该示例使用 <xref:System.Text.UnicodeEncoding> 类将字符串转换为通过使用 <xref:System.Security.Cryptography.SHA256> 类进行哈希处理的字节数组。</span><span class="sxs-lookup"><span data-stu-id="83eb7-114">The example uses the <xref:System.Text.UnicodeEncoding> class to convert the string into an array of bytes that are hashed by using the <xref:System.Security.Cryptography.SHA256> class.</span></span> <span data-ttu-id="83eb7-115">然后向控制台显示哈希值。</span><span class="sxs-lookup"><span data-stu-id="83eb7-115">The hash value is then displayed to the console.</span></span>  

 [!code-csharp[GeneratingAHash#1](../../../samples/snippets/csharp/VS_Snippets_CLR/generatingahash/cs/program.cs#1)]
 [!code-vb[GeneratingAHash#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/generatingahash/vb/program.vb#1)]  
  
 <span data-ttu-id="83eb7-116">此代码将向控制台显示以下字符串：</span><span class="sxs-lookup"><span data-stu-id="83eb7-116">This code will display the following string to the console:</span></span>  
  
 `185 203 236 22 3 228 27 130 87 23 244 15 87 88 14 43 37 61 106 224 81 172 224 211 104 85 194 197 194 25 120 217`  
  
## <a name="verifying-a-hash"></a><span data-ttu-id="83eb7-117">验证哈希</span><span class="sxs-lookup"><span data-stu-id="83eb7-117">Verifying a Hash</span></span>

 <span data-ttu-id="83eb7-118">可将数据与哈希值进行比较，以确定其完整性。</span><span class="sxs-lookup"><span data-stu-id="83eb7-118">Data can be compared to a hash value to determine its integrity.</span></span> <span data-ttu-id="83eb7-119">通常，在某个特定时间对数据进行哈希运算，并以某种方式保护哈希值。</span><span class="sxs-lookup"><span data-stu-id="83eb7-119">Usually, data is hashed at a certain time and the hash value is protected in some way.</span></span> <span data-ttu-id="83eb7-120">稍后，可以再次对数据进行哈希运算，并与受保护的值进行比较。</span><span class="sxs-lookup"><span data-stu-id="83eb7-120">At a later time, the data can be hashed again and compared to the protected value.</span></span> <span data-ttu-id="83eb7-121">如果哈希值匹配，则数据未更改。</span><span class="sxs-lookup"><span data-stu-id="83eb7-121">If the hash values match, the data has not been altered.</span></span> <span data-ttu-id="83eb7-122">如果值不匹配，则数据已损坏。</span><span class="sxs-lookup"><span data-stu-id="83eb7-122">If the values do not match, the data has been corrupted.</span></span> <span data-ttu-id="83eb7-123">要使此系统发挥作用，必须对受保护的哈希加密或对所有的不受信任方保密。</span><span class="sxs-lookup"><span data-stu-id="83eb7-123">For this system to work, the protected hash must be encrypted or kept secret from all untrusted parties.</span></span>  
  
 <span data-ttu-id="83eb7-124">以下示例将字符串旧的哈希值与新的哈希值进行比较。</span><span class="sxs-lookup"><span data-stu-id="83eb7-124">The following example compares the previous hash value of a string to a new hash value.</span></span> <span data-ttu-id="83eb7-125">此示例循环访问哈希值的每个字节并进行比较。</span><span class="sxs-lookup"><span data-stu-id="83eb7-125">This example loops through each byte of the hash values and makes a comparison.</span></span>  
  
 [!code-csharp[VerifyingAHash#1](../../../samples/snippets/csharp/VS_Snippets_CLR/verifyingahash/cs/program.cs#1)]
 [!code-vb[VerifyingAHash#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/verifyingahash/vb/program.vb#1)]  
  
 <span data-ttu-id="83eb7-126">如果两个哈希值匹配，则此代码将向控制台现实以下内容：</span><span class="sxs-lookup"><span data-stu-id="83eb7-126">If the two hash values match, this code displays the following to the console:</span></span>  
  
```console  
The hash codes match.  
```  
  
 <span data-ttu-id="83eb7-127">如果不匹配，则此代码显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="83eb7-127">If they do not match, the code displays the following:</span></span>  
  
```console  
The hash codes do not match.  
```  
  
## <a name="see-also"></a><span data-ttu-id="83eb7-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="83eb7-128">See also</span></span>

- [<span data-ttu-id="83eb7-129">加密模型</span><span class="sxs-lookup"><span data-stu-id="83eb7-129">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="83eb7-130">加密服务</span><span class="sxs-lookup"><span data-stu-id="83eb7-130">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="83eb7-131">跨平台加密</span><span class="sxs-lookup"><span data-stu-id="83eb7-131">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="83eb7-132">ASP.NET Core 数据保护</span><span class="sxs-lookup"><span data-stu-id="83eb7-132">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
