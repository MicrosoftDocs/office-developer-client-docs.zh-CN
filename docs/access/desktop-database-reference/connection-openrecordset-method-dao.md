---
title: OpenRecordset 方法 (DAO)
TOCTitle: OpenRecordset Method
ms:assetid: 584a3e00-7589-90f1-aa6a-5d6116f0b5b6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194324(v=office.15)
ms:contentKeyID: 48544993
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: abbb7a4f58714aef0e085d0f37b5ee49378e0f51
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295847"
---
# <a name="connectionopenrecordset-method-dao"></a>OpenRecordset 方法 (DAO)

**适用于**：Access 2013、Office 2013

创建一个新的 **[Recordset](recordset-object-dao.md)** 对象，并将其追加到 **Recordsets** 集合。

## <a name="syntax"></a>语法

*表达式*。OpenRecordset (***Name***、 ***Type***、 ***Options***、 ***LockEdit***)

*表达式*一个代表**Connection**对象的变量。

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
<td><p><em>Name</em></p></td>
<td><p>必需</p></td>
<td><p><strong>String</strong></p></td>
<td><p>新的 <strong>Recordset</strong> 的记录源。该源可能是表名、查询名或返回记录的 SQL 语句。对于 Microsoft Access 数据库引擎数据库中的表类型 <strong>Recordset</strong> 对象，该源只能是表名。  </p></td>
</tr>
<tr class="even">
<td><p><em>Type</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p><strong><a href="recordsettypeenum-enumeration-dao.md">RecordsetTypeEnum</a></strong> 常量，可指示要打开的 <strong>Recordset</strong> 的类型。</p><p><strong>注意</strong>: 如果在 Microsoft Access 工作区中打开<strong>Recordset</strong> , 但未指定类型, 则<strong>OpenRecordset</strong>将创建表类型的<strong>recordset</strong>(如果可能)。 If you specify a linked table or query, <strong>OpenRecordset</strong> creates a dynaset-type <strong>Recordset</strong>.</p>
</td>
</tr>
<tr class="odd">
<td><p><em>Options</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p><strong><a href="recordsetoptionenum-enumeration-dao.md">RecordsetOptionEnum</a></strong> 常量的组合，可指定新 <strong>Recordset</strong> 的特性。</p><p><strong>注意</strong>: 常量<strong>dbConsistent</strong>和<strong>dbInconsistent</strong>是互斥的, 同时使用 both 会导致错误。 当选项使用<strong>dbReadOnly</strong>常量时提供 lockedits 参数也会导致错误。</p>
</td>
</tr>
<tr class="even">
<td><p><em>LockEdit</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p><strong><a href="locktypeenum-enumeration-dao.md">LockTypeEnum</a></strong> 常量，可确定 <strong>Recordset</strong> 是否锁定。</p><p><strong>注意</strong>: 可以在 options 参数或 lockedits 参数中使用<strong>dbReadOnly</strong> , 但不能同时使用这两者。 If you use it for both arguments, a run-time error occurs.</p>
</td>
</tr>
</tbody>
</table>


## <a name="return-value"></a>返回值

Recordset

## <a name="remarks"></a>注解

通常，如果用户在更新记录时接收到此错误，代码应刷新字段的内容，然后检索最近修改的值。如果在删除记录时出错，代码应向用户显示新记录数据，同时显示一则消息，指示最近更改了数据。此时，代码可能会请求确认用户是否仍要删除记录。

如果在 Microsoft Access 数据库引擎连接的 ODBC 工作区中，对包含 IDENTITY 列的 Microsoft SQL Server 6.0（或更新版本）表打开了 **Recordset** ，则还应该使用 **dbSeeChanges** 常量，否则会导致出错。

对一个 ODBC 数据源打开多个 **Recordset** 可能会失败，因为连接正被 **OpenRecordset** 调用占用。解决此问题的一种方法是在打开 **Recordset** 后立即使用 **MoveLast** 方法，以完全填充 **Recordset** 。

使用 [**Close**](connection-close-method-dao.md) 方法关闭 **Recordset** 会自动从 **Recordsets** 集合中将其删除。

> [!NOTE]
> 如果*source*引用由与非整数值串联的字符串组成的 SQL 语句, 并且系统参数指定一个非美国十进制字符 (如逗号) (例如, strSQL = "PRICE &gt; " &amp; lngPrice 和 lngPrice =125, 50), 当您尝试打开**Recordset**时, 将发生错误。 这是因为在连接过程中，需要使用系统的默认小数字符将数字转换为字符串，并且 SQL 只接受美国格式的小数字符。


