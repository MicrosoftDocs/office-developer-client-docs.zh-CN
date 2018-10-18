---
title: Open 方法 (ADO Record)
TOCTitle: Open Method (ADO Record)
ms:assetid: ba71c5c7-326e-d3b6-0e74-e8343ee6896f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249896(v=office.15)
ms:contentKeyID: 48547371
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f29f707f02ed8adbf2b1881b0721ce912b278353
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25605826"
---
# <a name="open-method-ado-record"></a><span data-ttu-id="7c92a-102">Open 方法 (ADO Record)</span><span class="sxs-lookup"><span data-stu-id="7c92a-102">Open Method (ADO Record)</span></span>


<span data-ttu-id="7c92a-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="7c92a-103">**Applies to**: Access 2013 | Office 2013</span></span>


<span data-ttu-id="7c92a-104">用于打开现有的 [Record](record-object-ado.md) 对象，或创建由 **Record** 表示的新项（如文件或目录）。</span><span class="sxs-lookup"><span data-stu-id="7c92a-104">Opens an existing [Record](record-object-ado.md) object, or creates a new item represented by the **Record** (such as a file or directory).</span></span>

## <a name="syntax"></a><span data-ttu-id="7c92a-105">语法</span><span class="sxs-lookup"><span data-stu-id="7c92a-105">Syntax</span></span>

<span data-ttu-id="7c92a-106">打开*源*、 *ActiveConnection*、*模式*、 *CreateOptions*、*选项*、*用户名*、*密码*</span><span class="sxs-lookup"><span data-stu-id="7c92a-106">Open *Source*, *ActiveConnection*, *Mode*, *CreateOptions*, *Options*, *UserName*, *Password*</span></span>

