---
title: CopyDatabaseFile 宏操作
TOCTitle: CopyDatabaseFile macro action
ms:assetid: e6320b55-946b-9efc-9b64-b86513801a37
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835963(v=office.15)
ms:contentKeyID: 48548373
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 0f2034bb4d8d1fbf3f1a0a37bf6adc7c8b8001bb
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25925203"
---
# <a name="copydatabasefile-macro-action"></a><span data-ttu-id="911e9-102">CopyDatabaseFile 宏操作</span><span class="sxs-lookup"><span data-stu-id="911e9-102">CopyDatabaseFile macro action</span></span>


<span data-ttu-id="911e9-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="911e9-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="911e9-104">可以使用 **CopyDatabaseFile** 操作为连接至 Microsoft Access 项目的当前 Microsoft SQL Server 7.0（或更高版本）数据库创建一个副本。</span><span class="sxs-lookup"><span data-stu-id="911e9-104">You can use the **CopyDatabaseFile** action to make a copy of the current Microsoft SQL Server 7.0 or later database connected to your Access project.</span></span> <span data-ttu-id="911e9-105">访问当前数据库分离，然后将其附加到目标服务器。</span><span class="sxs-lookup"><span data-stu-id="911e9-105">Access detaches the current database and then attaches it to the destination server.</span></span> <span data-ttu-id="911e9-106">有关分离和附加数据库的详细信息，请参阅 SQL Server 文档。</span><span class="sxs-lookup"><span data-stu-id="911e9-106">For more information about detaching and attaching a database, see the SQL Server documentation.</span></span>


> [!NOTE]
> <span data-ttu-id="911e9-p102">[!注释] 如果数据库不受信任，将不允许此操作。有关启用宏的详细信息，请参阅本文 See Also 一节中的链接。</span><span class="sxs-lookup"><span data-stu-id="911e9-p102">This action will not be allowed if the database is not trusted. For more information about enabling macros, see the links in the See Also section of this article.</span></span>



## <a name="setting"></a><span data-ttu-id="911e9-109">设置</span><span class="sxs-lookup"><span data-stu-id="911e9-109">Setting</span></span>

<span data-ttu-id="911e9-110">**CopyDatabaseFile** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="911e9-110">The **CopyDatabaseFile** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="911e9-111">操作参数</span><span class="sxs-lookup"><span data-stu-id="911e9-111">Action argument</span></span></p></th>
<th><p><span data-ttu-id="911e9-112">说明</span><span class="sxs-lookup"><span data-stu-id="911e9-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="911e9-113"><strong>数据库文件名</strong></span><span class="sxs-lookup"><span data-stu-id="911e9-113"><strong>Database File Name</strong></span></span></p></td>
<td><p><span data-ttu-id="911e9-p103">新的主数据文件的名称。该文件的默认路径为 Access 项目文件 (.adp) 的当前位置。</span><span class="sxs-lookup"><span data-stu-id="911e9-p103">The name of the new Master Data File. The default path for the file is the current location of the Access project file (.adp).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="911e9-116"><strong>覆盖现有文件</strong></span><span class="sxs-lookup"><span data-stu-id="911e9-116"><strong>Overwrite Existing File</strong></span></span></p></td>
<td><p><span data-ttu-id="911e9-117">指定具有相同名称中替换现有文件。</span><span class="sxs-lookup"><span data-stu-id="911e9-117">Specifies whether or not to replace an existing file with the same name.</span></span> <span data-ttu-id="911e9-118">如果设置为<strong>是</strong>和已存在同名，都将被覆盖该文件。</span><span class="sxs-lookup"><span data-stu-id="911e9-118">If set to <strong>Yes</strong> and the filename already exists, the file is overwritten.</span></span> <span data-ttu-id="911e9-119">如果设置为<strong>No</strong>和已存在同名，该文件不会被覆盖操作失败。</span><span class="sxs-lookup"><span data-stu-id="911e9-119">If set to <strong>No</strong> and the filename already exists, the file is not overwritten and the action fails.</span></span> <span data-ttu-id="911e9-120">如果文件不存在，则忽略此设置。</span><span class="sxs-lookup"><span data-stu-id="911e9-120">If the file does not already exist, this setting is ignored.</span></span> <span data-ttu-id="911e9-121">默认值为 <strong>"是"</strong>。</span><span class="sxs-lookup"><span data-stu-id="911e9-121">The default is <strong>Yes</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="911e9-122"><strong>断开所有用户</strong></span><span class="sxs-lookup"><span data-stu-id="911e9-122"><strong>Disconnect All Users</strong></span></span></p></td>
<td><p><span data-ttu-id="911e9-123">指定访问应强制关闭数据库的用户。</span><span class="sxs-lookup"><span data-stu-id="911e9-123">Specifies whether or not Access should force users off the database.</span></span> <span data-ttu-id="911e9-124">如果设置为<strong>是</strong>，连接到当前数据库的任何用户已断开连接，以便可以继续执行复制数据库操作。</span><span class="sxs-lookup"><span data-stu-id="911e9-124">If set to <strong>Yes</strong>, any users that are connected to the current database are disconnected so that the copy database operation can proceed.</span></span> <span data-ttu-id="911e9-125">如果设置为<strong>No</strong> ，另一个或多个用户连接到数据库，则复制数据库操作将失败。</span><span class="sxs-lookup"><span data-stu-id="911e9-125">If set to <strong>No</strong> and one or more users are connected to the database, the copy database operation fails.</span></span> <span data-ttu-id="911e9-126">默认值为 <strong>"否"</strong>。</span><span class="sxs-lookup"><span data-stu-id="911e9-126">The default is <strong>No</strong>.</span></span></p>

