---
title: CREATE INDEX 语句 (Microsoft Access SQL)
TOCTitle: CREATE INDEX statement (Microsoft Access SQL)
ms:assetid: c5919ef4-a08d-df06-7078-5331adbcb45c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff823109(v=office.15)
ms:contentKeyID: 48547612
ms.date: 10/18/2018
mtps_version: v=office.15
f1_keywords:
- jetsql40.chm5277562
f1_categories:
- Office.Version=v15
localization_priority: Priority
ms.openlocfilehash: 46bc0a50e31555189c069e0ee09c4c84349c04c7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295427"
---
# <a name="create-index-statement-microsoft-access-sql"></a>CREATE INDEX 语句 (Microsoft Access SQL)

**适用于**：Access 2013、Office 2013

对现有表创建新索引。

> [!NOTE]
> [!注释] 对于非 Microsoft Access 数据库引擎的数据库，Microsoft Access 数据库引擎不支持使用 CREATE INDEX 语句（除了对 ODBC 链接表创建伪索引外）或者任何数据定义语言 (DDL) 语句。 请改为使用 DAO **Create** 方法。 有关详细信息，请参阅"备注"部分。

## <a name="syntax"></a>语法

CREATE \[ UNIQUE \] INDEX *index* ON *table* (*field* \[ASC|DESC\]\[, *field* \[ASC|DESC\], …\]) \[WITH { PRIMARY | DISALLOW NULL | IGNORE NULL }\]

CREATE INDEX 语句包含以下部分：

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Part</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>index</em></p></td>
<td><p>要创建的索引的名称。</p></td>
</tr>
<tr class="even">
<td><p><em>table</em></p></td>
<td><p>将包含索引的现有表的名称。</p></td>
</tr>
<tr class="odd">
<td><p><em>field</em></p></td>
<td><p>要索引的字段的名称。若要创建单字段索引，请在表名后面的圆括号里列出字段名称。若要创建多字段索引，请列出每一个将要包含在索引中的字段的名称。若要创建降序索引，请使用 DESC 保留字；否则，索引假定为升序。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

若要禁止不同记录的索引字段中出现重复值，请使用 UNIQUE 保留字。

在可选的 WITH 子句中，可以强制执行数据验证规则。 您可以进行以下操作：

- 通过使用 DISALLOW NULL 选项禁止新纪录的索引字段中使用 Null 项。

- 通过使用 IGNORE NULL 选项防止索引字段值为 **Null** 的记录包含在索引中。

- 使用 PRIMARY 保留字，将被索引字段指定为主键。这意味着该键是唯一的，所以可以省略 UNIQUE 保留字。

可以使用 CREATE INDEX 对 ODBC 数据源（如 Microsoft SQL Server）中不包含索引的链接表创建伪索引。 不需要针对远程服务器的权限或访问权限即可创建伪索引，远程数据库不会觉察到伪索引且不受其影响。 对链接表和本地表使用相同的语法。 对通常为只读状态的表创建伪索引非常有用。

也可以使用 [ALTER TABLE](alter-table-statement-microsoft-access-sql.md) 语句向表中添加单字段索引或多字段索引，还可以使用 ALTER TABLE 语句或 [DROP](drop-statement-microsoft-access-sql.md) 语句删除用 ALTER TABLE 或 CREATE INDEX 语句创建的索引。

> [!NOTE]
> 对已有主键的表创建新索引时，请勿使用 PRIMARY 保留字；这样做会出现错误。

## <a name="example"></a>示例

以下示例创建一个包含 Employees 表中的 Home Phone 和 Extension 字段的索引。

```vb
    Sub CreateIndexX1() 
     
        Dim dbs As Database 
     
        ' Modify this line to include the path to Northwind 
        ' on your computer. 
        Set dbs = OpenDatabase("Northwind.mdb") 
     
        ' Create the NewIndex index on the Employees table. 
        dbs.Execute "CREATE INDEX NewIndex ON Employees " _ 
            & "(HomePhone, Extension);" 
     
        dbs.Close 
     
    End Sub 
```

<br/>

本例使用 CustomerID 字段在 Customers 表上创建索引。CustomerID 字段中任何两个记录的数据都不能相同，并且不允许存在 Null 值。

```vb
    Sub CreateIndexX2() 
     
        Dim dbs As Database 
     
        ' Modify this line to include the path to Northwind 
        ' on your computer. 
        Set dbs = OpenDatabase("Northwind.mdb") 
     
        ' Create a unique index, CustID, on the  
        ' CustomerID field. 
        dbs.Execute "CREATE UNIQUE INDEX CustID " _ 
            & "ON Customers (CustomerID) " _ 
            & "WITH DISALLOW NULL;" 
     
        dbs.Close 
     
    End Sub
```
