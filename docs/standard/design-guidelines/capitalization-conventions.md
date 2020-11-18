---
title: 大小写约定
description: 为标识符、组合词和常见字词应用大写约定。 了解如何在 .NET 中使用区分大小写。
ms.date: 10/22/2008
helpviewer_keywords:
- camel-case names [.NET Framework]
- class library design guidelines [.NET Framework], capitalization
- Pascal-case names [.NET Framework]
- case sensitivity, capitalization conventions
- names [.NET Framework], capitalization
ms.assetid: 4c4ea526-9203-486f-b72d-29d61c5b3c6d
ms.openlocfilehash: 8df136fb57ad61ddfd87f4dec1f6490c63c3d977
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821523"
---
# <a name="capitalization-conventions"></a><span data-ttu-id="3003c-104">大小写约定</span><span class="sxs-lookup"><span data-stu-id="3003c-104">Capitalization Conventions</span></span>
<span data-ttu-id="3003c-105">本章中的指导原则介绍了使用大小写的简单方法，即在应用一致的情况下，使类型、成员和参数的标识符易于阅读。</span><span class="sxs-lookup"><span data-stu-id="3003c-105">The guidelines in this chapter lay out a simple method for using case that, when applied consistently, make identifiers for types, members, and parameters easy to read.</span></span>

## <a name="capitalization-rules-for-identifiers"></a><span data-ttu-id="3003c-106">标识符的大小写规则</span><span class="sxs-lookup"><span data-stu-id="3003c-106">Capitalization Rules for Identifiers</span></span>
 <span data-ttu-id="3003c-107">若要区分标识符中的单词，请将标识符中每个单词的首字母大写。</span><span class="sxs-lookup"><span data-stu-id="3003c-107">To differentiate words in an identifier, capitalize the first letter of each word in the identifier.</span></span> <span data-ttu-id="3003c-108">不要使用下划线来区分词，或在标识符中的任何位置使用下划线。</span><span class="sxs-lookup"><span data-stu-id="3003c-108">Do not use underscores to differentiate words, or for that matter, anywhere in identifiers.</span></span> <span data-ttu-id="3003c-109">有两种方法可以根据标识符的使用来大写标识符：</span><span class="sxs-lookup"><span data-stu-id="3003c-109">There are two appropriate ways to capitalize identifiers, depending on the use of the identifier:</span></span>

- <span data-ttu-id="3003c-110">PascalCasing</span><span class="sxs-lookup"><span data-stu-id="3003c-110">PascalCasing</span></span>

- <span data-ttu-id="3003c-111">camelCasing</span><span class="sxs-lookup"><span data-stu-id="3003c-111">camelCasing</span></span>

 <span data-ttu-id="3003c-112">PascalCasing 约定用于除了参数名称外的所有标识符，使每个单词的第一个字符大写， (包括长度超过两个字母的首字母缩写) ，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="3003c-112">The PascalCasing convention, used for all identifiers except parameter names, capitalizes the first character of each word (including acronyms over two letters in length), as shown in the following examples:</span></span>

 `PropertyDescriptor`
 `HtmlTag`

 <span data-ttu-id="3003c-113">这两个字母的首字母缩写词是一种特殊情况，其中两个字母都大写，如以下标识符所示：</span><span class="sxs-lookup"><span data-stu-id="3003c-113">A special case is made for two-letter acronyms in which both letters are capitalized, as shown in the following identifier:</span></span>

 `IOStream`

 <span data-ttu-id="3003c-114">CamelCasing 约定仅用于参数名称，将每个单词的第一个字符（除第一个单词之外）设为大写，如以下示例中所示。</span><span class="sxs-lookup"><span data-stu-id="3003c-114">The camelCasing convention, used only for parameter names, capitalizes the first character of each word except the first word, as shown in the following examples.</span></span> <span data-ttu-id="3003c-115">如示例中所示，以字母混合形式表示的两字母首字母缩写形式均为小写。</span><span class="sxs-lookup"><span data-stu-id="3003c-115">As the example also shows, two-letter acronyms that begin a camel-cased identifier are both lowercase.</span></span>

 `propertyDescriptor`
 `ioStream`
 `htmlTag`

 <span data-ttu-id="3003c-116">✔️对于包含多个单词的所有公共成员、类型和命名空间名称，请使用 PascalCasing。</span><span class="sxs-lookup"><span data-stu-id="3003c-116">✔️ DO use PascalCasing for all public member, type, and namespace names consisting of multiple words.</span></span>

 <span data-ttu-id="3003c-117">✔️使用 camelCasing 作为参数名称。</span><span class="sxs-lookup"><span data-stu-id="3003c-117">✔️ DO use camelCasing for parameter names.</span></span>

 <span data-ttu-id="3003c-118">下表描述了不同类型的标识符的大小写规则。</span><span class="sxs-lookup"><span data-stu-id="3003c-118">The following table describes the capitalization rules for different types of identifiers.</span></span>

