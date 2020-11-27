---
title: 异步通信
ms.date: 03/30/2017
ms.assetid: 128dc092-9eb2-4e33-9470-9a7f62b60df6
ms.openlocfilehash: db5a8f415479967d7579357bd0c8058c7fb961c5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255840"
---
# <a name="asynchronous-communication"></a><span data-ttu-id="b0968-102">异步通信</span><span class="sxs-lookup"><span data-stu-id="b0968-102">Asynchronous Communication</span></span>

<span data-ttu-id="b0968-103">此示例演示如何在默认情况下异步执行两个不同 Windows Workflow Foundation (WF) 服务之间的通信。</span><span class="sxs-lookup"><span data-stu-id="b0968-103">This sample demonstrates how the communication between two different Windows Workflow Foundation (WF) services is done asynchronously by default.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="b0968-104">演示</span><span class="sxs-lookup"><span data-stu-id="b0968-104">Demonstrates</span></span>  

 <span data-ttu-id="b0968-105">[!INCLUDE[wf1](../../../../includes/wf1-md.md)] 服务间的异步通信。</span><span class="sxs-lookup"><span data-stu-id="b0968-105">Asynchronous communication between [!INCLUDE[wf1](../../../../includes/wf1-md.md)] services.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="b0968-106">讨论 (Discussion)</span><span class="sxs-lookup"><span data-stu-id="b0968-106">Discussion</span></span>  

 <span data-ttu-id="b0968-107">此示例演示如何使用 .NET Framework 提供的消息传递活动来异步执行 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 应用程序间的通信。</span><span class="sxs-lookup"><span data-stu-id="b0968-107">This sample shows how the communication between [!INCLUDE[wf1](../../../../includes/wf1-md.md)] applications is done asynchronously by using the messaging activities provided by .NET Framework.</span></span>  
  
 <span data-ttu-id="b0968-108">此示例包含以下三个项目。</span><span class="sxs-lookup"><span data-stu-id="b0968-108">This sample consists of the following three projects.</span></span>  
  
 <span data-ttu-id="b0968-109">CreditCheckService</span><span class="sxs-lookup"><span data-stu-id="b0968-109">CreditCheckService</span></span>  
 <span data-ttu-id="b0968-110">此服务接收特定人员的信用评分或要购买的商品的价值，然后决定是否为该人员提供贷款。</span><span class="sxs-lookup"><span data-stu-id="b0968-110">This service receives the credit score of a particular person or the value of the item to acquire, and then decides whether the credit is given to the person.</span></span>  
  
 <span data-ttu-id="b0968-111">RentalApprovalService</span><span class="sxs-lookup"><span data-stu-id="b0968-111">RentalApprovalService</span></span>  
 <span data-ttu-id="b0968-112">此服务接收来自需要贷款的人员的申请。</span><span class="sxs-lookup"><span data-stu-id="b0968-112">This service receives an application from a person who is in need of some credit.</span></span> <span data-ttu-id="b0968-113">此服务与 `CreditCheckService` 进行异步通信以决定贷款申请是否有效。</span><span class="sxs-lookup"><span data-stu-id="b0968-113">This service communicates asynchronously with the `CreditCheckService` to decide whether the credit application is valid.</span></span>  
  
 <span data-ttu-id="b0968-114">客户端</span><span class="sxs-lookup"><span data-stu-id="b0968-114">Client</span></span>  
 <span data-ttu-id="b0968-115">此客户端与 `RentalApprovalService` 进行同步通信以了解是否已批准贷款。</span><span class="sxs-lookup"><span data-stu-id="b0968-115">The client communicates synchronously with the `RentalApprovalService` to know whether the credit is approved.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b0968-116">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="b0968-116">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="b0968-117">右键单击 **AsynchronousCommunication** 解决方案，然后选择 " **属性**"。</span><span class="sxs-lookup"><span data-stu-id="b0968-117">Right-click the **AsynchronousCommunication** solution and select **Properties**.</span></span>  
  
2. <span data-ttu-id="b0968-118">在 " **通用属性**" 中，选择 " **启动项目**"，然后选择 " **多启动项目**"。</span><span class="sxs-lookup"><span data-stu-id="b0968-118">In **Common Properties**, select **Startup Project**, and select **Multiple Startup Projects**.</span></span>  
  
3. <span data-ttu-id="b0968-119">将 **RentalApprovalService** 移动到列表中的第一个位置，后跟 **CreditCheckService**，后跟 **客户端**。</span><span class="sxs-lookup"><span data-stu-id="b0968-119">Move **RentalApprovalService** to the first position in the list, followed by **CreditCheckService**, followed by **Client**.</span></span> <span data-ttu-id="b0968-120">在所有三个项目上设置 " **启动** " 操作。</span><span class="sxs-lookup"><span data-stu-id="b0968-120">Set the **Start** action on all three projects.</span></span>  
  
4. <span data-ttu-id="b0968-121">单击 **"确定"**，然后按 F5 运行示例。</span><span class="sxs-lookup"><span data-stu-id="b0968-121">Click **OK**, and press F5 to run the sample.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b0968-122">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="b0968-122">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b0968-123">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="b0968-123">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="b0968-124">如果此目录不存在，请参阅[Windows Communication Foundation (wcf) ，并 Windows Workflow Foundation (的 WF](https://www.microsoft.com/download/details.aspx?id=21459)) .NET Framework Windows Communication Foundation ([!INCLUDE[wf1](../../../../includes/wf1-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0968-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b0968-125">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="b0968-125">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\AsynchronousCommunication`
