---
title: Recordsets Collection (DAO)
TOCTitle: Recordsets Collection
ms:assetid: 246d9a78-4ce8-6393-982b-77ac00cd85bb
ms:mtpsurl: https://msdn.microsoft.com/library/Ff191819(v=office.15)
ms:contentKeyID: 48543756
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 1a32c52f60ed8c7bd68f32ed9986638bffcdec84
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25868999"
---
# <a name="recordsets-collection-dao"></a>Recordsets Collection (DAO)

**适用于**： Access 2013、 Office 2013

**Recordsets** 集合包含 **Connection** 或 **Database** 对象中所有打开的 **Recordset** 对象。

## <a name="remarks"></a>注解

使用 DAO 对象时，几乎可以完全使用 **Recordset** 对象来处理数据。

打开 **Recordset** 对象时，会自动在 **Recordsets** 集合中添加一个新的 **Recordset** 对象；关闭该对象时，会自动删除该对象。

可根据需要创建任意数目的 **Recordset** 对象变量。不同的 **Recordset** 对象可以在不发生冲突的情况下访问相同的表、查询和字段。

若要按照序号或 **Name** 属性设置来引用集合中的 **Recordset** 对象，可以使用下列任何一种语法形式：

- **Recordsets**(0)

- **记录集**("name")

- **记录集**\!\[名称\]

> [!NOTE]
> [!注释] 可以多次打开同一个数据源或数据库中的 **Recordset** 对象，并在 **Recordsets** 集合中创建重复的名称。应该将 **Recordset** 对象分配给对象变量，并通过变量名来引用它们。

## <a name="example"></a>示例

以下示例通过打开四个不同类型的 **Recordsets**，枚举当前 **Database** 的 Recordsets 集合，以及枚举每个 **Recordset** 的 **Properties** 集合，演示 **Recordset** 对象和 **Recordsets** 集合。

```vb
    Sub RecordsetX() 
     
     Dim dbsNorthwind As Database 
     Dim rstTable As Recordset 
     Dim rstDynaset As Recordset 
     Dim rstSnapshot As Recordset 
     Dim rstForwardOnly As Recordset 
     Dim rstLoop As Recordset 
     Dim prpLoop As Property 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
     With dbsNorthwind 
     
     ' Open one of each type of Recordset object. 
     Set rstTable = .OpenRecordset("Categories", _ 
     dbOpenTable) 
     Set rstDynaset = .OpenRecordset("Employees", _ 
     dbOpenDynaset) 
     Set rstSnapshot = .OpenRecordset("Shippers", _ 
     dbOpenSnapshot) 
     Set rstForwardOnly = .OpenRecordset _ 
     ("Employees", dbOpenForwardOnly) 
     
     Debug.Print "Recordsets in Recordsets " & _ 
     "collection of dbsNorthwind" 
     
     ' Enumerate Recordsets collection. 
     For Each rstLoop In .Recordsets 
     
     With rstLoop 
     Debug.Print " " & .Name 
     
     ' Enumerate Properties collection of each 
     ' Recordset object. Trap for any 
     ' properties whose values are invalid in 
     ' this context. 
     For Each prpLoop In .Properties 
     On Error Resume Next 
     If prpLoop <> "" Then Debug.Print _ 
     " " & prpLoop.Name & _ 
     " = " & prpLoop 
     On Error GoTo 0 
     Next prpLoop 
     
     End With 
     
     Next rstLoop 
     
     rstTable.Close 
     rstDynaset.Close 
     rstSnapshot.Close 
     rstForwardOnly.Close 
     
     .Close 
     End With 
     
    End Sub
```
