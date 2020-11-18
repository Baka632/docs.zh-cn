---
title: 如何：在密钥容器中存储非对称密钥
description: 了解如何在 .NET 中的密钥容器中存储非对称密钥。 请参阅如何创建非对称密钥，将其保存在密钥容器中，然后检索和删除密钥。
ms.date: 05/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [.NET], asymmetric keys
- storing asymmetric keys
- keys, asymmetric
- encryption keys
- keys, storing in key containers
- asymmetric keys [.NET]
- encryption [.NET], asymmetric keys
- decryption keys
ms.assetid: 0dbcbd8d-0dcf-40e9-9f0c-e3f162d35ccc
ms.openlocfilehash: 946657f0c96aa80705575d8203ff158c63a72780
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "94820145"
---
# <a name="store-asymmetric-keys-in-a-key-container"></a><span data-ttu-id="c759e-104">将非对称密钥存储在密钥容器中</span><span class="sxs-lookup"><span data-stu-id="c759e-104">Store asymmetric keys in a key container</span></span>

<span data-ttu-id="c759e-105">非对称私钥永远不应以原义或纯文本形式存储在本地计算机上。</span><span class="sxs-lookup"><span data-stu-id="c759e-105">Asymmetric private keys should never be stored verbatim or in plain text on the local computer.</span></span> <span data-ttu-id="c759e-106">如果需要存储私钥，请使用密钥容器。</span><span class="sxs-lookup"><span data-stu-id="c759e-106">If you need to store a private key, use a key container.</span></span> <span data-ttu-id="c759e-107">有关密钥容器的详细信息，请参阅 [了解计算机级别和用户级别的 RSA 密钥容器](/previous-versions/aspnet/f5cs0acs(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="c759e-107">For more information on key containers, see [Understanding machine-level and user-level RSA key containers](/previous-versions/aspnet/f5cs0acs(v=vs.100)).</span></span>

> [!NOTE]
> <span data-ttu-id="c759e-108">本文中的代码适用于 Windows，并使用 .NET Core 2.2 及更低版本中不可用的功能。</span><span class="sxs-lookup"><span data-stu-id="c759e-108">The code in this article applies to Windows and uses features not available in .NET Core 2.2 and earlier versions.</span></span> <span data-ttu-id="c759e-109">有关详细信息，请参阅 [dotnet/runtime # 23391](https://github.com/dotnet/runtime/issues/23391)。</span><span class="sxs-lookup"><span data-stu-id="c759e-109">For more information, see [dotnet/runtime#23391](https://github.com/dotnet/runtime/issues/23391).</span></span>

## <a name="create-an-asymmetric-key-and-save-it-in-a-key-container"></a><span data-ttu-id="c759e-110">创建非对称密钥并将其保存在密钥容器中</span><span class="sxs-lookup"><span data-stu-id="c759e-110">Create an asymmetric key and save it in a key container</span></span>

1. <span data-ttu-id="c759e-111">创建类的新实例 <xref:System.Security.Cryptography.CspParameters> ，并将要调用密钥容器的名称传递给该 <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> 字段。</span><span class="sxs-lookup"><span data-stu-id="c759e-111">Create a new instance of a <xref:System.Security.Cryptography.CspParameters> class and pass the name that you want to call the key container to the <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> field.</span></span>

1. <span data-ttu-id="c759e-112">创建类的新实例，该类派生自 <xref:System.Security.Cryptography.AsymmetricAlgorithm> 类 (通常为 <xref:System.Security.Cryptography.RSACryptoServiceProvider> 或 <xref:System.Security.Cryptography.DSACryptoServiceProvider>) 并将以前创建的 `CspParameters` 对象传递给其构造函数。</span><span class="sxs-lookup"><span data-stu-id="c759e-112">Create a new instance of a class that derives from the <xref:System.Security.Cryptography.AsymmetricAlgorithm> class (usually <xref:System.Security.Cryptography.RSACryptoServiceProvider> or <xref:System.Security.Cryptography.DSACryptoServiceProvider>) and pass the previously created `CspParameters` object to its constructor.</span></span>

> [!NOTE]
> <span data-ttu-id="c759e-113">创建和检索非对称密钥是一项操作。</span><span class="sxs-lookup"><span data-stu-id="c759e-113">The creation and retrieval of an asymmetric key is one operation.</span></span> <span data-ttu-id="c759e-114">如果容器中不存在某个密钥，则会在返回该密钥之前创建该密钥。</span><span class="sxs-lookup"><span data-stu-id="c759e-114">If a key is not already in the container, it's created before being returned.</span></span>
>
> - <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType>
> - <xref:System.Security.Cryptography.DSA.ToXmlString%2A?displayProperty=nameWithType>

## <a name="delete-the-key-from-the-key-container"></a><span data-ttu-id="c759e-115">从密钥容器中删除密钥</span><span class="sxs-lookup"><span data-stu-id="c759e-115">Delete the key from the key container</span></span>

1. <span data-ttu-id="c759e-116">创建类的新实例 `CspParameters` ，并将要调用密钥容器的名称传递给该 <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> 字段。</span><span class="sxs-lookup"><span data-stu-id="c759e-116">Create a new instance of a `CspParameters` class and pass the name that you want to call the key container to the <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> field.</span></span>

1. <span data-ttu-id="c759e-117">创建类的新实例，该类派生自 <xref:System.Security.Cryptography.AsymmetricAlgorithm> 类 (通常为 `RSACryptoServiceProvider` 或 `DSACryptoServiceProvider`) 并将以前创建的 `CspParameters` 对象传递给其构造函数。</span><span class="sxs-lookup"><span data-stu-id="c759e-117">Create a new instance of a class that derives from the <xref:System.Security.Cryptography.AsymmetricAlgorithm> class (usually `RSACryptoServiceProvider` or `DSACryptoServiceProvider`) and pass the previously created `CspParameters` object to its constructor.</span></span>

1. <span data-ttu-id="c759e-118">将 <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> 派生自的类的或属性设置 `AsymmetricAlgorithm` 为 `false` `False` Visual Basic) 中 (。</span><span class="sxs-lookup"><span data-stu-id="c759e-118">Set the <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> or the <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> property of the class that derives from `AsymmetricAlgorithm` to `false` (`False` in Visual Basic).</span></span>

1. <span data-ttu-id="c759e-119">调用 `Clear` 派生自的类的方法 `AsymmetricAlgorithm` 。</span><span class="sxs-lookup"><span data-stu-id="c759e-119">Call the `Clear` method of the class that derives from `AsymmetricAlgorithm`.</span></span> <span data-ttu-id="c759e-120">该方法释放该类所有的资源并清除密钥容器。</span><span class="sxs-lookup"><span data-stu-id="c759e-120">This method releases all resources of the class and clears the key container.</span></span>

## <a name="example"></a><span data-ttu-id="c759e-121">示例</span><span class="sxs-lookup"><span data-stu-id="c759e-121">Example</span></span>

<span data-ttu-id="c759e-122">下面的示例说明下面这一过程：创建一个非对称密钥，将其保存在密钥容器中，以后检索此密钥，最后从该容器中删除此密钥。</span><span class="sxs-lookup"><span data-stu-id="c759e-122">The following example demonstrates how to create an asymmetric key, save it in a key container, retrieve the key at a later time, and delete the key from the container.</span></span>

<span data-ttu-id="c759e-123">请注意，`GenKey_SaveInContainer` 方法和 `GetKeyFromContainer` 方法的代码相似。</span><span class="sxs-lookup"><span data-stu-id="c759e-123">Notice that code in the `GenKey_SaveInContainer` method and the `GetKeyFromContainer` method is similar.</span></span> <span data-ttu-id="c759e-124">为对象指定密钥容器名称 <xref:System.Security.Cryptography.CspParameters> 并将其传递给 <xref:System.Security.Cryptography.AsymmetricAlgorithm> <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> 属性或 <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> 属性设置为的对象时 `true` ，该行为如下所示：</span><span class="sxs-lookup"><span data-stu-id="c759e-124">When you specify a key container name for a <xref:System.Security.Cryptography.CspParameters> object and pass it to an <xref:System.Security.Cryptography.AsymmetricAlgorithm> object with the <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> property or <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> property set to `true`, the behavior is as follows:</span></span>

- <span data-ttu-id="c759e-125">如果附带指定名称的密钥容器不存在，那么将创建一个并且该密钥保持不变。</span><span class="sxs-lookup"><span data-stu-id="c759e-125">If a key container with the specified name does not exist, then one is created and the key is persisted.</span></span>
- <span data-ttu-id="c759e-126">如果确实存在具有指定名称的密钥容器，则将此容器中的密钥自动加载到当前 <xref:System.Security.Cryptography.AsymmetricAlgorithm> 对象中。</span><span class="sxs-lookup"><span data-stu-id="c759e-126">If a key container with the specified name does exist, then the key in the container is automatically loaded into the current <xref:System.Security.Cryptography.AsymmetricAlgorithm> object.</span></span>

<span data-ttu-id="c759e-127">因此，方法中的代码 `GenKey_SaveInContainer` 会保留密钥，因为它首先运行，而方法中的代码 `GetKeyFromContainer` 加载键，因为它是第二个运行的。</span><span class="sxs-lookup"><span data-stu-id="c759e-127">Therefore, the code in the `GenKey_SaveInContainer` method persists the key because it is run first, while the code in the `GetKeyFromContainer` method loads the key because it's run second.</span></span>

```vb
Imports System
Imports System.Security.Cryptography

Public Class StoreKey

    Public Shared Sub Main()
        Try
            ' Create a key and save it in a container.
            GenKey_SaveInContainer("MyKeyContainer")

            ' Retrieve the key from the container.
            GetKeyFromContainer("MyKeyContainer")

            ' Delete the key from the container.
            DeleteKeyFromContainer("MyKeyContainer")

            ' Create a key and save it in a container.
            GenKey_SaveInContainer("MyKeyContainer")

            ' Delete the key from the container.
            DeleteKeyFromContainer("MyKeyContainer")
        Catch e As CryptographicException
            Console.WriteLine(e.Message)
        End Try
    End Sub

    Private Shared Sub GenKey_SaveInContainer(ByVal ContainerName As String)
        ' Create the CspParameters object and set the key container
        ' name used to store the RSA key pair.
        Dim parameters As New CspParameters With {
            .KeyContainerName = ContainerName
        }

        ' Create a new instance of RSACryptoServiceProvider that accesses
        ' the key container MyKeyContainerName.
        Using rsa As New RSACryptoServiceProvider(parameters)
            ' Display the key information to the console.
            Console.WriteLine($"Key added to container:  {rsa.ToXmlString(True)}")
        End Using
    End Sub

    Private Shared Sub GetKeyFromContainer(ByVal ContainerName As String)
        ' Create the CspParameters object and set the key container
        '  name used to store the RSA key pair.
        Dim parameters As New CspParameters With {
            .KeyContainerName = ContainerName
        }

        ' Create a new instance of RSACryptoServiceProvider that accesses
        ' the key container MyKeyContainerName.
        Using rsa As New RSACryptoServiceProvider(parameters)
            ' Display the key information to the console.
            Console.WriteLine($"Key retrieved from container : {rsa.ToXmlString(True)}")
        End Using
    End Sub

    Private Shared Sub DeleteKeyFromContainer(ByVal ContainerName As String)
        ' Create the CspParameters object and set the key container
        '  name used to store the RSA key pair.
        Dim parameters As New CspParameters With {
            .KeyContainerName = ContainerName
        }

        ' Create a new instance of RSACryptoServiceProvider that accesses
        ' the key container.
        ' Delete the key entry in the container.
        Dim rsa As New RSACryptoServiceProvider(parameters) With {
            .PersistKeyInCsp = False
        }

        ' Call Clear to release resources and delete the key from the container.
        rsa.Clear()

        Console.WriteLine("Key deleted.")
    End Sub
End Class
```

```csharp
using System;
using System.Security.Cryptography;

public class StoreKey
{
    public static void Main()
    {
        try
        {
            // Create a key and save it in a container.
            GenKey_SaveInContainer("MyKeyContainer");

            // Retrieve the key from the container.
            GetKeyFromContainer("MyKeyContainer");

            // Delete the key from the container.
            DeleteKeyFromContainer("MyKeyContainer");

            // Create a key and save it in a container.
            GenKey_SaveInContainer("MyKeyContainer");

            // Delete the key from the container.
            DeleteKeyFromContainer("MyKeyContainer");
        }
        catch (CryptographicException e)
        {
            Console.WriteLine(e.Message);
        }
    }

    private static void GenKey_SaveInContainer(string containerName)
    {
        // Create the CspParameters object and set the key container
        // name used to store the RSA key pair.
        var parameters = new CspParameters
        {
            KeyContainerName = containerName
        };

        // Create a new instance of RSACryptoServiceProvider that accesses
        // the key container MyKeyContainerName.
        using var rsa = new RSACryptoServiceProvider(parameters);

        // Display the key information to the console.
        Console.WriteLine($"Key added to container: \n  {rsa.ToXmlString(true)}");
    }

    private static void GetKeyFromContainer(string containerName)
    {
        // Create the CspParameters object and set the key container
        // name used to store the RSA key pair.
        var parameters = new CspParameters
        {
            KeyContainerName = containerName
        };

        // Create a new instance of RSACryptoServiceProvider that accesses
        // the key container MyKeyContainerName.
        using var rsa = new RSACryptoServiceProvider(parameters);

        // Display the key information to the console.
        Console.WriteLine($"Key retrieved from container : \n {rsa.ToXmlString(true)}");
    }

    private static void DeleteKeyFromContainer(string containerName)
    {
        // Create the CspParameters object and set the key container
        // name used to store the RSA key pair.
        var parameters = new CspParameters
        {
            KeyContainerName = containerName
        };

        // Create a new instance of RSACryptoServiceProvider that accesses
        // the key container.
        using var rsa = new RSACryptoServiceProvider(parameters)
        {
            // Delete the key entry in the container.
            PersistKeyInCsp = false
        };

        // Call Clear to release resources and delete the key from the container.
        rsa.Clear();

        Console.WriteLine("Key deleted.");
    }
}
```

<span data-ttu-id="c759e-128">输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="c759e-128">The output is as follows:</span></span>

```console
Key added to container:
<RSAKeyValue> Key Information A</RSAKeyValue>
Key retrieved from container :
<RSAKeyValue> Key Information A</RSAKeyValue>
Key deleted.
Key added to container:
<RSAKeyValue> Key Information B</RSAKeyValue>
Key deleted.
```

## <a name="see-also"></a><span data-ttu-id="c759e-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c759e-129">See also</span></span>

- [<span data-ttu-id="c759e-130">加密模型</span><span class="sxs-lookup"><span data-stu-id="c759e-130">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="c759e-131">加密服务</span><span class="sxs-lookup"><span data-stu-id="c759e-131">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="c759e-132">跨平台加密</span><span class="sxs-lookup"><span data-stu-id="c759e-132">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="c759e-133">生成加密和解密的密钥</span><span class="sxs-lookup"><span data-stu-id="c759e-133">Generating keys for encryption and decryption</span></span>](generating-keys-for-encryption-and-decryption.md)
- [<span data-ttu-id="c759e-134">加密数据</span><span class="sxs-lookup"><span data-stu-id="c759e-134">Encrypting data</span></span>](encrypting-data.md)
- [<span data-ttu-id="c759e-135">解密数据</span><span class="sxs-lookup"><span data-stu-id="c759e-135">Decrypting data</span></span>](decrypting-data.md)
- [<span data-ttu-id="c759e-136">ASP.NET Core 数据保护</span><span class="sxs-lookup"><span data-stu-id="c759e-136">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
