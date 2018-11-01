---
title: Field2.DataUpdatable Property (DAO)
TOCTitle: DataUpdatable Property
ms:assetid: e6619c4e-26b1-777b-f0de-78fed3dbc890
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835966(v=office.15)
ms:contentKeyID: 48548377
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 5f961bf727c016a025e5ebe7107c5082b1b63deb
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25885834"
---
# <a name="field2dataupdatable-property-dao"></a>Field2.DataUpdatable Property (DAO)


**适用于**： Access 2013、 Office 2013


返回一个值，该值指示是否可更新 **Field2** 对象所代表的字段中的数据。

## <a name="syntax"></a>语法

*表达式*。DataUpdatable

*表达式*一个代表**Field2**对象的变量。

## <a name="remarks"></a>注解

使用该属性确定是否可更改 [Field2](field-value-property-dao.md) 对象的 ****Value**** 属性设置。对于 ****Attributes**** 属性为 [dbAutoIncrField](field-attributes-property-dao.md) 的 **Field2** 对象，该属性始终为 **False**。

**DataUpdatable** 属性可用于已追加到 [**QueryDef**](fields-collection-dao.md) 、 [**Recordset**](querydef-object-dao.md) 和 [**Relation**](recordset-object-dao.md) 对象的 [**Fields**](relation-object-dao.md) 集合（但不是 ****Index**** 或 **[TableDef](index-object-dao.md)** 对象的 [Fields](tabledef-object-dao.md) 集合）中的 **Field2** 对象。

## <a name="example"></a>示例

以下示例演示使用了六个不同的 **Recordsets** 中的第一个字段的 **DataUpdatable** 属性。若要使该过程运行，需要使用 DataOutput 函数。

```vb 
Sub DataUpdatableX() 
 
 Dim dbsNorthwind As Database 
 Dim rstNorthwind As Recordset 
 
 Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
 
 With dbsNorthwind 
 ' Open and print report about a table-type Recordset. 
 Set rstNorthwind = .OpenRecordset("Employees") 
 DataOutput rstNorthwind 
 
 ' Open and print report about a dynaset-type Recordset. 
 Set rstNorthwind = .OpenRecordset("Employees", _ 
 dbOpenDynaset) 
 DataOutput rstNorthwind 
 
 ' Open and print report about a snapshot-type Recordset. 
 Set rstNorthwind = .OpenRecordset("Employees", _ 
 dbOpenSnapshot) 
 DataOutput rstNorthwind 
 
 ' Open and print report about a forward-only-type Recordset. 
 Set rstNorthwind = .OpenRecordset("Employees", _ 
 dbOpenForwardOnly) 
 DataOutput rstNorthwind 
 
 ' Open and print report about a Recordset based on 
 ' a select query. 
 Set rstNorthwind = _ 
 .OpenRecordset("Current Product List") 
 DataOutput rstNorthwind 
 
 ' Open and print report about a Recordset based on a 
 ' select query that calculates totals. 
 Set rstNorthwind = .OpenRecordset("Order Subtotals") 
 DataOutput rstNorthwind 
 
 .Close 
 End With 
 
End Sub 
 
Function DataOutput(rstTemp As Recordset) 
 
 With rstTemp 
 Debug.Print "Recordset: " & .Name & ", "; 
 Select Case .Type 
 Case dbOpenTable 
 Debug.Print "dbOpenTable" 
 Case dbOpenDynaset 
 Debug.Print "dbOpenDynaset" 
 Case dbOpenSnapshot 
 Debug.Print "dbOpenSnapshot" 
 Case dbOpenForwardOnly 
 Debug.Print "dbOpenForwardOnly" 
 End Select 
 Debug.Print " Field: " & .Fields(0).Name & ", " & _ 
 "DataUpdatable = " & .Fields(0).DataUpdatable 
 Debug.Print 
 .Close 
 End With 
 
End Function 
 
```

