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
ms.openlocfilehash: 4e7f27cb696b085b5c4536477ee3454df09cfabe
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25881284"
---
# <a name="update-statement-microsoft-access-sql"></a>UPDATE 语句 (Microsoft Access SQL)

**适用于**： Access 2013、 Office 2013

创建一个更新查询，以便基于特定的条件更改指定表的字段值。

## <a name="syntax"></a>语法

更新*表*设置*newvalue* WHERE*条件*;

UPDATE 语句包含以下部分：

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
<td><p><em>table</em></p></td>
<td><p>表名，该表包含要修改的数据。</p></td>
</tr>
<tr class="even">
<td><p><em>newvalue</em></p></td>
<td><p>表达式，该表达式确定将要插入到已更新记录的特定字段内的值。</p></td>
</tr>
<tr class="odd">
<td><p><em>criteria</em></p></td>
<td><p>表达式，用来确定将更新哪些记录。只有满足该表达式的记录才会被更新。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

当需要更改多个记录或者需要更改的记录存在于多个表中时，UPDATE 语句是最有用的。

可以同时更改多个字段。下面的示例把英国货主的订货量的值增加百分之十，并且把运费的值增加百分之三。

```sql
UPDATE Orders 
SET OrderAmount = OrderAmount * 1.1, 
Freight = Freight * 1.03 
WHERE ShipCountry = 'UK';
```


> [!IMPORTANT]
- UPDATE 不会生成结果集。而且，使用更新查询来更新记录后，您不能取消该操作。如果希望了解已更新哪些记录，请先检查使用相同条件的选择查询的结果，然后再运行更新查询。
- 不论什么时候都要维护数据的备份。如果更新了错误记录，您可以从备份副本中检索这些记录。




## <a name="example"></a>示例

以下示例将当前的 ReportsTo 值为 2 的所有雇员记录的 ReportsTo 字段中的值改为 5。



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
