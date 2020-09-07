---
ms.openlocfilehash: 4416a7c09f2d163961fe2fe3d6dfaa8bd5e66f93
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497700"
---
### <a name="change-in-behavior-in-data-definition-language-ddl-apis"></a><span data-ttu-id="d7233-101">数据定义语言 (DDL) API 行为的更改</span><span class="sxs-lookup"><span data-stu-id="d7233-101">Change in behavior in Data Definition Language (DDL) APIs</span></span>

#### <a name="details"></a><span data-ttu-id="d7233-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="d7233-102">Details</span></span>

<span data-ttu-id="d7233-103">指定 AttachDBFilename 时，DDL API 的行为已更改，具体如下：</span><span class="sxs-lookup"><span data-stu-id="d7233-103">The behavior of DDL APIs when AttachDBFilename is specified has changed as follows:</span></span><ul><li><span data-ttu-id="d7233-104">连接字符串不需要指定 Initial Catalog 值。</span><span class="sxs-lookup"><span data-stu-id="d7233-104">Connection strings need not specify an Initial Catalog value.</span></span> <span data-ttu-id="d7233-105">以前，需要 AttachDBFilename 和 Initial Catalog。</span><span class="sxs-lookup"><span data-stu-id="d7233-105">Previously, both AttachDBFilename and Initial Catalog were required.</span></span></li><li><span data-ttu-id="d7233-106">如果指定了 AttachDBFilename 和 Initial Catalog，并且存在给定的 MDF 文件，<xref:System.Data.Objects.ObjectContext.DatabaseExists%2A> 方法将返回 <code>true</code>。</span><span class="sxs-lookup"><span data-stu-id="d7233-106">If both AttachDBFilename and Initial Catalog are specified and the given MDF file exists, the <xref:System.Data.Objects.ObjectContext.DatabaseExists%2A> method returns <code>true</code>.</span></span> <span data-ttu-id="d7233-107">以前，它会返回 <code>false</code>。</span><span class="sxs-lookup"><span data-stu-id="d7233-107">Previously, it returned <code>false</code>.</span></span></li><li><span data-ttu-id="d7233-108">如果指定了 AttachDBFilename 和 Initial Catalog，并且存在给定的 MDF 文件，则调用 <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A> 方法会删除这些文件。</span><span class="sxs-lookup"><span data-stu-id="d7233-108">If both AttachDBFilename and Initial Catalog are specified and the given MDF file exists, calling the <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A> method deletes the files.</span></span></li><li><span data-ttu-id="d7233-109">如果在连接字符串指定一个 AttachDBFilename 值，且不存在 MDF 和 Initial Catalog 时调用 <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A>，则该方法将引发 <xref:System.InvalidOperationException> 异常。</span><span class="sxs-lookup"><span data-stu-id="d7233-109">If <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A> is called when the connection string specifies an AttachDBFilename value with an MDF that doesn't exist and an Initial Catalog that doesn't exist, the method throws an <xref:System.InvalidOperationException> exception.</span></span> <span data-ttu-id="d7233-110">以前，它会引发 <xref:System.Data.SqlClient.SqlException> 异常。</span><span class="sxs-lookup"><span data-stu-id="d7233-110">Previously, it threw a <xref:System.Data.SqlClient.SqlException> exception.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="d7233-111">建议</span><span class="sxs-lookup"><span data-stu-id="d7233-111">Suggestion</span></span>

<span data-ttu-id="d7233-112">利用这些更改，可以更轻松地生成使用 DDL API 的工具和应用程序。</span><span class="sxs-lookup"><span data-stu-id="d7233-112">These changes make it easier to build tools and applications that use the DDL APIs.</span></span> <span data-ttu-id="d7233-113">这些更改会影响以下方案中的应用程序兼容性：</span><span class="sxs-lookup"><span data-stu-id="d7233-113">These changes can affect application compatibility in the following scenarios:</span></span><ul><li><span data-ttu-id="d7233-114">如果 <code>DROP DATABASE</code> 返回 <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A>，则用户会编写直接执行 <xref:System.Data.Objects.ObjectContext.DatabaseExists%2A> 命令而不是调用 <code>true</code> 的代码。</span><span class="sxs-lookup"><span data-stu-id="d7233-114">The user writes code that executes a <code>DROP DATABASE</code> command directly instead of calling <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A> if <xref:System.Data.Objects.ObjectContext.DatabaseExists%2A> returns <code>true</code>.</span></span> <span data-ttu-id="d7233-115">如果未附加数据库但存在 MDF 文件，则会中断现有代码。</span><span class="sxs-lookup"><span data-stu-id="d7233-115">This breaks existing code If the database is not attached but the MDF file exists.</span></span></li><li><span data-ttu-id="d7233-116">用户编写的代码预期 <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A> 方法在 Initial Catalog 和 MDF 文件不存在时引发 <xref:System.Data.SqlClient.SqlException> 而非 <xref:System.InvalidOperationException>。</span><span class="sxs-lookup"><span data-stu-id="d7233-116">The user writes code that expects the <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A> method to throw a <xref:System.Data.SqlClient.SqlException> rather than an <xref:System.InvalidOperationException> when the Initial Catalog and MDF file don't exist.</span></span></li></ul>

| <span data-ttu-id="d7233-117">“属性”</span><span class="sxs-lookup"><span data-stu-id="d7233-117">Name</span></span>    | <span data-ttu-id="d7233-118">“值”</span><span class="sxs-lookup"><span data-stu-id="d7233-118">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d7233-119">范围</span><span class="sxs-lookup"><span data-stu-id="d7233-119">Scope</span></span>   |<span data-ttu-id="d7233-120">次要</span><span class="sxs-lookup"><span data-stu-id="d7233-120">Minor</span></span>|
|<span data-ttu-id="d7233-121">Version</span><span class="sxs-lookup"><span data-stu-id="d7233-121">Version</span></span>|<span data-ttu-id="d7233-122">4.5</span><span class="sxs-lookup"><span data-stu-id="d7233-122">4.5</span></span>|
|<span data-ttu-id="d7233-123">类型</span><span class="sxs-lookup"><span data-stu-id="d7233-123">Type</span></span>|<span data-ttu-id="d7233-124">运行时</span><span class="sxs-lookup"><span data-stu-id="d7233-124">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="d7233-125">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="d7233-125">Affected APIs</span></span>

<span data-ttu-id="d7233-126">无法通过 API 分析检测到。</span><span class="sxs-lookup"><span data-stu-id="d7233-126">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
