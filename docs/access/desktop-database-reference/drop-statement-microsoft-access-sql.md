---
title: DROP 语句 (Microsoft Access SQL)
TOCTitle: DROP statement (Microsoft Access SQL)
ms:assetid: a8c79c35-22da-2e6d-88b5-620eb481bb61
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821409(v=office.15)
ms:contentKeyID: 48546907
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: f31067c96c19804352ca74957e064f9338b49260
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32293649"
---
# <a name="drop-statement-microsoft-access-sql"></a>DROP 语句 (Microsoft Access SQL)

**适用于**：Access 2013、Office 2013

从数据库中删除现有表、过程或视图，或从表中删除现有索引。

> [!NOTE]
> [!注释] Microsoft Access 数据库引擎不支持将 DROP 或任何 DDL 语句用于非 Microsoft Access 数据库引擎数据库。可以改用 **Delete** 方法。

## <a name="syntax"></a>语法

DROP {TABLE *table* | INDEX *index* ON *table* | PROCEDURE *procedure* | VIEW *view*}

DROP 语句包含以下部分：

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
<td><p><em>table</em></p></td>
<td><p>要删除的表或要从中删除索引的表的名称。</p></td>
</tr>
<tr class="even">
<td><p><em>procedure</em></p></td>
<td><p>要删除的过程的名称。</p></td>
</tr>
<tr class="odd">
<td><p><em>view</em></p></td>
<td><p>要删除的视图的名称。</p></td>
</tr>
<tr class="even">
<td><p><em>index</em></p></td>
<td><p>要从<em>表</em>中删除的索引的名称。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

必须先关闭表才可删除该表或从其中删除索引。

还可以使用 [ALTER TABLE](alter-table-statement-microsoft-access-sql.md) 语句从表中删除索引。

可以使用 [CREATE TABLE](create-table-statement-microsoft-access-sql.md) 创建一个表，用 [CREATE INDEX](create-index-statement-microsoft-access-sql.md) 或者 ALTER TABLE 语句创建一个索引。若要对表进行修改，请使用 ALTER TABLE 语句。

## <a name="example"></a>示例

以下示例假定 Northwind 数据库的 Employees 表中存在一个假想的 NewIndex 索引。

以下示例从 Employees 表中删除 MyIndex 索引。

```vb
    Sub DropX1() 
     
        Dim dbs As Database 
     
        ' Modify this line to include the path to Northwind 
        ' on your computer. 
        Set dbs = OpenDatabase("Northwind.mdb") 
     
        ' Delete NewIndex from the Employees table. 
        dbs.Execute "DROP INDEX NewIndex ON Employees;" 
     
        dbs.Close 
     
    End Sub
```

<br/>

以下示例从数据库中删除 Employees 表。

```vb
    Sub DropX2() 
     
        Dim dbs As Database 
     
        ' Modify this line to include the path to Northwind 
        ' on your computer. 
        Set dbs = OpenDatabase("Northwind.mdb") 
     
        ' Delete the Employees table. 
        dbs.Execute "DROP TABLE Employees;" 
     
        dbs.Close 
     
    End Sub
```
