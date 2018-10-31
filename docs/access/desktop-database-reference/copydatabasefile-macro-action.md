---
title: CopyDatabaseFile 宏操作
TOCTitle: CopyDatabaseFile Macro Action
ms:assetid: e6320b55-946b-9efc-9b64-b86513801a37
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835963(v=office.15)
ms:contentKeyID: 48548373
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 934a44ee754c403a9ef185537c8af114f1200d82
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25862532"
---
# <a name="copydatabasefile-macro-action"></a>CopyDatabaseFile 宏操作


**适用于**： Access 2013 |Office 2013

可以使用 **CopyDatabaseFile** 操作为连接至 Microsoft Access 项目的当前 Microsoft SQL Server 7.0（或更高版本）数据库创建一个副本。 访问当前数据库分离，然后将其附加到目标服务器。 有关分离和附加数据库的详细信息，请参阅 SQL Server 文档。


> [!NOTE]
> [!注释] 如果数据库不受信任，将不允许此操作。有关启用宏的详细信息，请参阅本文 See Also 一节中的链接。



## <a name="setting"></a>设置

**CopyDatabaseFile** 操作具有下列参数。

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
<td><p><strong>数据库文件名</strong></p></td>
<td><p>新的主数据文件的名称。该文件的默认路径为 Access 项目文件 (.adp) 的当前位置。</p></td>
</tr>
<tr class="even">
<td><p><strong>覆盖现有文件</strong></p></td>
<td><p>指定具有相同名称中替换现有文件。 如果设置为<strong>是</strong>和已存在同名，都将被覆盖该文件。 如果设置为<strong>No</strong>和已存在同名，该文件不会被覆盖操作失败。 如果文件不存在，则忽略此设置。 默认值为 <strong>"是"</strong>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>断开所有用户</strong></p></td>
<td><p>指定访问应强制关闭数据库的用户。 如果设置为<strong>是</strong>，连接到当前数据库的任何用户已断开连接，以便可以继续执行复制数据库操作。 如果设置为<strong>No</strong> ，另一个或多个用户连接到数据库，则复制数据库操作将失败。 默认值为 <strong>"否"</strong>。</p>

> [!WARNING]
> 在无充分警告的情况下断开用户与数据库的连接可能会导致数据丢失。


<p></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

复制操作是同步进行的，因此在完成对数据库的复制之前，无法执行其他操作。

**CopyDatabaseFile** 操作不仅会复制数据、数据定义和数据库对象，还会复制默认值、文本约束和查阅值等扩展属性。

复制数据库的要求：

  - 复制数据库文件之前，必须断开与所有应用程序和用户的连接。

  - 必须关闭除导航窗格以外的所有对象和视图。

  - 不得复制当前数据库。

  - 源服务器数据库必须是 Microsoft SQL Server 7.0 版或更高版本，或是在本地计算机上运行的 SQL Server 2000 Desktop Engine。

<!-- end list -->

  - 源服务器上的 SQL Server 数据库必须是单个文件数据库。

  - 您在源和目标 SQL Server 计算机上必须都是 sysadmin 角色的成员。

要在 Visual Basic for Applications 模块中运行 **CopyDatabaseFile** 操作，请使用 **DoCmd** 对象的 **CopyDatabaseFile** 方法。

