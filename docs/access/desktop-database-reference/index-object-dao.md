---
title: Index 对象的数据访问对象 (DAO)
TOCTitle: Index object
ms:assetid: 92c32cad-ec8a-1243-1d18-83f50b269ecb
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197655(v=office.15)
ms:contentKeyID: 48546380
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: ca0a975017b5c5396d23817716689b37433d8f97
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28708912"
---
# <a name="index-object-dao"></a>Index 对象 (DAO)

**适用于**： Access 2013、 Office 2013

**Index** 对象指定从数据库表访问的记录的顺序，以及是否可接受重复的记录，以便提供高效的数据访问。对于外部数据库， **Index** 对象描述为外部表建立的索引（仅适用于 Microsoft Access 工作区）。

## <a name="remarks"></a>注解

Microsoft Access 数据库引擎在联接表和创建 **[Recordset](recordset-object-dao.md)** 对象时将会使用索引。索引确定表类型的 **Recordset** 对象返回记录时遵循的顺序，但是，索引不能确定 Microsoft Access 数据库引擎在基表中存储记录时遵循的顺序，也不能确定其他任何类型的 **Recordset** 对象返回记录时遵循的顺序。

使用 **Index** 对象，您可以进行下列操作：

- 使用 **Required** 属性确定索引中的 **[Field](field-object-dao.md)** 对象是否需要非 Null 值，然后使用 **IgnoreNulls** 属性确定空值是否具有索引项。

- 使用 **Primary** 和 **Unique** 属性确定 **Index** 对象的排序和唯一性。

Microsoft Access 数据库引擎可自动维护所有的基表索引。只要在基表中添加、更改或删除了记录，它就会更新索引。创建数据库后，请定期使用 **[CompactDatabase](dbengine-compactdatabase-method-dao.md)** 方法将索引统计保持为最新状态。

在访问表类型 **Recordset** 对象时，可以使用该对象的 **Index** 属性指定记录的顺序。将该属性设置为 **Indexes** 集合中的现有 **Index** 对象的 **Name** 属性设置。此集合包含在您所填充的 [Recordset](tabledef-object-dao.md) 对象下面的 ****TableDef**** 对象中。

> [!NOTE]
> [!注释] 不一定非要为表创建索引，但是对于大型的未创建索引的表，访问特定的记录或处理联接可能需要花费较长的时间。反过来，具有太多的索引也会减慢更新数据库的速度，原因是需要修正每个表索引。

索引中每个 [Field](field-attributes-property-dao.md) 对象的 ****Attributes**** 属性将确定返回记录的顺序，并从而确定要对该索引使用哪些访问技术。

**Index** 对象的 **Fields** 集合中的每个 **Field** 对象都是索引的组成部分。要定义一个新的 **Index** 对象，请先设置其属性，然后再将其追加到集合中，使该 **Index** 对象可用于后续应用。

> [!NOTE]
> [!注释] 仅当现有 **Index** 对象所在的 **TableDef** 对象的 **[Updatable](connection-updatable-property-dao.md)** 属性为 **True** 时，才可以修改该对象的 **Name** 属性设置。

在设置表的主键时，Microsoft Access 数据库引擎会自动将它定义为主索引。主索引包括一个或多个字段，这些字段可以按预定义的顺序唯一地标识表中的所有记录。由于主索引字段必须是唯一的，因此 Microsoft Access 数据库引擎会将主 **Index** 对象的 **Unique** 属性自动设置为 **True**。如果主索引包括多个字段，则每个字段可以包含重复值，但是所有索引字段中的值组合必须是唯一的。主索引包括表的键，并且始终由作为主键的相同字段组成。

> [!IMPORTANT]
> [!重要信息] 确保数据符合新索引的属性。如果索引需要唯一值，请确保现有数据记录中没有重复值。如果存在重复值，Microsoft Access 数据库引擎将无法创建索引；当您尝试对新索引使用 Append 方法时，会生成可捕获的错误。

在创建实施参照完整性的关系时，Microsoft Access 数据库引擎将使用 **Foreign** 属性自动创建一个索引，该索引在引用表中设置为外键。建立了表关系后，Microsoft Access 数据库引擎将防止对数据库执行会违背该关系的添加或更改操作。如果将 [**Relation**](relation-object-dao.md) 对象的 **Attributes** 属性设置为允许级联更新和级联删除，Microsoft Access 数据库引擎将自动更新或删除相关表中的记录。

1.  对 **TableDef** 对象使用 **CreateIndex** 方法。

2.  对 **Index** 对象使用 **CreateField** 方法，为要包含在 **Index** 对象中的每个字段（列）创建 **Field** 对象。

3.  根据需要设置 **Index** 属性。

4.  将 **Field** 对象追加到 **Fields** 集合。

5.  将 **Index** 对象追加到 **Indexes** 集合。

    > [!NOTE]
    > [!注释] 对于使用 Microsoft Access 数据库引擎（不支持聚簇索引）的数据库，将忽略 **Clustered** 属性。

## <a name="example"></a>示例

以下示例创建一个新的 **Index** 对象，并将该对象追加到 Employees **TableDef** 的 **Indexes** 集合，然后枚举 **TableDef** 的 **Indexes** 集合。最后，该示例枚举 **Recordset**，方法是首先使用主 **Index**，然后使用新的 **Index**。若要使该过程正常运行，需要使用 IndexOutput 过程。

