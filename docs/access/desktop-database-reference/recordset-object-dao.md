---
title: Recordset Object (DAO)
TOCTitle: Recordset Object
ms:assetid: 9774232c-e6da-175b-fc7f-ed2ab7908fa0
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197799(v=office.15)
ms:contentKeyID: 48546469
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3fb327b77a9b17ef83ef48cbe5f9e657f859687b
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466567"
---
# <a name="recordset-object-dao"></a>Recordset Object (DAO)

**适用于**： Access 2013 |Office 2013

**Recordset** 对象代表基表中的记录或通过运行查询得到的记录。

## <a name="remarks"></a>注解

使用 **Recordset** 对象在记录级别处理数据库中的数据。使用 DAO 对象时，几乎可以完全使用 **Recordset** 对象处理数据。所有 **Recordset** 对象都是使用记录（行）和字段（列）构建的。共有五种类型的 **Recordset** 对象：

- 表类型 Recordset - 基表在代码中的表示形式，可用于在单个数据库表中添加、更改或删除记录（仅适用于 Microsoft Access 工作区）。

- 动态集类型 Recordset - 其中可以包含可更新记录的查询结果。动态集类型 **Recordset** 对象是一个动态的记录集，可用于在一个或多个基础数据库表中添加、更改或删除记录。动态集类型 **Recordset** 对象可以包含数据库中的一个或多个表中的字段。此类型对应于 ODBC 键集游标。

- 快照类型 Recordset - 一组记录的静态副本，可用于查找数据或生成报表。快照类型 **Recordset** 对象可以包含数据库中的一个或多个表中的字段，但不能进行更新。此类型对应于 ODBC 静态游标。

- 仅向前类型 Recordset - 除不提供游标外，其他均与快照类型相同。只能在记录中向前滚动。如果只需遍历结果集一次，这种类型可提高性能。此类型对应于 ODBC 仅向前游标。

- 动态类型 Recordset - 一个或多个基表中的查询结果集，可以在该基表中添加、更改或删除行返回查询产生的记录。此外，其他用户在基表中添加、删除或编辑的记录也出现在 **Recordset** 中。此类型对应于 ODBC 动态游标（仅适用于 ODBCDirect 工作区）。

> [!NOTE]
> Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。 如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。

您可以选择您想要创建使用**OpenRecordset**方法的 type 参数的**Recordset**对象的类型。

在 Microsoft Access 工作区中，如果未指定类型，DAO 尝试创建**Recordset**的类型有可用的大多数功能开头表。 如果此类型不可用，DAO 将尝试动态集类型，其次为快照类型，最后为仅向前类型的 **Recordset** 对象。

在适用于 ODBCDirect 工作区中，如果未指定类型，DAO 尝试使用的最快的查询响应，创建**Recordset**的类型开头仅向前型。 如果此类型不可用，DAO 将尝试快照类型，其次为动态集类型，最后为动态类型的 **Recordset** 对象。

使用 Microsoft Access 工作区中的非链接 [**TableDef**](tabledef-object-dao.md) 对象创建 **Recordset** 对象时，将创建表类型 **Recordset** 对象。使用链接表或连接到 Microsoft Access 数据库引擎的 ODBC 数据库中的表只能创建动态集类型或快照类型 **Recordset** 对象。

打开 **Recordset** 对象时，会自动在 **Recordsets** 集合中添加一个新的相应对象；关闭该对象时，会自动删除相应的对象。

> [!NOTE]
> [!注释] 如果使用变量表示 **Recordset** 对象和包含 **Recordset** 的 **Database** 对象，请确保这些变量具有相同的范围或生命周期。例如，如果声明了表示 **Recordset** 对象的公共变量，请确保表示包含了 **Recordset** 的 **Database** 的变量也是公共的，或者是使用 **Static** 关键字在 **Sub** 或 **Function** 过程中声明的。

可根据需要创建任意数目的 **Recordset** 对象变量。不同的 **Recordset** 对象可以在不发生冲突的情况下访问相同的表、查询和字段。

动态集类型、 快照和仅向前类型**Recordset**对象存储在本地内存中。 如果本地内存的空间不足以存储数据，Microsoft Access 数据库引擎会将额外的数据保存到 TEMP 磁盘空间。 如果此空间已耗尽，将发生可捕获的错误。

**Recordset** 对象的默认集合为 **Fields** 集合， **[Field](field-object-dao.md)** 对象的默认属性为 **[Value](field-value-property-dao.md)** 属性。可使用这些默认值简化代码。

在创建 **Recordset** 对象时，如果存在任何记录的话，当前记录将定位到第一条记录。如果不存在任何记录， **RecordCount** 属性设置为 0，并且 **BOF** 和 **EOF** 属性设置为 **True**。

