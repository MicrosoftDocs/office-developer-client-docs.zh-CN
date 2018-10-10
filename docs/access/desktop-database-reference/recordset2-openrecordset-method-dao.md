---
title: Recordset2.OpenRecordset Method (DAO)
TOCTitle: OpenRecordset Method
ms:assetid: da6ce86e-957e-21f8-07ac-8acd57326a12
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835325(v=office.15)
ms:contentKeyID: 48548082
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: cb435d47a0851bef59bcb600886fcb22b5605f6e
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466272"
---
# <a name="recordset2openrecordset-method-dao"></a>Recordset2.OpenRecordset Method (DAO)


**适用于**： Access 2013 |Office 2013

创建一个新的 **[Recordset](recordset-object-dao.md)** 对象，并将其追加到 **Recordsets** 集合。

## <a name="syntax"></a>语法

*表达式*。OpenRecordset (***选项***中的***类型***）

*表达式*一个表示**Recordset2**对象的变量。

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
<td><p>名称</p></td>
<td><p>必需</p></td>
<td><p><strong>String</strong></p></td>
<td><p>新的 <strong>Recordset</strong> 的记录源。该源可能是表名、查询名或返回记录的 SQL 语句。对于 Microsoft Access 数据库引擎数据库中的表类型 <strong>Recordset</strong> 对象，该源只能是表名。  </p></td>
</tr>
<tr class="even">
<td><p>类型</p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p><strong><a href="recordsettypeenum-enumeration-dao.md">RecordsetTypeEnum</a></strong> 常量，可指示要打开的 <strong>Recordset</strong> 的类型。</p>

> [!NOTE]
> <P>如果您在 Microsoft Access 工作区中打开了一个 <STRONG>Recordset</STRONG> 但未指定类型，<STRONG>OpenRecordset</STRONG> 将创建一个表类型 <STRONG>Recordset</STRONG>（如果可能）。如果您指定一个链接表或查询，<STRONG>OpenRecordset</STRONG> 将创建一个 dynaset 类型 <STRONG>Recordset</STRONG>。</P>


</td>
</tr>
<tr class="odd">
<td><p>选项</p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p><strong><a href="recordsetoptionenum-enumeration-dao.md">RecordsetOptionEnum</a></strong> 常量的组合，可指定新 <strong>Recordset</strong> 的特性。</p>

> [!NOTE]
> <P>常量<STRONG>dbConsistent</STRONG>和<STRONG>dbInconsistent</STRONG>是互斥的并且在同时使用将导致出错。 提供 lockedits 实参，当选项使用<STRONG>dbReadOnly</STRONG>常量还会导致错误。</P>


</td>
</tr>
<tr class="even">
<td><p>LockEdit</p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p><strong><a href="locktypeenum-enumeration-dao.md">LockTypeEnum</a></strong> 常量，可确定 <strong>Recordset</strong> 是否锁定。</p>

> [!NOTE]
> <P>您可以使用<STRONG>dbReadOnly</STRONG> options 参数或 lockedits 参数，但不是能同时中。 如果您使用它为两个参数，将发生运行时错误。</P>


</td>
</tr>
</tbody>
</table>


### <a name="return-value"></a>返回值

Recordset

## <a name="remarks"></a>注解

通常，如果用户在更新记录时接收到此错误，代码应刷新字段的内容，然后检索最近修改的值。如果在删除记录时出错，代码应向用户显示新记录数据，同时显示一则消息，指示最近更改了数据。此时，代码可能会请求确认用户是否仍要删除记录。

如果在 Microsoft Access 数据库引擎连接的 ODBC 工作区中，对包含 IDENTITY 列的 Microsoft SQL Server 6.0（或更新版本）表打开了 **Recordset**，则还应该使用 **dbSeeChanges** 常量，否则会导致出错。

对一个 ODBC 数据源打开多个 **Recordset** 可能会失败，因为连接正被 **OpenRecordset** 调用占用。解决此问题的一种方法是在打开 **Recordset** 后立即使用 **MoveLast** 方法，以完全填充 **Recordset**。

使用 [**Close**](connection-close-method-dao.md) 方法关闭 **Recordset** 会自动从 **Recordsets** 集合中将其删除。


> [!NOTE]
> <P>如果<EM>源</EM>是指的 SQL 语句组成非整数值时，连接字符串和系统参数指定非美国十进制字符，例如逗号分隔 (例如，strSQL ="价格&gt;" &amp; lngPrice，和 lngPrice =125,50)，当您尝试打开<STRONG>Recordset</STRONG>时就会出错。 这是因为在连接过程中，需要使用系统的默认小数字符将数字转换为字符串，并且 SQL 只接受美国格式的小数字符。</P>


