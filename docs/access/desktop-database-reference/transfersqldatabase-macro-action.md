---
title: TransferSQLDatabase 宏操作
TOCTitle: TransferSQLDatabase macro action
ms:assetid: 8cb95e22-f1f0-6c70-7dcb-3a3e9aafdc57
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197344(v=office.15)
ms:contentKeyID: 48546244
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm111536
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 5ed20555726d0a6f63f0e48fb154cedb411ef8cd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306844"
---
# <a name="transfersqldatabase-macro-action"></a><span data-ttu-id="18c01-102">TransferSQLDatabase 宏操作</span><span class="sxs-lookup"><span data-stu-id="18c01-102">TransferSQLDatabase macro action</span></span>

<span data-ttu-id="18c01-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="18c01-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="18c01-104">在 Microsoft Access 项目中，可以使用 **TransferSQLDatabase** 操作将 Microsoft SQL Server 7.0 或更高版本的数据库迁移到另一个 SQL Server 7.0 或更高版本的数据库。</span><span class="sxs-lookup"><span data-stu-id="18c01-104">In an Access project, you can use the **TransferSQLDatabase** action to transfer a Microsoft SQL Server 7.0 or later database to another SQL Server 7.0 or later database.</span></span> <span data-ttu-id="18c01-105">有关传输数据库的详细信息, 请参阅 SQL Server 文档。</span><span class="sxs-lookup"><span data-stu-id="18c01-105">For more information about transferring a database, see the SQL Server documentation.</span></span>

> [!NOTE]
> <span data-ttu-id="18c01-106">如果数据库不受信任，则不允许执行此操作。</span><span class="sxs-lookup"><span data-stu-id="18c01-106">This action will not be allowed if the database is not trusted.</span></span>

## <a name="setting"></a><span data-ttu-id="18c01-107">设置</span><span class="sxs-lookup"><span data-stu-id="18c01-107">Setting</span></span>

<span data-ttu-id="18c01-108">**TransferSQLDatabase** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="18c01-108">The **TransferSQLDatabase** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="18c01-109">操作参数</span><span class="sxs-lookup"><span data-stu-id="18c01-109">Action argument</span></span></p></th>
<th><p><span data-ttu-id="18c01-110">说明</span><span class="sxs-lookup"><span data-stu-id="18c01-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18c01-111"><strong>服务器</strong></span><span class="sxs-lookup"><span data-stu-id="18c01-111"><strong>Server</strong></span></span></p></td>
<td><p><span data-ttu-id="18c01-112">要复制到的 SQL Server 7.0 或更高版本的数据库服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="18c01-112">The name of the SQL Server 7.0 or later database server you are copying to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18c01-113"><strong>数据库</strong></span><span class="sxs-lookup"><span data-stu-id="18c01-113"><strong>Database</strong></span></span></p></td>
<td><p><span data-ttu-id="18c01-114">将在目标服务器上创建的新数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="18c01-114">The name of the new database that will be created on the destination server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18c01-115"><strong>使用可信连接</strong></span><span class="sxs-lookup"><span data-stu-id="18c01-115"><strong>Use Trusted Connection</strong></span></span></p></td>
<td><p><span data-ttu-id="18c01-116">指定是否有到 SQL Server 的可信连接。</span><span class="sxs-lookup"><span data-stu-id="18c01-116">Specifes whether or not there is a trusted connection to the SQL Server.</span></span> <span data-ttu-id="18c01-117">如果设置为<strong>“是”</strong>，则有可信连接，而且“登录”<strong></strong>和“密码”<strong></strong>参数不是必选的。</span><span class="sxs-lookup"><span data-stu-id="18c01-117">If set to <strong>Yes</strong>, then there is a trusted connection and the <strong>Login</strong> and <strong>Password</strong> arguments are not required.</span></span> <span data-ttu-id="18c01-118">如果设置为<strong>“否”</strong>，“登录”<strong></strong>和“密码”<strong></strong>参数则是必选的。</span><span class="sxs-lookup"><span data-stu-id="18c01-118">If set to <strong>No</strong>, the <strong>Login</strong> and <strong>Password</strong> arguments are required.</span></span> <span data-ttu-id="18c01-119">默认值为<strong>“是”</strong>。</span><span class="sxs-lookup"><span data-stu-id="18c01-119">The default is <strong>Yes</strong>.</span></span> <span data-ttu-id="18c01-120">当您使用受信任的连接时, SQL Server 安全性将与 Windows 操作系统安全性集成, 以提供网络和数据库的单一登录。</span><span class="sxs-lookup"><span data-stu-id="18c01-120">When you use a trusted connection, SQL Server security integrates with the Windows operating system security to provide a single log on to the network and the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18c01-121"><strong>[</strong></span><span class="sxs-lookup"><span data-stu-id="18c01-121"><strong>Login</strong></span></span></p></td>
<td><p><span data-ttu-id="18c01-122">目标服务器的登录名。</span><span class="sxs-lookup"><span data-stu-id="18c01-122">The name of the Login to the destination server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18c01-123"><strong>Password</strong></span><span class="sxs-lookup"><span data-stu-id="18c01-123"><strong>Password</strong></span></span></p></td>
<td><p><span data-ttu-id="18c01-p103">“登录”<strong></strong>参数的密码。此密码在 Access 项目中作为文本存储，但在数据库迁移操作过程中是隐藏的。</span><span class="sxs-lookup"><span data-stu-id="18c01-p103">The password for the <strong>Login</strong> argument. This password is stored as text in the Access project, but is hidden during the transfer database operation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18c01-126"><strong>传输复制数据</strong></span><span class="sxs-lookup"><span data-stu-id="18c01-126"><strong>Transfer Copy Data</strong></span></span></p></td>
<td><p><span data-ttu-id="18c01-p104">指定在数据库迁移操作中是否包括数据。如果设置为<strong>“是”</strong>，则将包括所有表中的所有数据，以及所有的数据结构、扩展属性和数据库对象。如果设置为<strong>“否”</strong>，则将不包括表中的数据。仅将在目标服务器上创建表结构和扩展属性以及所有其他数据库对象（不包括数据库图表）。默认值为<strong>“是”</strong>。</span><span class="sxs-lookup"><span data-stu-id="18c01-p104">Specifies whether or not to include data in the transfer database operation. When set to <strong>Yes</strong>, all data is included for all the tables, along with all data structures, extended properties, and database objects. When set to <strong>No</strong>, no data is included from the tables. Only the table structure and extended properties are created on the destination server, along with all other database objects (except database diagrams). The default is <strong>Yes</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="18c01-132">注解</span><span class="sxs-lookup"><span data-stu-id="18c01-132">Remarks</span></span>