可以使用 **MoveNext**、 **MovePrevious**、 **MoveFirst** 和 **MoveLast** 方法重新定位当前记录。 仅向前类型**Recordset**对象才支持仅**MoveNext**方法。 在使用 Move 方法访问每条记录（或"遍历" **Recordset**）时，可以使用 **BOF** 和 **EOF** 属性检查 **Recordset** 对象的开头或结尾。

对于 Microsoft Access 工作区中的动态集类型和快照类型 **Recordset** 对象，还可以使用 Find 方法（例如 **FindFirst**）根据条件查找特定的记录。如果未找到记录， **NoMatch** 属性将设置为 **True**。对于表类型 **Recordset** 对象，可以使用 **Seek** 方法扫描记录。

**Type** 属性指示所创建的 **Recordset** 对象的类型， **Updatable** 属性指示是否可以更改对象的记录。

**TableDef** 对象中存储了有关基表结构的信息，例如每个 **Field** 对象及任何 **Index** 对象的名称和数据类型。

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
                Debug.Print "  " & .Name 
     
                ' Enumerate Properties collection of each 
                ' Recordset object. Trap for any  
                ' properties whose values are invalid in  
                ' this context. 
                For Each prpLoop In .Properties 
                   On Error Resume Next 
                   If prpLoop <> "" Then Debug.Print _ 
                      "    " & prpLoop.Name & _ 
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

<br/>

以下示例使用 **OpenRecordset** 方法打开五个不同的 **Recordset** 对象并显示其内容。若要使该过程正常运行，需要使用 OpenRecordsetOutput 过程。

```vb
    Sub OpenRecordsetX() 
     
       Dim wrkAcc As Workspace 
       Dim wrkODBC As Workspace 
       Dim dbsNorthwind As Database 
       Dim conPubs As Connection 
       Dim rstTemp As Recordset 
       Dim rstTemp2 As Recordset 
     
       ' Open Microsoft Access and ODBCDirect workspaces, Microsoft  
       ' Access database, and ODBCDirect connection. 
       Set wrkAcc = CreateWorkspace("", "admin", "", dbUseJet) 
       Set wrkODBC = CreateWorkspace("", "admin", "", dbUseODBC) 
       Set dbsNorthwind = wrkAcc.OpenDatabase("Northwind.mdb") 
        
       ' Note: The DSN referenced below must be set to  
       '       use Microsoft Windows NT Authentication Mode to  
       '       authorize user access to the Microsoft SQL Server. 
       Set conPubs = wrkODBC.OpenConnection("", , , _ 
          "ODBC;DATABASE=pubs;DSN=Publishers") 
     
       ' Open five different Recordset objects and display the  
       ' contents of each. 
     
       Debug.Print "Opening forward-only-type recordset " & _ 
          "where the source is a QueryDef object..." 
       Set rstTemp = dbsNorthwind.OpenRecordset( _ 
          "Ten Most Expensive Products", dbOpenForwardOnly) 
       OpenRecordsetOutput rstTemp 
     
       Debug.Print "Opening read-only dynaset-type " & _ 
          "recordset where the source is an SQL statement..." 
       Set rstTemp = dbsNorthwind.OpenRecordset( _ 
          "SELECT * FROM Employees", dbOpenDynaset, dbReadOnly) 
       OpenRecordsetOutput rstTemp 
     
       ' Use the Filter property to retrieve only certain  
       ' records with the next OpenRecordset call. 
       Debug.Print "Opening recordset from existing " & _ 
          "Recordset object to filter records..." 
       rstTemp.Filter = "LastName >= 'M'" 
       Set rstTemp2 = rstTemp.OpenRecordset() 
       OpenRecordsetOutput rstTemp2 
     
       Debug.Print "Opening dynamic-type recordset from " & _ 
          "an ODBC connection..." 
       Set rstTemp = conPubs.OpenRecordset( _ 
          "SELECT * FROM stores", dbOpenDynamic) 
       OpenRecordsetOutput rstTemp 
     
       ' Use the StillExecuting property to determine when the  
       ' Recordset is ready for manipulation. 
       Debug.Print "Opening snapshot-type recordset based " & _ 
          "on asynchronous query to ODBC connection..." 
       Set rstTemp = conPubs.OpenRecordset("publishers", _ 
          dbOpenSnapshot, dbRunAsync) 
       Do While rstTemp.StillExecuting 
          Debug.Print "  [still executing...]" 
       Loop 
       OpenRecordsetOutput rstTemp 
     
       rstTemp.Close 
       dbsNorthwind.Close 
       conPubs.Close 
       wrkAcc.Close 
       wrkODBC.Close 
     
    End Sub 
     
    Sub OpenRecordsetOutput(rstOutput As Recordset) 
     
       ' Enumerate the specified Recordset object. 
       With rstOutput 
          Do While Not .EOF 
             Debug.Print , .Fields(0), .Fields(1) 
             .MoveNext 
          Loop 
       End With 
     
    End Sub 
```

