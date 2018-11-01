---
title: Index.Primary Property (DAO)
TOCTitle: Primary Property
ms:assetid: 90eda1cb-cf7f-9682-9b74-81c27a37af16
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197416(v=office.15)
ms:contentKeyID: 48546336
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052908
f1_categories:
- Office.Version=v15
ms.openlocfilehash: efaf00dc54068c6ce7c2991613b9485bcbdf41c7
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "25891238"
---
# <a name="indexprimary-property-dao"></a>Index.Primary Property (DAO)


**适用于**： Access 2013、 Office 2013


设置或返回一个值，该值指示 **[Index](index-object-dao.md)** 对象是否代表了对一个表的主键索引（仅适用于 Microsoft Access 工作区）。

## <a name="syntax"></a>语法

*表达式*。主

*表达式*一个代表**Index**对象的变量。

## <a name="remarks"></a>注解

对于新的尚未追加到集合中的 **Index** 对象而言， **Primary** 属性设置是可读写的，对于 [**Indexes**](indexes-collection-dao.md) 集合中的 **Index** 对象而言，该属性设置是只读的。如果 **Index** 对象追加到 **[TableDef](tabledef-object-dao.md)** 对象，但是 **TableDef** 对象不追加到 **[TableDefs](tabledefs-collection-dao.md)** 集合中，则 **Index** 属性是可读写的。

主键索引包含一个或多个字段，这些字段可以按预定义的顺序唯一地对表中的所有记录进行标识。由于索引字段必须唯一，因此 [Index](index-unique-property-dao.md) 对象的 ****Unique**** 属性设置为 **True**。如果主键索引包含多个字段，则每个字段可以包含重复值，但是由所有索引字段中的值组成的每个组合则必须是唯一的。主键索引由表的键组成，包含的字段通常与主键所包含的相同。


> [!NOTE]
> <P>[!注释] 您不必为表创建索引，但是在未添加索引的大型表中，访问特定记录可能会花费很长时间。 <A href="field-attributes-property-dao.md">Index</A> 对象中每个 <A href="field-object-dao.md"><STRONG>Field</STRONG></A> 对象的 <STRONG><STRONG>Attributes</STRONG></STRONG> 属性决定了记录的顺序，因此决定了对该索引使用的访问技术。当在数据库中创建新表时，最好对唯一标识每条记录的一个或多个字段创建索引，然后将 <STRONG>Index</STRONG> 对象的 <STRONG>Primary</STRONG> 属性设置为 <STRONG>True</STRONG>。</P>



当设置表的主键时，该主键被自动定义为表的主键索引。

## <a name="example"></a>示例

以下示例使用 **Primary** 属性将新 **TableDef** 中的新 **Index** 指定为该表的主要 **Index**。请注意，将 **Primary** 属性设置为 **True** 会自动将 **Unique** 和 **Required** 属性也设置为 **True**。

```vb
    Sub PrimaryX() 
     
     Dim dbsNorthwind As Database 
     Dim tdfNew As TableDef 
     Dim idxNew As Index 
     Dim idxLoop As Index 
     Dim fldLoop As Field 
     Dim prpLoop As Property 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
     ' Create and append a new TableDef object to the 
     ' TableDefs collection of the Northwind database. 
     Set tdfNew = dbsNorthwind.CreateTableDef("NewTable") 
     tdfNew.Fields.Append tdfNew.CreateField("NumField", _ 
     dbLong, 20) 
     tdfNew.Fields.Append tdfNew.CreateField("TextField", _ 
     dbText, 20) 
     dbsNorthwind.TableDefs.Append tdfNew 
     
     With tdfNew 
     ' Create and append a new Index object to the 
     ' Indexes collection of the new TableDef object. 
     Set idxNew = .CreateIndex("NumIndex") 
     idxNew.Fields.Append idxNew.CreateField("NumField") 
     idxNew.Primary = True 
     .Indexes.Append idxNew 
     Set idxNew = .CreateIndex("TextIndex") 
     idxNew.Fields.Append idxNew.CreateField("TextField") 
     .Indexes.Append idxNew 
     
     Debug.Print .Indexes.Count & " Indexes in " & _ 
     .Name & " TableDef" 
     
     ' Enumerate Indexes collection. 
     For Each idxLoop In .Indexes 
     
     With idxLoop 
     Debug.Print " " & .Name 
     
     ' Enumerate Fields collection of each Index 
     ' object. 
     Debug.Print " Fields" 
     For Each fldLoop In .Fields 
     Debug.Print " " & fldLoop.Name 
     Next fldLoop 
     
     ' Enumerate Properties collection of each 
     ' Index object. 
     Debug.Print " Properties" 
     For Each prpLoop In .Properties 
     Debug.Print " " & prpLoop.Name & _ 
     " = " & IIf(prpLoop = "", "[empty]", _ 
     prpLoop) 
     Next prpLoop 
     End With 
     
     Next idxLoop 
     
     End With 
     
     dbsNorthwind.TableDefs.Delete tdfNew.Name 
     dbsNorthwind.Close 
     
    End Sub
```
