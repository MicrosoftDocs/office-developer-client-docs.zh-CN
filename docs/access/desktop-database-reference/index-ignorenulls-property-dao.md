---
title: Index.IgnoreNulls 属性 (DAO)
TOCTitle: IgnoreNulls Property
ms:assetid: f49f17b8-d7c1-18ab-07a8-e1be61488519
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836698(v=office.15)
ms:contentKeyID: 48548694
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052931
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 6c306f76e34e24abb5065c627d9325b48c3acead
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28708856"
---
# <a name="indexignorenulls-property-dao"></a>Index.IgnoreNulls 属性 (DAO)


**适用于**： Access 2013、 Office 2013

设置或返回一个值，该值指示索引字段中包含 Null 值的记录是否具有索引项（仅适用于 Microsoft Access 工作区）。

## <a name="syntax"></a>语法

*表达式*。IgnoreNulls

*表达式*一个代表**Index**对象的变量。

## <a name="remarks"></a>注解

对于尚未追加到集合的新 **[Index](index-object-dao.md)** 对象，该属性是可读写的；对于 [**Indexes**](indexes-collection-dao.md) 集合中的现有 **Index** 对象，该属性是只读的。

要加速搜索记录的过程，可以为字段定义一个索引。如果允许在索引字段中使用 **null** 项，并且希望有许多项为 **null**，可以将 **Index** 对象的 **IgnoreNulls** 属性设置为 **True**，以减少索引使用的存储空间量。

**IgnoreNulls** 属性设置和 **[Required](field-required-property-dao.md)** 属性设置共同确定包含 **null** 索引值的记录是否具有索引项。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>如果 IgnoreNulls 是</p></th>
<th><p>并且 Required 是</p></th>
<th><p>则</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>True</p></td>
<td><p>False</p></td>
<td><p>索引字段中允许空值；未添加任何索引项。</p></td>
</tr>
<tr class="even">
<td><p>False</p></td>
<td><p>False</p></td>
<td><p>索引字段中允许 Null 值；已添加索引项。</p></td>
</tr>
<tr class="odd">
<td><p>True 或 False</p></td>
<td><p>True</p></td>
<td><p>索引字段中允许 Null 值；未添加任何索引项。</p></td>
</tr>
</tbody>
</table>


## <a name="example"></a>示例

以下示例根据用户输入将新的 **Index** 的 **IgnoreNulls** 属性设置为 **True** 或 **False**，然后在一个带有记录（该记录的键字段包含 **Null** 值）的 **Recordset** 上演示该效果。

```vb
    Sub IgnoreNullsX() 
     
     Dim dbsNorthwind As Database 
     Dim tdfEmployees As TableDef 
     Dim idxNew As Index 
     Dim rstEmployees As Recordset 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set tdfEmployees = dbsNorthwind!Employees 
     
     With tdfEmployees 
     ' Create a new Index object. 
     Set idxNew = .CreateIndex("NewIndex") 
     idxNew.Fields.Append idxNew.CreateField("Country") 
     
     ' Set the IgnoreNulls property of the new Index object 
     ' based on the user's input. 
     Select Case MsgBox("Set IgnoreNulls to True?", _ 
     vbYesNoCancel) 
     Case vbYes 
     idxNew.IgnoreNulls = True 
     Case vbNo 
     idxNew.IgnoreNulls = False 
     Case Else 
     dbsNorthwind.Close 
     End 
     End Select 
     
     ' Append the new Index object to the Indexes 
     ' collection of the Employees table. 
     .Indexes.Append idxNew 
     .Indexes.Refresh 
     End With 
     
     Set rstEmployees = _ 
     dbsNorthwind.OpenRecordset("Employees") 
     
     With rstEmployees 
     ' Add a new record to the Employees table. 
     .AddNew 
     !FirstName = "Gary" 
     !LastName = "Haarsager" 
     .Update 
     
     ' Use the new index to set the order of the records. 
     .Index = idxNew.Name 
     .MoveFirst 
     
     Debug.Print "Index = " & .Index & _ 
     ", IgnoreNulls = " & idxNew.IgnoreNulls 
     Debug.Print " Country - Name" 
     
     ' Enumerate the Recordset. The value of the 
     ' IgnoreNulls property will determine if the newly 
     ' added record appears in the output. 
     Do While Not .EOF 
     Debug.Print " " & _ 
     IIf(IsNull(!Country), "[Null]", !Country) & _ 
     " - " & !FirstName & " " & !LastName 
     .MoveNext 
     Loop 
     
     ' Delete new record because this is a demonstration. 
     .Index = "" 
     .Bookmark = .LastModified 
     .Delete 
     .Close 
     End With 
     
     ' Delete new Index because this is a demonstration. 
     tdfEmployees.Indexes.Delete idxNew.Name 
     dbsNorthwind.Close 
     
    End Sub
```
