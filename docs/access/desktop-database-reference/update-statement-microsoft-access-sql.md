---
title: UPDATE 语句 (Microsoft Access SQL)
TOCTitle: UPDATE statement (Microsoft Access SQL)
ms:assetid: 08f9c3d6-c020-ecf1-5748-43b93a76dfbb
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845036(v=office.15)
ms:contentKeyID: 48543111
ms.date: 10/18/2018
mtps_version: v=office.15
f1_keywords:
- jetsql40.chm5277583
dev_langs:
- sql
f1_categories:
- Office.Version=v15
localization_priority: Priority
ms.openlocfilehash: 6a0404c21b308f6e389ee5577cc212763e660774
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306242"
---
# <a name="update-statement-microsoft-access-sql"></a>UPDATE 语句 (Microsoft Access SQL)

**适用于**：Access 2013、Office 2013

创建一个更新查询，以便基于特定的条件更改指定表的字段值。

## <a name="syntax"></a>语法

UPDATE *table* SET *newvalue* WHERE *criteria*;

UPDATE 语句包含以下部分：

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
<td><p>表的名称，此表中包含要修改的数据。</p></td>
</tr>
<tr class="even">
<td><p><em>newvalue</em></p></td>
<td><p>表达式，确定将哪些值插入已更新的记录中的特定字段。</p></td>
</tr>
<tr class="odd">
<td><p><em>criteria</em></p></td>
<td><p>表达式，用来确定将更新哪些记录。 只有满足该表达式的记录才会被更新。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

如果要更改许多记录，或者要更改的记录位于多个表中，UPDATE 则尤其有用。

可以同时更改若干字段。以下示例将英国货主的“采购量”值增加 10％，“运费”值增加 3％：

```sql
UPDATE Orders 
SET OrderAmount = OrderAmount * 1.1, 
Freight = Freight * 1.03 
WHERE ShipCountry = 'UK';
```


> [!IMPORTANT]
- UPDATE 不会生成结果集。而且，使用更新查询来更新记录后，您不能取消该操作。如果希望了解已更新哪些记录，请先检查使用相同条件的选择查询的结果，然后再运行更新查询。
- 随时维护数据的备份副本。 如果更新了错误的记录，可以从备份副本检索它们。



## <a name="example"></a>示例

本示例针对当前 ReportsTo 字段值为 2 的所有员工记录，将 ReportsTo 字段值更改为 5。

```vb
    Sub UpdateX() 
     
        Dim dbs As Database 
        Dim qdf As QueryDef 
     
        ' Modify this line to include the path to Northwind 
        ' on your computer. 
        Set dbs = OpenDatabase("Northwind.mdb") 
         
        ' Change values in the ReportsTo field to 5 for all  
        ' employee records that currently have ReportsTo  
        ' values of 2. 
        dbs.Execute "UPDATE Employees " _ 
            & "SET ReportsTo = 5 " _ 
            & "WHERE ReportsTo = 2;" 
             
        dbs.Close 
     
    End Sub
```
