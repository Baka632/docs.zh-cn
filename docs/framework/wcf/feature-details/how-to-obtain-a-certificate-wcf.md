---
title: 如何：获取证书 (WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], obtaining
ms.assetid: d53762fd-15ea-42dc-b0ea-6a6597aa23f7
ms.openlocfilehash: b1fea1a7357b937bd15517b313948ead6aab894d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557848"
---
# <a name="how-to-obtain-a-certificate-wcf"></a><span data-ttu-id="2f952-102">如何：获取证书 (WCF)</span><span class="sxs-lookup"><span data-stu-id="2f952-102">How to: Obtain a Certificate (WCF)</span></span>
<span data-ttu-id="2f952-103">若要使用 Windows Communication Foundation 的任何 (WCF) 功能，只需获取证书即可。</span><span class="sxs-lookup"><span data-stu-id="2f952-103">To use any of the Windows Communication Foundation (WCF) features of that use X.509 certificates, you just first obtain certificates.</span></span>  
  
### <a name="to-obtain-an-x509-certificate"></a><span data-ttu-id="2f952-104">获取 X.509 证书</span><span class="sxs-lookup"><span data-stu-id="2f952-104">To obtain an X.509 certificate</span></span>  
  
1. <span data-ttu-id="2f952-105">选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="2f952-105">Choose one of the following:</span></span>  
  
    - <span data-ttu-id="2f952-106">从证书颁发机构（如 VeriSign Inc）购买证书。</span><span class="sxs-lookup"><span data-stu-id="2f952-106">Purchase a certificate from a certification authority, such as VeriSign, Inc.</span></span>  
  
    - <span data-ttu-id="2f952-107">设置自己的证书服务，并让证书颁发机构为证书签名。</span><span class="sxs-lookup"><span data-stu-id="2f952-107">Set up your own certificate service and have a certification authority sign the certificates.</span></span> <span data-ttu-id="2f952-108">Windows Server 2003、Windows 2000 Server、Windows 2000 Server Datacenter 和 Windows 2000 Datacenter 服务器都包含支持公钥基础结构 (PKI) 的证书服务。</span><span class="sxs-lookup"><span data-stu-id="2f952-108">Windows Server 2003, Windows 2000 Server, Windows 2000 Server Datacenter, and Windows 2000 Datacenter Server all include certificate services that support public key infrastructure (PKI).</span></span> <span data-ttu-id="2f952-109">在 Windows Server 2008 中，使用 [Active Directory 证书服务](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731564(v=ws.10)) 角色来管理证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="2f952-109">In Windows Server 2008, use the [Active Directory Certificate Services](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731564(v=ws.10)) role to manage a certification authority.</span></span>  
  
    - <span data-ttu-id="2f952-110">设置自己的证书服务，但不对证书进行签名。</span><span class="sxs-lookup"><span data-stu-id="2f952-110">Set up your own certificate service and do not have the certificates signed.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="2f952-111">无论采取哪种方法，包含 X.509 证书的 SOAP 请求的接收方都必须信任 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="2f952-111">Whichever approach you take, the recipient of the SOAP request that contains the X.509 certificate must trust the X.509 certificate.</span></span> <span data-ttu-id="2f952-112">这意味着证书链中的 X.509 证书或颁发者位于“受信任的人”证书存储区中，并且 X.509 证书不在“不受信任的证书”存储区中。</span><span class="sxs-lookup"><span data-stu-id="2f952-112">This means that the X.509 certificate or an issuer in the certificate chain is in the Trusted People certificate store and that the X.509 certificate is not in the Untrusted Certificates store.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f952-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="2f952-113">See also</span></span>

- [<span data-ttu-id="2f952-114">使用证书</span><span class="sxs-lookup"><span data-stu-id="2f952-114">Working with Certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="2f952-115">如何：创建开发期间使用的临时证书</span><span class="sxs-lookup"><span data-stu-id="2f952-115">How to: Create Temporary Certificates for Use During Development</span></span>](how-to-create-temporary-certificates-for-use-during-development.md)
