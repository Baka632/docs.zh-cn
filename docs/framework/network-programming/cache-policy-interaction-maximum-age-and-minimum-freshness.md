---
title: 缓存策略交互 — 最长使用期限和最低新鲜度
ms.date: 03/30/2017
helpviewer_keywords:
- time-based cache policies
- Revalidate policy
- cache [.NET Framework], time-based policies
- freshness of cached resources
- maximum age policy
- minimum freshness policy
- age of cached resources
ms.assetid: 6567d451-ecec-496c-95a3-a415b99ba52a
ms.openlocfilehash: d4182268341f4a4334a627fc8c9e24fa235f003f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96287548"
---
# <a name="cache-policy-interactionmaximum-age-and-minimum-freshness"></a><span data-ttu-id="d96f4-102">缓存策略交互 — 最长使用期限和最低新鲜度</span><span class="sxs-lookup"><span data-stu-id="d96f4-102">Cache Policy Interaction—Maximum Age and Minimum Freshness</span></span>

<span data-ttu-id="d96f4-103">为了帮助确保将最新鲜的内容返回给客户端应用程序，客户端缓存策略和服务器重新验证要求的交互始终会造成最保守的缓存策略。</span><span class="sxs-lookup"><span data-stu-id="d96f4-103">To help ensure that the freshest content is returned to the client application, the interaction of client cache policy and server revalidation requirements always results in the most conservative cache policy.</span></span> <span data-ttu-id="d96f4-104">本主题中的所有示例阐明针对在 1 月 1 日缓存、1 月 4 日过期的资源的缓存策略。</span><span class="sxs-lookup"><span data-stu-id="d96f4-104">All the examples in this topic illustrate the cache policy for a resource that is cached on January 1 and expires on January 4.</span></span>  
  
 <span data-ttu-id="d96f4-105">以下示例将说明最长使用时间值 (`maxAge`) 和最低新鲜度值 (`minFresh`) 交互产生的缓存策略。</span><span class="sxs-lookup"><span data-stu-id="d96f4-105">The following examples illustrate the cache policy that results from the interaction of the maximum age (`maxAge`) and minimum freshness (`minFresh`) values.</span></span>  
  
- <span data-ttu-id="d96f4-106">如果缓存策略设置 `maxAge` = 2 天，`minFresh` 未指定，则会在 1 月 3 日重新验证此内容。</span><span class="sxs-lookup"><span data-stu-id="d96f4-106">If the cache policy sets `maxAge` = 2 days and `minFresh` is not specified, the content is revalidated on January 3.</span></span>  
  
- <span data-ttu-id="d96f4-107">如果缓存策略设置 `maxAge` = 2 天，`minFresh` = 1 天，根据 `maxAge`，内容在 1 月 3 日前是新鲜的。</span><span class="sxs-lookup"><span data-stu-id="d96f4-107">If the cache policy sets `maxAge` = 2 days and `minFresh` = 1 day, according to `maxAge`, the content is fresh until January 3.</span></span> <span data-ttu-id="d96f4-108">根据 `minFresh`，此内容在 1 月 3 日前也是新鲜的。</span><span class="sxs-lookup"><span data-stu-id="d96f4-108">According to `minFresh`, the content is fresh until January 3.</span></span> <span data-ttu-id="d96f4-109">因此，必须在 1 月 3 日重新验证此内容。</span><span class="sxs-lookup"><span data-stu-id="d96f4-109">Therefore, the content must be revalidated on January 3.</span></span>  
  
- <span data-ttu-id="d96f4-110">如果缓存策略设置 `maxAge` = 2 天，`minFresh` = 2 天，根据 `maxAge`，此内容在 1 月 3 日前是新鲜的。</span><span class="sxs-lookup"><span data-stu-id="d96f4-110">If the cache policy sets `maxAge` = 2 days and `minFresh` = 2 days, according to `maxAge`, the content is fresh until January 3.</span></span> <span data-ttu-id="d96f4-111">根据 `minFresh`，此内容在 1 月 2 日前也是新鲜的。</span><span class="sxs-lookup"><span data-stu-id="d96f4-111">According to `minFresh` the content is fresh until January 2.</span></span> <span data-ttu-id="d96f4-112">因此，必须在 1 月 2 日重新验证此内容。</span><span class="sxs-lookup"><span data-stu-id="d96f4-112">Therefore, the content must be revalidated on January 2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d96f4-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d96f4-113">See also</span></span>

- [<span data-ttu-id="d96f4-114">网络应用程序的缓存管理</span><span class="sxs-lookup"><span data-stu-id="d96f4-114">Cache Management for Network Applications</span></span>](cache-management-for-network-applications.md)
- [<span data-ttu-id="d96f4-115">缓存策略</span><span class="sxs-lookup"><span data-stu-id="d96f4-115">Cache Policy</span></span>](cache-policy.md)
- [<span data-ttu-id="d96f4-116">基于位置的缓存策略</span><span class="sxs-lookup"><span data-stu-id="d96f4-116">Location-Based Cache Policies</span></span>](location-based-cache-policies.md)
- [<span data-ttu-id="d96f4-117">基于时间的缓存策略</span><span class="sxs-lookup"><span data-stu-id="d96f4-117">Time-Based Cache Policies</span></span>](time-based-cache-policies.md)
- [<span data-ttu-id="d96f4-118">在网络应用程序中配置缓存</span><span class="sxs-lookup"><span data-stu-id="d96f4-118">Configuring Caching in Network Applications</span></span>](configuring-caching-in-network-applications.md)
- [<span data-ttu-id="d96f4-119">缓存策略交互 — 最长使用时间和最长过期时间</span><span class="sxs-lookup"><span data-stu-id="d96f4-119">Cache Policy Interaction—Maximum Age and Maximum Staleness</span></span>](cache-policy-interaction-maximum-age-and-maximum-staleness.md)
