---
title: DBEngine Members (DAO)
TOCTitle: DBEngine Members
ms:assetid: 740b6a85-585f-0e1d-710b-84ba24825325
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195868(v=office.15)
ms:contentKeyID: 48545652
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7b534d4595bd003c76e756c44d6e88f53a725cc8
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25861783"
---
# <a name="dbengine-members-dao"></a><span data-ttu-id="c4074-102">DBEngine Members (DAO)</span><span class="sxs-lookup"><span data-stu-id="c4074-102">DBEngine Members (DAO)</span></span>


<span data-ttu-id="c4074-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="c4074-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="c4074-104">DBEngine 对象是数据访问对象 (DAO) 对象模型中的顶层对象。</span><span class="sxs-lookup"><span data-stu-id="c4074-104">The DBEngine object is the top level object in the DAO object model.</span></span>

## <a name="methods"></a><span data-ttu-id="c4074-105">方法</span><span class="sxs-lookup"><span data-stu-id="c4074-105">Methods</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="c4074-106">名称</span><span class="sxs-lookup"><span data-stu-id="c4074-106">Name</span></span></p></th>
<th><p><span data-ttu-id="c4074-107">说明</span><span class="sxs-lookup"><span data-stu-id="c4074-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4074-108"><strong><a href="dbengine-begintrans-method-dao.md">BeginTrans</a></strong></span><span class="sxs-lookup"><span data-stu-id="c4074-108"><strong><a href="dbengine-begintrans-method-dao.md">BeginTrans</a></strong></span></span></p></td>
<td><p><span data-ttu-id="c4074-p101">开始新的事务。可读写 <strong>Database</strong>。</span><span class="sxs-lookup"><span data-stu-id="c4074-p101">Begins a new transaction. Read/write <strong>Database</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4074-111"><strong><a href="dbengine-committrans-method-dao.md">CommitTrans</a></strong></span><span class="sxs-lookup"><span data-stu-id="c4074-111"><strong><a href="dbengine-committrans-method-dao.md">CommitTrans</a></strong></span></span></p></td>
<td><p><span data-ttu-id="c4074-112">结束当前的事务并保存更改。</span><span class="sxs-lookup"><span data-stu-id="c4074-112">Ends the current transaction and saves the changes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4074-113"><strong><a href="dbengine-compactdatabase-method-dao.md">CompactDatabase</a></strong></span><span class="sxs-lookup"><span data-stu-id="c4074-113"><strong><a href="dbengine-compactdatabase-method-dao.md">CompactDatabase</a></strong></span></span></p></td>
<td><p><span data-ttu-id="c4074-p102">复制并压缩关闭的数据库，使您可以选择更改其版本、整理顺序和加密设置。（仅适用于 Microsoft Access 工作区。）</span><span class="sxs-lookup"><span data-stu-id="c4074-p102">Copies and compacts a closed database, and gives you the option of changing its version, collating order, and encryption. (Microsoft Access workspaces only). .</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4074-117"><strong><a href="dbengine-createdatabase-method-dao.md">CreateDatabase</a></strong></span><span class="sxs-lookup"><span data-stu-id="c4074-117"><strong><a href="dbengine-createdatabase-method-dao.md">CreateDatabase</a></strong></span></span></p></td>
<td><p><span data-ttu-id="c4074-p103">创建一个新的 <strong><a href="database-object-dao.md">Database</a></strong> 对象，将数据库保存到磁盘，然后返回一个打开的 <strong>Database</strong> 对象（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="c4074-p103">Creates a new <strong><a href="database-object-dao.md">Database</a></strong> object, saves the database to disk, and returns an opened <strong>Database</strong> object (Microsoft Access workspaces only). .</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4074-120"><strong><a href="dbengine-createworkspace-method-dao.md">CreateWorkspace</a></strong></span><span class="sxs-lookup"><span data-stu-id="c4074-120"><strong><a href="dbengine-createworkspace-method-dao.md">CreateWorkspace</a></strong></span></span></p></td>
<td><p><span data-ttu-id="c4074-121">创建新的 <strong><a href="workspace-object-dao.md">Workspace</a></strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="c4074-121">Creates a new <strong><a href="workspace-object-dao.md">Workspace</a></strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4074-122"><strong><a href="dbengine-idle-method-dao.md">空闲时间</a></strong></span><span class="sxs-lookup"><span data-stu-id="c4074-122"><strong><a href="dbengine-idle-method-dao.md">Idle</a></strong></span></span></p></td>
<td><p><span data-ttu-id="c4074-123">挂起数据处理，使 Microsoft Access 数据库引擎完成任何待定任务，例如内存优化或页面超时（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="c4074-123">Suspends data processing, enabling the Microsoft Access database engine to complete any pending tasks, such as memory optimization or page timeouts (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4074-124"><strong><a href="dbengine-openconnection-method-dao.md">OpenConnection</a></strong></span><span class="sxs-lookup"><span data-stu-id="c4074-124"><strong><a href="dbengine-openconnection-method-dao.md">OpenConnection</a></strong></span></span></p></td>
<td><p></p>

> [!NOTE]
> <span data-ttu-id="c4074-125">Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="c4074-125">ODBCDirect workspaces are not supported in Microsoft Access 2013.</span></span> <span data-ttu-id="c4074-126">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="c4074-126">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span>


<p><span data-ttu-id="c4074-127">打开 ODBC 数据源上的 <strong><a href="connection-object-dao.md">Connection</a></strong> 对象（仅适用于 ODBCDirect 工作区）。</span><span class="sxs-lookup"><span data-stu-id="c4074-127">Opens a <strong><a href="connection-object-dao.md">Connection</a></strong> object on an ODBC data source (ODBCDirect workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4074-128"><strong><a href="dbengine-opendatabase-method-dao.md">OpenDatabase</a></strong></span><span class="sxs-lookup"><span data-stu-id="c4074-128"><strong><a href="dbengine-opendatabase-method-dao.md">OpenDatabase</a></strong></span></span></p></td>
<td><p><span data-ttu-id="c4074-129">打开指定的数据库，并返回一个指向代表该数据库的 <strong><a href="database-object-dao.md">Database</a></strong> 对象的引用。</span><span class="sxs-lookup"><span data-stu-id="c4074-129">Opens a specified database and returns a reference to the <strong><a href="database-object-dao.md">Database</a></strong> object that represents it.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4074-130"><strong><a href="dbengine-registerdatabase-method-dao.md">RegisterDatabase</a></strong></span><span class="sxs-lookup"><span data-stu-id="c4074-130"><strong><a href="dbengine-registerdatabase-method-dao.md">RegisterDatabase</a></strong></span></span></p></td>
<td><p><span data-ttu-id="c4074-p105">在 Windows 注册表中输入 ODBC 数据源的连接信息。在会话期间如果 ODBC 数据源已打开，则 ODBC 驱动程序需要连接信息。</span><span class="sxs-lookup"><span data-stu-id="c4074-p105">Enters connection information for an ODBC data source in the Windows Registry. The ODBC driver needs connection information when the ODBC data source is opened during a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4074-133"><strong><a href="dbengine-rollback-method-dao.md">Rollback</a></strong></span><span class="sxs-lookup"><span data-stu-id="c4074-133"><strong><a href="dbengine-rollback-method-dao.md">Rollback</a></strong></span></span></p></td>
<td><p><span data-ttu-id="c4074-134">结束当前事务，并将 <strong>Workspace</strong> 对象中的数据库还原到开始当前事务时它们所处的状态。</span><span class="sxs-lookup"><span data-stu-id="c4074-134">Ends the current transaction and restores the databases in the <strong>Workspace</strong> object to the state they were in when the current transaction began.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4074-135"><strong><a href="dbengine-setoption-method-dao.md">SetOption</a></strong></span><span class="sxs-lookup"><span data-stu-id="c4074-135"><strong><a href="dbengine-setoption-method-dao.md">SetOption</a></strong></span></span></p></td>
<td><p><span data-ttu-id="c4074-136">暂时替代 Windows 注册表中的 Microsoft Access 数据库引擎项的值（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="c4074-136">Temporarily overrides values for the Microsoft Access database engine keys in the Windows Registry (Microsoft Access workspaces only).</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="properties"></a><span data-ttu-id="c4074-137">属性</span><span class="sxs-lookup"><span data-stu-id="c4074-137">Properties</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="c4074-138">名称</span><span class="sxs-lookup"><span data-stu-id="c4074-138">Name</span></span></p></th>
<th><p><span data-ttu-id="c4074-139">说明</span><span class="sxs-lookup"><span data-stu-id="c4074-139">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4074-140"><strong><a href="dbengine-defaultpassword-property-dao.md">DefaultPassword</a></strong></span><span class="sxs-lookup"><span data-stu-id="c4074-140"><strong><a href="dbengine-defaultpassword-property-dao.md">DefaultPassword</a></strong></span></span></p></td>
<td><p><span data-ttu-id="c4074-p106">设置初始化 <strong>Workspace</strong> 时创建其默认值所使用的密码。可读/写 <strong>String</strong> 类型。</span><span class="sxs-lookup"><span data-stu-id="c4074-p106">Sets the password used to create the default <strong>Workspace</strong> when it is initialized. Read/write <strong>String</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4074-143"><strong><a href="dbengine-defaulttype-property-dao.md">DefaultType</a></strong></span><span class="sxs-lookup"><span data-stu-id="c4074-143"><strong><a href="dbengine-defaulttype-property-dao.md">DefaultType</a></strong></span></span></p></td>
<td><p><span data-ttu-id="c4074-144">设置或返回一个值，该值指示下一个创建的 <strong><a href="workspace-object-dao.md">Workspace</a></strong> 对象将要使用的工作区类型。</span><span class="sxs-lookup"><span data-stu-id="c4074-144">Sets or returns a value that indicates what type of workspace will be used by the next <strong><a href="workspace-object-dao.md">Workspace</a></strong> object created.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4074-145"><strong><a href="dbengine-defaultuser-property-dao.md">DefaultUser</a></strong></span><span class="sxs-lookup"><span data-stu-id="c4074-145"><strong><a href="dbengine-defaultuser-property-dao.md">DefaultUser</a></strong></span></span></p></td>
<td><p><span data-ttu-id="c4074-p107">设置初始化 <strong>Workspace</strong> 时创建其默认值所使用的用户名。可读/写 <strong>String</strong> 类型。</span><span class="sxs-lookup"><span data-stu-id="c4074-p107">Sets the user name used to create the default <strong>Workspace</strong> when it is initialized. Read/write <strong>String</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4074-148"><strong><a href="dbengine-errors-property-dao.md">错误</a></strong></span><span class="sxs-lookup"><span data-stu-id="c4074-148"><strong><a href="dbengine-errors-property-dao.md">Errors</a></strong></span></span></p></td>
<td><p><span data-ttu-id="c4074-p108">返回一个 <strong>Errors</strong> 集合，该集合包含指定对象的所有存储的 <strong>Error</strong> 对象。只读。</span><span class="sxs-lookup"><span data-stu-id="c4074-p108">Returns an <strong>Errors</strong> collection that contains all of the stored <strong>Error</strong> objects for the specified object. Read-only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4074-151"><strong><a href="dbengine-inipath-property-dao.md">IniPath</a></strong></span><span class="sxs-lookup"><span data-stu-id="c4074-151"><strong><a href="dbengine-inipath-property-dao.md">IniPath</a></strong></span></span></p></td>
<td><p><span data-ttu-id="c4074-152">设置或返回与包含了 Microsoft Access 数据库引擎值的 Windows 注册表项有关的信息（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="c4074-152">Sets or returns information about the Windows Registry key that contains values for the Microsoft Access database engine (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4074-153"><strong><a href="dbengine-logintimeout-property-dao.md">LoginTimeout</a></strong></span><span class="sxs-lookup"><span data-stu-id="c4074-153"><strong><a href="dbengine-logintimeout-property-dao.md">LoginTimeout</a></strong></span></span></p></td>
<td><p><span data-ttu-id="c4074-154">设置或返回在您尝试登录 ODBC 数据库时发生错误之前的秒数。</span><span class="sxs-lookup"><span data-stu-id="c4074-154">Sets or returns the number of seconds before an error occurs when you attempt to log on to an ODBC database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4074-155"><strong><a href="dbengine-properties-property-dao.md">属性</a></strong></span><span class="sxs-lookup"><span data-stu-id="c4074-155"><strong><a href="dbengine-properties-property-dao.md">Properties</a></strong></span></span></p></td>
<td><p><span data-ttu-id="c4074-p109">返回指定对象的 <strong><a href="properties-collection-dao.md">Properties</a></strong> 集合。只读。</span><span class="sxs-lookup"><span data-stu-id="c4074-p109">Returns the <strong><a href="properties-collection-dao.md">Properties</a></strong> collection of the specified object. Read-only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4074-158"><strong><a href="dbengine-version-property-dao.md">版本</a></strong></span><span class="sxs-lookup"><span data-stu-id="c4074-158"><strong><a href="dbengine-version-property-dao.md">Version</a></strong></span></span></p></td>
<td><p><span data-ttu-id="c4074-p110">返回当前使用的 DAO 版本。只读 <strong>String</strong>。</span><span class="sxs-lookup"><span data-stu-id="c4074-p110">Rreturns the version of DAO currently in use. Read-only <strong>String</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4074-161"><strong><a href="dbengine-workspaces-property-dao.md">Workspaces</a></strong></span><span class="sxs-lookup"><span data-stu-id="c4074-161"><strong><a href="dbengine-workspaces-property-dao.md">Workspaces</a></strong></span></span></p></td>
<td><p><span data-ttu-id="c4074-p111">返回一个 <strong>Workspaces</strong> 集合，该集合包含所有可见的活动 <strong>Workspace</strong> 对象。只读。</span><span class="sxs-lookup"><span data-stu-id="c4074-p111">Returns a <strong>Workspaces</strong> collection that contains all of the active, unhidden <strong>Workspace</strong> objects. Read-only.</span></span></p></td>
</tr>
</tbody>
</table>