```vb
    Sub IndexObjectX() 
     
     Dim dbsNorthwind As Database 
     Dim tdfEmployees As TableDef 
     Dim idxNew As Index 
     Dim idxLoop As Index 
     Dim rstEmployees As Recordset 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set tdfEmployees = dbsNorthwind!Employees 
     
     With tdfEmployees 
     ' Create new index, create and append Field 
     ' objects to its Fields collection. 
     Set idxNew = .CreateIndex("NewIndex") 
     
     With idxNew 
     .Fields.Append .CreateField("Country") 
     .Fields.Append .CreateField("LastName") 
     .Fields.Append .CreateField("FirstName") 
     End With 
     
     ' Add new Index object to the Indexes collection 
     ' of the Employees table collection. 
     .Indexes.Append idxNew 
     .Indexes.Refresh 
     
     Debug.Print .Indexes.Count & " Indexes in " & _ 
     .Name & " TableDef" 
     
     ' Enumerate Indexes collection of Employees 
     ' table. 
     For Each idxLoop In .Indexes 
     Debug.Print " " & idxLoop.Name 
     Next idxLoop 
     
     Set rstEmployees = _ 
     dbsNorthwind.OpenRecordset("Employees") 
     
     ' Print report using old and new indexes. 
     IndexOutput rstEmployees, "PrimaryKey" 
     IndexOutput rstEmployees, idxNew.Name 
     rstEmployees.Close 
     
     ' Delete new Index because this is a 
     ' demonstration. 
     .Indexes.Delete idxNew.Name 
     End With 
     
     dbsNorthwind.Close 
     
    End Sub 
     
    Sub IndexOutput(rstTemp As Recordset, _ 
     strIndex As String) 
     ' Report function for FieldX. 
     
     With rstTemp 
     ' Set the index. 
     .Index = strIndex 
     .MoveFirst 
     Debug.Print "Recordset = " & .Name & _ 
     ", Index = " & .Index 
     Debug.Print " EmployeeID - Country - Name" 
     
     ' Enumerate the recordset using the specified 
     ' index. 
     Do While Not .EOF 
     Debug.Print " " & !EmployeeID & " - " & _ 
     !Country & " - " & !LastName & ", " & !FirstName 
     .MoveNext 
     Loop 
     
     End With 
     
    End Sub 
```

<br/>

以下示例使用 **CreateIndex** 方法创建两个新的 **Index** 对象，然后将它们追加到 Employees **TableDef** 对象的 **Indexes** 集合。然后，该示例枚举 **TableDef** 对象的 **Indexes** 集合、新 **Index** 对象的 **Fields** 集合，以及新 **Index** 对象的 Properties 集合。若要使该过程正常运行，需要使用 CreateIndexOutput 函数。

```vb
    Sub CreateIndexX() 
     
     Dim dbsNorthwind As Database 
     Dim tdfEmployees As TableDef 
     Dim idxCountry As Index 
     Dim idxFirstName As Index 
     Dim idxLoop As Index 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set tdfEmployees = dbsNorthwind!Employees 
     
     With tdfEmployees 
     ' Create first Index object, create and append Field 
     ' objects to the Index object, and then append the 
     ' Index object to the Indexes collection of the 
     ' TableDef. 
     Set idxCountry = .CreateIndex("CountryIndex") 
     With idxCountry 
     .Fields.Append .CreateField("Country") 
     .Fields.Append .CreateField("LastName") 
     .Fields.Append .CreateField("FirstName") 
     End With 
     .Indexes.Append idxCountry 
     
     ' Create second Index object, create and append Field 
     ' objects to the Index object, and then append the 
     ' Index object to the Indexes collection of the 
     ' TableDef. 
     Set idxFirstName = .CreateIndex 
     With idxFirstName 
     .Name = "FirstNameIndex" 
     .Fields.Append .CreateField("FirstName") 
     .Fields.Append .CreateField("LastName") 
     End With 
     .Indexes.Append idxFirstName 
     
     ' Refresh collection so that you can access new Index 
     ' objects. 
     .Indexes.Refresh 
     
     Debug.Print .Indexes.Count & " Indexes in " & _ 
     .Name & " TableDef" 
     
     ' Enumerate Indexes collection. 
     For Each idxLoop In .Indexes 
     Debug.Print " " & idxLoop.Name 
     Next idxLoop 
     
     ' Print report. 
     CreateIndexOutput idxCountry 
     CreateIndexOutput idxFirstName 
     
     ' Delete new Index objects because this is a 
     ' demonstration. 
     .Indexes.Delete idxCountry.Name 
     .Indexes.Delete idxFirstName.Name 
     End With 
     
     dbsNorthwind.Close 
     
    End Sub 
     
    Function CreateIndexOutput(idxTemp As Index) 
     
     Dim fldLoop As Field 
     Dim prpLoop As Property 
     
     With idxTemp 
     ' Enumerate Fields collection of Index object. 
     Debug.Print "Fields in " & .Name 
     For Each fldLoop In .Fields 
     Debug.Print " " & fldLoop.Name 
     Next fldLoop 
     
     ' Enumerate Properties collection of Index object. 
     Debug.Print "Properties of " & .Name 
     For Each prpLoop In .Properties 
     Debug.Print " " & prpLoop.Name & " - " & _ 
     IIf(prpLoop = "", "[empty]", prpLoop) 
     Next prpLoop 
     End With 
     
    End Function
```
