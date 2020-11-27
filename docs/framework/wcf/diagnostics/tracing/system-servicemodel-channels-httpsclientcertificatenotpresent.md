---
title: System.ServiceModel.Channels.HttpsClientCertificateNotPresent
ms.date: 03/30/2017
ms.assetid: b13ef1b6-e340-401d-93ca-2710c3842205
ms.openlocfilehash: 9ec25138130311f8cdd9af8fb32a3e80fb33ed68
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96258083"
---
# <a name="systemservicemodelchannelshttpsclientcertificatenotpresent"></a><span data-ttu-id="ceff6-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span><span class="sxs-lookup"><span data-stu-id="ceff6-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span></span>

<span data-ttu-id="ceff6-103">需要客户端证书。</span><span class="sxs-lookup"><span data-stu-id="ceff6-103">Client certificate is required.</span></span> <span data-ttu-id="ceff6-104">在请求中未找到任何证书。</span><span class="sxs-lookup"><span data-stu-id="ceff6-104">No certificate was found in the request.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ceff6-105">描述</span><span class="sxs-lookup"><span data-stu-id="ceff6-105">Description</span></span>  

 <span data-ttu-id="ceff6-106">此跟踪指示 HTTPS 侦听器收到与客户端证书无关的 HTTPS 请求。</span><span class="sxs-lookup"><span data-stu-id="ceff6-106">This trace indicates that the HTTPS listener received an HTTPS request that was not associated with a client certificate.</span></span> <span data-ttu-id="ceff6-107">因为侦听器被配置为对所有 HTTPS 请求都要求提供客户端证书，所以侦听器未能验证该客户端的真实性。</span><span class="sxs-lookup"><span data-stu-id="ceff6-107">Since the listener was configured to require client certificates on all HTTPS requests, the listener failed to validate the client’s authenticity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ceff6-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ceff6-108">See also</span></span>

- [<span data-ttu-id="ceff6-109">跟踪</span><span class="sxs-lookup"><span data-stu-id="ceff6-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="ceff6-110">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="ceff6-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="ceff6-111">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="ceff6-111">Administration and Diagnostics</span></span>](../index.md)
