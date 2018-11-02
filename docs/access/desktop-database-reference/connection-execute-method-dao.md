---
title: Connection.Execute 方法 (DAO)
TOCTitle: Execute Method
ms:assetid: d6140d4e-fa14-6455-525e-49d8aab3dff7
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835040(v=office.15)
ms:contentKeyID: 48547978
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 6a06837ec98d96cc4c6ae75a19dd953ca4dc59dc
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25920079"
---
# <a name="connectionexecute-method-dao"></a>Connection.Execute 方法 (DAO)


**适用于**： Access 2013、 Office 2013

对指定的对象运行动作查询，或执行 SQL 语句。

## <a name="syntax"></a>语法

*表达式*。执行 （***查询***，***选项***）

*表达式*代表**Connection**对象的变量。

### <a name="parameters"></a>参数

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
<td><p>Query</p></td>
<td><p>必需</p></td>
<td><p><strong>字符串</strong></p></td>
<td><p>一个 <strong>String</strong>，为 SQL 语句，或者 <strong>QueryDef</strong> 对象的 <strong>Name</strong> 属性值。</p></td>
</tr>
<tr class="even">
<td><p>选项</p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>一个常量或常量组合，按 Settings 中的指定确定查询的数据完整性特征。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

选项，可以使用以下**[RecordsetOptionEnum](recordsetoptionenum-enumeration-dao.md)** 常量。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>常量</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>dbDenyWrite</strong></p></td>
<td><p>拒绝其他用户的写入权限（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong>dbInconsistent</strong></p></td>
<td><p>（默认值）执行不一致的更新（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbConsistent</strong></p></td>
<td><p>执行一致的更新（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong>dbSQLPassThrough</strong></p></td>
<td><p>执行 SQL 传递查询。设置此选项会将 SQL 语句传递给 ODBC 数据库以进行处理（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbFailOnError</strong></p></td>
<td><p>发生错误时回滚更新（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong>dbSeeChanges</strong></p></td>
<td><p>如果其他用户更改您正编辑的数据，则生成运行时错误（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbRunAsync</strong></p></td>
<td><p>异步执行查询（仅适用于 ODBCDirect Connection 和 QueryDef 对象）。</p></td>
</tr>
<tr class="even">
<td><p><strong>一设置</strong></p></td>
<td><p>在不首先调用 SQLPrepare ODBC API 函数的情况下，执行语句（仅适用于 ODBCDirect Connection 和 QueryDef 对象）。</p></td>
</tr>
</tbody>
</table>

> [!NOTE]
> Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。 如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。

> [!NOTE]
> [!注释] 常量 **dbConsistent** 和 **dbInconsistent** 是互斥的。可以在 **OpenRecordset** 的给定实例中使用其中的某一个，但不能同时使用此两者。同时使用 **dbConsistent** 和 **dbInconsistent** 会导致出错。

**Execute** 方法仅对动作查询有效。如果将 **Execute** 与另一个查询类型一起使用，将会发生错误。由于动作查询不返回任何记录，因此 **Execute** 不返回 **Recordset**。（如果不返回 **Recordset**，在 ODBCDirect 工作区中执行 SQL 传递查询不会返回错误。）

使用 **Connection**、 **Database** 或 **QueryDef** 对象的 **RecordsAffected** 属性确定受最近的 **Execute** 方法影响的记录数。例如， **RecordsAffected** 包含执行某个动作查询时删除、更新或插入的记录数。如果使用 **Execute** 方法运行查询，会将 **QueryDef** 对象的 **RecordsAffected** 属性设置为受影响的记录数。

在 Microsoft Access 工作区中，如果提供了一个在语法上正确的 SQL 语句，并且您具有相应的权限，则 **Execute** 方法不会失败 - 即使一行都不能修改或删除，也是如此。因此，在使用 **Execute** 方法运行更新或删除查询时，请始终使用 **dbFailOnError** 选项。如果锁定了任何受影响的记录，因而无法对其进行更新或删除，此选项将生成运行时错误，同时回滚所有成功的更改。

在早期版本的 Microsoft Jet 数据库引擎中，SQL 语句自动嵌入到隐式事务中。如果使用 **dbFailOnError** 执行的语句的一部分失败，则整个语句都会回滚。为了改善性能，从版本 3.5 开始，删除了这些隐式事务。如果要更新早期的 DAO 代码，请务必考虑对 **Execute** 语句使用显式事务。

为了在 Microsoft Access 工作区中，特别是在多用户环境中获取最佳性能，请将 **Execute** 方法嵌套在事务中。对当前的 **Workspace** 对象使用 **BeginTrans** 方法，然后使用 **Execute** 方法，再对 **Workspace** 使用 **CommitTrans** 方法完成事务。这样可以保存磁盘上的更改，并且释放任何在运行查询时放置的锁定。

