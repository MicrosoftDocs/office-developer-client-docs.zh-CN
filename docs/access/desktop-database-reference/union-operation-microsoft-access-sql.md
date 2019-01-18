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
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28716248"
---
# <a name="union-operation-microsoft-access-sql"></a><span data-ttu-id="e067e-102">UNION 操作 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="e067e-102">UNION operation (Microsoft Access SQL)</span></span>

<span data-ttu-id="e067e-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="e067e-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="e067e-104">创建联合查询，该查询将两个或两个以上的独立查询或表的结果组合在一起。</span><span class="sxs-lookup"><span data-stu-id="e067e-104">Creates a union query, which combines the results of two or more independent queries or tables.</span></span>

## <a name="syntax"></a><span data-ttu-id="e067e-105">语法</span><span class="sxs-lookup"><span data-stu-id="e067e-105">Syntax</span></span>

<span data-ttu-id="e067e-106">\[表\] *query1*联合\[所有\]\[表\] *query2* \[联合\[所有\]\[表\] *queryn* \[ ...</span><span class="sxs-lookup"><span data-stu-id="e067e-106">\[TABLE\] *query1* UNION \[ALL\] \[TABLE\] *query2* \[UNION \[ALL\] \[TABLE\] *queryn* \[ …</span></span> <span data-ttu-id="e067e-107">\]\]</span><span class="sxs-lookup"><span data-stu-id="e067e-107"></span></span>

<span data-ttu-id="e067e-108">UNION 操作包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="e067e-108">The UNION operation has these parts:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e067e-109">部分</span><span class="sxs-lookup"><span data-stu-id="e067e-109">Part</span></span></p></th>
<th><p><span data-ttu-id="e067e-110">说明</span><span class="sxs-lookup"><span data-stu-id="e067e-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e067e-111"><em>query1-n</em></span><span class="sxs-lookup"><span data-stu-id="e067e-111"><em>query1-n</em></span></span></p></td>
<td><p><span data-ttu-id="e067e-112">一个 SELECT 语句、存储查询的名称或在 TABLE 关键字后面的存储表的名称。</span><span class="sxs-lookup"><span data-stu-id="e067e-112">A SELECT statement, the name of a stored query, or the name of a stored table preceded by the TABLE keyword.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="e067e-113">注解</span><span class="sxs-lookup"><span data-stu-id="e067e-113">Remarks</span></span>

<span data-ttu-id="e067e-p102">可以在单个 UNION 操作中以任何组合方式合并两个或两个以上的查询、表和 SELECT 语句的结果。下面的示例将一个名为 New Accounts 的现有表和一个 SELECT 语句进行合并：</span><span class="sxs-lookup"><span data-stu-id="e067e-p102">You can merge the results of two or more queries, tables, and SELECT statements, in any combination, in a single UNION operation. The following example merges an existing table named New Accounts and a SELECT statement:</span></span>

```sql
TABLE [New Accounts] UNION ALL 
SELECT * 
FROM Customers 
WHERE OrderAmount > 1000;
```

<span data-ttu-id="e067e-p103">默认情况下，使用 UNION 操作时不会返回重复的记录；但是，可以包含 [ALL](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/all-distinct-distinctrow-top-predicates-microsoft-access-sql) 谓词以确保返回所有记录。这样也会使查询运行得更快。</span><span class="sxs-lookup"><span data-stu-id="e067e-p103">By default, no duplicate records are returned when you use a UNION operation; however, you can include the [ALL](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/all-distinct-distinctrow-top-predicates-microsoft-access-sql) predicate to ensure that all records are returned. This also makes the query run faster.</span></span>

<span data-ttu-id="e067e-118">在 UNION 操作中的所有查询必须请求相同数量的字段；但是，这些字段不必都具有相同的大小或数据类型。</span><span class="sxs-lookup"><span data-stu-id="e067e-118">All queries in a UNION operation must request the same number of fields; however, the fields do not have to be of the same size or data type.</span></span>

<span data-ttu-id="e067e-p104">请只在第一个 SELECT 语句中使用别名，因为别名在其他语句中会被忽略。在 ORDER BY 子句中，请根据第一个 SELECT 语句中使用的字段名来引用该字段。</span><span class="sxs-lookup"><span data-stu-id="e067e-p104">Use aliases only in the first SELECT statement because they are ignored in any others. In the ORDER BY clause, refer to fields by what they are called in the first SELECT statement.</span></span>

> [!NOTE]
> - <span data-ttu-id="e067e-121">您可以使用[GROUP BY](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/group-by-clause-microsoft-access-sql)或[HAVING](https://docs.microsoft.com/office/vba/access/concepts/structured-query-language/having-clause-microsoft-access-sql)子句中每个*query*参数返回的数据进行分组。</span><span class="sxs-lookup"><span data-stu-id="e067e-121">You can use a [GROUP BY](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/group-by-clause-microsoft-access-sql) or [HAVING](https://docs.microsoft.com/office/vba/access/concepts/structured-query-language/having-clause-microsoft-access-sql) clause in each *query* argument to group the returned data.</span></span>
> - <span data-ttu-id="e067e-122">可以使用在最后一个*query*参数的末尾的[ORDER BY](https://docs.microsoft.com/office/vba/access/concepts/structured-query-language/order-by-clause-microsoft-access-sql)子句中指定的顺序显示返回的数据。</span><span class="sxs-lookup"><span data-stu-id="e067e-122">You can use an [ORDER BY](https://docs.microsoft.com/office/vba/access/concepts/structured-query-language/order-by-clause-microsoft-access-sql) clause at the end of the last *query* argument to display the returned data in a specified order.</span></span>

## <a name="example"></a><span data-ttu-id="e067e-123">示例</span><span class="sxs-lookup"><span data-stu-id="e067e-123">Example</span></span>

<span data-ttu-id="e067e-124">以下示例检索巴西的所有供应商和客户的名称和所在城市。</span><span class="sxs-lookup"><span data-stu-id="e067e-124">This example retrieves the names and cities of all suppliers and customers in Brazil.</span></span> <span data-ttu-id="e067e-125">它调用 EnumFields 过程，您可以在 SELECT 语句示例中找到。</span><span class="sxs-lookup"><span data-stu-id="e067e-125">It calls the EnumFields procedure, which you can find in the SELECT statement example.</span></span>

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
