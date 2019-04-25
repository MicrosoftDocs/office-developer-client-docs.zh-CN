---
title: QueryDef.OpenRecordset 方法 (DAO)
TOCTitle: OpenRecordset Method
ms:assetid: b4908c36-c156-e269-e2ad-b1fa20ec4884
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822070(v=office.15)
ms:contentKeyID: 48547232
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: a046359f39611e38b9e517495f54041f876addfc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32302847"
---
# <a name="querydefopenrecordset-method-dao"></a>QueryDef.OpenRecordset 方法 (DAO)

**适用于**：Access 2013、Office 2013

创建一个新的 **[Recordset](recordset-object-dao.md)** 对象，并将其追加到 **Recordsets** 集合。

## <a name="syntax"></a>语法

*表达式* .OpenRecordset(***Type***, ***Options***, ***LockEdit***)

*表达式* 一个表示 **QueryDef** 对象的变量。

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
<td><p><em>Type</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>
            <strong>
            <a href="recordsettypeenum-enumeration-dao.md">RecordsetTypeEnum</a></strong> 常量，可指示要打开的 <strong>Recordset</strong> 的类型。</p><p><strong>注意</strong>：如果在 Microsoft Access 工作区中打开 <STRONG>Recordset</STRONG>，并且不指定类型，<STRONG>OpenRecordset</STRONG> 会创建一个表类型 <STRONG>Recordset</STRONG>（如果可以）。 If you specify a linked table or query, <STRONG>OpenRecordset</STRONG> creates a dynaset-type <STRONG>Recordset</STRONG>.</p>
</td>
</tr>
<tr class="even">
<td><p><em>选项</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>
            <strong>
            <a href="recordsetoptionenum-enumeration-dao.md">RecordsetOptionEnum</a></strong> 常量的组合，可指定新 <strong>Recordset</strong> 的特性。</p></p><p><strong>注意</strong>：常量 <STRONG>dbConsistent</STRONG> 和 <STRONG>dbInconsistent</STRONG> 相互排斥，同时使用两者会产生错误。 当 Options 使用 <STRONG>dbReadOnly</STRONG> 常量时提供 LockEdit 参数也会导致错误。</p>
</td>
</tr>
<tr class="odd">
<td><p><em>LockEdit</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>
            <strong>
            <a href="locktypeenum-enumeration-dao.md">LockTypeEnum</a></strong> 常量，可确定 <strong>Recordset</strong> 是否锁定。</p></p><p><strong>注意</strong>：可以在 Options 参数或 LockedEdit 参数中使用 <STRONG>dbReadOnly</STRONG>，但不能同时在两个参数中使用。 如果将其同时用于这两个参数，将出现运行时错误。</p>
</td>
</tr>
</tbody>
</table>


## <a name="return-value"></a>返回值

Recordset

## <a name="remarks"></a>说明

如果在 Microsoft Access 数据库引擎连接的 ODBC 工作区中，对包含 IDENTITY 列的 Microsoft SQL Server 6.0（或更新版本）表打开了 **Recordset**，则还应该使用 **[dbSeeChanges](recordsetoptionenum-enumeration-dao.md)** 常量，否则会导致出错。

对一个 ODBC 数据源打开多个 **Recordset** 可能会失败，因为连接正被 **OpenRecordset** 调用占用。解决此问题的一种方法是在打开 **Recordset** 后立即使用 **[MoveLast](recordset-movelast-method-dao.md)** 方法，以完全填充 **Recordset**。

使用 **Close** 方法关闭 **Recordset** 会自动从 **Recordsets** 集合中将其删除。

> [!NOTE]
> 如果*源*引用了一个由连接了非整数值的字符串组成的 SQL 语句，并且系统参数指定了诸如逗号的非美国格式小数字符（例如 strSQL = "PRICE &gt; " &amp; lngPrice 和 lngPrice = 125,50），那么在尝试打开 **Recordset** 时会发生错误。 这是因为在连接过程中，需要使用系统的默认小数字符将数字转换为字符串，并且 SQL 只接受美国格式的小数字符。


