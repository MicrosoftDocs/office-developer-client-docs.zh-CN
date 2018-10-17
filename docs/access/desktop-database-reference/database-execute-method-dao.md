---
title: Database.Execute Method (DAO)
TOCTitle: Execute Method
ms:assetid: 9294d530-f70f-e1ed-3990-ce128de4378b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197654(v=office.15)
ms:contentKeyID: 48546378
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 1c66e6d3297359b3f3584932d8a1faa5dbee0fd7
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466012"
---
# <a name="databaseexecute-method-dao"></a><span data-ttu-id="cfe27-102">Database.Execute Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="cfe27-102">Database.Execute Method (DAO)</span></span>

<span data-ttu-id="cfe27-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="cfe27-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="cfe27-104">对指定的对象运行动作查询，或执行 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="cfe27-104">Runs an action query or executes an SQL statement on the specified object.</span></span>

## <a name="syntax"></a><span data-ttu-id="cfe27-105">语法</span><span class="sxs-lookup"><span data-stu-id="cfe27-105">Syntax</span></span>

<span data-ttu-id="cfe27-106">*表达式*。执行 （***查询***，***选项***）</span><span class="sxs-lookup"><span data-stu-id="cfe27-106">*expression* .Execute(***Query***, ***Options***)</span></span>

<span data-ttu-id="cfe27-107">*表达式*一个代表**Database**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="cfe27-107">*expression* A variable that represents a **Database** object.</span></span>

### <a name="parameters"></a><span data-ttu-id="cfe27-108">参数</span><span class="sxs-lookup"><span data-stu-id="cfe27-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="cfe27-109">名称</span><span class="sxs-lookup"><span data-stu-id="cfe27-109">Name</span></span></p></th>
<th><p><span data-ttu-id="cfe27-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="cfe27-110">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="cfe27-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="cfe27-111">Data Type</span></span></p></th>
<th><p><span data-ttu-id="cfe27-112">说明</span><span class="sxs-lookup"><span data-stu-id="cfe27-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cfe27-113">Query</span><span class="sxs-lookup"><span data-stu-id="cfe27-113">Query</span></span></p></td>
<td><p><span data-ttu-id="cfe27-114">必需</span><span class="sxs-lookup"><span data-stu-id="cfe27-114">Required</span></span></p></td>
<td><p><span data-ttu-id="cfe27-115"><strong>字符串</strong></span><span class="sxs-lookup"><span data-stu-id="cfe27-115"><strong>String</strong></span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfe27-116">选项</span><span class="sxs-lookup"><span data-stu-id="cfe27-116">Options</span></span></p></td>
<td><p><span data-ttu-id="cfe27-117">可选</span><span class="sxs-lookup"><span data-stu-id="cfe27-117">Optional</span></span></p></td>
<td><p><span data-ttu-id="cfe27-118"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="cfe27-118"><strong>Variant</strong></span></span></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="cfe27-119">说明</span><span class="sxs-lookup"><span data-stu-id="cfe27-119">Remarks</span></span>

