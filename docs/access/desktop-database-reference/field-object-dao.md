---
title: Field 对象 - 数据访问对象 (DAO)
TOCTitle: Field Object
ms:assetid: 47282ce2-9b49-ccf9-ad37-c4bb25cfd037
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193203(v=office.15)
ms:contentKeyID: 48544587
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: c58896fb0d0a5c5a28844fdd3a6df922dd587f32
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32293040"
---
# <a name="field-object-dao"></a>Field 对象 (DAO)

**适用于**：Access 2013、Office 2013

**Field** 对象表示具有公共数据类型和一组公共属性的数据列。

## <a name="remarks"></a>说明

**Index**、 **QueryDef**、 **Relation** 和 **TableDef** 对象的 **Fields** 集合包含这些对象代表的字段的规范。 **Recordset** 对象的 **Fields** 集合代表数据行中或记录中的 **Field** 对象。可使用 **Recordset** 对象中的 **Field** 对象读取和设置 **Recordset** 对象的当前记录中的字段的值。

在 Microsoft Access 工作区中，可以使用 **Field** 对象及其方法和属性操作字段。例如，您可以进行下列操作：

  - 使用 **OrdinalPosition** 属性设置或返回 **Fields** 集合中的 **Field** 对象的表示顺序。

  - 使用 **Recordset** 对象中的某个字段的 **Value** 属性设置或返回存储的数据。

  - 使用 **AppendChunk** 和 **GetChunk** 方法以及 **FieldSize** 属性获取或设置 **Recordset** 对象的"OLE 对象"或"备注"字段中的值。

  - 使用 **Type**、 **Size** 和 **Attributes** 属性确定可以存储在字段中的数据的类型。

  - 使用 **SourceField** 和 **SourceTable** 属性确定数据的原始源。

  - 使用 **ForeignName** 属性设置或返回与 **Relation** 对象中的外部字段有关的信息。

  - 使用 **AllowZeroLength**、 **DefaultValue**、 **Required**、 **ValidateOnSet**、 **ValidationRule** 或 **ValidationText** 属性设置或返回验证条件。

  - 使用 **TableDef** 对象上的某个字段的 **DefaultValue** 属性，设置添加新记录后该字段的默认值。

要在 **Index**、 **TableDef** 或 **Relation** 对象中创建新的 **Field** 对象，请使用 **CreateField** 方法。

在访问作为 **Recordset** 对象一部分的 **Field** 对象时，当前记录中的数据将在 **Field** 对象的 **Value** 属性中可见。要操作 **Recordset** 对象中的数据，通常不需要直接引用 **Fields** 集合；而是间接引用 **Recordset** 对象的 **Fields** 集合中的 **Field** 对象的 **Value** 属性。

若要按照序号或 **Name** 属性设置来引用集合中的 **Field** 对象，可以使用下列任何一种语法形式：

- **Fields**(0)

- **Fields**("name")

- **Fields**\!\[name\]

还可以使用相同的语法形式，引用创建并追加到 **Fields** 集合中的 **Field** 对象的 **Value** 属性。字段引用的上下文将确定引用的是 **Field** 对象还是 **Field** 对象的 **Value** 属性。

## <a name="example"></a>示例

以下示例演示根据 **Field** 驻留的位置（例如 **TableDef** 的 **Fields** 集合、 **QueryDef** 的 **Fields** 集合，等等），有哪些属性对 **Field** 对象有效。若要使该过程运行，需要使用 FieldOutput 过程。

```vb
    Sub FieldX() 
     
     Dim dbsNorthwind As Database 
     Dim rstEmployees As Recordset 
     Dim fldTableDef As Field 
     Dim fldQueryDef As Field 
     Dim fldRecordset As Field 
     Dim fldRelation As Field 
     Dim fldIndex As Field 
     Dim prpLoop As Property 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set rstEmployees = _ 
     dbsNorthwind.OpenRecordset("Employees") 
     
     ' Assign a Field object from different Fields 
     ' collections to object variables. 
     Set fldTableDef = _ 
     dbsNorthwind.TableDefs(0).Fields(0) 
     Set fldQueryDef =dbsNorthwind.QueryDefs(0).Fields(0) 
     Set fldRecordset = rstEmployees.Fields(0) 
     Set fldRelation =dbsNorthwind.Relations(0).Fields(0) 
     Set fldIndex = _ 
     dbsNorthwind.TableDefs(0).Indexes(0).Fields(0) 
     
     ' Print report. 
     FieldOutput "TableDef", fldTableDef 
     FieldOutput "QueryDef", fldQueryDef 
     FieldOutput "Recordset", fldRecordset 
     FieldOutput "Relation", fldRelation 
     FieldOutput "Index", fldIndex 
     
     rstEmployees.Close 
     dbsNorthwind.Close 
     
    End Sub 
     
    Sub FieldOutput(strTemp As String, fldTemp As Field) 
     ' Report function for FieldX. 
     
     Dim prpLoop As Property 
     
     Debug.Print "Valid Field properties in " & strTemp 
     
     ' Enumerate Properties collection of passed Field 
     ' object. 
     For Each prpLoop In fldTemp.Properties 
     ' Some properties are invalid in certain 
     ' contexts (the Value property in the Fields 
     ' collection of a TableDef for example). Any 
     ' attempt to use an invalid property will 
     ' trigger an error. 
     On Error Resume Next 
     Debug.Print " " & prpLoop.Name & " = " & _ 
     prpLoop.Value 
     On Error GoTo 0 
     Next prpLoop 
     
    End Sub 
```

<br/>

以下示例使用 **CreateField** 方法为新的 **TableDef** 创建三个 **Fields**。然后显示这些 **Field** 对象的、由 **CreateField** 方法自动设置的属性。（不显示创建 **Field** 时值为空的属性。）

```vb
    Sub CreateFieldX() 
     
     Dim dbsNorthwind As Database 
     Dim tdfNew As TableDef 
     Dim fldLoop As Field 
     Dim prpLoop As Property 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
     Set tdfNew = dbsNorthwind.CreateTableDef("NewTableDef") 
     
     ' Create and append new Field objects for the new 
     ' TableDef object. 
     With tdfNew 
     ' The CreateField method will set a default Size 
     ' for a new Field object if one is not specified. 
     .Fields.Append .CreateField("TextField", dbText) 
     .Fields.Append .CreateField("IntegerField", dbInteger) 
     .Fields.Append .CreateField("DateField", dbDate) 
     End With 
     
     dbsNorthwind.TableDefs.Append tdfNew 
     
     Debug.Print "Properties of new Fields in " & tdfNew.Name 
     
     ' Enumerate Fields collection to show the properties of 
     ' the new Field objects. 
     For Each fldLoop In tdfNew.Fields 
     Debug.Print " " & fldLoop.Name 
     
     For Each prpLoop In fldLoop.Properties 
     ' Properties that are invalid in the context of 
     ' TableDefs will trigger an error if an attempt 
     ' is made to read their values. 
     On Error Resume Next 
     Debug.Print " " & prpLoop.Name & " - " & _ 
     IIf(prpLoop = "", "[empty]", prpLoop) 
     On Error GoTo 0 
     Next prpLoop 
     
     Next fldLoop 
     
     ' Delete new TableDef because this is a demonstration. 
     dbsNorthwind.TableDefs.Delete tdfNew.Name 
     dbsNorthwind.Close 
     
    End Sub
```
