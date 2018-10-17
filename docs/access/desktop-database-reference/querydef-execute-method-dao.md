---
title: QueryDef.Execute Method (DAO)
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
ms.openlocfilehash: d3438392976051f744f3a449b02cce6aa1c23e8b
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466536"
---
# <a name="querydefexecute-method-dao"></a><span data-ttu-id="102dc-102">QueryDef.Execute Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="102dc-102">QueryDef.Execute Method (DAO)</span></span>

<span data-ttu-id="102dc-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="102dc-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="102dc-104">对指定的对象执行 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="102dc-104">Executes an SQL statement on the specified object.</span></span>

## <a name="syntax"></a><span data-ttu-id="102dc-105">语法</span><span class="sxs-lookup"><span data-stu-id="102dc-105">Syntax</span></span>

<span data-ttu-id="102dc-106">*表达式*。执行 （***选项***）</span><span class="sxs-lookup"><span data-stu-id="102dc-106">*expression* .Execute(***Options***)</span></span>

<span data-ttu-id="102dc-107">*表达式*一个代表**QueryDef**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="102dc-107">*expression* A variable that represents a **QueryDef** object.</span></span>

### <a name="parameters"></a><span data-ttu-id="102dc-108">参数</span><span class="sxs-lookup"><span data-stu-id="102dc-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="102dc-109">名称</span><span class="sxs-lookup"><span data-stu-id="102dc-109">Name</span></span></p></th>
<th><p><span data-ttu-id="102dc-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="102dc-110">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="102dc-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="102dc-111">Data Type</span></span></p></th>
<th><p><span data-ttu-id="102dc-112">说明</span><span class="sxs-lookup"><span data-stu-id="102dc-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="102dc-113">Options</span><span class="sxs-lookup"><span data-stu-id="102dc-113">Options</span></span></p></td>
<td><p><span data-ttu-id="102dc-114">可选</span><span class="sxs-lookup"><span data-stu-id="102dc-114">Optional</span></span></p></td>
<td><p><span data-ttu-id="102dc-115"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="102dc-115"><strong>Variant</strong></span></span></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="102dc-116">说明</span><span class="sxs-lookup"><span data-stu-id="102dc-116">Remarks</span></span>

