---
title: WSAT_TraceRecord
ms.date: 03/30/2017
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
ms.openlocfilehash: 0409277821a7cca3f97fcec1bb383aba9583a1f6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262211"
---
# <a name="wsat_tracerecord"></a><span data-ttu-id="a1545-102">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="a1545-102">WSAT_TraceRecord</span></span>

<span data-ttu-id="a1545-103">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="a1545-103">WSAT_TraceRecord</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1545-104">语法</span><span class="sxs-lookup"><span data-stu-id="a1545-104">Syntax</span></span>  
  
```csharp
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="a1545-105">方法</span><span class="sxs-lookup"><span data-stu-id="a1545-105">Methods</span></span>  

 <span data-ttu-id="a1545-106">WSAT_TraceRecord 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="a1545-106">The WSAT_TraceRecord class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a1545-107">属性</span><span class="sxs-lookup"><span data-stu-id="a1545-107">Properties</span></span>  

 <span data-ttu-id="a1545-108">WSAT_TraceRecord 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="a1545-108">The WSAT_TraceRecord class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="a1545-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="a1545-109">ActivityID</span></span>  

 <span data-ttu-id="a1545-110">数据类型：object</span><span class="sxs-lookup"><span data-stu-id="a1545-110">Data type: object</span></span>  
<span data-ttu-id="a1545-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="a1545-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a1545-112">跟踪记录的活动 ID。</span><span class="sxs-lookup"><span data-stu-id="a1545-112">The activity ID of the trace record.</span></span>  
  
### <a name="eventid"></a><span data-ttu-id="a1545-113">EventID</span><span class="sxs-lookup"><span data-stu-id="a1545-113">EventID</span></span>  

 <span data-ttu-id="a1545-114">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="a1545-114">Data type: sint32</span></span>  
<span data-ttu-id="a1545-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="a1545-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a1545-116">跟踪记录的事件 ID。</span><span class="sxs-lookup"><span data-stu-id="a1545-116">The event ID of the trace record.</span></span>  
  
### <a name="tracerecord"></a><span data-ttu-id="a1545-117">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="a1545-117">TraceRecord</span></span>  

 <span data-ttu-id="a1545-118">数据类型：字符串</span><span class="sxs-lookup"><span data-stu-id="a1545-118">Data type: string</span></span>  
<span data-ttu-id="a1545-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="a1545-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a1545-120">跟踪记录</span><span class="sxs-lookup"><span data-stu-id="a1545-120">Trace Record</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1545-121">要求</span><span class="sxs-lookup"><span data-stu-id="a1545-121">Requirements</span></span>  
  
|<span data-ttu-id="a1545-122">MOF</span><span class="sxs-lookup"><span data-stu-id="a1545-122">MOF</span></span>|<span data-ttu-id="a1545-123">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="a1545-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a1545-124">命名空间</span><span class="sxs-lookup"><span data-stu-id="a1545-124">Namespace</span></span>|<span data-ttu-id="a1545-125">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="a1545-125">Defined in root\ServiceModel</span></span>|
