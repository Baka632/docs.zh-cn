---
title: ServiceAuthorizationBehavior
ms.date: 03/30/2017
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
ms.openlocfilehash: d3625865484568746888ef0638d9a8501e610bef
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273199"
---
# <a name="serviceauthorizationbehavior"></a><span data-ttu-id="94304-102">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="94304-102">ServiceAuthorizationBehavior</span></span>

<span data-ttu-id="94304-103">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="94304-103">ServiceAuthorizationBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94304-104">语法</span><span class="sxs-lookup"><span data-stu-id="94304-104">Syntax</span></span>  
  
```csharp
class ServiceAuthorizationBehavior : Behavior  
{  
  boolean ImpersonateCallerForAllOperations;  
  string PrincipalPermissionMode;  
  string RoleProvider;  
  string ServiceAuthorizationManager;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="94304-105">方法</span><span class="sxs-lookup"><span data-stu-id="94304-105">Methods</span></span>  

 <span data-ttu-id="94304-106">ServiceAuthorizationBehavior 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="94304-106">The ServiceAuthorizationBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="94304-107">属性</span><span class="sxs-lookup"><span data-stu-id="94304-107">Properties</span></span>  

 <span data-ttu-id="94304-108">ServiceAuthorizationBehavior 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="94304-108">The ServiceAuthorizationBehavior class has the following properties:</span></span>  
  
### <a name="impersonatecallerforalloperations"></a><span data-ttu-id="94304-109">ImpersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="94304-109">ImpersonateCallerForAllOperations</span></span>  

 <span data-ttu-id="94304-110">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="94304-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="94304-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="94304-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="94304-112">一个值，控制服务是否尝试使用传入消息所提供的凭据进行模拟。</span><span class="sxs-lookup"><span data-stu-id="94304-112">A value that controls whether the service attempts to impersonate using the credentials provided by the incoming message.</span></span>  
  
### <a name="principalpermissionmode"></a><span data-ttu-id="94304-113">PrincipalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="94304-113">PrincipalPermissionMode</span></span>  

 <span data-ttu-id="94304-114">数据类型：字符串</span><span class="sxs-lookup"><span data-stu-id="94304-114">Data type: string</span></span>  
  
 <span data-ttu-id="94304-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="94304-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="94304-116">用于在服务器上执行操作的主体。</span><span class="sxs-lookup"><span data-stu-id="94304-116">The principal used to carry out operations on the server.</span></span>  
  
### <a name="roleprovider"></a><span data-ttu-id="94304-117">RoleProvider</span><span class="sxs-lookup"><span data-stu-id="94304-117">RoleProvider</span></span>  

 <span data-ttu-id="94304-118">数据类型：字符串</span><span class="sxs-lookup"><span data-stu-id="94304-118">Data type: string</span></span>  
  
 <span data-ttu-id="94304-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="94304-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="94304-120">ASP.NET 角色提供程序的名称。</span><span class="sxs-lookup"><span data-stu-id="94304-120">The name of the ASP.NET role provider.</span></span>  
  
### <a name="serviceauthorizationmanager"></a><span data-ttu-id="94304-121">ServiceAuthorizationManager</span><span class="sxs-lookup"><span data-stu-id="94304-121">ServiceAuthorizationManager</span></span>  

 <span data-ttu-id="94304-122">数据类型：字符串</span><span class="sxs-lookup"><span data-stu-id="94304-122">Data type: string</span></span>  
  
 <span data-ttu-id="94304-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="94304-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="94304-124">用于自定义授权的授权管理器。</span><span class="sxs-lookup"><span data-stu-id="94304-124">The authorization manager used for custom authorization.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94304-125">要求</span><span class="sxs-lookup"><span data-stu-id="94304-125">Requirements</span></span>  
  
|<span data-ttu-id="94304-126">MOF</span><span class="sxs-lookup"><span data-stu-id="94304-126">MOF</span></span>|<span data-ttu-id="94304-127">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="94304-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="94304-128">命名空间</span><span class="sxs-lookup"><span data-stu-id="94304-128">Namespace</span></span>|<span data-ttu-id="94304-129">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="94304-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="94304-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94304-130">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
