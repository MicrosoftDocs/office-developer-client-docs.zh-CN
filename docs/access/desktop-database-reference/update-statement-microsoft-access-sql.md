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
# <a name="update-statement-microsoft-access-sql"></a><span data-ttu-id="d541f-102">UPDATE 语句 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="d541f-102">UPDATE statement (Microsoft Access SQL)</span></span>

<span data-ttu-id="d541f-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="d541f-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="d541f-104">创建一个更新查询，以便基于特定的条件更改指定表的字段值。</span><span class="sxs-lookup"><span data-stu-id="d541f-104">Creates an update query that changes values in fields in a specified table based on specified criteria.</span></span>

## <a name="syntax"></a><span data-ttu-id="d541f-105">语法</span><span class="sxs-lookup"><span data-stu-id="d541f-105">Syntax</span></span>

<span data-ttu-id="d541f-106">更新*表*设置*newvalue* WHERE*条件*;</span><span class="sxs-lookup"><span data-stu-id="d541f-106">UPDATE *table* SET *newvalue* WHERE *criteria*;</span></span>

<span data-ttu-id="d541f-107">UPDATE 语句包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="d541f-107">The UPDATE statement has these parts:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="d541f-108">部分</span><span class="sxs-lookup"><span data-stu-id="d541f-108">Part</span></span></p></th>
<th><p><span data-ttu-id="d541f-109">说明</span><span class="sxs-lookup"><span data-stu-id="d541f-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d541f-110"><em>table</em></span><span class="sxs-lookup"><span data-stu-id="d541f-110"><em>table</em></span></span></p></td>
<td><p><span data-ttu-id="d541f-111">表名，该表包含要修改的数据。</span><span class="sxs-lookup"><span data-stu-id="d541f-111">The name of the table containing the data you want to modify.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d541f-112"><em>newvalue</em></span><span class="sxs-lookup"><span data-stu-id="d541f-112"><em>newvalue</em></span></span></p></td>
<td><p><span data-ttu-id="d541f-113">表达式，该表达式确定将要插入到已更新记录的特定字段内的值。</span><span class="sxs-lookup"><span data-stu-id="d541f-113">An expression that determines the value to be inserted into a particular field in the updated records.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d541f-114"><em>criteria</em></span><span class="sxs-lookup"><span data-stu-id="d541f-114"><em>criteria</em></span></span></p></td>
<td><p><span data-ttu-id="d541f-p101">表达式，用来确定将更新哪些记录。只有满足该表达式的记录才会被更新。</span><span class="sxs-lookup"><span data-stu-id="d541f-p101">An expression that determines which records will be updated. Only records that satisfy the expression are updated.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="d541f-117">说明</span><span class="sxs-lookup"><span data-stu-id="d541f-117">Remarks</span></span>

<span data-ttu-id="d541f-118">当需要更改多个记录或者需要更改的记录存在于多个表中时，UPDATE 语句是最有用的。</span><span class="sxs-lookup"><span data-stu-id="d541f-118">UPDATE is especially useful when you want to change many records or when the records that you want to change are in multiple tables.</span></span>

<span data-ttu-id="d541f-p102">可以同时更改多个字段。下面的示例把英国货主的订货量的值增加百分之十，并且把运费的值增加百分之三。</span><span class="sxs-lookup"><span data-stu-id="d541f-p102">You can change several fields at the same time. The following example increases the Order Amount values by 10 percent and the Freight values by 3 percent for shippers in the United Kingdom:</span></span>

```sql
UPDATE Orders 
SET OrderAmount = OrderAmount * 1.1, 
Freight = Freight * 1.03 
WHERE ShipCountry = 'UK';
```


> [!IMPORTANT]
- <span data-ttu-id="d541f-p103">UPDATE 不会生成结果集。而且，使用更新查询来更新记录后，您不能取消该操作。如果希望了解已更新哪些记录，请先检查使用相同条件的选择查询的结果，然后再运行更新查询。</span><span class="sxs-lookup"><span data-stu-id="d541f-p103">UPDATE does not generate a result set. Also, after you update records using an update query, you cannot undo the operation. If you want to know which records were updated, first examine the results of a select query that uses the same criteria, and then run the update query.</span></span>
- <span data-ttu-id="d541f-p104">不论什么时候都要维护数据的备份。如果更新了错误记录，您可以从备份副本中检索这些记录。
</span><span class="sxs-lookup"><span data-stu-id="d541f-p104">Maintain backup copies of your data at all times. If you update the wrong records, you can retrieve them from your backup copies.</span></span>



## <a name="example"></a><span data-ttu-id="d541f-126">示例</span><span class="sxs-lookup"><span data-stu-id="d541f-126">Example</span></span>

<span data-ttu-id="d541f-127">以下示例将当前的 ReportsTo 值为 2 的所有雇员记录的 ReportsTo 字段中的值改为 5。

</span><span class="sxs-lookup"><span data-stu-id="d541f-127">This example changes values in the ReportsTo field to 5 for all employee records that currently have ReportsTo values of 2.</span></span>

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
