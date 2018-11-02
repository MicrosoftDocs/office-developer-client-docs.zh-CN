---
title: QueryDef.Execute 方法 (DAO)
TOCTitle: Execute Method
ms:assetid: ad9e859e-c6fe-496c-a1f2-a000cf4bebcc
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821728(v=office.15)
ms:contentKeyID: 48547043
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052884
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 165a2703b3b3715ace7326df31477f1f9293be12
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25926211"
---
# <a name="querydefexecute-method-dao"></a>QueryDef.Execute 方法 (DAO)

**适用于**： Access 2013、 Office 2013

对指定的对象执行 SQL 语句。

## <a name="syntax"></a>语法

*表达式*。执行 （***选项***）

*表达式*一个代表**QueryDef**对象的变量。

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
<td><p>Options</p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

为选项，可以使用以下**[RecordsetOptionEnum](recordsetoptionenum-enumeration-dao.md)** 常量。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>常量</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>dbDenyWrite</strong></p></td>
<td><p>拒绝其他用户的写入权限（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong>dbInconsistent</strong></p></td>
<td><p>（默认值）执行不一致的更新（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbConsistent</strong></p></td>
<td><p>执行一致的更新（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong>dbSQLPassThrough</strong></p></td>
<td><p>执行 SQL 传递查询。设置此选项会将 SQL 语句传递给 ODBC 数据库以进行处理（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbFailOnError</strong></p></td>
<td><p>发生错误时回滚更新（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong>dbSeeChanges</strong></p></td>
<td><p>如果其他用户更改您正编辑的数据，则生成运行时错误（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbRunAsync</strong></p></td>
<td><p>异步执行查询（仅适用于 ODBCDirect Connection 和 QueryDef 对象）。</p></td>
</tr>
<tr class="even">
<td><p><strong>一设置</strong></p></td>
<td><p>在不首先调用 SQLPrepare ODBC API 函数的情况下，执行语句（仅适用于 ODBCDirect Connection 和 QueryDef 对象）。</p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。 如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。

> [!NOTE]
> [!注释] 常量 **dbConsistent** 和 **dbInconsistent** 是互斥的。可以在 **OpenRecordset** 的给定实例中使用其中的某一个，但不能同时使用此两者。同时使用 **dbConsistent** 和 **dbInconsistent** 会导致出错。

使用 **[Connection](querydef-recordsaffected-property-dao.md)** 、 **[Database](connection-object-dao.md)** 或 **[QueryDef](database-object-dao.md)** 对象的 **[RecordsAffected](querydef-object-dao.md)** 属性确定受最近的 **[Execute](querydef-execute-method-dao.md)** 方法影响的记录数。例如， **RecordsAffected** 包含执行某个动作查询时删除、更新或插入的记录数。如果使用 **Execute** 方法运行查询，会将 **QueryDef** 对象的 **RecordsAffected** 属性设置为受影响的记录数。

在 Microsoft Access 工作区中，如果提供了一个在语法上正确的 SQL 语句，并且您具有相应的权限，则 **Execute** 方法不会失败 - 即使一行都不能修改或删除，也是如此。因此，在使用 **Execute** 方法运行更新或删除查询时，请始终使用 **dbFailOnError** 选项。如果锁定了任何受影响的记录，因而无法对其进行更新或删除，此选项将生成运行时错误，同时回滚所有成功的更改。

在早期版本的 Microsoft Jet 数据库引擎中，SQL 语句自动嵌入到隐式事务中。如果使用 **dbFailOnError** 执行的语句的一部分失败，则整个语句都会回滚。为了改善性能，从版本 3.5 开始，删除了这些隐式事务。如果要更新早期的 DAO 代码，请务必考虑对 **Execute** 语句使用显式事务。

为了在 Microsoft Access 工作区中，特别是在多用户环境中获取最佳性能，请将 **Execute** 方法嵌套在事务中。对当前的 **[Workspace](workspace-begintrans-method-dao.md)** 对象使用 **[BeginTrans](workspace-object-dao.md)** 方法，然后使用 **Execute** 方法，再对 [Workspace](workspace-committrans-method-dao.md) 使用 ****CommitTrans**** 方法完成事务。这样可以保存磁盘上的更改，并且释放任何在运行查询时放置的锁定。

## <a name="example"></a>示例

