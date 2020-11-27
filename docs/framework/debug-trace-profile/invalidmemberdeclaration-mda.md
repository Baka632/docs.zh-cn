---
title: invalidMemberDeclaration MDA
description: 查看 invalidMemberDeclaration 托管调试助手，如果在未调用托管方法的情况下将错误 HRESULT 返回到 COM，则会调用它。
ms.date: 03/30/2017
helpviewer_keywords:
- invalid member declaration
- InvalidMemberDeclaration MDA
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: a84dd9a3-d6cf-4824-989a-ecbbf443eeb4
ms.openlocfilehash: c8d6c69fc6eb4f5f690b02809fdc492da675c3b1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272548"
---
# <a name="invalidmemberdeclaration-mda"></a><span data-ttu-id="ef385-103">invalidMemberDeclaration MDA</span><span class="sxs-lookup"><span data-stu-id="ef385-103">invalidMemberDeclaration MDA</span></span>

<span data-ttu-id="ef385-104">激活 `invalidMemberDeclaration` 托管调试助手 (MDA) 以报告在确定如何封送要从 COM 调用的成员的参数期间发生的错误。</span><span class="sxs-lookup"><span data-stu-id="ef385-104">The `invalidMemberDeclaration` managed debugging assistant (MDA) is activated to report an error that occurs while determining how to marshal the parameters of a member to be called from COM.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="ef385-105">症状</span><span class="sxs-lookup"><span data-stu-id="ef385-105">Symptoms</span></span>  

 <span data-ttu-id="ef385-106">一个失败 HRESULT 被返回到 COM，且未调用托管方法。</span><span class="sxs-lookup"><span data-stu-id="ef385-106">A failure HRESULT is returned to COM without the managed method having been called.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="ef385-107">原因</span><span class="sxs-lookup"><span data-stu-id="ef385-107">Cause</span></span>  

 <span data-ttu-id="ef385-108">这很有可能是因为不兼容其中一个参数上的 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 特性。</span><span class="sxs-lookup"><span data-stu-id="ef385-108">This is most likely due to an incompatible <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute on one of the parameters.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="ef385-109">解决方法</span><span class="sxs-lookup"><span data-stu-id="ef385-109">Resolution</span></span>  

 <span data-ttu-id="ef385-110">指定参数上的有效 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 特性。</span><span class="sxs-lookup"><span data-stu-id="ef385-110">Specify valid <xref:System.Runtime.InteropServices.MarshalAsAttribute> attributes on the parameters.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="ef385-111">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="ef385-111">Effect on the Runtime</span></span>  

 <span data-ttu-id="ef385-112">此 MDA 对 CLR 无任何影响。</span><span class="sxs-lookup"><span data-stu-id="ef385-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="ef385-113">输出</span><span class="sxs-lookup"><span data-stu-id="ef385-113">Output</span></span>  

 <span data-ttu-id="ef385-114">信息性消息包括成员名称、类型名称和错误消息。</span><span class="sxs-lookup"><span data-stu-id="ef385-114">An informational message containing the member name, type name, and error message.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="ef385-115">Configuration</span><span class="sxs-lookup"><span data-stu-id="ef385-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidMemberDeclaration/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ef385-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ef385-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="ef385-117">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="ef385-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="ef385-118">互操作封送处理</span><span class="sxs-lookup"><span data-stu-id="ef385-118">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
