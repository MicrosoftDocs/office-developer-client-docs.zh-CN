---
title: UNION 操作 (Microsoft Access SQL)
TOCTitle: UNION operation (Microsoft Access SQL)
ms:assetid: a5139921-51e5-7d96-74e3-11c3fd5f7eaa
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821131(v=office.15)
ms:contentKeyID: 48546826
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- jetsql40.chm5277582
dev_langs:
- sql
f1_categories:
- Office.Version=v15
localization_priority: Priority
ms.openlocfilehash: f842e662f2576d8aab5f3857877f45e380d3d3b0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32314698"
---
# <a name="union-operation-microsoft-access-sql"></a>UNION 操作 (Microsoft Access SQL)

**适用于**：Access 2013、Office 2013

创建联合查询，该查询将两个或两个以上的独立查询或表的结果组合在一起。

## <a name="syntax"></a>语法

\[TABLE\] *query1* UNION \[ALL\] \[TABLE\] *query2* \[UNION \[ALL\] \[TABLE\] *queryn* \[ … \]\]

合并操作包含以下部分：

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
<td><p><em>query1-n</em></p></td>
<td><p>一个 SELECT 语句、存储查询的名称或在 TABLE 关键字后面的存储表的名称。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

可在单个合并操作中任意合并两个或多个查询的结果、表和 SELECT 语句。以下示例合并名为新建账户的现有表和 SELECT 语句：

```sql
TABLE [New Accounts] UNION ALL 
SELECT * 
FROM Customers 
WHERE OrderAmount > 1000;
```

默认情况下，使用 UNION 操作时不会返回重复的记录；但是，可以包含 [ALL](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/all-distinct-distinctrow-top-predicates-microsoft-access-sql) 谓词以确保返回所有记录。这样也会使查询运行得更快。

在 UNION 操作中的所有查询必须请求相同数量的字段；但是，这些字段不必都具有相同的大小或数据类型。

仅在第一个 SELECT 语句中使用别名，因为在任何其他语句中，别名将被忽略。在 ORDER BY 子句中，通过字段在第一个 SELECT 语句中的名称来引用字段。

> [!NOTE]
> - 可以在每个 *query* 参数中使用 [GROUP BY](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/group-by-clause-microsoft-access-sql) 或 [HAVING](https://docs.microsoft.com/office/vba/access/concepts/structured-query-language/having-clause-microsoft-access-sql) 子句，以便对返回的数据进行分组。
> - 可以在最后一个 *query* 参数的末尾使用 [ORDER BY](https://docs.microsoft.com/office/vba/access/concepts/structured-query-language/order-by-clause-microsoft-access-sql) 子句，以便按指定顺序显示返回数据。

## <a name="example"></a>示例

此示例检索巴西所有供应商和客户的名称和城市。 它调用 EnumFields 过程，你可以在 SELECT 语句示例中找到该过程。

```vb
    Sub UnionX() 
     
        Dim dbs As Database, rst As Recordset 
     
        ' Modify this line to include the path to Northwind 
        ' on your computer. 
        Set dbs = OpenDatabase("Northwind.mdb") 
         
        ' Retrieve the names and cities of all suppliers  
        ' and customers in Brazil. 
        Set rst = dbs.OpenRecordset("SELECT CompanyName," _ 
            & " City FROM Suppliers" _ 
            & " WHERE Country = 'Brazil' UNION" _ 
            & " SELECT CompanyName, City FROM Customers" _ 
            & " WHERE Country = 'Brazil';") 
         
        ' Populate the Recordset. 
        rst.MoveLast 
         
        ' Call EnumFields to print the contents of the  
        ' Recordset. Pass the Recordset object and desired 
        ' field width. 
        EnumFields rst, 12 
     
        dbs.Close 
     
    End Sub
```
