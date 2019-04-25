---
title: Recordset.RecordCount 属性 (DAO)
TOCTitle: RecordCount Property
ms:assetid: aa1fed4f-ca51-918f-0a46-2b755b5f861a
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821452(v=office.15)
ms:contentKeyID: 48546941
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: b9bdc243aae48bd928468362cb86ca077f4abe52
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32307635"
---
# <a name="recordsetrecordcount-property-dao"></a>Recordset.RecordCount 属性 (DAO)

**适用于**：Access 2013、Office 2013

返回在 **[Recordset](recordset-object-dao.md)** 对象中访问的记录数，或者返回表类型 **Recordset** 对象或 **[TableDef](tabledef-object-dao.md)** 对象中的记录总数。只读 **Long**。

## <a name="syntax"></a>语法

*表达式* .RecordCount

*表达式* 一个表示 **Recordset** 对象的变量。

## <a name="remarks"></a>说明

使用 **RecordCount** 属性可以找出 **Recordset** 或 **TableDef** 对象中已访问的记录数。 在访问完所有记录之前，**RecordCount** 属性不指示动态集类型、快照类型或仅向前类型的 **Recordset** 对象中包含的记录数。 访问完最后一条记录后，**RecordCount** 属性将指示 **Recordset** 或 **TableDef** 对象中未删除的记录总数。 若要强制访问最后一条记录，请对 **Recordset** 对象使用 **[MoveLast](recordset-movelast-method-dao.md)** 方法。 还可以使用 SQL **Count** 函数来确定查询将返回的大致记录数。

> [!NOTE]
> [!注释] 使用 **MoveLast** 方法填充新打开的 **Recordset** 会对性能造成负面影响。除非在您打开 **Recordset** 时必须得到准确的 **RecordCount**，否则最好等到使用代码的其他部分填充完 **Recordset** 之后，再检查 **RecordCount** 属性。

由于应用程序删除了动态集类型 **Recordset** 对象中的记录，因此 **RecordCount** 属性的值将减小。但是，其他用户删除的记录不受 **RecordCount** 属性的影响，除非当前记录定位到已删除的记录。如果执行的事务影响 **RecordCount** 属性设置，之后您又回滚了该事务，则 **RecordCount** 属性将不会反映其余记录的实际数目。

快照类型或仅向前类型 **Recordset** 对象的 **RecordCount** 属性不受基础表中的更改的影响。

如果 **Recordset** 或 **TableDef** 对象不含记录，则其 **RecordCount** 属性设置为 0。

对 **Recordset** 对象使用 **[Requery](recordset-requery-method-dao.md)** 方法将会重置 **RecordCount** 属性，如同重新执行查询一样。

## <a name="example"></a>示例

以下示例演示填充不同类型的 **Recordsets** 之前和之后的 **RecordCount** 属性。

```vb
    Sub RecordCountX() 
     
     Dim dbsNorthwind As Database 
     Dim rstEmployees As Recordset 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
     With dbsNorthwind 
     ' Open table-type Recordset and show RecordCount 
     ' property. 
     Set rstEmployees = .OpenRecordset("Employees") 
     Debug.Print _ 
     "Table-type recordset from Employees table" 
     Debug.Print " RecordCount = " & _ 
     rstEmployees.RecordCount 
     rstEmployees.Close 
     
     ' Open dynaset-type Recordset and show RecordCount 
     ' property before populating the Recordset. 
     Set rstEmployees = .OpenRecordset("Employees", _ 
     dbOpenDynaset) 
     Debug.Print "Dynaset-type recordset " & _ 
     "from Employees table before MoveLast" 
     Debug.Print " RecordCount = " & _ 
     rstEmployees.RecordCount 
     
     ' Show the RecordCount property after populating the 
     ' Recordset. 
     rstEmployees.MoveLast 
     Debug.Print "Dynaset-type recordset " & _ 
     "from Employees table after MoveLast" 
     Debug.Print " RecordCount = " & _ 
     rstEmployees.RecordCount 
     rstEmployees.Close 
     
     ' Open snapshot-type Recordset and show RecordCount 
     ' property before populating the Recordset. 
     Set rstEmployees = .OpenRecordset("Employees", _ 
     dbOpenSnapshot) 
     Debug.Print "Snapshot-type recordset " & _ 
     "from Employees table before MoveLast" 
     Debug.Print " RecordCount = " & _ 
     rstEmployees.RecordCount 
     
     ' Show the RecordCount property after populating the 
     ' Recordset. 
     rstEmployees.MoveLast 
     Debug.Print "Snapshot-type recordset " & _ 
     "from Employees table after MoveLast" 
     Debug.Print " RecordCount = " & _ 
     rstEmployees.RecordCount 
     rstEmployees.Close 
     
     ' Open forward-only-type Recordset and show 
     ' RecordCount property before populating the 
     ' Recordset. 
     Set rstEmployees = .OpenRecordset("Employees", _ 
     dbOpenForwardOnly) 
     Debug.Print "Forward-only-type recordset " & _ 
     "from Employees table before MoveLast" 
     Debug.Print " RecordCount = " & _ 
     rstEmployees.RecordCount 
     
     ' Show the RecordCount property after calling the 
     ' MoveNext method. 
     rstEmployees.MoveNext 
     Debug.Print "Forward-only-type recordset " & _ 
     "from Employees table after MoveNext" 
     Debug.Print " RecordCount = " & _ 
     rstEmployees.RecordCount 
     rstEmployees.Close 
     
     .Close 
     End With 
     
    End Sub
```
