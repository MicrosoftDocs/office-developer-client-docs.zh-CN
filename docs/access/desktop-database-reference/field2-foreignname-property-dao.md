---
title: Field2.ForeignName 属性 (DAO)
TOCTitle: ForeignName Property
ms:assetid: 76da233a-efb4-63cd-a2a2-d18d9e2fb2fb
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196027(v=office.15)
ms:contentKeyID: 48545708
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052932
f1_categories:
- Office.Version=v15
ms.openlocfilehash: f95839ac7b8832e22f69b31914f42de4f4adad06
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25929233"
---
# <a name="field2foreignname-property-dao"></a>Field2.ForeignName 属性 (DAO)


**适用于**： Access 2013、 Office 2013

设置或返回一个值，该值指定某个外表中的 **Field2** 对象的名称，而该外表对应于某个关系的主表中的字段（仅适用于 Microsoft Access 工作区）。

## <a name="syntax"></a>语法

*表达式*。ForeignName

*表达式*一个代表**Field2**对象的变量。

## <a name="remarks"></a>注解

如果 **[Relation](relation-object-dao.md)** 对象未追加到 **[Database](database-object-dao.md)** ，但是 **Field2** 已追加到 **Relation** 对象，则 **ForeignName** 属性是可读写的。将 **Relation** 对象追加到数据库后， **ForeignName** 属性是只读的。

只有属于 **Relation** 对象 **Fields** 集合的 **Field2** 对象才能支持 **ForeignName** 属性。

[Field2](connection-name-property-dao.md) 对象的 ****Name**** 和 **ForeignName** 属性设置指定关系的主表和外表中相应字段的名称。 [Relation](relation-table-property-dao.md) 对象的 [**Table**](relation-foreigntable-property-dao.md) 和 ****ForeignTable**** 属性设置确定关系的主表和外表。

例如，如果您有一个存储在 ValidParts 表中的有效部件代码列表（这些代码存储在名为 PartNo 的字段中），则可以与 OrderItem 表建立关系，这样的话，如果部件代码输入到 OrderItem 表中，它就会出现在 ValidParts 表中。如果部件代码在 ValidParts 表中不存在，并且您未将 [Relation](field-attributes-property-dao.md) 对象的 ****Attributes**** 属性设置为 **dbRelationDontEnforce**，则会发生可捕获的错误。

在这种情况下，ValidParts 表将是外表，因此 **Relation** 对象的 **ForeignTable** 属性将设置为 ValidParts， **Relation** 对象的 **Table** 属性将设置为 OrderItem。 **Relation** 对象的 **Fields** 集合中的 **Field2** 对象的 **Name** 和 **ForeignName** 属性将设置为 PartNo。

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
