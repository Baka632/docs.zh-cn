---
title: 调用方信息
description: 介绍如何使用调用方信息参数特性从方法获取调用方信息。
ms.date: 11/04/2019
ms.openlocfilehash: 700cde26fbe4e6c48155f88bfc63af59af86cfe2
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739771"
---
# <a name="caller-information"></a><span data-ttu-id="eb2d2-103">调用方信息</span><span class="sxs-lookup"><span data-stu-id="eb2d2-103">Caller information</span></span>

<span data-ttu-id="eb2d2-104">通过使用调用方信息特性，可获取有关方法的调用方的信息。</span><span class="sxs-lookup"><span data-stu-id="eb2d2-104">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="eb2d2-105">可以获取源代码的文件路径、源代码中的行号和调用方的成员名称。</span><span class="sxs-lookup"><span data-stu-id="eb2d2-105">You can obtain file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="eb2d2-106">此信息有助于跟踪、调试和创建诊断工具。</span><span class="sxs-lookup"><span data-stu-id="eb2d2-106">This information is helpful for tracing, debugging, and creating diagnostic tools.</span></span>

<span data-ttu-id="eb2d2-107">若要获取此信息，可以使用应用于可选参数的特性，每个特性都具有默认值。</span><span class="sxs-lookup"><span data-stu-id="eb2d2-107">To obtain this information, you use attributes that are applied to optional parameters, each of which has a default value.</span></span> <span data-ttu-id="eb2d2-108">下表列出了在 [system.runtime.compilerservices](/dotnet/api/system.runtime.compilerservices) 命名空间中定义的调用方信息特性：</span><span class="sxs-lookup"><span data-stu-id="eb2d2-108">The following table lists the Caller Info attributes that are defined in the [System.Runtime.CompilerServices](/dotnet/api/system.runtime.compilerservices) namespace:</span></span>

|<span data-ttu-id="eb2d2-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="eb2d2-109">Attribute</span></span>|<span data-ttu-id="eb2d2-110">描述</span><span class="sxs-lookup"><span data-stu-id="eb2d2-110">Description</span></span>|<span data-ttu-id="eb2d2-111">类型</span><span class="sxs-lookup"><span data-stu-id="eb2d2-111">Type</span></span>|
|---------|-----------|----|
|[<span data-ttu-id="eb2d2-112">CallerFilePath</span><span class="sxs-lookup"><span data-stu-id="eb2d2-112">CallerFilePath</span></span>](/dotnet/api/system.runtime.compilerservices.callerfilepathattribute)|<span data-ttu-id="eb2d2-113">包含调用方的源文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="eb2d2-113">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="eb2d2-114">这是编译时的文件路径。</span><span class="sxs-lookup"><span data-stu-id="eb2d2-114">This is the file path at compile time.</span></span>|`String`
|[<span data-ttu-id="eb2d2-115">CallerLineNumber</span><span class="sxs-lookup"><span data-stu-id="eb2d2-115">CallerLineNumber</span></span>](/dotnet/api/system.runtime.compilerservices.callerlinenumberattribute)|<span data-ttu-id="eb2d2-116">源文件中调用方法的行号。</span><span class="sxs-lookup"><span data-stu-id="eb2d2-116">Line number in the source file at which the method is called.</span></span>|`Integer`|
|[<span data-ttu-id="eb2d2-117">CallerMemberName</span><span class="sxs-lookup"><span data-stu-id="eb2d2-117">CallerMemberName</span></span>](/dotnet/api/system.runtime.compilerservices.callermembernameattribute)|<span data-ttu-id="eb2d2-118">调用方的方法或属性名称。</span><span class="sxs-lookup"><span data-stu-id="eb2d2-118">Method or property name of the caller.</span></span> <span data-ttu-id="eb2d2-119">请参阅本主题后面的成员名称部分。</span><span class="sxs-lookup"><span data-stu-id="eb2d2-119">See the Member Names section later in this topic.</span></span>|`String`|

## <a name="example"></a><span data-ttu-id="eb2d2-120">示例</span><span class="sxs-lookup"><span data-stu-id="eb2d2-120">Example</span></span>

