---
title: 共享 WithEvents 变量的事件不能由非共享方法处理
ms.date: 07/20/2015
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
ms.openlocfilehash: d519463e036de215143efad5be3745484ac17d82
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874286"
---
# <a name="events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a><span data-ttu-id="408e1-102">共享 WithEvents 变量的事件不能由非共享方法处理</span><span class="sxs-lookup"><span data-stu-id="408e1-102">Events of shared WithEvents variables cannot be handled by non-shared methods</span></span>

<span data-ttu-id="408e1-103">使用修饰符声明的变量 `Shared` 是共享变量。</span><span class="sxs-lookup"><span data-stu-id="408e1-103">A variable declared with the `Shared` modifier is a shared variable.</span></span> <span data-ttu-id="408e1-104">共享变量精确标识一个存储位置。</span><span class="sxs-lookup"><span data-stu-id="408e1-104">A shared variable identifies exactly one storage location.</span></span> <span data-ttu-id="408e1-105">使用修饰符声明的变量 `WithEvents` 断言变量所属的类型将处理变量引发的事件集。</span><span class="sxs-lookup"><span data-stu-id="408e1-105">A variable declared with the `WithEvents` modifier asserts that the type to which the variable belongs handles the set of events the variable raises.</span></span> <span data-ttu-id="408e1-106">将值分配给变量时，由声明创建的属性将 `WithEvents` 卸载任何现有的事件处理程序，并通过方法挂钩新的事件处理程序 `Add` 。</span><span class="sxs-lookup"><span data-stu-id="408e1-106">When a value is assigned to the variable, the property created by the `WithEvents` declaration unhooks any existing event handler and hooks up the new event handler via the `Add` method.</span></span>  
  
 <span data-ttu-id="408e1-107">**错误 ID：** BC30594</span><span class="sxs-lookup"><span data-stu-id="408e1-107">**Error ID:** BC30594</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="408e1-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="408e1-108">To correct this error</span></span>  
  
- <span data-ttu-id="408e1-109">声明事件处理程序 `Shared` 。</span><span class="sxs-lookup"><span data-stu-id="408e1-109">Declare your event handler `Shared`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="408e1-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="408e1-110">See also</span></span>

- [<span data-ttu-id="408e1-111">共享</span><span class="sxs-lookup"><span data-stu-id="408e1-111">Shared</span></span>](../modifiers/shared.md)
- [<span data-ttu-id="408e1-112">WithEvents</span><span class="sxs-lookup"><span data-stu-id="408e1-112">WithEvents</span></span>](../modifiers/withevents.md)
