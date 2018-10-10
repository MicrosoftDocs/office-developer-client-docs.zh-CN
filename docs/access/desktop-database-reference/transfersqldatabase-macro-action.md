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
ms.openlocfilehash: 301fce8bcdeff45135c305054da72f4c75f503eb
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466125"
---
# <a name="transfersqldatabase-macro-action"></a>TransferSQLDatabase 宏操作


**适用于**： Access 2013 |Office 2013

在 Microsoft Access 项目中，可以使用 **TransferSQLDatabase** 操作将 Microsoft SQL Server 7.0 或更高版本的数据库迁移到另一个 SQL Server 7.0 或更高版本的数据库。有关迁移数据库的详细信息，请参阅 SQL Server 文档。


> [!NOTE]
> <P>[!注释] 如果数据库不受信任，将不允许此操作。有关启用宏的详细信息，请参阅本文 See Also 一节中的链接。</P>



## <a name="setting"></a>设置

**TransferSQLDatabase** 操作具有下列参数。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>操作参数</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Server</strong></p></td>
<td><p>要复制到的 SQL Server 7.0 或更高版本的数据库服务器的名称。</p></td>
</tr>
<tr class="even">
<td><p><strong>Database</strong></p></td>
<td><p>将在目标服务器上创建的新数据库的名称。</p></td>
</tr>
<tr class="odd">
<td><p><strong>使用可信连接</strong></p></td>
<td><p>指定是否存在是受信任的连接到 SQL Server。 如果设置为<strong>是</strong>，则没有受信任的连接和<strong>登录名</strong>和<strong>密码</strong>参数不是必需的。 如果设置为<strong>无</strong>、<strong>登录名</strong>和<strong>密码</strong>参数是必需的。 默认值为 <strong>"是"</strong>。 使用可信的连接时，具有 Windows 操作系统安全提供单一登录网络和数据库集成了 SQL Server 安全。</p></td>
</tr>
<tr class="even">
<td><p><strong>登录</strong></p></td>
<td><p>目标服务器的登录名。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Password</strong></p></td>
<td><p><strong>登录</strong>参数的密码。 此密码存储为文本中的 Access 项目，但在传输数据库操作过程中隐藏。</p></td>
</tr>
<tr class="even">
<td><p><strong>传输复制数据</strong></p></td>
<td><p>指定在数据库迁移操作中是否包括数据。如果设置为<strong>“是”</strong>，则将包括所有表中的所有数据，以及所有的数据结构、扩展属性和数据库对象。如果设置为<strong>“否”</strong>，则将不包括表中的数据。仅将在目标服务器上创建表结构和扩展属性以及所有其他数据库对象（不包括数据库图表）。默认值为<strong>“是”</strong>。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

在数据库迁移过程中不能执行其他操作。

默认情况下， **TransferSQLDatabase** 操作会复制数据、数据定义、数据库对象和扩展属性，例如默认值、文本约束和查阅值。

下面是关于迁移数据库的一些要求：

  - 您必须是目标服务器上 sysadmin 角色的成员（源服务器上不要求有任何特殊角色）。

<!-- end list -->

  - 当前连接到 Access 项目的 SQL 服务器和要向其迁移数据库的目标服务器必须为 SQL Server 7.0 版或更高版本。


> [!NOTE]
> <P>[!注释] 在数据库迁移操作过程中，不迁移链接服务器。</P>



要在 Visual Basic for Applications (VBA) 模块中运行 **TransferSQLDatabase** 操作，请使用 **DoCmd** 对象的 **TransferSQLDatabase** 方法。