<span data-ttu-id="eb2d2-121">下面的示例演示如何使用这些特性跟踪调用方。</span><span class="sxs-lookup"><span data-stu-id="eb2d2-121">The following example shows how you might use these attributes to trace a caller.</span></span>

```fsharp
open System.Diagnostics
open System.Runtime.CompilerServices
open System.Runtime.InteropServices

type Tracer() =
    member _.DoTrace(message: string,
                      [<CallerMemberName; Optional; DefaultParameterValue("")>] memberName: string,
                      [<CallerFilePath; Optional; DefaultParameterValue("")>] path: string,
                      [<CallerLineNumber; Optional; DefaultParameterValue(0)>] line: int) =
        Trace.WriteLine(sprintf $"Message: {message}")
        Trace.WriteLine(sprintf $"Member name: {memberName}")
        Trace.WriteLine(sprintf $"Source file path: {path}")
        Trace.WriteLine(sprintf $"Source line number: {line}")
```

## <a name="remarks"></a><span data-ttu-id="eb2d2-122">备注</span><span class="sxs-lookup"><span data-stu-id="eb2d2-122">Remarks</span></span>

<span data-ttu-id="eb2d2-123">调用方信息属性只能应用于可选参数。</span><span class="sxs-lookup"><span data-stu-id="eb2d2-123">Caller Info attributes can only be applied to optional parameters.</span></span> <span data-ttu-id="eb2d2-124">调用方信息特性导致编译器为使用调用方信息特性修饰的每个可选参数写入正确的值。</span><span class="sxs-lookup"><span data-stu-id="eb2d2-124">The Caller Info attributes cause the compiler to write the proper value for each optional parameter decorated with a Caller Info attribute.</span></span>

<span data-ttu-id="eb2d2-125">在编译时，调用方信息值将作为文本传入中间语言 (IL)。</span><span class="sxs-lookup"><span data-stu-id="eb2d2-125">Caller Info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="eb2d2-126">不同于异常的 [StackTrace](/dotnet/api/system.diagnostics.stacktrace) 属性的结果，结果不受模糊处理的影响。</span><span class="sxs-lookup"><span data-stu-id="eb2d2-126">Unlike the results of the [StackTrace](/dotnet/api/system.diagnostics.stacktrace) property for exceptions, the results aren't affected by obfuscation.</span></span>

<span data-ttu-id="eb2d2-127">你可显式提供可选参数来控制调用方信息或隐藏调用方信息。</span><span class="sxs-lookup"><span data-stu-id="eb2d2-127">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>

## <a name="member-names"></a><span data-ttu-id="eb2d2-128">成员名称</span><span class="sxs-lookup"><span data-stu-id="eb2d2-128">Member names</span></span>

<span data-ttu-id="eb2d2-129">可以使用 [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) 特性来避免将成员名称指定为 `String` 所调用的方法的参数。</span><span class="sxs-lookup"><span data-stu-id="eb2d2-129">You can use the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="eb2d2-130">通过使用此方法，您可以避免 "重命名重构" 不更改 `String` 值的问题。</span><span class="sxs-lookup"><span data-stu-id="eb2d2-130">By using this technique, you avoid the problem that Rename Refactoring doesn't change the `String` values.</span></span> <span data-ttu-id="eb2d2-131">此好处对于以下任务特别有用：</span><span class="sxs-lookup"><span data-stu-id="eb2d2-131">This benefit is especially useful for the following tasks:</span></span>

- <span data-ttu-id="eb2d2-132">使用跟踪和诊断例程。</span><span class="sxs-lookup"><span data-stu-id="eb2d2-132">Using tracing and diagnostic routines.</span></span>
- <span data-ttu-id="eb2d2-133">在绑定数据时实现 [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) 接口。</span><span class="sxs-lookup"><span data-stu-id="eb2d2-133">Implementing the [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) interface when binding data.</span></span> <span data-ttu-id="eb2d2-134">此接口允许对象的属性通知绑定控件该属性已更改，以便此控件能够显示更新的信息。</span><span class="sxs-lookup"><span data-stu-id="eb2d2-134">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="eb2d2-135">如果没有 [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) 特性，则必须将属性名称指定为文本。</span><span class="sxs-lookup"><span data-stu-id="eb2d2-135">Without the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute, you must specify the property name as a literal.</span></span>

