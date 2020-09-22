---
title: Error 语句
ms.date: 07/20/2015
f1_keywords:
- vb.error
helpviewer_keywords:
- Error statement [Visual Basic], syntax
- Error statement [Visual Basic]
- Error keyword [Visual Basic]
- run-time errors [Visual Basic], codes
- errors [Visual Basic], simulating
ms.assetid: 85cd5c59-5224-4f02-aaf5-fcfefab17a29
ms.openlocfilehash: f3f9f5ecb96686fe525e98cf64672d81a3145796
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873272"
---
# <a name="error-statement"></a><span data-ttu-id="36965-102">Error 语句</span><span class="sxs-lookup"><span data-stu-id="36965-102">Error Statement</span></span>

<span data-ttu-id="36965-103">模拟出现错误的情况。</span><span class="sxs-lookup"><span data-stu-id="36965-103">Simulates the occurrence of an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36965-104">语法</span><span class="sxs-lookup"><span data-stu-id="36965-104">Syntax</span></span>  
  
```vb  
Error errornumber  
```  
  
## <a name="parts"></a><span data-ttu-id="36965-105">组成部分</span><span class="sxs-lookup"><span data-stu-id="36965-105">Parts</span></span>  

 `errornumber`  
 <span data-ttu-id="36965-106">必需。</span><span class="sxs-lookup"><span data-stu-id="36965-106">Required.</span></span> <span data-ttu-id="36965-107">可以是任何有效的错误号。</span><span class="sxs-lookup"><span data-stu-id="36965-107">Can be any valid error number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36965-108">备注</span><span class="sxs-lookup"><span data-stu-id="36965-108">Remarks</span></span>  

 <span data-ttu-id="36965-109">`Error`支持语句，以便向后兼容。</span><span class="sxs-lookup"><span data-stu-id="36965-109">The `Error` statement is supported for backward compatibility.</span></span> <span data-ttu-id="36965-110">在新代码中，特别是在创建对象时，使用 `Err` 对象的 `Raise` 方法来生成运行时错误。</span><span class="sxs-lookup"><span data-stu-id="36965-110">In new code, especially when creating objects, use the `Err` object's `Raise` method to generate run-time errors.</span></span>  
  
 <span data-ttu-id="36965-111">如果 `errornumber` 定义了，则在为 `Error` 对象的属性 `Err` 分配以下默认值之后，语句将调用错误处理程序：</span><span class="sxs-lookup"><span data-stu-id="36965-111">If `errornumber` is defined, the `Error` statement calls the error handler after the properties of the `Err` object are assigned the following default values:</span></span>  
  
|<span data-ttu-id="36965-112">属性</span><span class="sxs-lookup"><span data-stu-id="36965-112">Property</span></span>|<span data-ttu-id="36965-113">值</span><span class="sxs-lookup"><span data-stu-id="36965-113">Value</span></span>|  
|--------------|-----------|  
|`Number`|<span data-ttu-id="36965-114">指定为语句的参数的值 `Error` 。</span><span class="sxs-lookup"><span data-stu-id="36965-114">Value specified as argument to `Error` statement.</span></span> <span data-ttu-id="36965-115">可以是任何有效的错误号。</span><span class="sxs-lookup"><span data-stu-id="36965-115">Can be any valid error number.</span></span>|  
|`Source`|<span data-ttu-id="36965-116">当前 Visual Basic 项目的名称。</span><span class="sxs-lookup"><span data-stu-id="36965-116">Name of the current Visual Basic project.</span></span>|  
|`Description`|<span data-ttu-id="36965-117">对应于指定的函数的返回值的字符串表达式 `Error` `Number` （如果此字符串存在）。</span><span class="sxs-lookup"><span data-stu-id="36965-117">String expression corresponding to the return value of the `Error` function for the specified `Number`, if this string exists.</span></span> <span data-ttu-id="36965-118">如果字符串不存在，则 `Description` 包含零长度字符串 ( "" ) 。</span><span class="sxs-lookup"><span data-stu-id="36965-118">If the string does not exist, `Description` contains a zero-length string ("").</span></span>|  
|`HelpFile`|<span data-ttu-id="36965-119">适当的 Visual Basic 帮助文件的完全限定驱动器、路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="36965-119">The fully qualified drive, path, and file name of the appropriate Visual Basic Help file.</span></span>|  
|`HelpContext`|<span data-ttu-id="36965-120">对应于属性的错误的相应 Visual Basic 帮助文件上下文 ID `Number` 。</span><span class="sxs-lookup"><span data-stu-id="36965-120">The appropriate Visual Basic Help file context ID for the error corresponding to the `Number` property.</span></span>|  
|`LastDLLError`|<span data-ttu-id="36965-121">Zero。</span><span class="sxs-lookup"><span data-stu-id="36965-121">Zero.</span></span>|  
  
 <span data-ttu-id="36965-122">如果没有错误处理程序，或者未启用任何错误处理程序，则将创建错误消息并将其显示在 `Err` 对象属性中。</span><span class="sxs-lookup"><span data-stu-id="36965-122">If no error handler exists, or if none is enabled, an error message is created and displayed from the `Err` object properties.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="36965-123">某些 Visual Basic 主机应用程序无法创建对象。</span><span class="sxs-lookup"><span data-stu-id="36965-123">Some Visual Basic host applications cannot create objects.</span></span> <span data-ttu-id="36965-124">请参阅宿主应用程序的文档，以确定它是否可以创建类和对象。</span><span class="sxs-lookup"><span data-stu-id="36965-124">See your host application's documentation to determine whether it can create classes and objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36965-125">示例</span><span class="sxs-lookup"><span data-stu-id="36965-125">Example</span></span>  

 <span data-ttu-id="36965-126">此示例使用 `Error` 语句生成错误号11。</span><span class="sxs-lookup"><span data-stu-id="36965-126">This example uses the `Error` statement to generate error number 11.</span></span>  
  
```vb  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a><span data-ttu-id="36965-127">要求</span><span class="sxs-lookup"><span data-stu-id="36965-127">Requirements</span></span>  

 <span data-ttu-id="36965-128">**命名空间：** [Microsoft](../runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="36965-128">**Namespace:** [Microsoft.VisualBasic](../runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="36965-129">**程序集：** Microsoft.VisualBasic.dll) 中的 Visual Basic 运行时库 (</span><span class="sxs-lookup"><span data-stu-id="36965-129">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36965-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36965-130">See also</span></span>

- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [<span data-ttu-id="36965-131">On Error 语句</span><span class="sxs-lookup"><span data-stu-id="36965-131">On Error Statement</span></span>](on-error-statement.md)
- [<span data-ttu-id="36965-132">Resume 语句</span><span class="sxs-lookup"><span data-stu-id="36965-132">Resume Statement</span></span>](resume-statement.md)
- [<span data-ttu-id="36965-133">错误消息</span><span class="sxs-lookup"><span data-stu-id="36965-133">Error Messages</span></span>](../error-messages/index.md)
