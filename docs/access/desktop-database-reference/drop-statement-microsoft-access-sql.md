---
title: DROP 语句 (Microsoft Access SQL)
TOCTitle: DROP Statement (Microsoft Access SQL)
ms:assetid: a8c79c35-22da-2e6d-88b5-620eb481bb61
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821409(v=office.15)
ms:contentKeyID: 48546907
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3fc43547d6b9b744e004d44fff14b3fe82360732
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467373"
---
# <a name="drop-statement-microsoft-access-sql"></a><span data-ttu-id="eb74b-102">DROP 语句 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="eb74b-102">DROP Statement (Microsoft Access SQL)</span></span>

<span data-ttu-id="eb74b-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="eb74b-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="eb74b-104">删除数据库中现有的表、过程或视图，或者删除表中现有的索引。</span><span class="sxs-lookup"><span data-stu-id="eb74b-104">Deletes an existing table, procedure, or view from a database, or deletes an existing index from a table.</span></span>

> [!NOTE]
> <span data-ttu-id="eb74b-p101">[!注释] Microsoft Access 数据库引擎不支持将 DROP 或任何 DDL 语句用于非 Microsoft Access 数据库引擎数据库。可以改用 **Delete** 方法。</span><span class="sxs-lookup"><span data-stu-id="eb74b-p101">The Microsoft Access database engine does not support the use of DROP, or any of the DDL statements, with non-Microsoft Access database engine databases. Use the DAO **Delete** method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="eb74b-107">语法</span><span class="sxs-lookup"><span data-stu-id="eb74b-107">Syntax</span></span>

<span data-ttu-id="eb74b-108">DROP {TABLE *table* | INDEX *index* ON *table* | PROCEDURE *procedure* | VIEW *view*}</span><span class="sxs-lookup"><span data-stu-id="eb74b-108">DROP {TABLE *table* | INDEX *index* ON *table* | PROCEDURE *procedure* | VIEW *view*}</span></span>

<span data-ttu-id="eb74b-109">DROP 语句包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="eb74b-109">The DROP statement has these parts:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="eb74b-110">部分</span><span class="sxs-lookup"><span data-stu-id="eb74b-110">Part</span></span></p></th>
<th><p><span data-ttu-id="eb74b-111">说明</span><span class="sxs-lookup"><span data-stu-id="eb74b-111">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb74b-112"><em>table</em></span><span class="sxs-lookup"><span data-stu-id="eb74b-112"><em>table</em></span></span></p></td>
<td><p><span data-ttu-id="eb74b-113">要删除的表的名称，或者要从中删除索引的表的名称。</span><span class="sxs-lookup"><span data-stu-id="eb74b-113">The name of the table to be deleted or the table from which an index is to be deleted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb74b-114"><em>procedure</em></span><span class="sxs-lookup"><span data-stu-id="eb74b-114"><em>procedure</em></span></span></p></td>
<td><p><span data-ttu-id="eb74b-115">要删除的过程的名称。</span><span class="sxs-lookup"><span data-stu-id="eb74b-115">The name of the procedure to be deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb74b-116"><em>view</em></span><span class="sxs-lookup"><span data-stu-id="eb74b-116"><em>view</em></span></span></p></td>
<td><p><span data-ttu-id="eb74b-117">要删除的视图的名称。</span><span class="sxs-lookup"><span data-stu-id="eb74b-117">The name of the view to be deleted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb74b-118"><em>index</em></span><span class="sxs-lookup"><span data-stu-id="eb74b-118"><em>index</em></span></span></p></td>
<td><p><span data-ttu-id="eb74b-119">要从 <em>table</em> 中删除的索引的名称。</span><span class="sxs-lookup"><span data-stu-id="eb74b-119">The name of the index to be deleted from <em>table.</em></span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="eb74b-120">说明</span><span class="sxs-lookup"><span data-stu-id="eb74b-120">Remarks</span></span>

<span data-ttu-id="eb74b-121">在删除表或从表中删除索引之前，必须先关闭该表。</span><span class="sxs-lookup"><span data-stu-id="eb74b-121">You must close the table before you can delete it or remove an index from it.</span></span>

<span data-ttu-id="eb74b-122">还可以使用 [ALTER TABLE](alter-table-statement-microsoft-access-sql.md) 语句从表中删除索引。</span><span class="sxs-lookup"><span data-stu-id="eb74b-122">You can also use [ALTER TABLE](alter-table-statement-microsoft-access-sql.md) to delete an index from a table.</span></span>

<span data-ttu-id="eb74b-p102">可以使用 [CREATE TABLE](create-table-statement-microsoft-access-sql.md) 创建一个表，用 [CREATE INDEX](create-index-statement-microsoft-access-sql.md) 或者 ALTER TABLE 语句创建一个索引。若要对表进行修改，请使用 ALTER TABLE 语句。</span><span class="sxs-lookup"><span data-stu-id="eb74b-p102">You can use [CREATE TABLE](create-table-statement-microsoft-access-sql.md) to create a table and [CREATE INDEX](create-index-statement-microsoft-access-sql.md) or ALTER TABLE to create an index. To modify a table, use ALTER TABLE.</span></span>

## <a name="example"></a><span data-ttu-id="eb74b-125">示例</span><span class="sxs-lookup"><span data-stu-id="eb74b-125">Example</span></span>

<span data-ttu-id="eb74b-126">以下示例假定 Northwind 数据库的 Employees 表中存在一个假想的 NewIndex 索引。</span><span class="sxs-lookup"><span data-stu-id="eb74b-126">The following example assumes the existence of a hypothetical NewIndex index on the Employees table in the Northwind database.</span></span>

<span data-ttu-id="eb74b-127">以下示例从 Employees 表中删除 MyIndex 索引。</span><span class="sxs-lookup"><span data-stu-id="eb74b-127">This example deletes the index MyIndex from the Employees table.</span></span>

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

<span data-ttu-id="eb74b-128">以下示例从数据库中删除 Employees 表。</span><span class="sxs-lookup"><span data-stu-id="eb74b-128">This example deletes the Employees table from the database.</span></span>

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
