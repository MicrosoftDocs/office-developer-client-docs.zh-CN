---
title: SELECT.INTO 语句 (Microsoft Access SQL)
TOCTitle: SELECT.INTO statement (Microsoft Access SQL)
ms:assetid: 29f3bd55-52f5-a36e-4e33-4b3499c6ce8d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192059(v=office.15)
ms:contentKeyID: 48543897
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: fd7152eaa7dd29f6d0bf5621d1b8b8b6f648673c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308720"
---
# <a name="selectinto-statement-microsoft-access-sql"></a>SELECT.INTO 语句 (Microsoft Access SQL)

**适用于**：Access 2013、Office 2013

创建生成表查询。

## <a name="syntax"></a>语法

SELECT *field1*\[, *field2*\[, …\]\] INTO *newtable* \[IN *externaldatabase*\] FROM *source*

SELECT...INTO 语句包含以下部分：

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
<td><p><em>field1</em>, <em>field2</em></p></td>
<td><p>要复制到新表中的字段的名称。</p></td>
</tr>
<tr class="even">
<td><p><em>newtable</em></p></td>
<td><p>要创建的表的名称。它必须符合标准命名约定。如果 <em>newtable</em> 和现有表同名，会发生一个可捕捉的错误。</p></td>
</tr>
<tr class="odd">
<td><p><em>externaldatabase</em></p></td>
<td><p>外部数据库的路径。 有关路径的说明，请参阅 <a href="https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/in-clause-microsoft-access-sql">IN</a> 子句。</p></td>
</tr>
<tr class="even">
<td><p><em>source</em></p></td>
<td><p>从中选择记录的现有表的名称。 可以是单个表或多个表，也可以是查询。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

可使用生成表查询来存档记录、创建表的备份副本、或创建副本，用于导出到另一个数据库，或用作在特定时间段内显示数据的报表的基础。例如，可通过每月运行相同的生成表查询来生成 Monthly Sales by Region 报表。

> [!NOTE]
> - 您可能希望定义新表的主键。创建表时，新表中的字段会继承查询的基表中每个字段的数据类型和字段大小，但不会传输其他字段或表属性。
> - 若要将数据添加到现有表中，请使用 [INSERT INTO](insert-into-statement-microsoft-access-sql.md) 语句，而不用创建追加查询。
> - 若要在运行生成表查询之前查找出将要选择哪些记录，请先检查使用相同选择条件的 [SELECT](select-statement-microsoft-access-sql.md) 语句的结果。



## <a name="example"></a>示例

本示例选择 Employees 表中的所有记录，并将它们复制到名为 Emp Backup 的新表中。

```vb
    Sub SelectIntoX() 
     
        Dim dbs As Database 
        Dim qdf As QueryDef 
     
        ' Modify this line to include the path to Northwind 
        ' on your computer. 
        Set dbs = OpenDatabase("Northwind.mdb") 
     
        ' Select all records in the Employees table  
        ' and copy them into a new table, Emp Backup. 
        dbs.Execute "SELECT Employees.* INTO " _ 
            & "[Emp Backup] FROM Employees;" 
             
        ' Delete the table because this is a demonstration. 
        dbs.Execute "DROP TABLE [Emp Backup];" 
         
        dbs.Close 
     
    End Sub
```
