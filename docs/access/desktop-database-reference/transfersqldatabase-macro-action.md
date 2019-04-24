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
# <a name="transfersqldatabase-macro-action"></a>TransferSQLDatabase 宏操作

**适用于**：Access 2013、Office 2013

在 Microsoft Access 项目中，可以使用 **TransferSQLDatabase** 操作将 Microsoft SQL Server 7.0 或更高版本的数据库迁移到另一个 SQL Server 7.0 或更高版本的数据库。 有关传输数据库的详细信息, 请参阅 SQL Server 文档。

> [!NOTE]
> 如果数据库不受信任，则不允许执行此操作。

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
<td><p><strong>服务器</strong></p></td>
<td><p>要复制到的 SQL Server 7.0 或更高版本的数据库服务器的名称。</p></td>
</tr>
<tr class="even">
<td><p><strong>数据库</strong></p></td>
<td><p>将在目标服务器上创建的新数据库的名称。</p></td>
</tr>
<tr class="odd">
<td><p><strong>使用可信连接</strong></p></td>
<td><p>指定是否有到 SQL Server 的可信连接。 如果设置为<strong>“是”</strong>，则有可信连接，而且“登录”<strong></strong>和“密码”<strong></strong>参数不是必选的。 如果设置为<strong>“否”</strong>，“登录”<strong></strong>和“密码”<strong></strong>参数则是必选的。 默认值为<strong>“是”</strong>。 当您使用受信任的连接时, SQL Server 安全性将与 Windows 操作系统安全性集成, 以提供网络和数据库的单一登录。</p></td>
</tr>
<tr class="even">
<td><p><strong>[</strong></p></td>
<td><p>目标服务器的登录名。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Password</strong></p></td>
<td><p>“登录”<strong></strong>参数的密码。此密码在 Access 项目中作为文本存储，但在数据库迁移操作过程中是隐藏的。</p></td>
</tr>
<tr class="even">
<td><p><strong>传输复制数据</strong></p></td>
<td><p>指定在数据库迁移操作中是否包括数据。如果设置为<strong>“是”</strong>，则将包括所有表中的所有数据，以及所有的数据结构、扩展属性和数据库对象。如果设置为<strong>“否”</strong>，则将不包括表中的数据。仅将在目标服务器上创建表结构和扩展属性以及所有其他数据库对象（不包括数据库图表）。默认值为<strong>“是”</strong>。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

在数据库迁移过程中不能执行其他操作。

默认情况下，**TransferSQLDatabase** 操作会复制数据、数据定义、数据库对象和扩展属性，例如默认值、文本约束和查阅值。

下面是关于迁移数据库的一些要求：

- 您必须是目标服务器上 sysadmin 角色的成员（源服务器上不要求有任何特殊角色）。

- 当前连接到 Access 项目的 SQL 服务器和要向其迁移数据库的目标服务器必须为 SQL Server 7.0 版或更高版本。

  > [!NOTE]
  > 在数据库迁移操作过程中，不迁移链接服务器。

要在 Visual Basic for Applications (VBA) 模块中运行 **TransferSQLDatabase** 操作，请使用 **DoCmd** 对象的 **TransferSQLDatabase** 方法。

