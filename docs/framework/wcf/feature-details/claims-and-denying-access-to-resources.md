---
title: 声明和拒绝访问资源
ms.date: 03/30/2017
helpviewer_keywords:
- claims [WCF], denying access to resources
ms.assetid: 145ebb41-680e-4256-b14c-1efb4af1e982
ms.openlocfilehash: 2c903d5b5aa520b9c79fb8b36912324feaf9a432
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96264916"
---
# <a name="claims-and-denying-access-to-resources"></a><span data-ttu-id="f2290-102">声明和拒绝访问资源</span><span class="sxs-lookup"><span data-stu-id="f2290-102">Claims and Denying Access to Resources</span></span>

<span data-ttu-id="f2290-103">Windows Communication Foundation (WCF) 支持基于声明的授权机制。</span><span class="sxs-lookup"><span data-stu-id="f2290-103">Windows Communication Foundation (WCF) supports a claims-based authorization mechanism.</span></span> <span data-ttu-id="f2290-104">在基于是否存在声明来允许访问资源的同时，系统通常也基于是否存在声明来拒绝访问资源。</span><span class="sxs-lookup"><span data-stu-id="f2290-104">As well as allowing access to resources based on the presence of claims, systems often deny access to resources based on the presence of claims.</span></span> <span data-ttu-id="f2290-105">这样的系统应该在查找导致允许访问的声明之前先检查 <xref:System.IdentityModel.Policy.AuthorizationContext> 是否存在导致拒绝访问的声明。</span><span class="sxs-lookup"><span data-stu-id="f2290-105">Such systems should examine the <xref:System.IdentityModel.Policy.AuthorizationContext> for claims that result in access being denied before looking for claims that result in access being allowed.</span></span>  
  
 <span data-ttu-id="f2290-106">例如，对于具有类型为 `Age`、权限为 <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> 和资源值为 `Under 21` 的声明的任何用户，仅当该标识同时也具有类型为 `Name`、权限为 <xref:System.IdentityModel.Claims.Rights.Identity%2A> 和资源值为 `Mallory` 的声明时，系统才会拒绝其访问资源。</span><span class="sxs-lookup"><span data-stu-id="f2290-106">For example, a system might deny access to a resource to anyone who has a claim with a type of `Age`, a right of <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>, and a resource value of `Under 21` only when that identity also has a claim of type `Name`, a right of <xref:System.IdentityModel.Claims.Rights.Identity%2A>, and a resource value of `Mallory`.</span></span> <span data-ttu-id="f2290-107">换言之，对于年龄不到 21 岁的任何人，系统拒绝其访问资源，如果姓名为 Mallory，则系统允许其访问资源。</span><span class="sxs-lookup"><span data-stu-id="f2290-107">Put another way, the system denies access to anyone who is under 21 years old and grants access when the name is Mallory.</span></span> <span data-ttu-id="f2290-108">为了正确地实现此语义，必须首先查找 `Age` 声明，然后确定年龄是否低于 21 岁。</span><span class="sxs-lookup"><span data-stu-id="f2290-108">To correctly implement this semantic, it is important to look for the `Age` claim first and determine whether the age is under 21 years old.</span></span> <span data-ttu-id="f2290-109">否则，如果 Mallory 不到 21 岁，则仅基于 `Name` 声明授予对资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="f2290-109">Otherwise, if Mallory is under 21, then the resource may be granted access solely on the basis of the `Name` claim.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2290-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f2290-110">See also</span></span>

- [<span data-ttu-id="f2290-111">使用标识模型管理声明和授权</span><span class="sxs-lookup"><span data-stu-id="f2290-111">Managing Claims and Authorization with the Identity Model</span></span>](managing-claims-and-authorization-with-the-identity-model.md)
- [<span data-ttu-id="f2290-112">声明和令牌</span><span class="sxs-lookup"><span data-stu-id="f2290-112">Claims and Tokens</span></span>](claims-and-tokens.md)
