---
title: Narrowing
ms.date: 07/20/2015
f1_keywords:
- vb.narrowing
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Narrowing keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: a207ee91-aca4-4771-b4e2-713f029bf2bb
ms.openlocfilehash: 77515357ac9dc972992df09c471695aad13985c4
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867926"
---
# <a name="narrowing-visual-basic"></a><span data-ttu-id="bcf4e-102">Narrowing (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bcf4e-102">Narrowing (Visual Basic)</span></span>

<span data-ttu-id="bcf4e-103">指示转换运算符 (`CType`) 将类或结构转换为可能无法保存原始类或结构的某些可能值的类型。</span><span class="sxs-lookup"><span data-stu-id="bcf4e-103">Indicates that a conversion operator (`CType`) converts a class or structure to a type that might not be able to hold some of the possible values of the original class or structure.</span></span>  
  
## <a name="converting-with-the-narrowing-keyword"></a><span data-ttu-id="bcf4e-104">用收缩关键字转换</span><span class="sxs-lookup"><span data-stu-id="bcf4e-104">Converting with the Narrowing Keyword</span></span>  

 <span data-ttu-id="bcf4e-105">除了之外，转换过程必须指定 `Public Shared` `Narrowing` 。</span><span class="sxs-lookup"><span data-stu-id="bcf4e-105">The conversion procedure must specify `Public Shared` in addition to `Narrowing`.</span></span>  
  
 <span data-ttu-id="bcf4e-106">收缩转换在运行时并不总是成功，可能会失败或导致数据丢失。</span><span class="sxs-lookup"><span data-stu-id="bcf4e-106">Narrowing conversions do not always succeed at run time, and can fail or incur data loss.</span></span> <span data-ttu-id="bcf4e-107">示例包括 `Long` 对 `Integer` `String` 派生类型的、到 `Date` 和基类型。</span><span class="sxs-lookup"><span data-stu-id="bcf4e-107">Examples are `Long` to `Integer`, `String` to `Date`, and a base type to a derived type.</span></span> <span data-ttu-id="bcf4e-108">此上一转换是收缩的，因为基类型可能不包含派生类型的所有成员，因此不是派生类型的实例。</span><span class="sxs-lookup"><span data-stu-id="bcf4e-108">This last conversion is narrowing because the base type might not contain all the members of the derived type and thus is not an instance of the derived type.</span></span>  
  
 <span data-ttu-id="bcf4e-109">如果 `Option Strict` 为 `On` ，则使用的代码必须用于 `CType` 所有收缩转换。</span><span class="sxs-lookup"><span data-stu-id="bcf4e-109">If `Option Strict` is `On`, the consuming code must use `CType` for all narrowing conversions.</span></span>  
  
 <span data-ttu-id="bcf4e-110">`Narrowing`关键字可以在此上下文中使用：</span><span class="sxs-lookup"><span data-stu-id="bcf4e-110">The `Narrowing` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="bcf4e-111">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="bcf4e-111">Operator Statement</span></span>](../statements/operator-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="bcf4e-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bcf4e-112">See also</span></span>

- [<span data-ttu-id="bcf4e-113">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="bcf4e-113">Operator Statement</span></span>](../statements/operator-statement.md)
- [<span data-ttu-id="bcf4e-114">Widening</span><span class="sxs-lookup"><span data-stu-id="bcf4e-114">Widening</span></span>](widening.md)
- [<span data-ttu-id="bcf4e-115">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="bcf4e-115">Widening and Narrowing Conversions</span></span>](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="bcf4e-116">如何：定义运算符</span><span class="sxs-lookup"><span data-stu-id="bcf4e-116">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="bcf4e-117">CType Function</span><span class="sxs-lookup"><span data-stu-id="bcf4e-117">CType Function</span></span>](../functions/ctype-function.md)
- [<span data-ttu-id="bcf4e-118">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="bcf4e-118">Option Strict Statement</span></span>](../statements/option-strict-statement.md)
