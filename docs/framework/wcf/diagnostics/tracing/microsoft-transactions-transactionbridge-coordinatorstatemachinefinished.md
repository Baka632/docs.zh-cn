---
title: Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished
ms.date: 03/30/2017
ms.assetid: 16cb428d-d886-4789-a961-6fded4b0dbba
ms.openlocfilehash: 2d874cebe96b9caa99032e2881e19ec9cd34d047
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96259006"
---
# <a name="microsofttransactionstransactionbridgecoordinatorstatemachinefinished"></a><span data-ttu-id="0e7a0-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span><span class="sxs-lookup"><span data-stu-id="0e7a0-102">Microsoft.Transactions.TransactionBridge.CoordinatorStateMachineFinished</span></span>

<span data-ttu-id="0e7a0-103">用于协调器登记的状态机已进入已完成状态。</span><span class="sxs-lookup"><span data-stu-id="0e7a0-103">The state machine for a coordinator enlistment has entered the finished state.</span></span>  
  
## <a name="description"></a><span data-ttu-id="0e7a0-104">描述</span><span class="sxs-lookup"><span data-stu-id="0e7a0-104">Description</span></span>  

 <span data-ttu-id="0e7a0-105">本地事务管理器认为高级协调器登记已完成 2pc 处理时跟踪。</span><span class="sxs-lookup"><span data-stu-id="0e7a0-105">Traced when the local Transaction Manager believes a superior coordinator enlistment has completed 2pc processing.</span></span> <span data-ttu-id="0e7a0-106">登记的结果可以是“已提交”、“已中止”或“已忘记”。</span><span class="sxs-lookup"><span data-stu-id="0e7a0-106">The outcome for the enlistment can be Committed or Aborted or Forgotten.</span></span> <span data-ttu-id="0e7a0-107">本地事务管理器在“准备”过程中对“只读”投票时也会进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="0e7a0-107">It is also traced if the local Transaction Manager votes ReadOnly during Prepare.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e7a0-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0e7a0-108">See also</span></span>

- [<span data-ttu-id="0e7a0-109">跟踪</span><span class="sxs-lookup"><span data-stu-id="0e7a0-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="0e7a0-110">使用跟踪来排除应用程序故障</span><span class="sxs-lookup"><span data-stu-id="0e7a0-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="0e7a0-111">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="0e7a0-111">Administration and Diagnostics</span></span>](../index.md)
