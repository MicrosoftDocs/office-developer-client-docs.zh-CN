---
title: UNION 操作 (Microsoft Access SQL)
TOCTitle: UNION Operation (Microsoft Access SQL)
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
ms.openlocfilehash: 63ff883f35dabbbd69e1bf144eb32016f303c7ef
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25879107"
---
# <a name="union-operation-microsoft-access-sql"></a>UNION 操作 (Microsoft Access SQL)


**适用于**： Access 2013、 Office 2013

创建联合查询，该查询将两个或两个以上的独立查询或表的结果组合在一起。

## <a name="syntax"></a>语法

\[表\] *query1*联合\[所有\]\[表\] *query2* \[联合\[所有\]\[表\] *queryn* \[ ... \]\]

UNION 操作包含以下部分：

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
<td><p><em>query1-n</em></p></td>
<td><p>一个 SELECT 语句、存储查询的名称或在 TABLE 关键字后面的存储表的名称。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

可以在单个 UNION 操作中以任何组合方式合并两个或两个以上的查询、表和 SELECT 语句的结果。下面的示例将一个名为 New Accounts 的现有表和一个 SELECT 语句进行合并：

```sql
TABLE [New Accounts] UNION ALL 
SELECT * 
FROM Customers 
WHERE OrderAmount > 1000;
```

默认情况下，使用 UNION 操作时不会返回重复的记录；但是，可以包含 [ALL](https://msdn.microsoft.com/library/ff195711\(v=office.15\)) 谓词以确保返回所有记录。这样也会使查询运行得更快。

在 UNION 操作中的所有查询必须请求相同数量的字段；但是，这些字段不必都具有相同的大小或数据类型。

请只在第一个 SELECT 语句中使用别名，因为别名在其他语句中会被忽略。在 ORDER BY 子句中，请根据第一个 SELECT 语句中使用的字段名来引用该字段。


> [!NOTE]
> <UL>
> <LI>
> <P>您可以使用<A href="https://msdn.microsoft.com/library/ff837271(v=office.15)">GROUP BY</A>或<A href="https://msdn.microsoft.com/library/ff193795(v=office.15)">HAVING</A>子句中每个<EM>query</EM>参数返回的数据进行分组。</P>
> <LI>
> <P>可以使用在最后一个<EM>query</EM>参数的末尾的<A href="https://msdn.microsoft.com/library/ff198293(v=office.15)">ORDER BY</A>子句中指定的顺序显示返回的数据。</P></LI></UL>



## <a name="example"></a>示例

以下示例检索巴西的所有供应商和客户的名称和所在城市。

以下示例调用 EnumFields 过程，您可以在 SELECT 语句示例中找到该过程。

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