|<span data-ttu-id="3003c-119">标识符</span><span class="sxs-lookup"><span data-stu-id="3003c-119">Identifier</span></span>|<span data-ttu-id="3003c-120">大小写</span><span class="sxs-lookup"><span data-stu-id="3003c-120">Casing</span></span>|<span data-ttu-id="3003c-121">示例</span><span class="sxs-lookup"><span data-stu-id="3003c-121">Example</span></span>|
|----------------|------------|-------------|
|<span data-ttu-id="3003c-122">命名空间</span><span class="sxs-lookup"><span data-stu-id="3003c-122">Namespace</span></span>|<span data-ttu-id="3003c-123">形式</span><span class="sxs-lookup"><span data-stu-id="3003c-123">Pascal</span></span>|`namespace System.Security { ... }`|
|<span data-ttu-id="3003c-124">类型</span><span class="sxs-lookup"><span data-stu-id="3003c-124">Type</span></span>|<span data-ttu-id="3003c-125">形式</span><span class="sxs-lookup"><span data-stu-id="3003c-125">Pascal</span></span>|`public class StreamReader { ... }`|
|<span data-ttu-id="3003c-126">接口</span><span class="sxs-lookup"><span data-stu-id="3003c-126">Interface</span></span>|<span data-ttu-id="3003c-127">形式</span><span class="sxs-lookup"><span data-stu-id="3003c-127">Pascal</span></span>|`public interface IEnumerable { ... }`|
|<span data-ttu-id="3003c-128">方法</span><span class="sxs-lookup"><span data-stu-id="3003c-128">Method</span></span>|<span data-ttu-id="3003c-129">形式</span><span class="sxs-lookup"><span data-stu-id="3003c-129">Pascal</span></span>|`public class Object {` <br />  `public virtual string ToString();` <br /> `}`|
|<span data-ttu-id="3003c-130">属性</span><span class="sxs-lookup"><span data-stu-id="3003c-130">Property</span></span>|<span data-ttu-id="3003c-131">形式</span><span class="sxs-lookup"><span data-stu-id="3003c-131">Pascal</span></span>|`public class String {` <br />  `public int Length { get; }` <br /> `}`|
|<span data-ttu-id="3003c-132">事件</span><span class="sxs-lookup"><span data-stu-id="3003c-132">Event</span></span>|<span data-ttu-id="3003c-133">形式</span><span class="sxs-lookup"><span data-stu-id="3003c-133">Pascal</span></span>|`public class Process {` <br />  `public event EventHandler Exited;` <br /> `}`|
|<span data-ttu-id="3003c-134">字段</span><span class="sxs-lookup"><span data-stu-id="3003c-134">Field</span></span>|<span data-ttu-id="3003c-135">形式</span><span class="sxs-lookup"><span data-stu-id="3003c-135">Pascal</span></span>|`public class MessageQueue {` <br />  `public static readonly TimeSpan` <br /> `InfiniteTimeout;` <br /> `}` <br /> `public struct UInt32 {` <br />  `public const Min = 0;` <br /> `}`|
|<span data-ttu-id="3003c-136">枚举值</span><span class="sxs-lookup"><span data-stu-id="3003c-136">Enum value</span></span>|<span data-ttu-id="3003c-137">形式</span><span class="sxs-lookup"><span data-stu-id="3003c-137">Pascal</span></span>|`public enum FileMode {` <br />  `Append,` <br />  `...` <br /> `}`|
|<span data-ttu-id="3003c-138">参数</span><span class="sxs-lookup"><span data-stu-id="3003c-138">Parameter</span></span>|<span data-ttu-id="3003c-139">混合</span><span class="sxs-lookup"><span data-stu-id="3003c-139">Camel</span></span>|`public class Convert {` <br />  `public static int ToInt32(string value);` <br /> `}`|

## <a name="capitalizing-compound-words-and-common-terms"></a><span data-ttu-id="3003c-140">大写复合词和常见字词</span><span class="sxs-lookup"><span data-stu-id="3003c-140">Capitalizing Compound Words and Common Terms</span></span>
 <span data-ttu-id="3003c-141">出于大写字母的目的，大多数复合词都被视为单个字词。</span><span class="sxs-lookup"><span data-stu-id="3003c-141">Most compound terms are treated as single words for purposes of capitalization.</span></span>

 <span data-ttu-id="3003c-142">❌ 不要将所谓的 "封闭格式" 组合词中的每个词大写。</span><span class="sxs-lookup"><span data-stu-id="3003c-142">❌ DO NOT capitalize each word in so-called closed-form compound words.</span></span>

 <span data-ttu-id="3003c-143">它们是以单个词（如终结点）形式编写的组合词。</span><span class="sxs-lookup"><span data-stu-id="3003c-143">These are compound words written as a single word, such as endpoint.</span></span> <span data-ttu-id="3003c-144">为了实现大小写准则，请将关闭窗体的组合词视为单个单词。</span><span class="sxs-lookup"><span data-stu-id="3003c-144">For the purpose of casing guidelines, treat a closed-form compound word as a single word.</span></span> <span data-ttu-id="3003c-145">使用当前字典来确定是否以闭合形式写入复合单词。</span><span class="sxs-lookup"><span data-stu-id="3003c-145">Use a current dictionary to determine if a compound word is written in closed form.</span></span>

