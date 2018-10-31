---
title: 选择。INTO 语句 (Microsoft Access SQL)
TOCTitle: SELECT.INTO statement (Microsoft Access SQL)
ms:assetid: 29f3bd55-52f5-a36e-4e33-4b3499c6ce8d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192059(v=office.15)
ms:contentKeyID: 48543897
ms.date: 10/18/2018
mtps_version: v=office.15
ms.openlocfilehash: 1c05679994cfd98fdc5d6ffb389df00c2f5c9b94
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25861993"
---
# <a name="selectinto-statement-microsoft-access-sql"></a><span data-ttu-id="c8214-102">选择。INTO 语句 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="c8214-102">SELECT.INTO statement (Microsoft Access SQL)</span></span>

<span data-ttu-id="c8214-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="c8214-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="c8214-104">创建生成表查询。</span><span class="sxs-lookup"><span data-stu-id="c8214-104">Creates a make-table query.</span></span>

## <a name="syntax"></a><span data-ttu-id="c8214-105">语法</span><span class="sxs-lookup"><span data-stu-id="c8214-105">Syntax</span></span>

<span data-ttu-id="c8214-106">SELECT *field1*\[， *field2*\[，...\] \] INTO *newtable* \[IN *externaldatabase* \] *源*中</span><span class="sxs-lookup"><span data-stu-id="c8214-106">SELECT *field1*\[, *field2*\[, …\]\] INTO *newtable* \[IN *externaldatabase*\] FROM *source*</span></span>

<span data-ttu-id="c8214-107">SELECT...INTO 语句包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="c8214-107">The SELECT…INTO statement has these parts:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="c8214-108">部分</span><span class="sxs-lookup"><span data-stu-id="c8214-108">Part</span></span></p></th>
<th><p><span data-ttu-id="c8214-109">说明</span><span class="sxs-lookup"><span data-stu-id="c8214-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8214-110"><em>field1</em>、<em>field2</em></span><span class="sxs-lookup"><span data-stu-id="c8214-110"><em>field1</em>, <em>field2</em></span></span></p></td>
<td><p><span data-ttu-id="c8214-111">要复制到新表中的字段的名称。</span><span class="sxs-lookup"><span data-stu-id="c8214-111">The name of the fields to be copied into the new table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8214-112"><em>newtable</em></span><span class="sxs-lookup"><span data-stu-id="c8214-112"><em>newtable</em></span></span></p></td>
<td><p><span data-ttu-id="c8214-p101">要创建的表的名称。它必须符合标准命名约定。如果 <em>newtable</em> 和现有表同名，会发生一个可捕捉的错误。</span><span class="sxs-lookup"><span data-stu-id="c8214-p101">The name of the table to be created. It must conform to standard naming conventions. If <em>newtable</em> is the same as the name of an existing table, a trappable error occurs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8214-116"><em>externaldatabase</em></span><span class="sxs-lookup"><span data-stu-id="c8214-116"><em>externaldatabase</em></span></span></p></td>
<td><p><span data-ttu-id="c8214-p102">外部数据库的路径。有关路径的说明，请参阅 <a href="https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/in-clause-microsoft-access-sql">IN</a> 子句。</span><span class="sxs-lookup"><span data-stu-id="c8214-p102">The path to an external database. For a description of the path, see the <a href="https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/in-clause-microsoft-access-sql">IN</a> clause.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8214-119"><em>source</em></span><span class="sxs-lookup"><span data-stu-id="c8214-119"><em>source</em></span></span></p></td>
<td><p><span data-ttu-id="c8214-p103">从中选择记录的现有表的名称。它可以是单个或多个表或查询。</span><span class="sxs-lookup"><span data-stu-id="c8214-p103">The name of the existing table from which records are selected. This can be single or multiple tables or a query.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="c8214-122">说明</span><span class="sxs-lookup"><span data-stu-id="c8214-122">Remarks</span></span>

<span data-ttu-id="c8214-p104">可以通过生成表查询来存档记录，或制作表的备份副本，或者将副本导出到其他数据库，或作为某个特定时间段的数据的报表产生基础。例如，可以通过每个月运行相同的生成表查询来生成一个月销售区域报表。</span><span class="sxs-lookup"><span data-stu-id="c8214-p104">You can use make-table queries to archive records, make backup copies of your tables, or make copies to export to another database or to use as a basis for reports that display data for a particular time period. For example, you could produce a Monthly Sales by Region report by running the same make-table query each month.</span></span>

> [!NOTE]
> - <span data-ttu-id="c8214-p105">您可能希望定义新表的主键。创建表时，新表中的字段会继承查询的基表中每个字段的数据类型和字段大小，但不会传输其他字段或表属性。</span><span class="sxs-lookup"><span data-stu-id="c8214-p105">You may want to define a primary key for the new table. When you create the table, the fields in the new table inherit the data type and field size of each field in the query's underlying tables, but no other field or table properties are transferred.</span></span>
> - <span data-ttu-id="c8214-127">若要将数据添加到现有表中，请使用 [INSERT INTO](insert-into-statement-microsoft-access-sql.md) 语句，而不用创建追加查询。</span><span class="sxs-lookup"><span data-stu-id="c8214-127">To add data to an existing table, use the [INSERT INTO](insert-into-statement-microsoft-access-sql.md) statement instead to create an append query.</span></span>
> - <span data-ttu-id="c8214-128">若要在运行生成表查询之前查找出将要选择哪些记录，请先检查使用相同选择条件的 [SELECT](select-statement-microsoft-access-sql.md) 语句的结果。</span><span class="sxs-lookup"><span data-stu-id="c8214-128">To find out which records will be selected before you run the make-table query, first examine the results of a [SELECT](select-statement-microsoft-access-sql.md) statement that uses the same selection criteria.</span></span>



## <a name="example"></a><span data-ttu-id="c8214-129">示例</span><span class="sxs-lookup"><span data-stu-id="c8214-129">Example</span></span>

<span data-ttu-id="c8214-130">以下示例选择 Employees 表中的所有记录，并将它们复制到名为 Emp Backup 的新表中。</span><span class="sxs-lookup"><span data-stu-id="c8214-130">This example selects all records in the Employees table and copies them into a new table named Emp Backup.</span></span>

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
