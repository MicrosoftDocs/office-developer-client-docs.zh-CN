---
title: Recordset.NextRecordset Method (DAO)
TOCTitle: NextRecordset Method
ms:assetid: 4a3a6176-0aa0-efb6-b175-dbe23e266abc
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193483(v=office.15)
ms:contentKeyID: 48544664
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: df017e68fd2778acacdefeea09e0787f497ab225
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466124"
---
# <a name="recordsetnextrecordset-method-dao"></a><span data-ttu-id="f8edf-102">Recordset.NextRecordset Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="f8edf-102">Recordset.NextRecordset Method (DAO)</span></span>


<span data-ttu-id="f8edf-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="f8edf-103">**Applies to**: Access 2013 | Office 2013</span></span>

## <a name="syntax"></a><span data-ttu-id="f8edf-104">语法</span><span class="sxs-lookup"><span data-stu-id="f8edf-104">Syntax</span></span>

<span data-ttu-id="f8edf-105">*表达式*。NextRecordset</span><span class="sxs-lookup"><span data-stu-id="f8edf-105">*expression* .NextRecordset</span></span>

<span data-ttu-id="f8edf-106">*表达式*一个表示**Recordset**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="f8edf-106">*expression* A variable that represents a **Recordset** object.</span></span>

### <a name="return-value"></a><span data-ttu-id="f8edf-107">返回值</span><span class="sxs-lookup"><span data-stu-id="f8edf-107">Return Value</span></span>

<span data-ttu-id="f8edf-108">Boolean</span><span class="sxs-lookup"><span data-stu-id="f8edf-108">Boolean</span></span>

## <a name="remarks"></a><span data-ttu-id="f8edf-109">说明</span><span class="sxs-lookup"><span data-stu-id="f8edf-109">Remarks</span></span>

<span data-ttu-id="f8edf-110">在适用于 ODBCDirect 工作区中，您可以打开**[Recordset](recordset-object-dao.md)** ，其中包含多个源参数的**OpenRecordset**或选择查询**[QueryDef](querydef-object-dao.md)** 对象，如以下示例所示的**[SQL](querydef-sql-property-dao.md)** 属性中的选择查询。</span><span class="sxs-lookup"><span data-stu-id="f8edf-110">In an ODBCDirect workspace, you can open a **[Recordset](recordset-object-dao.md)** containing more than one select query in the source argument of **OpenRecordset**, or the **[SQL](querydef-sql-property-dao.md)** property of a select query **[QueryDef](querydef-object-dao.md)** object, as in the following example.</span></span>

```sql
    SELECT LastName, FirstName FROM Authors 
    WHERE LastName = 'Smith'; 
    SELECT Title, ISBN FROM Titles 
    WHERE Pub_ID = 9999 
```

<span data-ttu-id="f8edf-p101">将使用第一个查询打开返回的 **Recordset**。若要从后续查询获取记录的结果集，请使用 **NextRecordset** 方法。</span><span class="sxs-lookup"><span data-stu-id="f8edf-p101">The returned **Recordset** will open with the results of the first query. To obtain the result sets of records from subsequent queries, use the **NextRecordset** method.</span></span>

<span data-ttu-id="f8edf-p102">如果有更多的可用记录（也就是说， **OpenRecordset** 调用或 **SQL** 属性中有另一个选择查询），从下一个查询返回的记录将被载入 **Recordset**，同时 **NextRecordset** 将返回 **True**，表示记录可用。如果没有更多的可用记录（也就是说，最后一个选择查询的结果已被载入 **Recordset**），则 **NextRecordset** 将返回 **False**，且 **Recordset** 为空。</span><span class="sxs-lookup"><span data-stu-id="f8edf-p102">If more records are available (that is, there was another select query in the **OpenRecordset** call or in the **SQL** property), the records returned from the next query will be loaded into the **Recordset**, and **NextRecordset** will return **True**, indicating that the records are available. When no more records are available (that is, results of the last select query have been loaded into the **Recordset**), then **NextRecordset** will return **False**, and the **Recordset** will be empty.</span></span>

<span data-ttu-id="f8edf-p103">还可以使用 **[Cancel](connection-cancel-method-dao.md)** 方法刷新 **Recordset** 的内容。但是， **Cancel** 还会刷新任何尚未加载的附加记录。</span><span class="sxs-lookup"><span data-stu-id="f8edf-p103">You can also use the **[Cancel](connection-cancel-method-dao.md)** method to flush the contents of a **Recordset**. However, **Cancel** also flushes any additional records not yet loaded.</span></span>

## <a name="example"></a><span data-ttu-id="f8edf-117">示例</span><span class="sxs-lookup"><span data-stu-id="f8edf-117">Example</span></span>

