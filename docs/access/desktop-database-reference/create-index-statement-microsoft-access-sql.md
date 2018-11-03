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
ms.openlocfilehash: 1b12fcf4d92bbe0949065557973efe94688a7a30
ms.sourcegitcommit: 38d0db57580cc5f4a0231c27b1643f8db5431ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25937202"
---
# <a name="create-index-statement-microsoft-access-sql"></a>CREATE INDEX 语句 (Microsoft Access SQL)

**适用于**： Access 2013、 Office 2013

对现有表创建一个新索引。

> [!NOTE]
> 对于 Microsoft Access 数据库引擎数据库，Microsoft Access 数据库引擎不支持使用 CREATE INDEX （除以创建一个 ODBC 链接表伪索引） 或任何数据定义语言 (DDL) 语句。 而是使用 DAO**创建**方法。 有关详细信息，请参阅"备注"部分。

## <a name="syntax"></a>语法

创建\[唯一\]索引*索引*ON*表*(*域* \[ASC |DESC\]\[，*字段* \[ASC |DESC\]，...\]) \[WITH {主 |不允许 NULL |忽略 NULL}\]

CREATE INDEX 语句包含以下部分：

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>部分</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>index</em></p></td>
<td><p>将要创建的索引的名称。</p></td>
</tr>
<tr class="even">
<td><p><em>table</em></p></td>
<td><p>将包含该索引的现有表的名称。</p></td>
</tr>
<tr class="odd">
<td><p><em>field</em></p></td>
<td><p>要索引的字段的名称。若要创建单字段索引，请在表名后面的圆括号里列出字段名称。若要创建多字段索引，请列出每一个将要包含在索引中的字段的名称。若要创建降序索引，请使用 DESC 保留字；否则，索引假定为升序。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

若要禁止在不同记录的被索引字段中的值重复，请使用 UNIQUE 保留字。

在与子句可选，您可以实施数据验证规则。 您可以：

- 使用 DISALLOW NULL 选项，以禁止在新记录的被索引字段中出现 Null 条目。

- 使用 IGNORE NULL 选项，以防止被索引字段中含有 **NULL** 值的记录被包含在索引中。

- 使用 PRIMARY 保留字，将被索引字段指定为主键。这意味着该键是唯一的，所以可以省略 UNIQUE 保留字。

CREATE INDEX 用于 ODBC 数据源，例如 Microsoft SQL Server，尚不具有索引中的链接表上创建伪索引。 创建伪索引不需要得到授权或者访问远程服务器，并且远程数据库不知情也不会受伪索引的影响。 可以对链接表或本地表使用相同的语法。 对通常为只读的表创建伪索引会很有用。

也可以使用 [ALTER TABLE](alter-table-statement-microsoft-access-sql.md) 语句向表中添加单字段索引或多字段索引，还可以使用 ALTER TABLE 语句或 [DROP](drop-statement-microsoft-access-sql.md) 语句删除用 ALTER TABLE 或 CREATE INDEX 语句创建的索引。

> [!NOTE]
> [!注释] 如果对已包含主键的表创建一个新索引，请不要使用 PRIMARY 保留字；如果这样做，就会产生错误。

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
