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
# <a name="update-statement-microsoft-access-sql"></a><span data-ttu-id="2151c-102">UPDATE 语句 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="2151c-102">UPDATE Statement (Microsoft Access SQL)</span></span>

<span data-ttu-id="2151c-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="2151c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="2151c-104">创建一个更新查询，以便基于特定的条件更改指定表的字段值。</span><span class="sxs-lookup"><span data-stu-id="2151c-104">Creates an update query that changes values in fields in a specified table based on specified criteria.</span></span>

## <a name="syntax"></a><span data-ttu-id="2151c-105">语法</span><span class="sxs-lookup"><span data-stu-id="2151c-105">Syntax</span></span>

<span data-ttu-id="2151c-106">UPDATE *table* SET *newvalue* WHERE *criteria*;</span><span class="sxs-lookup"><span data-stu-id="2151c-106">UPDATE *table*
    SET *newvalue*
    WHERE *criteria*;</span></span>

<span data-ttu-id="2151c-107">UPDATE 语句包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="2151c-107">The UPDATE statement has these parts:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="2151c-108">Part</span><span class="sxs-lookup"><span data-stu-id="2151c-108">Part</span></span></p></th>
<th><p><span data-ttu-id="2151c-109">说明</span><span class="sxs-lookup"><span data-stu-id="2151c-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2151c-110"><em>table</em></span><span class="sxs-lookup"><span data-stu-id="2151c-110"><em>table</em></span></span></p></td>
<td><p><span data-ttu-id="2151c-111">表的名称，此表中包含要修改的数据。</span><span class="sxs-lookup"><span data-stu-id="2151c-111">The name of the table containing the data you want to modify.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2151c-112"><em>newvalue</em></span><span class="sxs-lookup"><span data-stu-id="2151c-112"><em>newValue</em></span></span></p></td>
<td><p><span data-ttu-id="2151c-113">表达式，确定将哪些值插入已更新的记录中的特定字段。</span><span class="sxs-lookup"><span data-stu-id="2151c-113">An expression that determines the value to be inserted into a particular field in the updated records.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2151c-114"><em>criteria</em></span><span class="sxs-lookup"><span data-stu-id="2151c-114"><em>criteria</em></span></span></p></td>
<td><p><span data-ttu-id="2151c-115">表达式，用来确定将更新哪些记录。</span><span class="sxs-lookup"><span data-stu-id="2151c-115">An expression that determines which records will be updated.</span></span> <span data-ttu-id="2151c-116">只有满足该表达式的记录才会被更新。</span><span class="sxs-lookup"><span data-stu-id="2151c-116">Only records that satisfy the expression are updated.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="2151c-117">说明</span><span class="sxs-lookup"><span data-stu-id="2151c-117">Remarks</span></span>

<span data-ttu-id="2151c-118">如果要更改许多记录，或者要更改的记录位于多个表中，UPDATE 则尤其有用。</span><span class="sxs-lookup"><span data-stu-id="2151c-118">UPDATE is especially useful when you want to change many records or when the records that you want to change are in multiple tables.</span></span>

<span data-ttu-id="2151c-p102">可以同时更改若干字段。以下示例将英国货主的“采购量”值增加 10％，“运费”值增加 3％：</span><span class="sxs-lookup"><span data-stu-id="2151c-p102">You can change several fields at the same time. The following example increases the Order Amount values by 10 percent and the Freight values by 3 percent for shippers in the United Kingdom:</span></span>

```sql
UPDATE Orders 
SET OrderAmount = OrderAmount * 1.1, 
Freight = Freight * 1.03 
WHERE ShipCountry = 'UK';
```


> [!IMPORTANT]
- <span data-ttu-id="2151c-p103">UPDATE 不会生成结果集。而且，使用更新查询来更新记录后，您不能取消该操作。如果希望了解已更新哪些记录，请先检查使用相同条件的选择查询的结果，然后再运行更新查询。</span><span class="sxs-lookup"><span data-stu-id="2151c-p103">UPDATE does not generate a result set. Also, after you update records using an update query, you cannot undo the operation. If you want to know which records were updated, first examine the results of a select query that uses the same criteria, and then run the update query.</span></span>
- <span data-ttu-id="2151c-124">随时维护数据的备份副本。</span><span class="sxs-lookup"><span data-stu-id="2151c-124">Maintain backup copies of your data at all times.</span></span> <span data-ttu-id="2151c-125">如果更新了错误的记录，可以从备份副本检索它们。</span><span class="sxs-lookup"><span data-stu-id="2151c-125">If you update the wrong records, you can retrieve them from your backup copies.</span></span>



## <a name="example"></a><span data-ttu-id="2151c-126">示例</span><span class="sxs-lookup"><span data-stu-id="2151c-126">Example</span></span>

<span data-ttu-id="2151c-127">本示例针对当前 ReportsTo 字段值为 2 的所有员工记录，将 ReportsTo 字段值更改为 5。</span><span class="sxs-lookup"><span data-stu-id="2151c-127">This example changes values in the ReportsTo field to 5 for all employee records that currently have ReportsTo values of 2.</span></span>

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
