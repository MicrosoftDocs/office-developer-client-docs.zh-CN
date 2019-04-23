---
title: Open 方法（ADO 记录）
TOCTitle: Open method (ADO Record)
ms:assetid: ba71c5c7-326e-d3b6-0e74-e8343ee6896f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249896(v=office.15)
ms:contentKeyID: 48547371
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: db8953cafc5ad266c81c51e59cbf92787d07cdfb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288376"
---
# <a name="open-method-ado-record"></a><span data-ttu-id="149e3-102">Open 方法（ADO 记录）</span><span class="sxs-lookup"><span data-stu-id="149e3-102">Open method (ADO Record)</span></span>

<span data-ttu-id="149e3-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="149e3-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="149e3-104">用于打开现有的 [Record](record-object-ado.md) 对象，或创建由 **Record** 表示的新项（如文件或目录）。</span><span class="sxs-lookup"><span data-stu-id="149e3-104">Opens an existing [Record](record-object-ado.md) object, or creates a new item represented by the **Record** (such as a file or directory).</span></span>

## <a name="syntax"></a><span data-ttu-id="149e3-105">语法</span><span class="sxs-lookup"><span data-stu-id="149e3-105">Syntax</span></span>

<span data-ttu-id="149e3-106">开放*源代码*、 *ActiveConnection*、 *Mode*、 *CreateOptions*、 *Options*、 *UserName*、 *Password*</span><span class="sxs-lookup"><span data-stu-id="149e3-106">Open *Source*, *ActiveConnection*, *Mode*, *CreateOptions*, *Options*, *UserName*, *Password*</span></span>

## <a name="parameters"></a><span data-ttu-id="149e3-107">参数</span><span class="sxs-lookup"><span data-stu-id="149e3-107">Parameters</span></span>

