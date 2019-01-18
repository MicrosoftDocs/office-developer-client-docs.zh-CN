---
title: DELETE 语句 (Microsoft Access SQL)
TOCTitle: DELETE statement (Microsoft Access SQL)
ms:assetid: 64c235bc-5b1a-0a33-714a-9933ba7a81e5
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195097(v=office.15)
ms:contentKeyID: 48545299
ms.date: 10/18/2018
mtps_version: v=office.15
f1_keywords:
- jetsql40.chm5277573
f1_categories:
- Office.Version=v15
localization_priority: Priority
ms.openlocfilehash: a4ef478e74f9851012d6f749e64b4ddb34f3a959
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28715618"
---
# <a name="delete-statement-microsoft-access-sql"></a>DELETE 语句 (Microsoft Access SQL)

**适用于**： Access 2013、 Office 2013

创建一个删除查询，用于从 [FROM](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/from-clause-microsoft-access-sql) 子句中列出的一个或多个表中删除满足 [WHERE](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/where-clause-microsoft-access-sql) 子句的记录。

## <a name="syntax"></a>语法

删除\[*表*。\* \] *TABLE* WHERE*条件*

DELETE 语句包含以下部分：

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
<td><p>从中删除记录的表的名称，可选。</p></td>
</tr>
<tr class="even">
<td><p><em>table</em></p></td>
<td><p>从中删除记录的表的名称。</p></td>
</tr>
<tr class="odd">
<td><p><em>criteria</em></p></td>
<td><p>表达式，用于确定要删除哪些记录。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

希望删除多个记录时，DELETE 语句特别有用。

要从数据库中删除整个表，可以使用带有 **DROP** 语句的 [Execute](drop-statement-microsoft-access-sql.md) 方法。但是，如果删除表，表的结构就会丢失；而使用 DELETE 语句时，只会删除表中的数据，表的结构和所有表属性（如字段属性和索引）将保持不变。

可以使用 DELETE 从与其他表存在一对多关系的表中删除记录。

删除查询将删除整个记录，而不仅仅删除特定字段中的数据。

> [!IMPORTANT]
> - 使用删除查询删除记录后，无法取消该操作。如果要知道删除了哪些记录，先检查使用相同条件的选择查询的结果，然后运行删除查询。
> - 不论什么时候都要维护数据的备份。如果错删了记录，还可以从备份中检索这些记录。

## <a name="example"></a>示例

本例删除职务为 Trainee 的雇员的所有记录。当 FROM 子句中仅包含一个表时，您不必在 DELETE 语句中列出该表的名称。

```vb
    Sub DeleteX() 
     
        Dim dbs As Database, rst As Recordset 
     
        ' Modify this line to include the path to Northwind 
        ' on your computer. 
        Set dbs = OpenDatabase("Northwind.mdb") 
     
        ' Delete employee records where title is Trainee.     
        dbs.Execute "DELETE * FROM " _ 
            & "Employees WHERE Title = 'Trainee';" 
         
        dbs.Close 
     
    End Sub
```
