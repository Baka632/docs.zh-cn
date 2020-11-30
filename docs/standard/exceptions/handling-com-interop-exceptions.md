---
title: 处理 COM 互操作异常
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged code, exceptions
- exceptions, unmanaged code
- HRESULTs
- exceptions, COM interop
- COM interop, exceptions
ms.assetid: e6104aa8-8e5f-4069-b864-def85579c96c
ms.openlocfilehash: 42efd1a5622bae7c476c92fb0864a6214c9bac9b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726179"
---
# <a name="handling-com-interop-exceptions"></a><span data-ttu-id="1ee1f-102">处理 COM 互操作异常</span><span class="sxs-lookup"><span data-stu-id="1ee1f-102">Handling COM Interop Exceptions</span></span>

<span data-ttu-id="1ee1f-103">托管和非托管代码可协同工作来处理异常。</span><span class="sxs-lookup"><span data-stu-id="1ee1f-103">Managed and unmanaged code can work together to handle exceptions.</span></span> <span data-ttu-id="1ee1f-104">如果方法在托管代码中引发异常，公共语言运行时可将 HRESULT 传递至 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="1ee1f-104">If a method throws an exception in managed code, the common language runtime can pass an HRESULT to a COM object.</span></span> <span data-ttu-id="1ee1f-105">如果方法因返回失败 HRESULT 而在非托管代码中失败，运行时会引发可由托管代码捕获的异常。</span><span class="sxs-lookup"><span data-stu-id="1ee1f-105">If a method fails in unmanaged code by returning a failure HRESULT, the runtime throws an exception that can be caught by managed code.</span></span>  
  
 <span data-ttu-id="1ee1f-106">运行时自动将 HRESULT 从 COM 互操作映射到更具体的异常。</span><span class="sxs-lookup"><span data-stu-id="1ee1f-106">The runtime automatically maps the HRESULT from COM interop to more specific exceptions.</span></span> <span data-ttu-id="1ee1f-107">例如，E_ACCESSDENIED 成为 <xref:System.UnauthorizedAccessException>、E_OUTOFMEMORY 成为 <xref:System.OutOfMemoryException>，依次类推。</span><span class="sxs-lookup"><span data-stu-id="1ee1f-107">For example, E_ACCESSDENIED becomes <xref:System.UnauthorizedAccessException>, E_OUTOFMEMORY becomes <xref:System.OutOfMemoryException>, and so on.</span></span>  
  
 <span data-ttu-id="1ee1f-108">如果 HRESULT 为自定义结果或运行时不知道它，运行时会将泛型 <xref:System.Runtime.InteropServices.COMException> 传递到客户端。</span><span class="sxs-lookup"><span data-stu-id="1ee1f-108">If the HRESULT is a custom result or if it is unknown to the runtime, the runtime passes a generic <xref:System.Runtime.InteropServices.COMException> to the client.</span></span> <span data-ttu-id="1ee1f-109">COMException 的 ErrorCode 属性包含 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="1ee1f-109">The **ErrorCode** property of the **COMException** contains the HRESULT value.</span></span>  
  
## <a name="working-with-ierrorinfo"></a><span data-ttu-id="1ee1f-110">处理 IErrorInfo</span><span class="sxs-lookup"><span data-stu-id="1ee1f-110">Working with IErrorInfo</span></span>  

 <span data-ttu-id="1ee1f-111">当错误从 COM 传递至托管代码时，运行时会将错误信息填充至异常对象。</span><span class="sxs-lookup"><span data-stu-id="1ee1f-111">When an error is passed from COM to managed code, the runtime populates the exception object with error information.</span></span> <span data-ttu-id="1ee1f-112">支持 IErrorInfo 并返回 HRESULT 的 COM 对象将向托管代码异常提供此信息。</span><span class="sxs-lookup"><span data-stu-id="1ee1f-112">COM objects that support IErrorInfo and return HRESULTS provide this information to managed code exceptions.</span></span> <span data-ttu-id="1ee1f-113">例如，运行时将“说明”从 COM 错误映射至异常的 <xref:System.Exception.Message%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="1ee1f-113">For example, the runtime maps the Description from the COM error to the exception's <xref:System.Exception.Message%2A> property.</span></span> <span data-ttu-id="1ee1f-114">如果 HRESULT 未提供任何其他错误信息，运行时将对很多异常的属性填充默认值。</span><span class="sxs-lookup"><span data-stu-id="1ee1f-114">If the HRESULT provides no additional error information, the runtime fills many of the exception's properties with default values.</span></span>  
  
 <span data-ttu-id="1ee1f-115">如果方法在非托管代码中失败，则异常可以传递至托管代码段中。</span><span class="sxs-lookup"><span data-stu-id="1ee1f-115">If a method fails in unmanaged code, an exception can be passed to a managed code segment.</span></span> <span data-ttu-id="1ee1f-116">主题 [HRESULTS 和异常](../../framework/interop/how-to-map-hresults-and-exceptions.md)中的表展示了如何将 HRESULTS 映射到运行时异常对象。</span><span class="sxs-lookup"><span data-stu-id="1ee1f-116">The topic [HRESULTS and Exceptions](../../framework/interop/how-to-map-hresults-and-exceptions.md) contains a table showing how HRESULTS map to runtime exception objects.</span></span>  

## <a name="see-also"></a><span data-ttu-id="1ee1f-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1ee1f-117">See also</span></span>

- [<span data-ttu-id="1ee1f-118">异常</span><span class="sxs-lookup"><span data-stu-id="1ee1f-118">Exceptions</span></span>](index.md)
