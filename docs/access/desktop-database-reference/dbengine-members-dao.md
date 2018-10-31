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
# <a name="dbengine-members-dao"></a>DBEngine Members (DAO)


**适用于**： Access 2013 |Office 2013

DBEngine 对象是数据访问对象 (DAO) 对象模型中的顶层对象。

## <a name="methods"></a>方法

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>名称</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong><a href="dbengine-begintrans-method-dao.md">BeginTrans</a></strong></p></td>
<td><p>开始新的事务。可读写 <strong>Database</strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="dbengine-committrans-method-dao.md">CommitTrans</a></strong></p></td>
<td><p>结束当前的事务并保存更改。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="dbengine-compactdatabase-method-dao.md">CompactDatabase</a></strong></p></td>
<td><p>复制并压缩关闭的数据库，使您可以选择更改其版本、整理顺序和加密设置。（仅适用于 Microsoft Access 工作区。）</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="dbengine-createdatabase-method-dao.md">CreateDatabase</a></strong></p></td>
<td><p>创建一个新的 <strong><a href="database-object-dao.md">Database</a></strong> 对象，将数据库保存到磁盘，然后返回一个打开的 <strong>Database</strong> 对象（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="dbengine-createworkspace-method-dao.md">CreateWorkspace</a></strong></p></td>
<td><p>创建新的 <strong><a href="workspace-object-dao.md">Workspace</a></strong> 对象。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="dbengine-idle-method-dao.md">空闲时间</a></strong></p></td>
<td><p>挂起数据处理，使 Microsoft Access 数据库引擎完成任何待定任务，例如内存优化或页面超时（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="dbengine-openconnection-method-dao.md">OpenConnection</a></strong></p></td>
<td><p></p>

> [!NOTE]
> Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。 如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。


<p>打开 ODBC 数据源上的 <strong><a href="connection-object-dao.md">Connection</a></strong> 对象（仅适用于 ODBCDirect 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="dbengine-opendatabase-method-dao.md">OpenDatabase</a></strong></p></td>
<td><p>打开指定的数据库，并返回一个指向代表该数据库的 <strong><a href="database-object-dao.md">Database</a></strong> 对象的引用。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="dbengine-registerdatabase-method-dao.md">RegisterDatabase</a></strong></p></td>
<td><p>在 Windows 注册表中输入 ODBC 数据源的连接信息。在会话期间如果 ODBC 数据源已打开，则 ODBC 驱动程序需要连接信息。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="dbengine-rollback-method-dao.md">Rollback</a></strong></p></td>
<td><p>结束当前事务，并将 <strong>Workspace</strong> 对象中的数据库还原到开始当前事务时它们所处的状态。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="dbengine-setoption-method-dao.md">SetOption</a></strong></p></td>
<td><p>暂时替代 Windows 注册表中的 Microsoft Access 数据库引擎项的值（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
</tbody>
</table>


## <a name="properties"></a>属性

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>名称</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong><a href="dbengine-defaultpassword-property-dao.md">DefaultPassword</a></strong></p></td>
<td><p>设置初始化 <strong>Workspace</strong> 时创建其默认值所使用的密码。可读/写 <strong>String</strong> 类型。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="dbengine-defaulttype-property-dao.md">DefaultType</a></strong></p></td>
<td><p>设置或返回一个值，该值指示下一个创建的 <strong><a href="workspace-object-dao.md">Workspace</a></strong> 对象将要使用的工作区类型。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="dbengine-defaultuser-property-dao.md">DefaultUser</a></strong></p></td>
<td><p>设置初始化 <strong>Workspace</strong> 时创建其默认值所使用的用户名。可读/写 <strong>String</strong> 类型。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="dbengine-errors-property-dao.md">错误</a></strong></p></td>
<td><p>返回一个 <strong>Errors</strong> 集合，该集合包含指定对象的所有存储的 <strong>Error</strong> 对象。只读。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="dbengine-inipath-property-dao.md">IniPath</a></strong></p></td>
<td><p>设置或返回与包含了 Microsoft Access 数据库引擎值的 Windows 注册表项有关的信息（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="dbengine-logintimeout-property-dao.md">LoginTimeout</a></strong></p></td>
<td><p>设置或返回在您尝试登录 ODBC 数据库时发生错误之前的秒数。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="dbengine-properties-property-dao.md">属性</a></strong></p></td>
<td><p>返回指定对象的 <strong><a href="properties-collection-dao.md">Properties</a></strong> 集合。只读。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="dbengine-version-property-dao.md">版本</a></strong></p></td>
<td><p>返回当前使用的 DAO 版本。只读 <strong>String</strong>。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="dbengine-workspaces-property-dao.md">Workspaces</a></strong></p></td>
<td><p>返回一个 <strong>Workspaces</strong> 集合，该集合包含所有可见的活动 <strong>Workspace</strong> 对象。只读。</p></td>
</tr>
</tbody>
</table>