<span data-ttu-id="f8edf-p104">以下示例使用 **NextRecordset** 方法查看 SELECT 复合查询中的数据。在执行此类查询时， **DefaultCursorDriver** 属性必须设置为 **dbUseODBCCursor**。即使部分或全部 SELECT 语句返回零记录， **NextRecordset** 方法也会返回 **True**；仅当检查了所有单个 SQL 子句后，它才返回 **False**。</span><span class="sxs-lookup"><span data-stu-id="f8edf-p104">This example uses the **NextRecordset** method to view the data from a compound SELECT query. The **DefaultCursorDriver** property must be set to **dbUseODBCCursor** when executing such queries. The **NextRecordset** method will return **True** even if some or all of the SELECT statements return zero records; it will return **False** only after all the individual SQL clauses have been checked.</span></span>

```vb
    Sub NextRecordsetX() 
     
     Dim wrkODBC As Workspace 
     Dim conPubs As Connection 
     Dim rstTemp As Recordset 
     Dim intCount As Integer 
     Dim booNext As Boolean 
     
     ' Create ODBCDirect Workspace object and open Connection 
     ' object. The DefaultCursorDriver setting is required 
     ' when using compound SQL statements. 
     Set wrkODBC = CreateWorkspace("", _ 
     "admin", "", dbUseODBC) 
     wrkODBC.DefaultCursorDriver = dbUseODBCCursor 
     
     ' Note: The DSN referenced below must be set to 
     ' use Microsoft Windows NT Authentication Mode to 
     ' authorize user access to the Microsoft SQL Server. 
     Set conPubs = wrkODBC.OpenConnection("Publishers", , , _ 
     "ODBC;DATABASE=pubs;DSN=Publishers") 
     
     ' Construct compound SELECT statement. 
     Set rstTemp = conPubs.OpenRecordset("SELECT * " & _ 
     "FROM authors; " & _ 
     "SELECT * FROM stores; " & _ 
     "SELECT * FROM jobs") 
     
     ' Try printing results from each of the three SELECT 
     ' statements. 
     booNext = True 
     intCount = 1 
     With rstTemp 
     Do While booNext 
     Debug.Print "Contents of recordset #" & intCount 
     Do While Not .EOF 
     Debug.Print , .Fields(0), .Fields(1) 
     .MoveNext 
     Loop 
     booNext = .NextRecordset 
     Debug.Print " rstTemp.NextRecordset = " & _ 
     booNext 
     intCount = intCount + 1 
     Loop 
     End With 
     
     rstTemp.Close 
     conPubs.Close 
     wrkODBC.Close 
     
    End Sub 
```

<br/>

<span data-ttu-id="f8edf-p105">完成同一任务的另一种方法是创建一个包含 SQL 复合语句的预备语句。 **QueryDef** 对象的 **CacheSize** 属性必须设置为 1， **Recordset** 对象必须为仅向前类型，并且是只读的。</span><span class="sxs-lookup"><span data-stu-id="f8edf-p105">Another way to accomplish the same task would be to create a prepared statement containing the compound SQL statement. The **CacheSize** property of the **QueryDef** object must be set to 1, and the **Recordset** object must be forward-only and read-only.</span></span>

```vb 
Sub NextRecordsetX2() 
 
 Dim wrkODBC As Workspace 
 Dim conPubs As Connection 
 Dim qdfTemp As QueryDef 
 Dim rstTemp As Recordset 
 Dim intCount As Integer 
 Dim booNext As Boolean 
 
 ' Create ODBCDirect Workspace object and open Connection 
 ' object. The DefaultCursorDriver setting is required 
 ' when using compound SQL statements. 
 Set wrkODBC = CreateWorkspace("", _ 
 "admin", "", dbUseODBC) 
 wrkODBC.DefaultCursorDriver = dbUseODBCCursor 
 
 ' Note: The DSN referenced below must be set to 
 ' use Microsoft Windows NT Authentication Mode to 
 ' authorize user access to the Microsoft SQL Server. 
 Set conPubs = wrkODBC.OpenConnection("Publishers", , , _ 
 "ODBC;DATABASE=pubs;DSN=Publishers") 
 
 ' Create a temporary stored procedure with a compound 
 ' SELECT statement. 
 Set qdfTemp = conPubs.CreateQueryDef("", _ 
 "SELECT * FROM authors; " & _ 
 "SELECT * FROM stores; " & _ 
 "SELECT * FROM jobs") 
 ' Set CacheSize and open Recordset object with arguments 
 ' that will allow access to multiple recordsets. 
 qdfTemp.CacheSize = 1 
 Set rstTemp = qdfTemp.OpenRecordset(dbOpenForwardOnly, _ 
 dbReadOnly) 
 
 ' Try printing results from each of the three SELECT 
 ' statements. 
 booNext = True 
 intCount = 1 
 With rstTemp 
 Do While booNext 
 Debug.Print "Contents of recordset #" & intCount 
 Do While Not .EOF 
 Debug.Print , .Fields(0), .Fields(1) 
 .MoveNext 
 Loop 
 booNext = .NextRecordset 
 Debug.Print " rstTemp.NextRecordset = " & _ 
 booNext 
 intCount = intCount + 1 
 Loop 
 End With 
 
 rstTemp.Close 
 qdfTemp.Close 
 conPubs.Close 
 wrkODBC.Close 
 
End Sub 
 
```

