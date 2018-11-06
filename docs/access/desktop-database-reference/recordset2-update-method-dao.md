---
title: Recordset2.Update 方法 (DAO)
TOCTitle: Update Method
ms:assetid: 1b47606a-e79c-23f1-b120-46d1429bc167
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845700(v=office.15)
ms:contentKeyID: 48543537
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052882
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 996686501d355555814a48bc665f3eb634a74298
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25998614"
---
# <a name="recordset2update-method-dao"></a>Recordset2.Update 方法 (DAO)

**适用于**： Access 2013、 Office 2013

## <a name="syntax"></a>语法

*表达式*。更新 （***UpdateType***，***强制***）

*表达式*一个表示**Recordset2**对象的变量。

## <a name="parameters"></a>参数

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>名称</p></th>
<th><p>必需/可选</p></th>
<th><p>数据类型</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>UpdateType</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Long</strong></p></td>
<td><p>一个 <strong><a href="updatetypeenum-enumeration-dao.md">UpdateTypeEnum</a></strong> 常量，指示"设置"中指定的更新类型（仅适用于 ODBCDirect 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Boolean</strong></p></td>
<td><p>一个 <strong>Boolean</strong> 值，指示是否将更改强制到数据库中，而不管自从 <strong><a href="recordset-addnew-method-dao.md">AddNew</a></strong> 、 <strong><a href="fields-delete-method-dao.md">Delete</a></strong> 或 <strong><a href="recordset2-edit-method-dao.md">Edit</a></strong> 调用以来，其他用户是否更改了基础数据。如果为 <strong>True</strong> ，则会强制更改，并且只是覆盖由其他用户所做的更改。如果为 <strong>False</strong> （默认值），在更新处于待定状态时由其他用户所做的更改将导致更改对冲突的更改失败。不发生错误，但是 <strong><a href="recordset-batchcollisioncount-property-dao.md">BatchCollisionCount</a></strong> 和 <strong>BatchCollisions</strong> 属性将分别指示冲突数和受冲突影响的行数（仅适用于 ODBCDirect 工作区）。  </p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

使用 **Update** 可保存当前记录以及对它所做的任何更改。

> [!IMPORTANT]
> [!重要信息] 在以下情况下，对当前记录所做的更改将会丢失：
> - 使用了 **Edit** 或 **AddNew** 方法，然后在没有事先使用 **Update** 的情况下移到另一条记录。
> - 使用了 **Edit** 或 **AddNew** ，然后在没有事先使用 **Update** 的情况下再次使用 **Edit** 或 **AddNew** 。
> - 将 **[Bookmark](recordset2-bookmark-property-dao.md)** 属性设置为另一条记录。
> - 在没有事先使用 **Update** 的情况下关闭了 **Recordset** 。
> - 使用 [**CancelUpdate**](recordset2-cancelupdate-method-dao.md) 取消 **Edit** 操作。

要编辑一条记录，请使用 **Edit** 方法将当前记录的内容复制到复制缓冲区。如果不首先使用 **Edit** ，在使用 **Update** 或试图更改字段值时将会发生错误。

在 ODBCDirect 工作区中，如果游标库支持批更新，并且使用开放式批锁定选项打开了 **Recordset** ，则可以执行批更新。

在 Microsoft Access 工作区中，如果多用户环境中的 **Recordset** 对象的 **LockEdits** 属性设置为 **True** （悲观锁定），那么从使用 **Edit** 开始到执行了 **Update** 方法或取消了编辑的时间范围内，记录将保持锁定状态。 如果 **LockEdits** 属性设置为 **False** （乐观锁定），那会锁定此记录，并且在数据库中对它更新之前，将它与预编辑的记录进行比较。 如果自从使用 **Edit** 方法之后记录发生了更改， **Update** 操作将会失败。 Microsoft Access 数据库引擎连接的 ODBC 和可安装的 ISAM 数据库始终使用乐观锁定。 若要使用更改继续 **Update** 操作，请再次使用 **Update** 方法。 若要恢复到其他用户记录更改它，刷新当前记录，请使用 Move 0。

> [!NOTE]
> [!注释] 若要添加、编辑或删除记录，基础数据源中的记录必须存在唯一索引。如果不存在此索引，在 Microsoft Access 工作区中， **AddNew**、 **Delete** 或 **Edit** 方法调用将发生"权限被拒绝"错误，在 ODBCDirect 工作区中， **Update** 调用将发生"无效参数"错误。