<span data-ttu-id="102dc-117">为选项，可以使用以下**[RecordsetOptionEnum](recordsetoptionenum-enumeration-dao.md)** 常量。</span><span class="sxs-lookup"><span data-stu-id="102dc-117">You can use the following **[RecordsetOptionEnum](recordsetoptionenum-enumeration-dao.md)** constants for Options.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="102dc-118">常量</span><span class="sxs-lookup"><span data-stu-id="102dc-118">Constant</span></span></p></th>
<th><p><span data-ttu-id="102dc-119">说明</span><span class="sxs-lookup"><span data-stu-id="102dc-119">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="102dc-120"><strong>dbDenyWrite</strong></span><span class="sxs-lookup"><span data-stu-id="102dc-120"><strong>dbDenyWrite</strong></span></span></p></td>
<td><p><span data-ttu-id="102dc-121">拒绝其他用户的写入权限（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="102dc-121">Denies write permission to other users (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="102dc-122"><strong>dbInconsistent</strong></span><span class="sxs-lookup"><span data-stu-id="102dc-122"><strong>dbInconsistent</strong></span></span></p></td>
<td><p><span data-ttu-id="102dc-123">（默认值）执行不一致的更新（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="102dc-123">(Default) Executes inconsistent updates (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="102dc-124"><strong>dbConsistent</strong></span><span class="sxs-lookup"><span data-stu-id="102dc-124"><strong>dbConsistent</strong></span></span></p></td>
<td><p><span data-ttu-id="102dc-125">执行一致的更新（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="102dc-125">Executes consistent updates (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="102dc-126"><strong>dbSQLPassThrough</strong></span><span class="sxs-lookup"><span data-stu-id="102dc-126"><strong>dbSQLPassThrough</strong></span></span></p></td>
<td><p><span data-ttu-id="102dc-p101">执行 SQL 传递查询。设置此选项会将 SQL 语句传递给 ODBC 数据库以进行处理（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="102dc-p101">Executes an SQL pass-through query. Setting this option passes the SQL statement to an ODBC database for processing (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="102dc-129"><strong>dbFailOnError</strong></span><span class="sxs-lookup"><span data-stu-id="102dc-129"><strong>dbFailOnError</strong></span></span></p></td>
<td><p><span data-ttu-id="102dc-130">发生错误时回滚更新（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="102dc-130">Rolls back updates if an error occurs (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="102dc-131"><strong>dbSeeChanges</strong></span><span class="sxs-lookup"><span data-stu-id="102dc-131"><strong>dbSeeChanges</strong></span></span></p></td>
<td><p><span data-ttu-id="102dc-132">如果其他用户更改您正编辑的数据，则生成运行时错误（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="102dc-132">Generates a run-time error if another user is changing data you are editing (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="102dc-133"><strong>dbRunAsync</strong></span><span class="sxs-lookup"><span data-stu-id="102dc-133"><strong>dbRunAsync</strong></span></span></p></td>
<td><p><span data-ttu-id="102dc-134">异步执行查询（仅适用于 ODBCDirect Connection 和 QueryDef 对象）。</span><span class="sxs-lookup"><span data-stu-id="102dc-134">Executes the query asynchronously (ODBCDirect Connection and QueryDef objects only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="102dc-135"><strong>一设置</strong></span><span class="sxs-lookup"><span data-stu-id="102dc-135"><strong>dbExecDirect</strong></span></span></p></td>
<td><p><span data-ttu-id="102dc-136">在不首先调用 SQLPrepare ODBC API 函数的情况下，执行语句（仅适用于 ODBCDirect Connection 和 QueryDef 对象）。</span><span class="sxs-lookup"><span data-stu-id="102dc-136">Executes the statement without first calling SQLPrepare ODBC API function (ODBCDirect Connection and QueryDef objects only).</span></span></p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> <span data-ttu-id="102dc-137">Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="102dc-137">ODBCDirect workspaces are not supported in Microsoft Access 2013.</span></span> <span data-ttu-id="102dc-138">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="102dc-138">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span>

> [!NOTE]
> <span data-ttu-id="102dc-p103">[!注释] 常量 **dbConsistent** 和 **dbInconsistent** 是互斥的。可以在 **OpenRecordset** 的给定实例中使用其中的某一个，但不能同时使用此两者。同时使用 **dbConsistent** 和 **dbInconsistent** 会导致出错。</span><span class="sxs-lookup"><span data-stu-id="102dc-p103">The constants **dbConsistent** and **dbInconsistent** are mutually exclusive. You can use one or the other, but not both in a given instance of **OpenRecordset**. Using both **dbConsistent** and **dbInconsistent** causes an error.</span></span>

<span data-ttu-id="102dc-p104">使用 **[Connection](querydef-recordsaffected-property-dao.md)** 、 **[Database](connection-object-dao.md)** 或 **[QueryDef](database-object-dao.md)** 对象的 **[RecordsAffected](querydef-object-dao.md)** 属性确定受最近的 **[Execute](querydef-execute-method-dao.md)** 方法影响的记录数。例如， **RecordsAffected** 包含执行某个动作查询时删除、更新或插入的记录数。如果使用 **Execute** 方法运行查询，会将 **QueryDef** 对象的 **RecordsAffected** 属性设置为受影响的记录数。</span><span class="sxs-lookup"><span data-stu-id="102dc-p104">Use the **[RecordsAffected](querydef-recordsaffected-property-dao.md)** property of the **[Connection](connection-object-dao.md)**, **[Database](database-object-dao.md)**, or **[QueryDef](querydef-object-dao.md)** object to determine the number of records affected by the most recent **[Execute](querydef-execute-method-dao.md)** method. For example, **RecordsAffected** contains the number of records deleted, updated, or inserted when executing an action query. When you use the **Execute** method to run a query, the **RecordsAffected** property of the **QueryDef** object is set to the number of records affected.</span></span>

<span data-ttu-id="102dc-p105">在 Microsoft Access 工作区中，如果提供了一个在语法上正确的 SQL 语句，并且您具有相应的权限，则 **Execute** 方法不会失败 - 即使一行都不能修改或删除，也是如此。因此，在使用 **Execute** 方法运行更新或删除查询时，请始终使用 **dbFailOnError** 选项。如果锁定了任何受影响的记录，因而无法对其进行更新或删除，此选项将生成运行时错误，同时回滚所有成功的更改。</span><span class="sxs-lookup"><span data-stu-id="102dc-p105">In a Microsoft Access workspace, if you provide a syntactically correct SQL statement and have the appropriate permissions, the **Execute** method won't fail — even if not a single row can be modified or deleted. Therefore, always use the **dbFailOnError** option when using the **Execute** method to run an update or delete query. This option generates a run-time error and rolls back all successful changes if any of the records affected are locked and can't be updated or deleted.</span></span>

<span data-ttu-id="102dc-p106">在早期版本的 Microsoft Jet 数据库引擎中，SQL 语句自动嵌入到隐式事务中。如果使用 **dbFailOnError** 执行的语句的一部分失败，则整个语句都会回滚。为了改善性能，从版本 3.5 开始，删除了这些隐式事务。如果要更新早期的 DAO 代码，请务必考虑对 **Execute** 语句使用显式事务。</span><span class="sxs-lookup"><span data-stu-id="102dc-p106">In earlier versions of the Microsoft Jet database engine, SQL statements were automatically embedded in implicit transactions. If part of a statement executed with **dbFailOnError** failed, the entire statement would be rolled back. To improve performance, these implicit transactions were removed starting with version 3.5. If you are updating older DAO code, be sure to consider using explicit transactions around **Execute** statements.</span></span>

<span data-ttu-id="102dc-p107">为了在 Microsoft Access 工作区中，特别是在多用户环境中获取最佳性能，请将 **Execute** 方法嵌套在事务中。对当前的 **[Workspace](workspace-begintrans-method-dao.md)** 对象使用 **[BeginTrans](workspace-object-dao.md)** 方法，然后使用 **Execute** 方法，再对 [Workspace](workspace-committrans-method-dao.md) 使用 \*\*\*\*CommitTrans\*\*\*\* 方法完成事务。这样可以保存磁盘上的更改，并且释放任何在运行查询时放置的锁定。</span><span class="sxs-lookup"><span data-stu-id="102dc-p107">For best performance in a Microsoft Access workspace, especially in a multiuser environment, nest the **Execute** method inside a transaction. Use the **[BeginTrans](workspace-begintrans-method-dao.md)** method on the current **[Workspace](workspace-object-dao.md)** object, then use the **Execute** method, and complete the transaction by using the **[CommitTrans](workspace-committrans-method-dao.md)** method on the **Workspace**. This saves changes on disk and frees any locks placed while the query is running.</span></span>

## <a name="example"></a><span data-ttu-id="102dc-155">示例</span><span class="sxs-lookup"><span data-stu-id="102dc-155">Example</span></span>

<span data-ttu-id="102dc-p108">以下示例演示同时从 **QueryDef** 对象和 **Database** 对象运行时的 **Execute** 方法。若要使该过程运行，需要使用 ExecuteQueryDef 和 PrintOutput 过程。</span><span class="sxs-lookup"><span data-stu-id="102dc-p108">This example demonstrates the **Execute** method when run from both a **QueryDef** object and a **Database** object. The ExecuteQueryDef and PrintOutput procedures are required for this procedure to run.</span></span>

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

<span data-ttu-id="102dc-158">下面的示例演示如何执行参数查询。</span><span class="sxs-lookup"><span data-stu-id="102dc-158">The following example shows how to execute a parameter query.</span></span> <span data-ttu-id="102dc-159">Parameters 集合用于设置 myActionQuery 查询的 Organization 参数之前执行查询。</span><span class="sxs-lookup"><span data-stu-id="102dc-159">The Parameters collection is used to set the Organization parameter of the myActionQuery query before the query is executed.</span></span>

<span data-ttu-id="102dc-160">**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="102dc-160">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

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