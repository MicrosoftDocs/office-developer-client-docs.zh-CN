---
title: Parameters 集合 (DAO)
TOCTitle: Parameters Collection
ms:assetid: 52fc1ce4-7b3e-152d-7b6a-9c32a6470147
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193967(v=office.15)
ms:contentKeyID: 48544862
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: 09f60cb8dde407aacbb19e6b2124151dbbf9b3c5
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28721743"
---
# <a name="parameters-collection-dao"></a><span data-ttu-id="a132f-102">Parameters 集合 (DAO)</span><span class="sxs-lookup"><span data-stu-id="a132f-102">Parameters collection (DAO)</span></span>

<span data-ttu-id="a132f-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="a132f-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="a132f-104">**Parameters** 集合包含 **QueryDef** 对象的所有 **Parameter** 对象。</span><span class="sxs-lookup"><span data-stu-id="a132f-104">A **Parameters** collection contains all the **Parameter** objects of a **QueryDef** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="a132f-105">注解</span><span class="sxs-lookup"><span data-stu-id="a132f-105">Remarks</span></span>

<span data-ttu-id="a132f-p101">**Parameters** 集合仅提供有关现有参数的信息。您不能向 **Parameters** 集合追加对象或从中删除对象。</span><span class="sxs-lookup"><span data-stu-id="a132f-p101">The **Parameters** collection provides information only about existing parameters. You can't append objects to or delete objects from the **Parameters** collection.</span></span>

## <a name="example"></a><span data-ttu-id="a132f-108">示例</span><span class="sxs-lookup"><span data-stu-id="a132f-108">Example</span></span>

<span data-ttu-id="a132f-p102">以下示例通过创建一个临时 **QueryDef**，并基于对 **QueryDef** 对象的 **Parameters** 所做的更改检索数据，来演示 **Parameter** 对象和 **Parameters** 集合。若要使该过程运行，需要使用 ParametersChange 过程。</span><span class="sxs-lookup"><span data-stu-id="a132f-p102">This example demonstrates **Parameter** objects and the **Parameters** collection by creating a temporary **QueryDef** and retrieving data based on changes made to the **QueryDef** object's **Parameters**. The ParametersChange procedure is required for this procedure to run.</span></span>

```vb
    Sub ParameterX() 
     
       Dim dbsNorthwind As Database 
       Dim qdfReport As QueryDef 
       Dim prmBegin As Parameter 
       Dim prmEnd As Parameter 
     
       Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
       ' Create temporary QueryDef object with two  
       ' parameters. 
       Set qdfReport = dbsNorthwind.CreateQueryDef("", _ 
          "PARAMETERS dteBegin DateTime, dteEnd DateTime; " & _ 
          "SELECT EmployeeID, COUNT(OrderID) AS NumOrders " & _ 
          "FROM Orders WHERE ShippedDate BETWEEN " & _ 
          "[dteBegin] AND [dteEnd] GROUP BY EmployeeID " & _ 
          "ORDER BY EmployeeID") 
       Set prmBegin = qdfReport.Parameters!dteBegin 
       Set prmEnd = qdfReport.Parameters!dteEnd 
     
       ' Print report using specified parameter values. 
       ParametersChange qdfReport, prmBegin, #1/1/95#, _ 
          prmEnd, #6/30/95# 
       ParametersChange qdfReport, prmBegin, #7/1/95#, _ 
          prmEnd, #12/31/95# 
     
       dbsNorthwind.Close 
     
    End Sub 
     
    Sub ParametersChange(qdfTemp As QueryDef, _ 
       prmFirst As Parameter, dteFirst As Date, _ 
       prmLast As Parameter, dteLast As Date) 
       ' Report function for ParameterX. 
     
       Dim rstTemp As Recordset 
       Dim fldLoop As Field 
     
       ' Set parameter values and open recordset from  
       ' temporary QueryDef object. 
       prmFirst = dteFirst 
       prmLast = dteLast 
       Set rstTemp = _  
          qdfTemp.OpenRecordset(dbOpenForwardOnly) 
       Debug.Print "Period " & dteFirst & " to " & dteLast 
     
       ' Enumerate recordset. 
       Do While Not rstTemp.EOF 
     
          ' Enumerate Fields collection of recordset. 
          For Each fldLoop In rstTemp.Fields 
             Debug.Print " - " & fldLoop.Name & " = " & fldLoop; 
          Next fldLoop 
     
          Debug.Print 
          rstTemp.MoveNext 
       Loop 
     
       rstTemp.Close 
     
    End Sub 
```

<br/>

下面的示例演示如何创建参数查询。 两个参数，名为 Param1 和 Param2 创建名为**myQuery**的查询。 <span data-ttu-id="a132f-113">若要执行此操作，查询的 SQL 属性设置为定义的参数的结构化查询语言 (SQL) 语句。</span><span class="sxs-lookup"><span data-stu-id="a132f-113">To do this, the SQL property of the query is set to a Structured Query Language (SQL) statement that defines the parameters.</span></span>

<span data-ttu-id="a132f-114">**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="a132f-114">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

```vb
    Sub CreateQueryWithParameters()
    
        Dim dbs As DAO.Database
        Dim qdf As DAO.QueryDef
        Dim strSQL As String
    
        Set dbs = CurrentDb
        Set qdf = dbs.CreateQueryDef("myQuery")
        Application.RefreshDatabaseWindow
    
        strSQL = "PARAMETERS Param1 TEXT, Param2 INT; "
        strSQL = strSQL & "SELECT * FROM [Table1] "
        strSQL = strSQL & "WHERE [Field1] = [Param1] AND [Field2] = [Param2];"
        qdf.SQL = strSQL
    
        qdf.Close
        Set qdf = Nothing
        Set dbs = Nothing
    
    End Sub
```

<br/>

<span data-ttu-id="a132f-115">下面的示例演示如何执行参数查询。</span><span class="sxs-lookup"><span data-stu-id="a132f-115">The following example shows how to execute a parameter query.</span></span> <span data-ttu-id="a132f-116">Parameters 集合用于设置 myActionQuery 查询的 Organization 参数之前执行查询。</span><span class="sxs-lookup"><span data-stu-id="a132f-116">The Parameters collection is used to set the Organization parameter of the myActionQuery query before the query is executed.</span></span>

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

<br/>

<span data-ttu-id="a132f-117">以下示例说明如何打开基于参数查询的 Recordset。</span><span class="sxs-lookup"><span data-stu-id="a132f-117">The following example shows how to open a Recordset that is based on a parameter query.</span></span>

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