|<span data-ttu-id="3003c-146">形式</span><span class="sxs-lookup"><span data-stu-id="3003c-146">Pascal</span></span>|<span data-ttu-id="3003c-147">混合</span><span class="sxs-lookup"><span data-stu-id="3003c-147">Camel</span></span>|<span data-ttu-id="3003c-148">非</span><span class="sxs-lookup"><span data-stu-id="3003c-148">Not</span></span>|
|------------|-----------|---------|
|`BitFlag`|`bitFlag`|`Bitflag`|
|`Callback`|`callback`|`CallBack`|
|`Canceled`|`canceled`|`Cancelled`|
|`DoNot`|`doNot`|`Don't`|
|`Email`|`email`|`EMail`|
|`Endpoint`|`endpoint`|`EndPoint`|
|`FileName`|`fileName`|`Filename`|
|`Gridline`|`gridline`|`GridLine`|
|`Hashtable`|`hashtable`|`HashTable`|
|`Id`|`id`|`ID`|
|`Indexes`|`indexes`|`Indices`|
|`LogOff`|`logOff`|`LogOut`|
|`LogOn`|`logOn`|`LogIn`|
|`Metadata`|`metadata`|`MetaData, metaData`|
|`Multipanel`|`multipanel`|`MultiPanel`|
|`Multiview`|`multiview`|`MultiView`|
|`Namespace`|`namespace`|`NameSpace`|
|`Ok`|`ok`|`OK`|
|`Pi`|`pi`|`PI`|
|`Placeholder`|`placeholder`|`PlaceHolder`|
|`SignIn`|`signIn`|`SignOn`|
|`SignOut`|`signOut`|`SignOff`|
|`UserName`|`userName`|`Username`|
|`WhiteSpace`|`whiteSpace`|`Whitespace`|
|`Writable`|`writable`|`Writeable`|

## <a name="case-sensitivity"></a><span data-ttu-id="3003c-149">区分大小写</span><span class="sxs-lookup"><span data-stu-id="3003c-149">Case Sensitivity</span></span>
 <span data-ttu-id="3003c-150">可在 CLR 上运行的语言不需要支持区分大小写，但有些则不需要。</span><span class="sxs-lookup"><span data-stu-id="3003c-150">Languages that can run on the CLR are not required to support case-sensitivity, although some do.</span></span> <span data-ttu-id="3003c-151">即使您的语言支持，其他可能访问您的框架的语言也不是这样。</span><span class="sxs-lookup"><span data-stu-id="3003c-151">Even if your language supports it, other languages that might access your framework do not.</span></span> <span data-ttu-id="3003c-152">因此，外部可访问的任何 Api 都不能单独依赖于 case 来区分同一上下文中的两个名称。</span><span class="sxs-lookup"><span data-stu-id="3003c-152">Any APIs that are externally accessible, therefore, cannot rely on case alone to distinguish between two names in the same context.</span></span>

 <span data-ttu-id="3003c-153">❌ 不要假设所有编程语言都区分大小写。</span><span class="sxs-lookup"><span data-stu-id="3003c-153">❌ DO NOT assume that all programming languages are case sensitive.</span></span> <span data-ttu-id="3003c-154">它们不是。</span><span class="sxs-lookup"><span data-stu-id="3003c-154">They are not.</span></span> <span data-ttu-id="3003c-155">名称不能单独区分。</span><span class="sxs-lookup"><span data-stu-id="3003c-155">Names cannot differ by case alone.</span></span>

 <span data-ttu-id="3003c-156">*部分©2005，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="3003c-156">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="3003c-157">*经许可重印皮尔逊教育，Inc. 的作者 [：从框架设计指导原则：用于可重复使用的 .Net 库的约定、惯例和模式; 第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) By Krzysztof Cwalina，Brad Abrams，通过 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分2008发布。*</span><span class="sxs-lookup"><span data-stu-id="3003c-157">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="3003c-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3003c-158">See also</span></span>

- [<span data-ttu-id="3003c-159">框架设计准则</span><span class="sxs-lookup"><span data-stu-id="3003c-159">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="3003c-160">命名准则</span><span class="sxs-lookup"><span data-stu-id="3003c-160">Naming Guidelines</span></span>](naming-guidelines.md)
