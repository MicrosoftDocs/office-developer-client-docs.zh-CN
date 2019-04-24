---
title: FindPrevious 方法 (DAO) Recordset2
TOCTitle: FindPrevious Method
ms:assetid: ec35faf4-20f2-a83f-54e4-ac1f66c3c2be
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836294(v=office.15)
ms:contentKeyID: 48548509
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 9cf53526f9643737c7236bb2c98589e74f3f2eb5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32307313"
---
# <a name="recordset2findprevious-method-dao"></a>FindPrevious 方法 (DAO) Recordset2

**适用于**：Access 2013、Office 2013

在动态集类型或快照类型的 **[Recordset](recordset-object-dao.md)** 对象中查找符合指定条件的上一条记录，并且使该记录成为当前记录（仅适用于 Microsoft Access 工作区）。

## <a name="syntax"></a>语法

*表达式*。FindPrevious (***条件***)

*表达式*一个代表**Recordset2**对象的变量。

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
<td><p><em>Criteria</em></p></td>
<td><p>必需</p></td>
<td><p><strong>String</strong></p></td>
<td><p>用于查找记录的字符串。 它类似于 SQL 语句中的 WHERE 子句，但不包括单词 WHERE。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

如果要在搜索中包括所有记录（而不仅仅是符合特定条件的记录），请使用 **Move** 方法在记录之间移动。若要在表类型的 **Recordset** 中查找记录，请使用 **Seek** 方法。

如果未找到与条件匹配的记录，当前记录指针将是未知的，同时 **NoMatch** 属性将设置为 **True**。 如果 recordset 包含多个满足条件的记录, 则**FindFirst**将查找第一个匹配项, **FindNext**查找下一个匹配项, 依此类推。

每个 **Find** 方法都按下表中指定的方向，从该表指定的位置开始搜索。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Find 方法</p></th>
<th><p>开始搜索的位置</p></th>
<th><p>搜索方向</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>FindFirst</strong></p></td>
<td><p>记录集开头</p></td>
<td><p>记录集末尾</p></td>
</tr>
<tr class="even">
<td><p><strong>FindLast</strong></p></td>
<td><p>记录集末尾</p></td>
<td><p>记录集开头</p></td>
</tr>
<tr class="odd">
<td><p><strong>FindNext</strong></p></td>
<td><p>当前记录</p></td>
<td><p>记录集末尾</p></td>
</tr>
<tr class="even">
<td><p><strong>FindPrevious</strong></p></td>
<td><p>当前记录</p></td>
<td><p>记录集开头</p></td>
</tr>
</tbody>
</table>


但是，使用 **Find** 方法之一与使用 **Move** 方法不同，后者只是将第一条、最后一条、下一条或上一条记录设置为当前记录，而不会指定条件。可以在 Find 操作后面跟随一个 Move 操作。

始终检查 **NoMatch** 属性的值，以确定 Find 操作是否已成功。如果搜索成功，则 **NoMatch** 为 **False**。如果搜索失败，则 **NoMatch** 为 **True**，并且不定义当前记录。在这种情况下，必须将当前记录指针往回定位到有效的记录。

如果将 **Find** 方法用于 Microsoft Access 数据库引擎连接的 ODBC 访问记录集，效率可能较低。 您可能会发现, 更快地查找特定记录的条件会更快, 尤其是在处理大型记录集时。

在处理 Microsoft Access 数据库引擎连接的 ODBC 数据库以及大型动态集类型 **Recordset** 对象时，可能会发现使用 **Find** 方法或使用 **Sort** 或 **Filter** 属性都比较慢。若要改善性能，请将 SQL 查询与自定义的 ORDER BY 或 WHERE 子句、参数查询或检索特定索引记录的 **QueryDef** 对象一起使用。

在搜索包含日期的字段时，即使使用的不是美国版本的 Microsoft Access 数据库引擎，也应使用美国日期格式（月-日-年）；否则将无法找到数据。使用 Visual Basic **Format** 函数转换日期。例如：

```vb
rstEmployees.FindFirst "HireDate > #" _ 
        & Format(mydate, 'm-d-yy' ) & "#" 
```

如果条件由连接到非整数值的字符串组成, 并且系统参数指定一个非美国十进制字符 (如逗号) (例如, strSQL = "PRICE \> " & lngPrice, lngPrice = 125, 50), 则当您尝试调用方法。 这是因为在连接过程中，需要使用系统的默认小数字符将数字转换为字符串，并且 Microsoft Access SQL 只接受美国格式的小数字符。

> [!NOTE]
> - 为获得最佳性能,*条件** 应为 "*字段* = *值*" 窗体中的*字段*是基础基表中的索引字段, 或者是 "*字段*类似*前缀*", 其中*字段*是基础基表中的索引字段和*前缀*是前缀搜索字符串 (例如, "ART *")。
> - 一般而言，作为等效的搜索类型， **Seek** 方法的性能优于 **Find** 方法。这假定表类型的 **Recordset** 对象可单独满足您的需求。