|<span data-ttu-id="149e3-108">参数</span><span class="sxs-lookup"><span data-stu-id="149e3-108">Parameter</span></span>|<span data-ttu-id="149e3-109">描述</span><span class="sxs-lookup"><span data-stu-id="149e3-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="149e3-110">*Source*</span><span class="sxs-lookup"><span data-stu-id="149e3-110">*Source*</span></span> |<span data-ttu-id="149e3-p101">可选。 **变量型** 值，可以表示要由该 **Record** 对象表示的实体的 URL、 **Command** 、打开的 [Recordset](recordset-object-ado.md) 或其他 **Record** 对象，也可以表示包含 SQL SELECT 语句或表名的字符串。</span><span class="sxs-lookup"><span data-stu-id="149e3-p101">Optional. A **Variant** that may represent the URL of the entity to be represented by this **Record** object, a **Command**, an open [Recordset](recordset-object-ado.md) or another **Record** object, a string containing a SQL SELECT statement or a table name.</span></span>|
|<span data-ttu-id="149e3-113">*ActiveConnection*</span><span class="sxs-lookup"><span data-stu-id="149e3-113">*ActiveConnection*</span></span> | <span data-ttu-id="149e3-p102">可选。 **变量型** 值，表示连接字符串或打开的 [Connection](connection-object-ado.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="149e3-p102">Optional. A **Variant** that represents the connect string or open [Connection](connection-object-ado.md) object.</span></span>|
|<span data-ttu-id="149e3-116">*Mode*</span><span class="sxs-lookup"><span data-stu-id="149e3-116">*Mode*</span></span> |<span data-ttu-id="149e3-p103">可选。[ConnectModeEnum](connectmodeenum.md) 值，其默认值为 **adModeUnknown** ，指定生成的 **Record** 对象的访问模式。</span><span class="sxs-lookup"><span data-stu-id="149e3-p103">Optional. A [ConnectModeEnum](connectmodeenum.md) value, whose default value is **adModeUnknown**, that specifies the access mode for the resultant **Record** object.</span></span>|
|<span data-ttu-id="149e3-119">*CreateOptions*</span><span class="sxs-lookup"><span data-stu-id="149e3-119">*CreateOptions*</span></span> |<span data-ttu-id="149e3-p104">可选。[RecordCreateOptionsEnum](recordcreateoptionsenum.md) 值，其默认值为 **adFailIfNotExists**，指定应打开现有的文件或目录，还是创建新文件或目录。如果设置为默认值，则从 [Mode](mode-property-ado.md) 属性获取访问模式。当 *Source* 参数不包含 URL 时忽略该参数。</span><span class="sxs-lookup"><span data-stu-id="149e3-p104">Optional. A [RecordCreateOptionsEnum](recordcreateoptionsenum.md) value, whose default value is **adFailIfNotExists**, that specifies whether an existing file or directory should be opened, or a new file or directory should be created. If set to the default value, the access mode is obtained from the [Mode](mode-property-ado.md) property. This parameter is ignored when the *Source* parameter doesnt contain a URL.</span></span>|
|<span data-ttu-id="149e3-124">*Options*</span><span class="sxs-lookup"><span data-stu-id="149e3-124">*Options*</span></span> |<span data-ttu-id="149e3-p105">可选。[RecordOpenOptionsEnum](recordopenoptionsenum.md) 值，其默认值为 **adOpenRecordUnspecified** ，指定用于打开 **Record** 的选项。这些值可以组合使用。</span><span class="sxs-lookup"><span data-stu-id="149e3-p105">Optional. A [RecordOpenOptionsEnum](recordopenoptionsenum.md) value, whose default value is **adOpenRecordUnspecified**, that specifies options for opening the **Record**. These values may be combined.</span></span>|
|<span data-ttu-id="149e3-128">*UserName*</span><span class="sxs-lookup"><span data-stu-id="149e3-128">*UserName*</span></span> |<span data-ttu-id="149e3-129">可选。</span><span class="sxs-lookup"><span data-stu-id="149e3-129">Optional.</span></span> <span data-ttu-id="149e3-130">包含用户 ID 的**字符串型**值，如果需要，授予访问 *Source* 的权限。</span><span class="sxs-lookup"><span data-stu-id="149e3-130">A **String** value that contains the user ID that, if needed, authorizes access to *Source*.</span></span>|
|<span data-ttu-id="149e3-131">*Password*</span><span class="sxs-lookup"><span data-stu-id="149e3-131">*Password*</span></span> |<span data-ttu-id="149e3-132">可选。</span><span class="sxs-lookup"><span data-stu-id="149e3-132">Optional.</span></span> <span data-ttu-id="149e3-133">包含密码的**字符串型**值，如果需要，将验证 *UserName*。</span><span class="sxs-lookup"><span data-stu-id="149e3-133">A **String** value that contains the password that, if needed, verifies *UserName*.</span></span>|

## <a name="remarks"></a><span data-ttu-id="149e3-134">注解</span><span class="sxs-lookup"><span data-stu-id="149e3-134">Remarks</span></span>

<span data-ttu-id="149e3-135">*Source* 可以是：</span><span class="sxs-lookup"><span data-stu-id="149e3-135">*Source* may be:</span></span>

- <span data-ttu-id="149e3-p108">URL。如果 URL 的协议为 HTTP，则默认情况下将调用 Internet 提供程序。如果 URL 指向的节点包含可执行脚本（如 .ASP 页），则默认情况下打开包含源（而不是执行的内容）的 **Record**。使用 *Options* 参数可修改此行为。</span><span class="sxs-lookup"><span data-stu-id="149e3-p108">A URL. If the protocol for the URL is http, then the Internet Provider will be invoked by default. If the URL points to a node that contains an executable script (such as an .ASP page), then a **Record** containing the source rather than the executed contents is opened by default. Use the *Options* argument to modify this behavior.</span></span>

- <span data-ttu-id="149e3-p109">**Record** 对象。从其他 **Record** 打开的 **Record** 对象将克隆原始 **Record** 对象。</span><span class="sxs-lookup"><span data-stu-id="149e3-p109">A **Record** object. A **Record** object opened from another **Record** will clone the original **Record** object.</span></span>

- <span data-ttu-id="149e3-p110">**Command** 对象。打开的 **Record** 对象代表通过执行 **Command** 返回的单个行。如果结果包含多个行，则将第一个行的内容放置在记录中，并且会向 **Errors** 集合添加一个错误。</span><span class="sxs-lookup"><span data-stu-id="149e3-p110">A **Command** object. The opened **Record** object represents the single row returned by executing the **Command**. If the results contain more than a single row, the contents of the first row are placed in the record and an error may be added to the **Errors** collection.</span></span>

- <span data-ttu-id="149e3-p111">SQL SELECT 语句。打开的 **Record** 对象代表通过执行字符串的内容返回的单个行。如果结果包含多个行，则将第一个行的内容放置在记录中，并且会向 **Errors** 集合添加一个错误。</span><span class="sxs-lookup"><span data-stu-id="149e3-p111">A SQL SELECT statement. The opened **Record** object represents the single row returned by executing the contents of the string. If the results contain more than a single row, the contents of the first row are placed in the record and an error may be added to the **Errors** collection.</span></span>

- <span data-ttu-id="149e3-148">表名。</span><span class="sxs-lookup"><span data-stu-id="149e3-148">A table name.</span></span>

<span data-ttu-id="149e3-149">如果 **Record** 对象代表的实体无法通过 URL 访问（例如，从数据库派生的 **Recordset** 的某个行），则 [ParentURL](parenturl-property-ado.md) 属性的值和使用 **adRecordURL** 常量访问的字段的值都为 Null。</span><span class="sxs-lookup"><span data-stu-id="149e3-149">If the **Record** object represents an entity that cannot be accessed with a URL (for example, a row of a **Recordset** derived from a database), then the values of both the [ParentURL](parenturl-property-ado.md) property and the field accessed with the **adRecordURL** constant are null.</span></span>

> [!NOTE]
> <span data-ttu-id="149e3-150">[!注释] 使用 HTTP 架构的 URL 将自动调用 [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)。</span><span class="sxs-lookup"><span data-stu-id="149e3-150">URLs using the http scheme will automatically invoke the [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md).</span></span> <span data-ttu-id="149e3-151">有关详细信息, 请参阅[绝对和相对 url](absolute-and-relative-urls.md)。</span><span class="sxs-lookup"><span data-stu-id="149e3-151">For more information, see [Absolute and relative URLs](absolute-and-relative-urls.md).</span></span>


