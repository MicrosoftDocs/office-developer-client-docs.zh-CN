---
title: Recordset2 属性 (DAO)
TOCTitle: Index Property
ms:assetid: 614bdf53-aca3-25ef-a23c-50095b345d20
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194872(v=office.15)
ms:contentKeyID: 48545209
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 05a29ff9dbe720fe7c5539639b20e0abdc3c587b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32307299"
---
# <a name="recordset2index-property-dao"></a>Recordset2 属性 (DAO)

**适用于**：Access 2013、Office 2013

设置或返回一个值，该值指示表类型 **[Recordset](index-object-dao.md)** 对象中的当前 **[Index](recordset-object-dao.md)** 对象的名称（仅适用于 Microsoft Access 工作区）。

## <a name="syntax"></a>语法

*表达式*。索引

*表达式*一个代表**Recordset2**对象的变量。

## <a name="remarks"></a>注解

基表中的记录不按任何特定顺序存储。设置 **Index** 属性会更改从数据库返回的记录的顺序；它不影响存储记录的顺序。

必须已经定义了指定的 **Index** 对象。如果将 **Index** 属性设置为不存在的 **Index** 对象，或者当您使用 [**Seek**](recordset2-seek-method-dao.md) 方法时 **Index** 属性不存在，则会发生可捕获的错误。

检查 **TableDef** 对象的 **Indexes** 集合，以确定哪些 **Index** 对象可用于从该 **TableDef** 对象创建的表类型 **Recordset** 对象。

可以为表创建新的索引，方法是创建新的 **Index** 对象，设置其属性，将其追加到基础 **TableDef** 对象的 **Indexes** 集合中，然后重新打开 **Recordset** 对象。

从表类型 **Recordset** 对象返回的记录只能按为基础 **TableDef** 对象定义的索引进行排序。 若要按其他顺序对记录进行排序, 可以使用带有 order by 子句的 SQL 语句打开动态集–、快照或仅向前类型**Recordset**对象。

> [!NOTE]
> - 您不必为表创建索引。对于大型的未编制索引的表，访问特定记录或创建 **Recordset** 对象可能花费很长时间。另一方面，由于所有索引都是自动更新的，创建太多索引会降低更新、追加和删除操作的速度。
> - 从不含索引的表中读取的记录没有特定返回顺序。
> - **index**对象中每个**[Field](field-object-dao.md)** 对象的**[Attributes](field-attributes-property-dao.md)** 属性决定了记录的顺序, 因此决定了该索引使用的访问技术。
> - 唯一索引有助于优化记录的查找。
> - 索引不影响基表的实际顺序，只影响当选择特定索引或打开 **Recordset** 时表类型 **Recordset** 对象访问记录的方式。

## <a name="example"></a>示例

以下示例使用 **Index** 属性来设置表类型 **Recordset** 的不同记录顺序。

```vb
    Sub IndexPropertyX() 
     
       Dim dbsNorthwind As Database 
       Dim tdfEmployees As TableDef 
       Dim rstEmployees As Recordset2 
       Dim idxLoop As Index 
     
       Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
       Set rstEmployees = _ 
          dbsNorthwind.OpenRecordset("Employees") 
       Set tdfEmployees = dbsNorthwind.TableDefs!Employees 
     
       With rstEmployees 
     
          ' Enumerate Indexes collection of Employees table. 
          For Each idxLoop In tdfEmployees.Indexes 
             .Index = idxLoop.Name 
             Debug.Print "Index = " & .Index 
             Debug.Print "  EmployeeID - PostalCode - Name" 
             .MoveFirst 
     
             ' Enumerate Recordset to show the order of records. 
             Do While Not .EOF 
                Debug.Print "    " & !EmployeeID & " - " & _ 
                   !PostalCode & " - " & !FirstName & " " & _ 
                   !LastName 
                .MoveNext 
             Loop 
     
          Next idxLoop 
     
          .Close 
       End With 
     
       dbsNorthwind.Close 
     
    End Sub 
```

<br/>

以下示例通过允许用户根据 ID 编号搜索产品，来演示 **Seek** 方法。

```vb
    Sub SeekX() 
     
       Dim dbsNorthwind As Database 
       Dim rstProducts As Recordset2 
       Dim intFirst As Integer 
       Dim intLast As Integer 
       Dim strMessage As String 
       Dim strSeek As String 
       Dim varBookmark As Variant 
     
       Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
       ' You must open a table-type Recordset to use an index,  
       ' and hence the Seek method. 
       Set rstProducts = _ 
          dbsNorthwind.OpenRecordset("Products", dbOpenTable) 
     
       With rstProducts 
          ' Set the index. 
          .Index = "PrimaryKey" 
     
          ' Get the lowest and highest product IDs. 
          .MoveLast 
          intLast = !ProductID 
          .MoveFirst 
          intFirst = !ProductID 
     
          Do While True 
             ' Display current record information and ask user  
             ' for ID number. 
             strMessage = "Product ID: " & !ProductID & vbCr & _ 
                "Name: " & !ProductName & vbCr & vbCr & _ 
                "Enter a product ID between " & intFirst & _ 
                " and " & intLast & "." 
             strSeek = InputBox(strMessage) 
     
             If strSeek = "" Then Exit Do 
     
             ' Store current bookmark in case the Seek fails. 
             varBookmark = .Bookmark 
     
             .Seek "=", Val(strSeek) 
     
             ' Return to the current record if the Seek fails. 
             If .NoMatch Then 
                MsgBox "ID not found!" 
                .Bookmark = varBookmark 
             End If 
          Loop 
     
          .Close 
       End With 
     
       dbsNorthwind.Close 
     
    End Sub
```
