---
title: Database.CreateRelation Method (DAO)
TOCTitle: CreateRelation Method
ms:assetid: e240c7e3-c293-5e19-afcc-34d9a5549c64
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835692(v=office.15)
ms:contentKeyID: 48548279
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052969
f1_categories:
- Office.Version=v15
ms.openlocfilehash: e1e3919cbb47ca00d6fe9f399cba0c77e91417e7
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25606813"
---
# <a name="databasecreaterelation-method-dao"></a>Database.CreateRelation Method (DAO)

**适用于**： Access 2013 |Office 2013

创建一个新的 **[Relation](relation-object-dao.md)** 对象（仅适用于 Microsoft Access 工作区）。

## <a name="syntax"></a>语法

*表达式*。CreateRelation （***名称***、***表***、 ***ForeignTable***、***属性***）

*表达式*一个代表**Database**对象的变量。

### <a name="parameters"></a>参数

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>名称</p></th>
<th><p>必需/可选</p></th>
<th><p>数据类型</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>名称</p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>一个 <strong>Variant</strong>（<strong>String</strong> 子类型），用于对新的 <strong>Relation</strong> 对象进行唯一命名。有关有效 <strong>Relation</strong> 名称的详细信息，请参阅 <strong><a href="connection-name-property-dao.md">Name</a></strong> 属性。</p></td>
</tr>
<tr class="even">
<td><p>Table</p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>一个 <strong>Variant</strong>（<strong>String</strong> 子类型），用于命名关系中的主表。如果在追加 <strong>Relation</strong> 对象之前该表不存在，将发生运行时错误。</p></td>
</tr>
<tr class="odd">
<td><p>ForeignTable</p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>一个 <strong>Variant</strong>（<strong>String</strong> 子类型），用于命名关系中的外表。如果在追加 <strong>Relation</strong> 对象之前该表不存在，将发生运行时错误。</p></td>
</tr>
<tr class="even">
<td><p>Attributes</p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>一个常量或常量组合，包含有关关系类型的信息。有关详细信息，请参阅 <strong><a href="field-attributes-property-dao.md">Attributes</a></strong> 属性。</p></td>
</tr>
</tbody>
</table>


<<<<<<< 标头
### <a name="return-value"></a>返回值
=======
### <a name="return-value"></a>返回值
>>>>>>> master

Relation

## <a name="remarks"></a>注解

**Relation** 对象向 Microsoft Access 数据库引擎提供有关两个 **[TableDef](tabledef-object-dao.md)** 对象或 **[QueryDef](querydef-object-dao.md)** 对象中的字段之间的关系的信息。可以通过使用 **Attributes** 属性来实现参照完整性。

如果使用 **CreateRelation** 方法时省略了一个或多个可选部分，则可以在将新对象追加到集合之前，使用适当的赋值语句设置或重置相应的属性。追加对象后，不能改动此对象的任何属性设置。有关详细信息，请参阅各个属性主题。

对 [Relation](fields-append-method-dao.md) 对象使用 ****Append**** 方法之前，必须追加相应的 **[Field](field-object-dao.md)** 对象以定义主键和外键关系表。

如果 name 引用已经是集合成员的对象或提供的从属**Fields**集合中的**Field**对象名称均无效，当您使用**Append**方法时，发生此事件运行时错误。

不能在复制表和本地表之间建立或维持关系。

若要从 [**Relations**](relations-collection-dao.md) 集合中删除 **Relation** 对象，请对集合使用 **[Delete](fields-delete-method-dao.md)** 方法。

## <a name="example"></a>示例

以下示例使用 **CreateRelation** 方法在 Employees **TableDef** 和名为 Departments 的新的 **TableDef** 之间创建一个 **Relation**。该示例还演示创建新的 **Relation** 将如何同时在外部表中创建任何需要的 **Indexes**（Employees 表中的 DepartmentsEmployees 索引）。

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
