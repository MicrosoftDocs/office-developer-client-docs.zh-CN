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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32294041"
---
# <a name="delete-statement-microsoft-access-sql"></a><span data-ttu-id="10157-102">DELETE 语句 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="10157-102">DELETE Statement (Microsoft Access SQL)</span></span>

<span data-ttu-id="10157-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="10157-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="10157-104">创建一个删除查询，用于从 [FROM](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/from-clause-microsoft-access-sql) 子句中列出的一个或多个表中删除满足 [WHERE](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/where-clause-microsoft-access-sql) 子句的记录。</span><span class="sxs-lookup"><span data-stu-id="10157-104">Creates a delete query that removes records from one or more of the tables listed in the [FROM](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/from-clause-microsoft-access-sql) clause that satisfy the [WHERE](https://docs.microsoft.com/office/vba/access/Concepts/Structured-Query-Language/where-clause-microsoft-access-sql) clause.</span></span>

## <a name="syntax"></a><span data-ttu-id="10157-105">语法</span><span class="sxs-lookup"><span data-stu-id="10157-105">Syntax</span></span>

<span data-ttu-id="10157-106">DELETE \[*table*.\*\] FROM *table* WHERE *criteria*</span><span class="sxs-lookup"><span data-stu-id="10157-106">DELETE [table.\*]
    FROM table
    WHERE criteria</span></span>

<span data-ttu-id="10157-107">DELETE 语句包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="10157-107">The DELETE statement has these parts:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="10157-108">Part</span><span class="sxs-lookup"><span data-stu-id="10157-108">Part</span></span></p></th>
<th><p><span data-ttu-id="10157-109">说明</span><span class="sxs-lookup"><span data-stu-id="10157-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="10157-110"><em>table</em></span><span class="sxs-lookup"><span data-stu-id="10157-110"><em>table</em></span></span></p></td>
<td><p><span data-ttu-id="10157-111">从中删除记录的表的可选名称。</span><span class="sxs-lookup"><span data-stu-id="10157-111">The optional name of the table from which records are deleted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10157-112"><em>table</em></span><span class="sxs-lookup"><span data-stu-id="10157-112"><em>table</em></span></span></p></td>
<td><p><span data-ttu-id="10157-113">从中删除记录的表的名称。</span><span class="sxs-lookup"><span data-stu-id="10157-113">The name of the table from which records are deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10157-114"><em>criteria</em></span><span class="sxs-lookup"><span data-stu-id="10157-114"><em>criteria</em></span></span></p></td>
<td><p><span data-ttu-id="10157-115">表达式，用于确定要删除哪些记录。</span><span class="sxs-lookup"><span data-stu-id="10157-115">An expression that determines which records to delete.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="10157-116">说明</span><span class="sxs-lookup"><span data-stu-id="10157-116">Remarks</span></span>

<span data-ttu-id="10157-117">要删除多条记录时，DELETE 非常有用。</span><span class="sxs-lookup"><span data-stu-id="10157-117">DELETE is especially useful when you want to delete many records.</span></span>

<span data-ttu-id="10157-p101">要从数据库中删除整个表，可以使用带有 **DROP** 语句的 [Execute](drop-statement-microsoft-access-sql.md) 方法。但是，如果删除表，表的结构就会丢失；而使用 DELETE 语句时，只会删除表中的数据，表的结构和所有表属性（如字段属性和索引）将保持不变。</span><span class="sxs-lookup"><span data-stu-id="10157-p101">To drop an entire table from the database, you can use the **Execute** method with a [DROP](drop-statement-microsoft-access-sql.md) statement. If you delete the table, however, the structure is lost. In contrast, when you use DELETE, only the data is deleted; the table structure and all of the table properties, such as field attributes and indexes, remain intact.</span></span>

<span data-ttu-id="10157-p102">可以使用 DELETE 从与其他表存在一对多关系的表中删除记录。</span><span class="sxs-lookup"><span data-stu-id="10157-p102">You can use DELETE to remove records from tables that are in a one-to-many relationship with other tables. Cascade delete operations cause the records in tables that are on the many side of the relationship to be deleted when the corresponding record in the one side of the relationship is deleted in the query. For example, in the relationship between the Customers and Orders tables, the Customers table is on the one side and the Orders table is on the many side of the relationship. Deleting a record from Customers results in the corresponding Orders records being deleted if the cascade delete option is specified.</span></span>

<span data-ttu-id="10157-p103">删除查询将删除整个记录，而不仅仅删除特定字段中的数据。</span><span class="sxs-lookup"><span data-stu-id="10157-p103">A delete query deletes entire records, not just data in specific fields. If you want to delete values in a specific field, create an update query that changes the values to **Null**.</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="10157-p104">使用删除查询删除记录后，无法取消该操作。如果要知道删除了哪些记录，先检查使用相同条件的选择查询的结果，然后运行删除查询。</span><span class="sxs-lookup"><span data-stu-id="10157-p104">After you remove records using a delete query, you cannot undo the operation. If you want to know which records were deleted, first examine the results of a select query that uses the same criteria, and then run the delete query.</span></span>
> - <span data-ttu-id="10157-p105">随时维护数据的备份副本。如果错误地删除了记录，可以从备份副本检索它们。</span><span class="sxs-lookup"><span data-stu-id="10157-p105">Maintain backup copies of your data at all times. If you delete the wrong records, you can retrieve them from your backup copies.</span></span>

## <a name="example"></a><span data-ttu-id="10157-131">示例</span><span class="sxs-lookup"><span data-stu-id="10157-131">Example</span></span>

<span data-ttu-id="10157-p106">本例删除职务为 Trainee 的雇员的所有记录。当 FROM 子句中仅包含一个表时，您不必在 DELETE 语句中列出该表的名称。</span><span class="sxs-lookup"><span data-stu-id="10157-p106">This example deletes all records for employees whose title is Trainee. When the FROM clause includes only one table, you do not have to list the table name in the DELETE statement.</span></span>

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
