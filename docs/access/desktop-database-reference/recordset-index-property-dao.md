---
title: Recordset.Index 属性 (DAO)
TOCTitle: Index Property
ms:assetid: 54626de0-eb51-31f2-bf24-e29cbfbbaa02
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194103(v=office.15)
ms:contentKeyID: 48544895
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052906
f1_categories:
- Office.Version=v15
localization_priority: Priority
ms.openlocfilehash: f475635424cfb9ed8ddab4025d6a944bdedd39fd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32300523"
---
# <a name="recordsetindex-property-dao"></a>Recordset.Index 属性 (DAO)

**适用于**：Access 2013、Office 2013

设置或返回指示表类型 **[Recordset](recordset-object-dao.md)** 对象中当前 **[Index](index-object-dao.md)** 对象名称的一个值（仅适用于 Microsoft Access 工作区）。

## <a name="syntax"></a>语法

*表达式* .Index

*表达式* 一个表示 **Recordset** 对象的变量。

## <a name="remarks"></a>说明

基表中的记录不按任何特定顺序存储。设置 **Index** 属性会更改从数据库返回的记录的顺序；它不影响存储记录的顺序。

必须已经定义了指定的 **Index** 对象。如果将 **Index** 属性设置为不存在的 **Index** 对象，或者当您使用 [**Seek**](recordset-seek-method-dao.md) 方法时 **Index** 属性不存在，则会发生可捕获的错误。

检查 **TableDef** 对象的 **Indexes** 集合，以确定哪些 **Index** 对象可用于从该 **TableDef** 对象创建的表类型 **Recordset** 对象。

可以为表创建新的索引，方法是创建新的 **Index** 对象，设置其属性，将其追加到基础 **TableDef** 对象的 **Indexes** 集合中，然后重新打开 **Recordset** 对象。

从表类型 **Recordset** 对象返回的记录只能按为基础 **TableDef** 对象定义的索引进行排序。 若要按其他顺序对记录进行排序，可以使用带有 ORDER BY 子句的 SQL 语句打开动态集类型、快照类型或仅向前类型的 **Recordset** 对象。


> [!NOTE]
> - 您不必为表创建索引。对于大型的未编制索引的表，访问特定记录或创建 **Recordset** 对象可能花费很长时间。另一方面，由于所有索引都是自动更新的，创建太多索引会降低更新、追加和删除操作的速度。
> - 从不含索引的表中读取的记录没有特定返回顺序。
> - **Index** 对象中的每个 **[Field](field-object-dao.md)** 对象的 **[Attributes](field-attributes-property-dao.md)** 属性决定了记录的顺序，因此决定了对该索引使用的访问技术。
> - 唯一索引有助于优化记录的查找。
> - 索引不影响基表的实际顺序，只影响当选择特定索引或打开 **Recordset** 时表类型 **Recordset** 对象访问记录的方式。


## <a name="example"></a>示例

本示例使用 **Index** 属性设置表类型 **Recordset** 的不同记录顺序。

```vb
    Sub IndexPropertyX() 
     
       Dim dbsNorthwind As Database 
       Dim tdfEmployees As TableDef 
       Dim rstEmployees As Recordset 
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

本示例演示了 **Seek** 方法，允许用户基于 ID 号码搜索产品。

```vb
    Sub SeekX() 
     
       Dim dbsNorthwind As Database 
       Dim rstProducts As Recordset 
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

<br/>

以下示例说明如何使用 Seek 方法在链接的表中查找记录。

**示例代码提供方：**[Microsoft Access 2010 程序员参考](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。

```vb
    Sub TestSeek()
        ' Get the path to the external database that contains
        ' the tblCustomers table we're going to search.
        Dim strMyExternalDatabase
        Dim dbs    As DAO.Database
        Dim dbsExt As DAO.Database
        Dim rst    As DAO.Recordset
        Dim tdf    As DAO.TableDef
        
        Set dbs = CurrentDb()
        Set tdf = dbs.TableDefs("tblCustomers")
        strMyExternalDatabase = Mid(tdf.Connect, 11)
        
        'Open the database that contains the table that is linked
        Set dbsExt = OpenDatabase(strMyExternalDatabase)
        
        'Open a table-type recordset against the external table
        Set rst = dbsExt.OpenRecordset("tblCustomers", dbOpenTable)
        
        'Specify which index to search on
        rst.Index = "PrimaryKey"
        
        'Specify the criteria
        rst.Seek "=", 123
        
        'Check the result
        If rst.NoMatch Then
            MsgBox "Record not found."
        Else
            MsgBox "Customer name: " & rst!CustName
        End If
        
        rst.Close
        dbs.Close
        dbsExt.Close
        Set rst = Nothing
        Set tdf = Nothing
        Set dbs = Nothing
        
        
    End Sub
```
