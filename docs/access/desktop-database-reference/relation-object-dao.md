---
title: Relation 对象 (DAO)
TOCTitle: Relation Object
ms:assetid: 46d6dfaf-a97d-3abd-0b4b-396a41eb3be7
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193195(v=office.15)
ms:contentKeyID: 48544578
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 49e8cdb7586af93ca17782ba0cb1071036c38eeb
ms.sourcegitcommit: 38d0db57580cc5f4a0231c27b1643f8db5431ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25936950"
---
# <a name="relation-object-dao"></a>Relation 对象 (DAO)


**适用于**： Access 2013、 Office 2013

**Relation** 对象表示表或查询中的字段之间的关系（仅适用于 Microsoft Access 数据库引擎数据库）。

## <a name="remarks"></a>注解

可以使用 **Relation** 对象创建新关系并检查数据库中的现有关系。

使用 **Relation** 对象及其属性，您可以进行下列操作：

  - 指定基表中的字段之间的实施关系（但不是与查询或链接表有关的关系）。

  - 在任何类型的表或查询（本地或链接）之间建立未实施的关系。

  - 使用 **Name** 属性引用被引用的主表和引用的外表中的字段之间的关系。

  - 使用 **Attributes** 属性确定表中字段之间的关系是一对一还是一对多，以及如何实施参照完整性。

  - 使用 **Attributes** 属性确定 Microsoft Access 数据库引擎是否可以对主表和外表执行级联更新和级联删除操作。

  - 使用 **Attributes** 属性确定表中字段之间的关系是左联接还是右联接。

  - 使用 **Relation** 对象的 **Fields** 集合中所有 **Field** 对象的 **Name** 属性设置或返回被引用表主键中的字段的名称，或者使用 **Field** 对象的 **ForeignName** 属性设置或返回引用表外键中的字段的名称。

如果所做的更改违背了为数据库建立的关系，将发生可捕获的错误。如果请求级联更新或级联删除操作，Microsoft Access 数据库引擎还将修改主键 或外键表，以实施建立的关系。

例如，Northwind 数据库包含 Orders 表和 Customers 表之间的关系。Customers 表的 CustomerID 字段为主键，Orders 表的 CustomerID 字段为外键。Microsoft Access 数据库引擎为了接受 Orders 表中的新记录，将搜索 Customers 表，以获取 Orders 表 CustomerID 字段的匹配项。如果 Microsoft Access 数据库引擎未找到匹配项，则不会接受新记录，同时将发生可捕获的错误。

在实施参照完整性时，被引用表的键字段必须已经存在唯一的索引。Microsoft Access 数据库引擎将使用 **Foreign** 属性自动创建一个索引，经设置的索引在引用表中充当外键。

若要创建新的 **Relation** 对象，请使用 **CreateRelation** 方法。若要按照序号或 **Name** 属性设置来引用集合中的 **Relation** 对象，可以使用下列任何一种语法形式：

**Relations**(0)

**关系**("name")

**关系**\!\[名称\]

## <a name="example"></a>示例

以下示例演示现有的 **Relation** 对象如何控制数据输入。此过程尝试添加一个具有有意弄错的 CategoryID 的记录，从而触发错误处理例程。

```vb 
    Sub RelationX() 
     
     Dim dbsNorthwind As Database 
     Dim rstProducts As Recordset 
     Dim prpLoop As Property 
     Dim fldLoop As Field 
     Dim errLoop As Error 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set rstProducts = dbsNorthwind.OpenRecordset("Products") 
     
     ' Print a report showing all the different parts of 
     ' the relation and where each part is stored. 
     With dbsNorthwind.Relations!CategoriesProducts 
     Debug.Print "Properties of " & .Name & " Relation" 
     Debug.Print " Table = " & .Table 
     Debug.Print " ForeignTable = " & .ForeignTable 
     Debug.Print "Fields of " & .Name & " Relation" 
     With .Fields!CategoryID 
     Debug.Print " " & .Name 
     Debug.Print " Name = " & .Name 
     Debug.Print " ForeignName = " & .ForeignName 
     End With 
     End With 
     
     ' Attempt to add a record that violates the relation. 
     With rstProducts 
     .AddNew 
     !ProductName = "Trygve's Lutefisk" 
     !CategoryID = 10 
     On Error GoTo Err_Relation 
     .Update 
     On Error GoTo 0 
     .Close 
     End With 
     
     dbsNorthwind.Close 
     
     Exit Sub 
     
    Err_Relation: 
     
     ' Notify user of any errors that result from 
     ' the invalid data. 
     If DBEngine.Errors.Count > 0 Then 
     For Each errLoop In DBEngine.Errors 
     MsgBox "Error number: " & errLoop.Number & _ 
     vbCr & errLoop.Description 
     Next errLoop 
     End If 
     
     Resume Next 
     
    End Sub 
```

