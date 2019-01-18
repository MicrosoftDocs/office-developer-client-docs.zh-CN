---
title: Index.DistinctCount 属性 (DAO)
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
localization_priority: Normal
ms.openlocfilehash: 3264ea010db12f3fee6c16bd82fb19ed9bda1992
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28705188"
---
# <a name="indexdistinctcount-property-dao"></a>Index.DistinctCount 属性 (DAO)

**适用于**： Access 2013、 Office 2013

返回一个值，该值指示 **[Index](index-object-dao.md)** 对象中的、包含在关联表中的唯一值的数目（仅适用于 Microsoft Access 工作区）。

## <a name="syntax"></a>语法

*表达式*。DistinctCount

*表达式*一个代表**Index**对象的变量。

## <a name="remarks"></a>注解

检查 **DistinctCount** 属性，以确定索引中唯一值或键的数目。即使在索引允许重复值的情况下可能出现该值的多个重复项，任何一个键也只统计一次。在试图通过评估索引信息来优化数据访问的应用程序中，该信息十分有用。唯一值的数目亦称 **Index** 对象的基数。

**DistinctCount** 属性不一定总会反映特定时间的实际键数。例如， **DistinctCount** 属性中就不会立即反映回滚的事务导致的更改。 **DistinctCount** 属性值也有可能不会反映包含唯一键的记录的删除。使用 **[CreateIndex](tabledef-createindex-method-dao.md)** 方法之后，该数字立即变准确。

## <a name="example"></a>示例

以下示例使用 **DistinctCount** 属性演示如何确定 **Index** 对象中唯一值的数目。但是，只是在创建了 **Index** 之后，该值才立即变准确。如果没有任何键发生更改，或者添加了新键且没有删除任何旧键，该值将保持为准确值；否则，该值是不可靠的。（如果该过程已运行数次，则可以在现有 Index 对象的 **DistinctCount** 属性值上见证这种效果。）

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