<span data-ttu-id="cfe27-120">选项，可以使用以下**[RecordsetOptionEnum](recordsetoptionenum-enumeration-dao.md)** 常量。</span><span class="sxs-lookup"><span data-stu-id="cfe27-120">You can use the following **[RecordsetOptionEnum](recordsetoptionenum-enumeration-dao.md)** constants for options.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="cfe27-121">常量</span><span class="sxs-lookup"><span data-stu-id="cfe27-121">Constant</span></span></p></th>
<th><p><span data-ttu-id="cfe27-122">说明</span><span class="sxs-lookup"><span data-stu-id="cfe27-122">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cfe27-123"><strong>dbDenyWrite</strong></span><span class="sxs-lookup"><span data-stu-id="cfe27-123"><strong>dbDenyWrite</strong></span></span></p></td>
<td><p><span data-ttu-id="cfe27-124">拒绝其他用户的写入权限（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="cfe27-124">Denies write permission to other users (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfe27-125"><strong>dbInconsistent</strong></span><span class="sxs-lookup"><span data-stu-id="cfe27-125"><strong>dbInconsistent</strong></span></span></p></td>
<td><p><span data-ttu-id="cfe27-126">（默认值）执行不一致的更新（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="cfe27-126">(Default) Executes inconsistent updates (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfe27-127"><strong>dbConsistent</strong></span><span class="sxs-lookup"><span data-stu-id="cfe27-127"><strong>dbConsistent</strong></span></span></p></td>
<td><p><span data-ttu-id="cfe27-128">执行一致的更新（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="cfe27-128">Executes consistent updates (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfe27-129"><strong>dbSQLPassThrough</strong></span><span class="sxs-lookup"><span data-stu-id="cfe27-129"><strong>dbSQLPassThrough</strong></span></span></p></td>
<td><p><span data-ttu-id="cfe27-p101">执行 SQL 传递查询。设置此选项会将 SQL 语句传递给 ODBC 数据库以进行处理（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="cfe27-p101">Executes an SQL pass-through query. Setting this option passes the SQL statement to an ODBC database for processing (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfe27-132"><strong>dbFailOnError</strong></span><span class="sxs-lookup"><span data-stu-id="cfe27-132"><strong>dbFailOnError</strong></span></span></p></td>
<td><p><span data-ttu-id="cfe27-133">发生错误时回滚更新（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="cfe27-133">Rolls back updates if an error occurs (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfe27-134"><strong>dbSeeChanges</strong></span><span class="sxs-lookup"><span data-stu-id="cfe27-134"><strong>dbSeeChanges</strong></span></span></p></td>
<td><p><span data-ttu-id="cfe27-135">如果其他用户更改您正编辑的数据，则生成运行时错误（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="cfe27-135">Generates a run-time error if another user is changing data you are editing (Microsoft Access workspaces only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfe27-136"><strong>dbRunAsync</strong></span><span class="sxs-lookup"><span data-stu-id="cfe27-136"><strong>dbRunAsync</strong></span></span></p></td>
<td><p><span data-ttu-id="cfe27-137">异步执行查询（仅适用于 ODBCDirect Connection 和 QueryDef 对象）。</span><span class="sxs-lookup"><span data-stu-id="cfe27-137">Executes the query asynchronously (ODBCDirect Connection and QueryDef objects only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfe27-138"><strong>一设置</strong></span><span class="sxs-lookup"><span data-stu-id="cfe27-138"><strong>dbExecDirect</strong></span></span></p></td>
<td><p><span data-ttu-id="cfe27-139">在不首先调用 SQLPrepare ODBC API 函数的情况下，执行语句（仅适用于 ODBCDirect Connection 和 QueryDef 对象）。</span><span class="sxs-lookup"><span data-stu-id="cfe27-139">Executes the statement without first calling SQLPrepare ODBC API function (ODBCDirect Connection and QueryDef objects only).</span></span></p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> <span data-ttu-id="cfe27-140">Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="cfe27-140">ODBCDirect workspaces are not supported in Microsoft Access 2013.</span></span> <span data-ttu-id="cfe27-141">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="cfe27-141">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span>

> [!NOTE]
> <span data-ttu-id="cfe27-p103">[!注释] 常量 **dbConsistent** 和 **dbInconsistent** 是互斥的。可以在 **OpenRecordset** 的给定实例中使用其中的某一个，但不能同时使用此两者。同时使用 **dbConsistent** 和 **dbInconsistent** 会导致出错。</span><span class="sxs-lookup"><span data-stu-id="cfe27-p103">The constants **dbConsistent** and **dbInconsistent** are mutually exclusive. You can use one or the other, but not both in a given instance of **OpenRecordset**. Using both **dbConsistent** and **dbInconsistent** causes an error.</span></span>

<span data-ttu-id="cfe27-p104">**Execute** 方法仅对动作查询有效。如果将 **Execute** 与另一个查询类型一起使用，将会发生错误。由于动作查询不返回任何记录，因此 **Execute** 不返回 **Recordset**。（如果不返回 **Recordset**，在 ODBCDirect 工作区中执行 SQL 传递查询不会返回错误。）</span><span class="sxs-lookup"><span data-stu-id="cfe27-p104">The **Execute** method is valid only for action queries. If you use **Execute** with another type of query, an error occurs. Because an action query doesn't return any records, **Execute** doesn't return a **Recordset**. (Executing an SQL pass-through query in an ODBCDirect workspace will not return an error if a **Recordset** isn't returned.)</span></span>

<span data-ttu-id="cfe27-p105">使用 **Connection**、 **Database** 或 **QueryDef** 对象的 **RecordsAffected** 属性确定受最近的 **Execute** 方法影响的记录数。例如， **RecordsAffected** 包含执行某个动作查询时删除、更新或插入的记录数。如果使用 **Execute** 方法运行查询，会将 **QueryDef** 对象的 **RecordsAffected** 属性设置为受影响的记录数。</span><span class="sxs-lookup"><span data-stu-id="cfe27-p105">Use the **RecordsAffected** property of the **Connection**, **Database**, or **QueryDef** object to determine the number of records affected by the most recent **Execute** method. For example, **RecordsAffected** contains the number of records deleted, updated, or inserted when executing an action query. When you use the **Execute** method to run a query, the **RecordsAffected** property of the **QueryDef** object is set to the number of records affected.</span></span>

<span data-ttu-id="cfe27-p106">在 Microsoft Access 工作区中，如果提供了一个在语法上正确的 SQL 语句，并且您具有相应的权限，则 **Execute** 方法不会失败 - 即使一行都不能修改或删除，也是如此。因此，在使用 **Execute** 方法运行更新或删除查询时，请始终使用 **dbFailOnError** 选项。如果锁定了任何受影响的记录，因而无法对其进行更新或删除，此选项将生成运行时错误，同时回滚所有成功的更改。</span><span class="sxs-lookup"><span data-stu-id="cfe27-p106">In a Microsoft Access workspace, if you provide a syntactically correct SQL statement and have the appropriate permissions, the **Execute** method won't fail — even if not a single row can be modified or deleted. Therefore, always use the **dbFailOnError** option when using the **Execute** method to run an update or delete query. This option generates a run-time error and rolls back all successful changes if any of the records affected are locked and can't be updated or deleted.</span></span>

<span data-ttu-id="cfe27-p107">在早期版本的 Microsoft Jet 数据库引擎中，SQL 语句自动嵌入到隐式事务中。如果使用 **dbFailOnError** 执行的语句的一部分失败，则整个语句都会回滚。为了改善性能，从版本 3.5 开始，删除了这些隐式事务。如果要更新早期的 DAO 代码，请务必考虑对 **Execute** 语句使用显式事务。</span><span class="sxs-lookup"><span data-stu-id="cfe27-p107">In earlier versions of the Microsoft Jet database engine, SQL statements were automatically embedded in implicit transactions. If part of a statement executed with **dbFailOnError** failed, the entire statement would be rolled back. To improve performance, these implicit transactions were removed starting with version 3.5. If you are updating older DAO code, be sure to consider using explicit transactions around **Execute** statements.</span></span>

<span data-ttu-id="cfe27-p108">为了在 Microsoft Access 工作区中，特别是在多用户环境中获取最佳性能，请将 **Execute** 方法嵌套在事务中。对当前的 **Workspace** 对象使用 **BeginTrans** 方法，然后使用 **Execute** 方法，再对 **Workspace** 使用 **CommitTrans** 方法完成事务。这样可以保存磁盘上的更改，并且释放任何在运行查询时放置的锁定。</span><span class="sxs-lookup"><span data-stu-id="cfe27-p108">For best performance in a Microsoft Access workspace, especially in a multiuser environment, nest the **Execute** method inside a transaction. Use the **BeginTrans** method on the current **Workspace** object, then use the **Execute** method, and complete the transaction by using the **CommitTrans** method on the **Workspace**. This saves changes on disk and frees any locks placed while the query is running.</span></span>

## <a name="example"></a><span data-ttu-id="cfe27-162">示例</span><span class="sxs-lookup"><span data-stu-id="cfe27-162">Example</span></span>

<span data-ttu-id="cfe27-p109">以下示例演示同时从 **QueryDef** 对象和 **Database** 对象运行时的 **Execute** 方法。若要使该过程运行，需要使用 ExecuteQueryDef 和 PrintOutput 过程。</span><span class="sxs-lookup"><span data-stu-id="cfe27-p109">This example demonstrates the **Execute** method when run from both a **QueryDef** object and a **Database** object. The ExecuteQueryDef and PrintOutput procedures are required for this procedure to run.</span></span>

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
     Debug.Print " " & rstTemp!LastName & _ 
     ", " & rstTemp!Country 
     rstTemp.MoveNext 
     Loop 
     
    End Sub
```