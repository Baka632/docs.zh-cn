---
title: 使用用户筛选的异常处理程序
ms.date: 03/30/2017
helpviewer_keywords:
- user-filtered exceptions
- exceptions, user-filtered
ms.assetid: aa80d155-060d-41b4-a636-1ceb424afee8
ms.openlocfilehash: d98412ed651886afc54e15b346a63dc0c549abd0
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "94827979"
---
# <a name="using-user-filtered-exception-handlers"></a><span data-ttu-id="30110-102">使用用户筛选的异常处理程序</span><span class="sxs-lookup"><span data-stu-id="30110-102">Using User-Filtered Exception Handlers</span></span>

<span data-ttu-id="30110-103">目前，Visual Basic 支持用户筛选的异常。</span><span class="sxs-lookup"><span data-stu-id="30110-103">Currently, Visual Basic supports user-filtered exceptions.</span></span> <span data-ttu-id="30110-104">用户筛选的异常处理程序基于定义的异常需求来捕获和处理异常。</span><span class="sxs-lookup"><span data-stu-id="30110-104">User-filtered exception handlers catch and handle exceptions based on requirements you define for the exception.</span></span> <span data-ttu-id="30110-105">这些处理程序使用含有关键字 **When** 的 **Catch** 语句。</span><span class="sxs-lookup"><span data-stu-id="30110-105">These handlers use the **Catch** statement with the **When** keyword.</span></span>  
  
 <span data-ttu-id="30110-106">特定异常对象对应于多个错误时，此方法非常有用。</span><span class="sxs-lookup"><span data-stu-id="30110-106">This technique is useful when a particular exception object corresponds to multiple errors.</span></span> <span data-ttu-id="30110-107">在这种情况下，该对象通常包含与错误关联的特定错误代码的属性。</span><span class="sxs-lookup"><span data-stu-id="30110-107">In this case, the object typically has a property that contains the specific error code associated with the error.</span></span> <span data-ttu-id="30110-108">可以在表达式中使用此错误代码属性，以便只选择要在 **Catch** 子句中处理的特定错误。</span><span class="sxs-lookup"><span data-stu-id="30110-108">You can use the error code property in the expression to select only the particular error you want to handle in that **Catch** clause.</span></span>  
  
 <span data-ttu-id="30110-109">下面的 Visual Basic 示例阐释 **Catch/When** 语句。</span><span class="sxs-lookup"><span data-stu-id="30110-109">The following Visual Basic example illustrates the **Catch/When** statement.</span></span>  
  
```vb
Try  
    'Try statements.  
    Catch When Err = VBErr_ClassLoadException
    'Catch statements.
End Try  
```  
  
 <span data-ttu-id="30110-110">用户筛选的子句的表达式不受任何限制。</span><span class="sxs-lookup"><span data-stu-id="30110-110">The expression of the user-filtered clause is not restricted in any way.</span></span> <span data-ttu-id="30110-111">如果在执行用户筛选的表达式期间发生异常，则将放弃该异常，并视筛选表达式的值为 false。</span><span class="sxs-lookup"><span data-stu-id="30110-111">If an exception occurs during execution of the user-filtered expression, that exception is discarded and the filter expression is considered to have evaluated to false.</span></span> <span data-ttu-id="30110-112">在这种情况下，公共语言运行时继续搜索当前异常的处理程序。</span><span class="sxs-lookup"><span data-stu-id="30110-112">In this case, the common language runtime continues the search for a handler for the current exception.</span></span>  
  
## <a name="combining-the-specific-exception-and-the-user-filtered-clauses"></a><span data-ttu-id="30110-113">结合特定异常和用户筛选的子句</span><span class="sxs-lookup"><span data-stu-id="30110-113">Combining the Specific Exception and the User-Filtered Clauses</span></span>  
 <span data-ttu-id="30110-114">Catch 语句可以同时包含特定异常和用户筛选的子句。</span><span class="sxs-lookup"><span data-stu-id="30110-114">A catch statement can contain both the specific exception and the user-filtered clauses.</span></span> <span data-ttu-id="30110-115">运行时首先测试特定异常。</span><span class="sxs-lookup"><span data-stu-id="30110-115">The runtime tests the specific exception first.</span></span> <span data-ttu-id="30110-116">如果特定异常成功，运行时会执行用户筛选。</span><span class="sxs-lookup"><span data-stu-id="30110-116">If the specific exception succeeds, the runtime executes the user filter.</span></span> <span data-ttu-id="30110-117">普通筛选可包含对类筛选器中声明的变量的引用。</span><span class="sxs-lookup"><span data-stu-id="30110-117">The generic filter can contain a reference to the variable declared in the class filter.</span></span> <span data-ttu-id="30110-118">请注意，两个筛选子句的顺序不能颠倒。</span><span class="sxs-lookup"><span data-stu-id="30110-118">Note that the order of the two filter clauses cannot be reversed.</span></span>  
  
 <span data-ttu-id="30110-119">下面的 Visual Basic 示例介绍 **Catch** 语句中的特定异常 `ClassLoadException` 以及使用 **When** 关键字的用户筛选的子句。</span><span class="sxs-lookup"><span data-stu-id="30110-119">The following Visual Basic example shows the specific exception `ClassLoadException` in the **Catch** statement as well as the user-filtered clause using the **When** keyword.</span></span>  
  
```vb
Try  
    'Try statements.
    Catch cle As ClassLoadException When cle.IsRecoverable()  
    'Catch statements.
End Try  
```  

## <a name="see-also"></a><span data-ttu-id="30110-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="30110-120">See also</span></span>

- [<span data-ttu-id="30110-121">异常</span><span class="sxs-lookup"><span data-stu-id="30110-121">Exceptions</span></span>](index.md)
