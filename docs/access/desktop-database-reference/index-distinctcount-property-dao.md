---
title: Index.DistinctCount Property (DAO)
TOCTitle: DistinctCount Property
ms:assetid: 24cb7247-76b4-1fce-c3c4-892f16634eff
ms:mtpsurl: https://msdn.microsoft.com/library/Ff191836(v=office.15)
ms:contentKeyID: 48543767
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053119
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 2028334a2fc1d63262d9f109cb6f76c624b64e3a
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467729"
---
# <a name="indexdistinctcount-property-dao"></a><span data-ttu-id="bd69c-102">Index.DistinctCount Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="bd69c-102">Index.DistinctCount Property (DAO)</span></span>

<span data-ttu-id="bd69c-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="bd69c-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="bd69c-104">返回一个值，该值指示 **[Index](index-object-dao.md)** 对象中的、包含在关联表中的唯一值的数目（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="bd69c-104">Returns a value that indicates the number of unique values for the **[Index](index-object-dao.md)** object that are included in the associated table (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="bd69c-105">语法</span><span class="sxs-lookup"><span data-stu-id="bd69c-105">Syntax</span></span>

<span data-ttu-id="bd69c-106">*表达式*。DistinctCount</span><span class="sxs-lookup"><span data-stu-id="bd69c-106">*expression* .DistinctCount</span></span>

<span data-ttu-id="bd69c-107">*表达式*一个代表**Index**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="bd69c-107">*expression* A variable that represents an **Index** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="bd69c-108">注解</span><span class="sxs-lookup"><span data-stu-id="bd69c-108">Remarks</span></span>

<span data-ttu-id="bd69c-p101">检查 **DistinctCount** 属性，以确定索引中唯一值或键的数目。即使在索引允许重复值的情况下可能出现该值的多个重复项，任何一个键也只统计一次。在试图通过评估索引信息来优化数据访问的应用程序中，该信息十分有用。唯一值的数目亦称 **Index** 对象的基数。</span><span class="sxs-lookup"><span data-stu-id="bd69c-p101">Check the **DistinctCount** property to determine the number of unique values, or keys, in an index. Any key is counted only once, even though there may be multiple occurrences of that value if the index permits duplicate values. This information is useful in applications that attempt to optimize data access by evaluating index information. The number of unique values is also known as the cardinality of an **Index** object.</span></span>

<span data-ttu-id="bd69c-p102">**DistinctCount** 属性不一定总会反映特定时间的实际键数。例如， **DistinctCount** 属性中就不会立即反映回滚的事务导致的更改。 **DistinctCount** 属性值也有可能不会反映包含唯一键的记录的删除。使用 **[CreateIndex](tabledef-createindex-method-dao.md)** 方法之后，该数字立即变准确。</span><span class="sxs-lookup"><span data-stu-id="bd69c-p102">The **DistinctCount** property won't always reflect the actual number of keys at a particular time. For example, a change caused by a rolled back transaction won't be reflected immediately in the **DistinctCount** property. The **DistinctCount** property value also may not reflect the deletion of records with unique keys. The number will be accurate immediately after you use the **[CreateIndex](tabledef-createindex-method-dao.md)** method.</span></span>

## <a name="example"></a><span data-ttu-id="bd69c-117">示例</span><span class="sxs-lookup"><span data-stu-id="bd69c-117">Example</span></span>

<span data-ttu-id="bd69c-p103">以下示例使用 **DistinctCount** 属性演示如何确定 **Index** 对象中唯一值的数目。但是，只是在创建了 **Index** 之后，该值才立即变准确。如果没有任何键发生更改，或者添加了新键且没有删除任何旧键，该值将保持为准确值；否则，该值是不可靠的。（如果该过程已运行数次，则可以在现有 Index 对象的 **DistinctCount** 属性值上见证这种效果。）</span><span class="sxs-lookup"><span data-stu-id="bd69c-p103">This example uses the **DistinctCount** property to show how you can determine the number of unique values in an **Index** object. However, this value is only accurate immediately after creating the **Index**. It will remain accurate if no keys change, or if new keys are added and no old keys are deleted; otherwise, it will not be reliable. (If this procedure is run several times, you can see the effect on the **DistinctCount** property values of the existing Index objects.)</span></span>

```vb
    Sub DistinctCountX() 
     
     Dim dbsNorthwind As Database 
     Dim tdfEmployees As TableDef 
     Dim idxCountry As Index 
     Dim idxLoop As Index 
     Dim rstEmployees As Recordset 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set tdfEmployees = dbsNorthwind!Employees 
     
     With tdfEmployees 
     ' Create and append new Index object to the Employees 
     ' table. 
     Set idxCountry = .CreateIndex("CountryIndex") 
     idxCountry.Fields.Append _ 
     idxCountry.CreateField("Country") 
     .Indexes.Append idxCountry 
     
     ' The collection must be refreshed for the new 
     ' DistinctCount data to be available. 
     .Indexes.Refresh 
     
     ' Enumerate Indexes collection to show the current 
     ' DistinctCount values. 
     Debug.Print "Indexes before adding new record" 
     For Each idxLoop In .Indexes 
     Debug.Print " DistinctCount = " & _ 
     idxLoop.DistinctCount & ", Name = " & _ 
     idxLoop.Name 
     Next idxLoop 
     
     Set rstEmployees = _ 
     dbsNorthwind.OpenRecordset("Employees") 
     
     ' Add a new record to the Employees table. 
     With rstEmployees 
     .AddNew 
     !FirstName = "April" 
     !LastName = "LaMonte" 
     !Country = "Canada" 
     .Update 
     End With 
     
     ' Enumerate Indexes collection to show the modified 
     ' DistinctCount values. 
     Debug.Print "Indexes after adding new record and " & _ 
     "refreshing Indexes" 
     .Indexes.Refresh 
     For Each idxLoop In .Indexes 
     Debug.Print " DistinctCount = " & _ 
     idxLoop.DistinctCount & ", Name = " & _ 
     idxLoop.Name 
     Next idxLoop 
     
     ' Delete new record because this is a demonstration. 
     With rstEmployees 
     .Bookmark = .LastModified 
     .Delete 
     .Close 
     End With 
     
     ' Delete new Indexes because this is a demonstration. 
     .Indexes.Delete idxCountry.Name 
     End With 
     
     dbsNorthwind.Close 
     
    End Sub
```