<br/>

以下示例打开一个动态类型 **Recordset** 对象，然后枚举其记录。

```vb
    Sub dbOpenDynamicX() 
     
       Dim wrkMain As Workspace 
       Dim conMain As Connection 
       Dim qdfTemp As QueryDef 
       Dim rstTemp As Recordset 
       Dim strSQL As String 
       Dim intLoop As Integer 
     
       ' Create ODBC workspace and open connection to 
       ' SQL Server database. 
       Set wrkMain = CreateWorkspace("ODBCWorkspace", _ 
          "admin", "", dbUseODBC) 
           
       ' Note: The DSN referenced below must be configured to  
       '       use Microsoft Windows NT Authentication Mode to  
       '       authorize user access to the Microsoft SQL Server.     
       Set conMain = wrkMain.OpenConnection("Publishers", _ 
          dbDriverNoPrompt, False, _ 
          "ODBC;DATABASE=pubs;DSN=Publishers") 
           
       ' Open dynamic-type recordset. 
       Set rstTemp = _ 
          conMain.OpenRecordset("authors", _ 
          dbOpenDynamic) 
     
       With rstTemp 
          Debug.Print "Dynamic-type recordset: " & .Name 
     
          ' Enumerate records. 
          Do While Not .EOF 
             Debug.Print "    " & !au_lname & ", " & _ 
                !au_fname 
             .MoveNext 
          Loop 
     
          .Close 
       End With 
     
       conMain.Close 
       wrkMain.Close 
     
    End Sub 
```

<br/>

以下示例打开一个动态集类型 **Recordset**，然后显示其字段的可更新程度。

```vb
    Sub dbOpenDynasetX() 
     
       Dim dbsNorthwind As Database 
       Dim rstInvoices As Recordset 
       Dim fldLoop As Field 
     
       Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
       Set rstInvoices = _ 
          dbsNorthwind.OpenRecordset("Invoices", dbOpenDynaset) 
     
       With rstInvoices 
          Debug.Print "Dynaset-type recordset: " & .Name 
     
          If .Updatable Then 
             Debug.Print "  Updatable fields:" 
     
             ' Enumerate Fields collection of dynaset-type 
             ' Recordset object, print only updatable 
             ' fields. 
             For Each fldLoop In .Fields 
                If fldLoop.DataUpdatable Then 
                   Debug.Print "    " & fldLoop.Name 
                End If 
             Next fldLoop 
     
          End If 
     
          .Close 
       End With 
     
       dbsNorthwind.Close 
     
    End Sub 
```

<br/>

以下示例打开一个仅向前类型 **Recordset**，演示其只读特征，然后使用 **MoveNext** 方法遍历 **Recordset**。

```vb 
Sub dbOpenForwardOnlyX() 
 
   Dim dbsNorthwind As Database 
   Dim rstEmployees As Recordset 
   Dim fldLoop As Field 
 
   Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
   ' Open a forward-only-type Recordset object. Only the  
   ' MoveNext and Move methods may be used to navigate  
   ' through the recordset. 
   Set rstEmployees = _ 
      dbsNorthwind.OpenRecordset("Employees", _ 
      dbOpenForwardOnly) 
 
   With rstEmployees 
      Debug.Print "Forward-only-type recordset: " & _ 
         .Name & ", Updatable = " & .Updatable 
 
      Debug.Print "  Field - DataUpdatable" 
      ' Enumerate Fields collection, printing the Name and  
      ' DataUpdatable properties of each Field object. 
      For Each fldLoop In .Fields 
         Debug.Print "    " & _ 
            fldLoop.Name & " - " & fldLoop.DataUpdatable 
      Next fldLoop 
 
      Debug.Print "  Data" 
      ' Enumerate the recordset. 
      Do While Not .EOF 
         Debug.Print "    " & !FirstName & " " & _ 
            !LastName 
         .MoveNext 
      Loop 
 
      .Close 
   End With 
 
   dbsNorthwind.Close 
 
End Sub 
```

<br/>

以下示例打开一个快照类型 **Recordset**，演示其只读特征。

```vb
    Sub dbOpenSnapshotX() 
     
       Dim dbsNorthwind As Database 
       Dim rstEmployees As Recordset 
       Dim prpLoop As Property 
     
       Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
       Set rstEmployees = _ 
          dbsNorthwind.OpenRecordset("Employees", _ 
          dbOpenSnapshot) 
     
       With rstEmployees 
          Debug.Print "Snapshot-type recordset: " & _ 
             .Name 
     
          ' Enumerate the Properties collection of the 
          ' snapshot-type Recordset object, trapping for 
          ' any properties whose values are invalid in  
          ' this context. 
          For Each prpLoop In .Properties 
             On Error Resume Next 
             Debug.Print "  " & _ 
                prpLoop.Name & " = " & prpLoop 
             On Error Goto 0 
          Next prpLoop 
     
          .Close 
       End With 
     
       dbsNorthwind.Close 
     
    End Sub 
```