## <a name="parameters"></a><span data-ttu-id="7c92a-107">参数</span><span class="sxs-lookup"><span data-stu-id="7c92a-107">Parameters</span></span>

  - <span data-ttu-id="7c92a-108">*Source*</span><span class="sxs-lookup"><span data-stu-id="7c92a-108">*Source*</span></span>

  - <span data-ttu-id="7c92a-p101">可选。 **变量型** 值，可以表示要由该 **Record** 对象表示的实体的 URL、 **Command** 、打开的 [Recordset](recordset-object-ado.md) 或其他 **Record** 对象，也可以表示包含 SQL SELECT 语句或表名的字符串。</span><span class="sxs-lookup"><span data-stu-id="7c92a-p101">Optional. A **Variant** that may represent the URL of the entity to be represented by this **Record** object, a **Command**, an open [Recordset](recordset-object-ado.md) or another **Record** object, a string containing a SQL SELECT statement or a table name.</span></span>

  - <span data-ttu-id="7c92a-111">*ActiveConnection*</span><span class="sxs-lookup"><span data-stu-id="7c92a-111">*ActiveConnection*</span></span>

  - <span data-ttu-id="7c92a-p102">可选。 **变量型** 值，表示连接字符串或打开的 [Connection](connection-object-ado.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="7c92a-p102">Optional. A **Variant** that represents the connect string or open [Connection](connection-object-ado.md) object.</span></span>

  - <span data-ttu-id="7c92a-114">*Mode*</span><span class="sxs-lookup"><span data-stu-id="7c92a-114">*Mode*</span></span>

  - <span data-ttu-id="7c92a-p103">可选。[ConnectModeEnum](connectmodeenum.md) 值，其默认值为 **adModeUnknown** ，指定生成的 **Record** 对象的访问模式。</span><span class="sxs-lookup"><span data-stu-id="7c92a-p103">Optional. A [ConnectModeEnum](connectmodeenum.md) value, whose default value is **adModeUnknown**, that specifies the access mode for the resultant **Record** object.</span></span>

  - <span data-ttu-id="7c92a-117">*CreateOptions*</span><span class="sxs-lookup"><span data-stu-id="7c92a-117">*CreateOptions*</span></span>

  - <span data-ttu-id="7c92a-118">可选。</span><span class="sxs-lookup"><span data-stu-id="7c92a-118">Optional.</span></span> <span data-ttu-id="7c92a-119">应创建一个[RecordCreateOptionsEnum](recordcreateoptionsenum.md)值，其默认值是**adFailIfNotExists**，指定是否应打开现有文件或目录，或新文件或目录。</span><span class="sxs-lookup"><span data-stu-id="7c92a-119">A [RecordCreateOptionsEnum](recordcreateoptionsenum.md) value, whose default value is **adFailIfNotExists**, that specifies whether an existing file or directory should be opened, or a new file or directory should be created.</span></span> <span data-ttu-id="7c92a-120">如果设置为默认值，访问模式从[Mode](mode-property-ado.md)属性。</span><span class="sxs-lookup"><span data-stu-id="7c92a-120">If set to the default value, the access mode is obtained from the [Mode](mode-property-ado.md) property.</span></span> <span data-ttu-id="7c92a-121">*Source*参数不包含 URL 时，将忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="7c92a-121">This parameter is ignored when the *Source* parameter doesnt contain a URL.</span></span>

  - <span data-ttu-id="7c92a-122">*Options*</span><span class="sxs-lookup"><span data-stu-id="7c92a-122">*Options*</span></span>

  - <span data-ttu-id="7c92a-p105">可选。[RecordOpenOptionsEnum](recordopenoptionsenum.md) 值，其默认值为 **adOpenRecordUnspecified** ，指定用于打开 **Record** 的选项。这些值可以组合使用。</span><span class="sxs-lookup"><span data-stu-id="7c92a-p105">Optional. A [RecordOpenOptionsEnum](recordopenoptionsenum.md) value, whose default value is **adOpenRecordUnspecified**, that specifies options for opening the **Record**. These values may be combined.</span></span>

  - <span data-ttu-id="7c92a-126">*UserName*</span><span class="sxs-lookup"><span data-stu-id="7c92a-126">*UserName*</span></span>

  - <span data-ttu-id="7c92a-p106">可选。包含用户 ID 的**字符串型**值，如果需要，授予访问 *Source* 的权限。</span><span class="sxs-lookup"><span data-stu-id="7c92a-p106">Optional. A **String** value that contains the user ID that, if needed, authorizes access to *Source*.</span></span>

  - <span data-ttu-id="7c92a-129">*Password*</span><span class="sxs-lookup"><span data-stu-id="7c92a-129">*Password*</span></span>

  - <span data-ttu-id="7c92a-p107">可选。包含密码的**字符串型**值，如果需要，将验证 *UserName*。</span><span class="sxs-lookup"><span data-stu-id="7c92a-p107">Optional. A **String** value that contains the password that, if needed, verifies *UserName*.</span></span>

## <a name="remarks"></a><span data-ttu-id="7c92a-132">说明</span><span class="sxs-lookup"><span data-stu-id="7c92a-132">Remarks</span></span>

<span data-ttu-id="7c92a-133">*Source*可以是：</span><span class="sxs-lookup"><span data-stu-id="7c92a-133">*Source* may be:</span></span>

  - <span data-ttu-id="7c92a-134">URL。</span><span class="sxs-lookup"><span data-stu-id="7c92a-134">A URL.</span></span> <span data-ttu-id="7c92a-135">如果 URL 的协议为 HTTP，则默认情况下将调用 Internet 提供程序。</span><span class="sxs-lookup"><span data-stu-id="7c92a-135">If the protocol for the URL is http, then the Internet Provider will be invoked by default.</span></span> <span data-ttu-id="7c92a-136">如果 URL 指向的节点包含可执行脚本（如 .ASP 页），则默认情况下打开包含源（而不是执行的内容）的 **Record** 。</span><span class="sxs-lookup"><span data-stu-id="7c92a-136">If the URL points to a node that contains an executable script (such as an .ASP page), then a **Record** containing the source rather than the executed contents is opened by default.</span></span> <span data-ttu-id="7c92a-137">使用在*Options*参数来修改此行为。</span><span class="sxs-lookup"><span data-stu-id="7c92a-137">Use the *Options* argument to modify this behavior.</span></span>

  - <span data-ttu-id="7c92a-p109">**Record** 对象。从其他 **Record** 打开的 **Record** 对象将克隆原始 **Record** 对象。</span><span class="sxs-lookup"><span data-stu-id="7c92a-p109">A **Record** object. A **Record** object opened from another **Record** will clone the original **Record** object.</span></span>

  - <span data-ttu-id="7c92a-p110">**Command** 对象。打开的 **Record** 对象代表通过执行 **Command** 返回的单个行。如果结果包含多个行，则将第一个行的内容放置在记录中，并且会向 **Errors** 集合添加一个错误。</span><span class="sxs-lookup"><span data-stu-id="7c92a-p110">A **Command** object. The opened **Record** object represents the single row returned by executing the **Command**. If the results contain more than a single row, the contents of the first row are placed in the record and an error may be added to the **Errors** collection.</span></span>

  - <span data-ttu-id="7c92a-p111">SQL SELECT 语句。打开的 **Record** 对象代表通过执行字符串的内容返回的单个行。如果结果包含多个行，则将第一个行的内容放置在记录中，并且会向 **Errors** 集合添加一个错误。</span><span class="sxs-lookup"><span data-stu-id="7c92a-p111">A SQL SELECT statement. The opened **Record** object represents the single row returned by executing the contents of the string. If the results contain more than a single row, the contents of the first row are placed in the record and an error may be added to the **Errors** collection.</span></span>

  - <span data-ttu-id="7c92a-146">表名。</span><span class="sxs-lookup"><span data-stu-id="7c92a-146">A table name.</span></span>

<span data-ttu-id="7c92a-147">如果 **Record** 对象代表的实体无法通过 URL 访问（例如，从数据库派生的 **Recordset** 的某个行），则 [ParentURL](parenturl-property-ado.md) 属性的值和使用 **adRecordURL** 常量访问的字段的值都为 Null。</span><span class="sxs-lookup"><span data-stu-id="7c92a-147">If the **Record** object represents an entity that cannot be accessed with a URL (for example, a row of a **Recordset** derived from a database), then the values of both the [ParentURL](parenturl-property-ado.md) property and the field accessed with the **adRecordURL** constant are null.</span></span>


> [!NOTE]
<span data-ttu-id="7c92a-148"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="7c92a-148"><<<<<<< HEAD</span></span>
> <P><span data-ttu-id="7c92a-p112">[!注释] 使用 HTTP 架构的 URL 将自动调用 <A href="microsoft-ole-db-provider-for-internet-publishing.md">Microsoft OLE DB Provider for Internet Publishing</A>。有关详细信息，请参阅<A href="absolute-and-relative-urls.md">绝对 URL 和相对 URL</A>。</span><span class="sxs-lookup"><span data-stu-id="7c92a-p112">URLs using the http scheme will automatically invoke the <A href="microsoft-ole-db-provider-for-internet-publishing.md">Microsoft OLE DB Provider for Internet Publishing</A>. For more information, see <A href="absolute-and-relative-urls.md">Absolute and Relative URLs</A>.</span></span></P>
=======
> <span data-ttu-id="7c92a-151">[!注释] 使用 HTTP 架构的 URL 将自动调用 [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)。</span><span class="sxs-lookup"><span data-stu-id="7c92a-151">URLs using the http scheme will automatically invoke the [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md).</span></span> <span data-ttu-id="7c92a-152">有关详细信息，请参阅[绝对和相对 Url](absolute-and-relative-urls.md)。</span><span class="sxs-lookup"><span data-stu-id="7c92a-152">For more information, see [Absolute and relative URLs](absolute-and-relative-urls.md).</span></span>
>>>>>>> <span data-ttu-id="7c92a-153">master</span><span class="sxs-lookup"><span data-stu-id="7c92a-153">master</span></span>