<span data-ttu-id="18c01-133">在数据库迁移过程中不能执行其他操作。</span><span class="sxs-lookup"><span data-stu-id="18c01-133">You cannot perform other operations while the database is being transferred.</span></span>

<span data-ttu-id="18c01-134">默认情况下，**TransferSQLDatabase** 操作会复制数据、数据定义、数据库对象和扩展属性，例如默认值、文本约束和查阅值。</span><span class="sxs-lookup"><span data-stu-id="18c01-134">The **TransferSQLDatabase** action, by default, copies data, data definitions, database objects, and extended properties, such as default values, text constraints, and lookup values.</span></span>

<span data-ttu-id="18c01-135">下面是关于迁移数据库的一些要求：</span><span class="sxs-lookup"><span data-stu-id="18c01-135">There are requirements for transferring a database:</span></span>

- <span data-ttu-id="18c01-136">您必须是目标服务器上 sysadmin 角色的成员（源服务器上不要求有任何特殊角色）。</span><span class="sxs-lookup"><span data-stu-id="18c01-136">You must be a member of the sysadmin role on the destination server (No special role is required on the source server).</span></span>

- <span data-ttu-id="18c01-137">当前连接到 Access 项目的 SQL 服务器和要向其迁移数据库的目标服务器必须为 SQL Server 7.0 版或更高版本。</span><span class="sxs-lookup"><span data-stu-id="18c01-137">The current SQL server connected to the Access project and the destination server you are transferring the database to must be SQL Server version 7.0 or later.</span></span>

  > [!NOTE]
  > <span data-ttu-id="18c01-138">在数据库迁移操作过程中，不迁移链接服务器。</span><span class="sxs-lookup"><span data-stu-id="18c01-138">Linked servers are not transferred during a database transfer operation.</span></span>

<span data-ttu-id="18c01-139">要在 Visual Basic for Applications (VBA) 模块中运行 **TransferSQLDatabase** 操作，请使用 **DoCmd** 对象的 **TransferSQLDatabase** 方法。</span><span class="sxs-lookup"><span data-stu-id="18c01-139">To run the **TransferSQLDatabase** action in a Visual Basic for Applications (VBA) module, use the **TransferSQLDatabase** method of the **DoCmd** object.</span></span>