<span data-ttu-id="eb2d2-136">下图显示了使用 CallerMemberName 特性时返回的成员名称。</span><span class="sxs-lookup"><span data-stu-id="eb2d2-136">The following chart shows the member names that are returned when you use the CallerMemberName attribute.</span></span>

|<span data-ttu-id="eb2d2-137">调用发生中</span><span class="sxs-lookup"><span data-stu-id="eb2d2-137">Calls occurs within</span></span>|<span data-ttu-id="eb2d2-138">成员名称结果</span><span class="sxs-lookup"><span data-stu-id="eb2d2-138">Member name result</span></span>|
|-------------------|------------------|
|<span data-ttu-id="eb2d2-139">方法、属性或事件</span><span class="sxs-lookup"><span data-stu-id="eb2d2-139">Method, property, or event</span></span>|<span data-ttu-id="eb2d2-140">从中发起调用的方法、属性或事件的名称。</span><span class="sxs-lookup"><span data-stu-id="eb2d2-140">The name of the method, property, or event from which the call originated.</span></span>|
|<span data-ttu-id="eb2d2-141">构造函数</span><span class="sxs-lookup"><span data-stu-id="eb2d2-141">Constructor</span></span>|<span data-ttu-id="eb2d2-142">字符串“.ctor”</span><span class="sxs-lookup"><span data-stu-id="eb2d2-142">The string ".ctor"</span></span>|
|<span data-ttu-id="eb2d2-143">静态构造函数</span><span class="sxs-lookup"><span data-stu-id="eb2d2-143">Static constructor</span></span>|<span data-ttu-id="eb2d2-144">字符串“.cctor”</span><span class="sxs-lookup"><span data-stu-id="eb2d2-144">The string ".cctor"</span></span>|
|<span data-ttu-id="eb2d2-145">析构函数</span><span class="sxs-lookup"><span data-stu-id="eb2d2-145">Destructor</span></span>|<span data-ttu-id="eb2d2-146">字符串“Finalize”</span><span class="sxs-lookup"><span data-stu-id="eb2d2-146">The string "Finalize"</span></span>|
|<span data-ttu-id="eb2d2-147">用户定义的运算符或转换</span><span class="sxs-lookup"><span data-stu-id="eb2d2-147">User-defined operators or conversions</span></span>|<span data-ttu-id="eb2d2-148">为成员生成的名称，例如，“op_Addition”。</span><span class="sxs-lookup"><span data-stu-id="eb2d2-148">The generated name for the member, for example, "op_Addition".</span></span>|
|<span data-ttu-id="eb2d2-149">特性构造函数</span><span class="sxs-lookup"><span data-stu-id="eb2d2-149">Attribute constructor</span></span>|<span data-ttu-id="eb2d2-150">要应用特性的成员的名称。</span><span class="sxs-lookup"><span data-stu-id="eb2d2-150">The name of the member to which the attribute is applied.</span></span> <span data-ttu-id="eb2d2-151">如果该特性是成员中的任何元素（如参数、返回值或泛型参数），则此结果是与该元素关联的成员的名称。</span><span class="sxs-lookup"><span data-stu-id="eb2d2-151">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|
|<span data-ttu-id="eb2d2-152">无包含的成员（例如，程序集级别或应用于类型的特性）</span><span class="sxs-lookup"><span data-stu-id="eb2d2-152">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="eb2d2-153">可选参数的默认值。</span><span class="sxs-lookup"><span data-stu-id="eb2d2-153">The default value of the optional parameter.</span></span>|

## <a name="see-also"></a><span data-ttu-id="eb2d2-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="eb2d2-154">See also</span></span>

- [<span data-ttu-id="eb2d2-155">特性</span><span class="sxs-lookup"><span data-stu-id="eb2d2-155">Attributes</span></span>](attributes.md)
- [<span data-ttu-id="eb2d2-156">命名参数</span><span class="sxs-lookup"><span data-stu-id="eb2d2-156">Named arguments</span></span>](parameters-and-arguments.md#named-arguments)
- [<span data-ttu-id="eb2d2-157">可选参数</span><span class="sxs-lookup"><span data-stu-id="eb2d2-157">Optional parameters</span></span>](parameters-and-arguments.md#optional-parameters)