<br/>

以下示例打开一个表类型 **Recordset**，并设置其 **Index** 属性，然后枚举其记录。

```vb
    Sub dbOpenTableX() 
     
       Dim dbsNorthwind As Database 
       Dim rstEmployees As Recordset 
     
       Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
       ' dbOpenTable is default. 
       Set rstEmployees = _ 
          dbsNorthwind.OpenRecordset("Employees") 
     
       With rstEmployees 
          Debug.Print "Table-type recordset: " & .Name 
     
          ' Use predefined index. 
          .Index = "LastName" 
          Debug.Print "  Index = " & .Index 
     
          ' Enumerate records. 
          Do While Not .EOF 
             Debug.Print "    " & !LastName & ", " & _ 
                !FirstName 
             .MoveNext 
          Loop 
     
          .Close 
       End With 
     
       dbsNorthwind.Close 
     
    End Sub 
```

<br/>

下面的示例演示如何使用 Seek 方法来查找链接表中的记录。

**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。


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

<br/>

以下示例说明如何打开基于参数查询的 Recordset。

```vb
    Dim dbs As DAO.Database
    Dim qdf As DAO.QueryDef
    Dim rst As DAO.Recordset
    
    Set dbs = CurrentDb
    
    'Get the parameter query
    Set qfd = dbs.QueryDefs("qryMyParameterQuery")
    
    'Supply the parameter value
    qdf.Parameters("EnterStartDate") = Date
    qdf.Parameters("EnterEndDate") = Date + 7
    
    'Open a Recordset based on the parameter query
    Set rst = qdf.OpenRecordset()
```

<br/>

以下示例说明如何打开基于表或查询的 Recordset。

```vb
    Dim dbs As DAO.Database
    Dim rsTable As DAO.Recordset
    Dim rsQuery As DAO.Recordset
    
    Set dbs = CurrentDb
    
    'Open a table-type Recordset
    Set rsTable = dbs.OpenRecordset("Table1", dbOpenTable)
    
    'Open a dynaset-type Recordset using a saved query
    Set rsQuery = dbs.OpenRecordset("qryMyQuery", dbOpenDynaset)
```

<br/>

以下示例说明如何打开基于结构化查询语言 (SQL) 语句的 Recordset。

```vb
    Dim dbs As DAO.Database
    Dim rsSQL As DAO.Recordset
    Dim strSQL As String
    
    Set dbs = CurrentDb
    
    'Open a snapshot-type Recordset based on an SQL statement
    strSQL = "SELECT * FROM Table1 WHERE Field2 = 33"
    Set rsSQL = dbs.OpenRecordset(strSQL, dbOpenSnapshot)
```

<br/>

下面的示例演示如何使用 FindFirst 和 FindNext 方法在记录集中查找记录。

```vb
    Sub FindOrgName()
    
        Dim dbs As DAO.Database
        Dim rst As DAO.Recordset
        
        'Get the database and Recordset
        Set dbs = CurrentDb
        Set rst = dbs.OpenRecordset("tblCustomers")
    
        'Search for the first matching record   
        rst.FindFirst "[OrgName] LIKE '*parts*'"
        
        'Check the result
        If rst.NoMatch Then
            MsgBox "Record not found."
            GotTo Cleanup
        Else
            Do While Not rst.NoMatch
                MsgBox "Customer name: " & rst!CustName
                rst.FindNext "[OrgName] LIKE '*parts*'"
            Loop
    
            'Search for the next matching record
            rst.FindNext "[OrgName] LIKE '*parts*'"
        End If
       
        Cleanup:
            rst.Close
            Set rst = Nothing
            Set dbs = Nothing
    
    End Sub
```

<br/>

下面的示例演示如何将查询的结果复制到新的 Microsoft Excel 工作簿中的工作表。

```vb
    Public Sub CopyDataFromQuery( _
        xlApp As Excel.Application, _
        strQueryName As String)
    
        ' If the xlApp object exists
        If Not xlApp Is Nothing Then
        
            ' If the Workbook exists
            If xlApp.Workbooks.Count = 1 Then
            
                ' Create Recrodset Object from the Query
                Dim rsQuery As DAO.Recordset
                Set rsQuery = Application.CurrentDb.OpenRecordset(strQueryName)
                
                ' Get the Cells object
                Dim Cells As Object
                Set Cells = xlApp.Workbooks(1).ActiveSheet.Cells
                
                ' Copy the Data from the Query into the Sheet
                Cells.CopyFromRecordset rsQuery
                
            End If
        End If
    
    End Sub
```