> [!WARNING]
> <span data-ttu-id="911e9-127">在无充分警告的情况下断开用户与数据库的连接可能会导致数据丢失。</span><span class="sxs-lookup"><span data-stu-id="911e9-127">Disconnecting users from a database without adequate warning can lead to data loss.</span></span>


<p></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="911e9-128">说明</span><span class="sxs-lookup"><span data-stu-id="911e9-128">Remarks</span></span>

<span data-ttu-id="911e9-129">复制操作是同步进行的，因此在完成对数据库的复制之前，无法执行其他操作。</span><span class="sxs-lookup"><span data-stu-id="911e9-129">The copy operation is synchronous, so you can't perform other operations until the copy of the database is complete.</span></span>

<span data-ttu-id="911e9-130">**CopyDatabaseFile** 操作不仅会复制数据、数据定义和数据库对象，还会复制默认值、文本约束和查阅值等扩展属性。</span><span class="sxs-lookup"><span data-stu-id="911e9-130">The **CopyDatabaseFile** action not only copies data, data definitions, and database objects, but also copies extended properties, such as default values, text constraints, and lookup values.</span></span>

<span data-ttu-id="911e9-131">复制数据库的要求：</span><span class="sxs-lookup"><span data-stu-id="911e9-131">Requirements for copying a database:</span></span>

  - <span data-ttu-id="911e9-132">复制数据库文件之前，必须断开与所有应用程序和用户的连接。</span><span class="sxs-lookup"><span data-stu-id="911e9-132">You must disconnect all applications and users before you copy the database file.</span></span>

  - <span data-ttu-id="911e9-133">必须关闭除导航窗格以外的所有对象和视图。</span><span class="sxs-lookup"><span data-stu-id="911e9-133">All objects and views except the Navigation Pane must be closed.</span></span>

  - <span data-ttu-id="911e9-134">不得复制当前数据库。</span><span class="sxs-lookup"><span data-stu-id="911e9-134">The current database must not be replicated.</span></span>

  - <span data-ttu-id="911e9-135">源服务器数据库必须是 Microsoft SQL Server 7.0 版或更高版本，或是在本地计算机上运行的 SQL Server 2000 Desktop Engine。</span><span class="sxs-lookup"><span data-stu-id="911e9-135">The source server database must be Microsoft SQL Server version 7.0 or later, or SQL Server 2000 Desktop Engine running on a local computer.</span></span>

<!-- end list -->

  - <span data-ttu-id="911e9-136">源服务器上的 SQL Server 数据库必须是单个文件数据库。</span><span class="sxs-lookup"><span data-stu-id="911e9-136">The SQL Server database on the source server must be a single file database.</span></span>

  - <span data-ttu-id="911e9-137">您在源和目标 SQL Server 计算机上必须都是 sysadmin 角色的成员。</span><span class="sxs-lookup"><span data-stu-id="911e9-137">You must be a member of the sysadmin role on both the source and destination SQL Server computers.</span></span>

<span data-ttu-id="911e9-138">要在 Visual Basic for Applications 模块中运行 **CopyDatabaseFile** 操作，请使用 **DoCmd** 对象的 **CopyDatabaseFile** 方法。</span><span class="sxs-lookup"><span data-stu-id="911e9-138">To run the **CopyDatabaseFile** action in a Visual Basic for Applications module, use the **CopyDatabaseFile** method of the **DoCmd** object.</span></span>