<br/>

以下示例使用 **CreateRelation** 方法在 Employees **TableDef** 和名为 Departments 的新的 **TableDef** 之间创建一个 **Relation**。 它还演示了如何创建新的**Relation**还将创建任何必要的**索引**中的外表 （DepartmentsEmployees Employees 表中的索引）。

```vb
    Sub CreateRelationX() 
     
     Dim dbsNorthwind As Database 
     Dim tdfEmployees As TableDef 
     Dim tdfNew As TableDef 
     Dim idxNew As Index 
     Dim relNew As Relation 
     Dim idxLoop As Index 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
     With dbsNorthwind 
     ' Add new field to Employees table. 
     Set tdfEmployees = .TableDefs!Employees 
     tdfEmployees.Fields.Append _ 
     tdfEmployees.CreateField("DeptID", dbInteger, 2) 
     
     ' Create new Departments table. 
     Set tdfNew = .CreateTableDef("Departments") 
     
     With tdfNew 
     ' Create and append Field objects to Fields 
     ' collection of the new TableDef object. 
     .Fields.Append .CreateField("DeptID", dbInteger, 2) 
     .Fields.Append .CreateField("DeptName", dbText, 20) 
     
     ' Create Index object for Departments table. 
     Set idxNew = .CreateIndex("DeptIDIndex") 
     ' Create and append Field object to Fields 
     ' collection of the new Index object. 
     idxNew.Fields.Append idxNew.CreateField("DeptID") 
     ' The index in the primary table must be Unique in 
     ' order to be part of a Relation. 
     idxNew.Unique = True 
     .Indexes.Append idxNew 
     End With 
     
     .TableDefs.Append tdfNew 
     
     ' Create EmployeesDepartments Relation object, using 
     ' the names of the two tables in the relation. 
     Set relNew = .CreateRelation("EmployeesDepartments", _ 
     tdfNew.Name, tdfEmployees.Name, _ 
     dbRelationUpdateCascade) 
     
     ' Create Field object for the Fields collection of the 
     ' new Relation object. Set the Name and ForeignName 
     ' properties based on the fields to be used for the 
     ' relation. 
     relNew.Fields.Append relNew.CreateField("DeptID") 
     relNew.Fields!DeptID.ForeignName = "DeptID" 
     .Relations.Append relNew 
     
     ' Print report. 
     Debug.Print "Properties of " & relNew.Name & _ 
     " Relation" 
     Debug.Print " Table = " & relNew.Table 
     Debug.Print " ForeignTable = " & _ 
     relNew.ForeignTable 
     Debug.Print "Fields of " & relNew.Name & " Relation" 
     
     With relNew.Fields!DeptID 
     Debug.Print " " & .Name 
     Debug.Print " Name = " & .Name 
     Debug.Print " ForeignName = " & .ForeignName 
     End With 
     
     Debug.Print "Indexes in " & tdfEmployees.Name & _ 
     " TableDef" 
     For Each idxLoop In tdfEmployees.Indexes 
     Debug.Print " " & idxLoop.Name & _ 
     ", Foreign = " & idxLoop.Foreign 
     Next idxLoop 
     
     ' Delete new objects because this is a demonstration. 
     .Relations.Delete relNew.Name 
     .TableDefs.Delete tdfNew.Name 
     tdfEmployees.Fields.Delete "DeptID" 
     .Close 
     End With 
     
    End Sub
```
