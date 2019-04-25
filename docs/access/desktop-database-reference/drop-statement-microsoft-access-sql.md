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
# <a name="drop-statement-microsoft-access-sql"></a><span data-ttu-id="88cdb-102">DROP 语句 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="88cdb-102">DROP Statement (Microsoft Access SQL)</span></span>

<span data-ttu-id="88cdb-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="88cdb-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="88cdb-104">从数据库中删除现有表、过程或视图，或从表中删除现有索引。</span><span class="sxs-lookup"><span data-stu-id="88cdb-104">Deletes an existing table, procedure, or view from a database, or deletes an existing index from a table.</span></span>

> [!NOTE]
> <span data-ttu-id="88cdb-p101">[!注释] Microsoft Access 数据库引擎不支持将 DROP 或任何 DDL 语句用于非 Microsoft Access 数据库引擎数据库。可以改用 **Delete** 方法。</span><span class="sxs-lookup"><span data-stu-id="88cdb-p101">The Microsoft Access database engine does not support the use of DROP, or any of the DDL statements, with non-Microsoft Access database engine databases. Use the DAO **Delete** method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="88cdb-107">语法</span><span class="sxs-lookup"><span data-stu-id="88cdb-107">Syntax</span></span>

<span data-ttu-id="88cdb-108">DROP {TABLE *table* | INDEX *index* ON *table* | PROCEDURE *procedure* | VIEW *view*}</span><span class="sxs-lookup"><span data-stu-id="88cdb-108">DROP {TABLE *table* | INDEX *index* ON *table* | PROCEDURE *procedure* | VIEW *view*}</span></span>

<span data-ttu-id="88cdb-109">DROP 语句包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="88cdb-109">The DROP statement has these parts:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="88cdb-110">Part</span><span class="sxs-lookup"><span data-stu-id="88cdb-110">Part</span></span></p></th>
<th><p><span data-ttu-id="88cdb-111">说明</span><span class="sxs-lookup"><span data-stu-id="88cdb-111">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88cdb-112"><em>table</em></span><span class="sxs-lookup"><span data-stu-id="88cdb-112"><em>table</em></span></span></p></td>
<td><p><span data-ttu-id="88cdb-113">要删除的表或要从中删除索引的表的名称。</span><span class="sxs-lookup"><span data-stu-id="88cdb-113">The name of the table to be deleted or the table from which an index is to be deleted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88cdb-114"><em>procedure</em></span><span class="sxs-lookup"><span data-stu-id="88cdb-114"><em>procedure</em></span></span></p></td>
<td><p><span data-ttu-id="88cdb-115">要删除的过程的名称。</span><span class="sxs-lookup"><span data-stu-id="88cdb-115">The name of the procedure to be deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88cdb-116"><em>view</em></span><span class="sxs-lookup"><span data-stu-id="88cdb-116"><em>view</em></span></span></p></td>
<td><p><span data-ttu-id="88cdb-117">要删除的视图的名称。</span><span class="sxs-lookup"><span data-stu-id="88cdb-117">The name of the view to be deleted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88cdb-118"><em>index</em></span><span class="sxs-lookup"><span data-stu-id="88cdb-118"><em>index</em></span></span></p></td>
<td><p><span data-ttu-id="88cdb-119">要从<em>表</em>中删除的索引的名称。</span><span class="sxs-lookup"><span data-stu-id="88cdb-119">The name of the index to be deleted from <em>table.</em></span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="88cdb-120">说明</span><span class="sxs-lookup"><span data-stu-id="88cdb-120">Remarks</span></span>

<span data-ttu-id="88cdb-121">必须先关闭表才可删除该表或从其中删除索引。</span><span class="sxs-lookup"><span data-stu-id="88cdb-121">You must close the table before you can delete it or remove an index from it.</span></span>

<span data-ttu-id="88cdb-122">还可以使用 [ALTER TABLE](alter-table-statement-microsoft-access-sql.md) 语句从表中删除索引。</span><span class="sxs-lookup"><span data-stu-id="88cdb-122">You can also use [ALTER TABLE](alter-table-statement-microsoft-access-sql.md) to delete an index from a table.</span></span>

<span data-ttu-id="88cdb-p102">可以使用 [CREATE TABLE](create-table-statement-microsoft-access-sql.md) 创建一个表，用 [CREATE INDEX](create-index-statement-microsoft-access-sql.md) 或者 ALTER TABLE 语句创建一个索引。若要对表进行修改，请使用 ALTER TABLE 语句。</span><span class="sxs-lookup"><span data-stu-id="88cdb-p102">You can use [CREATE TABLE](create-table-statement-microsoft-access-sql.md) to create a table and [CREATE INDEX](create-index-statement-microsoft-access-sql.md) or ALTER TABLE to create an index. To modify a table, use ALTER TABLE.</span></span>

## <a name="example"></a><span data-ttu-id="88cdb-125">示例</span><span class="sxs-lookup"><span data-stu-id="88cdb-125">Example</span></span>

<span data-ttu-id="88cdb-126">以下示例假定 Northwind 数据库的 Employees 表中存在一个假想的 NewIndex 索引。</span><span class="sxs-lookup"><span data-stu-id="88cdb-126">The following example assumes the existence of a hypothetical NewIndex index on the Employees table in the Northwind database.</span></span>

<span data-ttu-id="88cdb-127">以下示例从 Employees 表中删除 MyIndex 索引。</span><span class="sxs-lookup"><span data-stu-id="88cdb-127">This example deletes the index MyIndex from the Employees table.</span></span>

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

<span data-ttu-id="88cdb-128">以下示例从数据库中删除 Employees 表。</span><span class="sxs-lookup"><span data-stu-id="88cdb-128">This example deletes the Employees table from the database.</span></span>

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