以下示例演示同时从 **QueryDef** 对象和 **Database** 对象运行时的 **Execute** 方法。若要使该过程运行，需要使用 ExecuteQueryDef 和 PrintOutput 过程。

```vb
    Sub ExecuteX() 
     
       Dim dbsNorthwind As Database 
       Dim strSQLChange As String 
       Dim strSQLRestore As String 
       Dim qdfChange As QueryDef 
       Dim rstEmployees As Recordset 
       Dim errLoop As Error 
     
       ' Define two SQL statements for action queries. 
       strSQLChange = "UPDATE Employees SET Country = " & _ 
          "'United States' WHERE Country = 'USA'" 
       strSQLRestore = "UPDATE Employees SET Country = " & _ 
          "'USA' WHERE Country = 'United States'" 
     
       Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
       ' Create temporary QueryDef object. 
       Set qdfChange = dbsNorthwind.CreateQueryDef("", _ 
          strSQLChange) 
       Set rstEmployees = dbsNorthwind.OpenRecordset( _ 
          "SELECT LastName, Country FROM Employees", _ 
          dbOpenForwardOnly) 
     
       ' Print report of original data. 
       Debug.Print _ 
          "Data in Employees table before executing the query" 
       PrintOutput rstEmployees 
        
       ' Run temporary QueryDef. 
       ExecuteQueryDef qdfChange, rstEmployees 
        
       ' Print report of new data. 
       Debug.Print _ 
          "Data in Employees table after executing the query" 
       PrintOutput rstEmployees 
     
       ' Run action query to restore data. Trap for errors, 
       ' checking the Errors collection if necessary. 
       On Error GoTo Err_Execute 
       dbsNorthwind.Execute strSQLRestore, dbFailOnError 
       On Error GoTo 0 
     
       ' Retrieve the current data by requerying the recordset. 
       rstEmployees.Requery 
     
       ' Print report of restored data. 
       Debug.Print "Data after executing the query " & _ 
          "to restore the original information" 
       PrintOutput rstEmployees 
     
       rstEmployees.Close 
        
       Exit Sub 
        
    Err_Execute: 
     
       ' Notify user of any errors that result from 
       ' executing the query. 
       If DBEngine.Errors.Count > 0 Then 
          For Each errLoop In DBEngine.Errors 
             MsgBox "Error number: " & errLoop.Number & vbCr & _ 
                errLoop.Description 
          Next errLoop 
       End If 
        
       Resume Next 
     
    End Sub 
     
    Sub ExecuteQueryDef(qdfTemp As QueryDef, _ 
       rstTemp As Recordset) 
     
       Dim errLoop As Error 
        
       ' Run the specified QueryDef object. Trap for errors, 
       ' checking the Errors collection if necessary. 
       On Error GoTo Err_Execute 
       qdfTemp.Execute dbFailOnError 
       On Error GoTo 0 
     
       ' Retrieve the current data by requerying the recordset. 
       rstTemp.Requery 
        
       Exit Sub 
     
    Err_Execute: 
     
       ' Notify user of any errors that result from 
       ' executing the query. 
       If DBEngine.Errors.Count > 0 Then 
          For Each errLoop In DBEngine.Errors 
             MsgBox "Error number: " & errLoop.Number & vbCr & _ 
                errLoop.Description 
          Next errLoop 
       End If 
        
       Resume Next 
     
    End Sub 
     
    Sub PrintOutput(rstTemp As Recordset) 
     
       ' Enumerate Recordset. 
       Do While Not rstTemp.EOF 
          Debug.Print "  " & rstTemp!LastName & _ 
             ", " & rstTemp!Country 
          rstTemp.MoveNext 
       Loop 
     
    End Sub 
```

<br/>

下面的示例演示如何执行参数查询。 Parameters 集合用于设置 myActionQuery 查询的 Organization 参数之前执行查询。

**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。

```vb
    Public Sub ExecParameterQuery()
    
        Dim dbs As DAO.Database
        Dim qdf As DAO.QueryDef
    
        Set dbs = CurrentDb
        Set qdf = dbs.QueryDefs("myActionQuery")
    
        'Set the value of the QueryDef's parameter
        qdf.Parameters("Organization").Value = "Microsoft"
    
        'Execute the query
        qdf.Execute dbFailOnError
    
        'Clean up
        qdf.Close
        Set qdf = Nothing
        Set dbs = Nothing
    
    End Sub
```
