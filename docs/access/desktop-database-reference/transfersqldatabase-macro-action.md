---
title: TransferSQLDatabase 宏操作
TOCTitle: TransferSQLDatabase Macro Action
ms:assetid: 8cb95e22-f1f0-6c70-7dcb-3a3e9aafdc57
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197344(v=office.15)
ms:contentKeyID: 48546244
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm111536
f1_categories:
- Office.Version=v15
ms.openlocfilehash: fff0c9ac46e4a616fb5ea134e3dabc6b4e90576f
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25873101"
---
# <a name="transfersqldatabase-macro-action"></a><span data-ttu-id="b603e-102">TransferSQLDatabase 宏操作</span><span class="sxs-lookup"><span data-stu-id="b603e-102">TransferSQLDatabase Macro Action</span></span>


<span data-ttu-id="b603e-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="b603e-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="b603e-104">在 Microsoft Access 项目中，可以使用 **TransferSQLDatabase** 操作将 Microsoft SQL Server 7.0 或更高版本的数据库迁移到另一个 SQL Server 7.0 或更高版本的数据库。</span><span class="sxs-lookup"><span data-stu-id="b603e-104">In an Access project, you can use the **TransferSQLDatabase** action to transfer a Microsoft SQL Server 7.0 or later database to another SQL Server 7.0 or later database.</span></span> <span data-ttu-id="b603e-105">关于迁移数据库的详细信息，请参阅 SQL Server 文档。</span><span class="sxs-lookup"><span data-stu-id="b603e-105">For more information about transferring a database, see the SQL Server documentation.</span></span>


> [!NOTE]
> <span data-ttu-id="b603e-p102">[!注释] 如果数据库不受信任，将不允许此操作。有关启用宏的详细信息，请参阅本文 See Also 一节中的链接。</span><span class="sxs-lookup"><span data-stu-id="b603e-p102">This action will not be allowed if the database is not trusted. For more information about enabling macros, see the links in the See Also section of this article.</span></span>



## <a name="setting"></a><span data-ttu-id="b603e-108">设置</span><span class="sxs-lookup"><span data-stu-id="b603e-108">Setting</span></span>

<span data-ttu-id="b603e-109">**TransferSQLDatabase** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="b603e-109">The **TransferSQLDatabase** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="b603e-110">操作参数</span><span class="sxs-lookup"><span data-stu-id="b603e-110">Action argument</span></span></p></th>
<th><p><span data-ttu-id="b603e-111">说明</span><span class="sxs-lookup"><span data-stu-id="b603e-111">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b603e-112"><strong>Server</strong></span><span class="sxs-lookup"><span data-stu-id="b603e-112"><strong>Server</strong></span></span></p></td>
<td><p><span data-ttu-id="b603e-113">要复制到的 SQL Server 7.0 或更高版本的数据库服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="b603e-113">The name of the SQL Server 7.0 or later database server you are copying to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b603e-114"><strong>Database</strong></span><span class="sxs-lookup"><span data-stu-id="b603e-114"><strong>Database</strong></span></span></p></td>
<td><p><span data-ttu-id="b603e-115">将在目标服务器上创建的新数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="b603e-115">The name of the new database that will be created on the destination server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b603e-116"><strong>使用可信连接</strong></span><span class="sxs-lookup"><span data-stu-id="b603e-116"><strong>Use Trusted Connection</strong></span></span></p></td>
<td><p><span data-ttu-id="b603e-117">指定是否存在是受信任的连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="b603e-117">Specifes whether or not there is a trusted connection to the SQL Server.</span></span> <span data-ttu-id="b603e-118">如果设置为<strong>是</strong>，则没有受信任的连接和<strong>登录名</strong>和<strong>密码</strong>参数不是必需的。</span><span class="sxs-lookup"><span data-stu-id="b603e-118">If set to <strong>Yes</strong>, then there is a trusted connection and the <strong>Login</strong> and <strong>Password</strong> arguments are not required.</span></span> <span data-ttu-id="b603e-119">如果设置为<strong>无</strong>、<strong>登录名</strong>和<strong>密码</strong>参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="b603e-119">If set to <strong>No</strong>, the <strong>Login</strong> and <strong>Password</strong> arguments are required.</span></span> <span data-ttu-id="b603e-120">默认值为 <strong>"是"</strong>。</span><span class="sxs-lookup"><span data-stu-id="b603e-120">The default is <strong>Yes</strong>.</span></span> <span data-ttu-id="b603e-121">使用可信的连接时，具有 Windows 操作系统安全提供单一登录网络和数据库集成了 SQL Server 安全。</span><span class="sxs-lookup"><span data-stu-id="b603e-121">When you use a trusted connection, SQL Server security integrates with the Windows operating system security to provide a single log on to the network and the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b603e-122"><strong>登录</strong></span><span class="sxs-lookup"><span data-stu-id="b603e-122"><strong>Login</strong></span></span></p></td>
<td><p><span data-ttu-id="b603e-123">目标服务器的登录名。</span><span class="sxs-lookup"><span data-stu-id="b603e-123">The name of the Login to the destination server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b603e-124"><strong>Password</strong></span><span class="sxs-lookup"><span data-stu-id="b603e-124"><strong>Password</strong></span></span></p></td>
<td><p><span data-ttu-id="b603e-125"><strong>登录</strong>参数的密码。</span><span class="sxs-lookup"><span data-stu-id="b603e-125">The password for the <strong>Login</strong> argument.</span></span> <span data-ttu-id="b603e-126">此密码存储为文本中的 Access 项目，但在传输数据库操作过程中隐藏。</span><span class="sxs-lookup"><span data-stu-id="b603e-126">This password is stored as text in the Access project, but is hidden during the transfer database operation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b603e-127"><strong>传输复制数据</strong></span><span class="sxs-lookup"><span data-stu-id="b603e-127"><strong>Transfer Copy Data</strong></span></span></p></td>
<td><p><span data-ttu-id="b603e-p105">指定在数据库迁移操作中是否包括数据。如果设置为<strong>“是”</strong>，则将包括所有表中的所有数据，以及所有的数据结构、扩展属性和数据库对象。如果设置为<strong>“否”</strong>，则将不包括表中的数据。仅将在目标服务器上创建表结构和扩展属性以及所有其他数据库对象（不包括数据库图表）。默认值为<strong>“是”</strong>。</span><span class="sxs-lookup"><span data-stu-id="b603e-p105">Specifies whether or not to include data in the transfer database operation. When set to <strong>Yes</strong>, all data is included for all the tables, along with all data structures, extended properties, and database objects. When set to <strong>No</strong>, no data is included from the tables. Only the table structure and extended properties are created on the destination server, along with all other database objects (except database diagrams). The default is <strong>Yes</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="b603e-133">说明</span><span class="sxs-lookup"><span data-stu-id="b603e-133">Remarks</span></span>

