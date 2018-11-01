---
title: Relation.ForeignTable Property (DAO)
TOCTitle: ForeignTable Property
ms:assetid: 3f896433-2962-1c7c-f5a2-4e030ba8d4a0
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192853(v=office.15)
ms:contentKeyID: 48544401
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052989
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 0ad95e1ff7402ce9115421554c5a08b31a6145ac
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25878659"
---
# <a name="relationforeigntable-property-dao"></a>Relation.ForeignTable Property (DAO)


**适用于**： Access 2013、 Office 2013

设置或返回某个关系中的外表的名称（仅适用于 Microsoft Access 工作区）。

## <a name="syntax"></a>语法

*表达式*。ForeignTable

*表达式*一个代表**Relation**对象的变量。

## <a name="remarks"></a>注解

对于尚未追加到集合的新 **[Relation](relation-object-dao.md)** 对象，该属性是可读写。的；对于 [**Relations**](relations-collection-dao.md) 集合中的现有 **Relation** 对象，该属性是只读的。

**Relation** 对象的 **ForeignTable** 属性设置是代表外表或查询的 **[TableDef](connection-name-property-dao.md)** 或 **[QueryDef](tabledef-object-dao.md)** 对象的 **[Name](querydef-object-dao.md)** 属性设置； **[Table](relation-table-property-dao.md)** 属性设置是代表主表或查询的 **TableDef** 或 **QueryDef** 对象的 **Name** 属性设置。

例如，如果您有一个存储在 ValidParts 表中的有效部件代码列表（这些代码存储在名为 PartNo 的字段中），则可以与 OrderItem 表建立关系，这样的话，如果部件代码输入到 OrderItem 表中，它就会出现在 ValidParts 表中。如果部件代码在 ValidParts 表中不存在，并且您未将 [Relation](field-attributes-property-dao.md) 对象的 ****Attributes**** 属性设置为 **dbRelationDontEnforce**，则会发生可捕获的错误。

在此例中，ValidParts 表是主表，所以 **Relation** 对象的 **Table** 属性将设置为 ValidParts， **Relation** 对象的 **ForeignTable** 属性将设置为 OrderItem。 **Relation** 对象的 **Fields** 集合中的 **Field** 对象的 **Name** 和 **ForeignName** 属性将设置为 PartNo。

## <a name="example"></a>示例

以下示例演示 **Table**、 **ForeignTable** 和 **ForeignName** 属性如何定义两个表之间的 **Relation** 条件。

```vb 
    Sub ForeignNameX() 
     
     Dim dbsNorthwind As Database 
     Dim relLoop As Relation 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
     Debug.Print "Relation" 
     Debug.Print " Table - Field" 
     Debug.Print " Primary (One) "; 
     Debug.Print ".Table - .Fields(0).Name" 
     Debug.Print " Foreign (Many) "; 
     Debug.Print ".ForeignTable - .Fields(0).ForeignName" 
     
     ' Enumerate the Relations collection of the Northwind 
     ' database to report on the property values of 
     ' the Relation objects and their Field objects. 
     For Each relLoop In dbsNorthwind.Relations 
     With relLoop 
     Debug.Print 
     Debug.Print .Name & " Relation" 
     Debug.Print " Table - Field" 
     Debug.Print " Primary (One) "; 
     Debug.Print .Table & " - " & .Fields(0).Name 
     Debug.Print " Foreign (Many) "; 
     Debug.Print .ForeignTable & " - " & _ 
     .Fields(0).ForeignName 
     End With 
     Next relLoop 
     
     dbsNorthwind.Close 
     
    End Sub
```