<span data-ttu-id="b603e-134">在数据库迁移过程中不能执行其他操作。</span><span class="sxs-lookup"><span data-stu-id="b603e-134">You cannot perform other operations while the database is being transferred.</span></span>

<span data-ttu-id="b603e-135">默认情况下， **TransferSQLDatabase** 操作会复制数据、数据定义、数据库对象和扩展属性，例如默认值、文本约束和查阅值。</span><span class="sxs-lookup"><span data-stu-id="b603e-135">The **TransferSQLDatabase** action, by default, copies data, data definitions, database objects, and extended properties, such as default values, text constraints, and lookup values.</span></span>

<span data-ttu-id="b603e-136">下面是关于迁移数据库的一些要求：</span><span class="sxs-lookup"><span data-stu-id="b603e-136">There are requirements for transferring a database:</span></span>

  - <span data-ttu-id="b603e-137">您必须是目标服务器上 sysadmin 角色的成员（源服务器上不要求有任何特殊角色）。</span><span class="sxs-lookup"><span data-stu-id="b603e-137">You must be a member of the sysadmin role on the destination server (No special role is required on the source server).</span></span>

<!-- end list -->

  - <span data-ttu-id="b603e-138">当前连接到 Access 项目的 SQL 服务器和要向其迁移数据库的目标服务器必须为 SQL Server 7.0 版或更高版本。</span><span class="sxs-lookup"><span data-stu-id="b603e-138">The current SQL server connected to the Access project and the destination server you are transferring the database to must be SQL Server version 7.0 or later.</span></span>


> [!NOTE]
> <P><span data-ttu-id="b603e-139">[!注释] 在数据库迁移操作过程中，不迁移链接服务器。</span><span class="sxs-lookup"><span data-stu-id="b603e-139">Linked servers are not transferred during a database transfer operation.</span></span></P>



<span data-ttu-id="b603e-140">要在 Visual Basic for Applications (VBA) 模块中运行 **TransferSQLDatabase** 操作，请使用 **DoCmd** 对象的 **TransferSQLDatabase** 方法。</span><span class="sxs-lookup"><span data-stu-id="b603e-140">To run the **TransferSQLDatabase** action in a Visual Basic for Applications (VBA) module, use the **TransferSQLDatabase** method of the **DoCmd** object.</span></span>

