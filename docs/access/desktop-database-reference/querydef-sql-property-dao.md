---
title: QueryDef.SQL 属性 (DAO)
TOCTitle: SQL property
ms:assetid: 16446789-c8be-bff0-eddd-b5f6a8530128
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845522(v=office.15)
ms:contentKeyID: 48543429
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053054
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 43acce256d3a46fd7b01122a8502e0af502eb3e9
ms.sourcegitcommit: 38d0db57580cc5f4a0231c27b1643f8db5431ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25937678"
---
# <a name="querydefsql-property-dao"></a><span data-ttu-id="34233-102">QueryDef.SQL 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="34233-102">QueryDef.SQL property (DAO)</span></span>

<span data-ttu-id="34233-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="34233-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="34233-104">设置或返回定义 **[QueryDef](querydef-object-dao.md)** 对象所执行的查询的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="34233-104">Sets or returns the SQL statement that defines the query executed by a **[QueryDef](querydef-object-dao.md)** object.</span></span>

## <a name="syntax"></a><span data-ttu-id="34233-105">语法</span><span class="sxs-lookup"><span data-stu-id="34233-105">Syntax</span></span>

<span data-ttu-id="34233-106">*表达式*。SQL</span><span class="sxs-lookup"><span data-stu-id="34233-106">*expression* .SQL</span></span>

<span data-ttu-id="34233-107">*表达式*一个代表**QueryDef**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="34233-107">*expression* A variable that represents a **QueryDef** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="34233-108">注解</span><span class="sxs-lookup"><span data-stu-id="34233-108">Remarks</span></span>

<span data-ttu-id="34233-p101">**SQL** 属性包含用于确定当您执行查询时如何对记录进行选择、分组和排序的 SQL 语句。您可以使用查询选择要在 **[Recordset](recordset-object-dao.md)** 对象中包括的记录。还可以定义动作查询，以便在不返回记录的情况下修改数据。</span><span class="sxs-lookup"><span data-stu-id="34233-p101">The **SQL** property contains the SQL statement that determines how records are selected, grouped, and ordered when you execute the query. You can use the query to select records to include in a **[Recordset](recordset-object-dao.md)** object. You can also define action queries to modify data without returning records.</span></span>

<span data-ttu-id="34233-p102">查询中使用的 SQL 语法必须符合查询引擎的 SQL 特定语言，该语言是由工作区的类型决定的。在 Microsoft Access 工作区中，除非创建的是 SQL 传递查询（在这种情况下应当使用服务器的特定语言），否则应使用 Microsoft Access SQL 特定语言。</span><span class="sxs-lookup"><span data-stu-id="34233-p102">The SQL syntax used in a query must conform to the SQL dialect of the query engine, which is determined by the type of workspace. In a Microsoft Access workspace, use the Microsoft Access SQL dialect, unless you create an SQL pass-through query, in which case you should use the dialect of the server.</span></span>

<span data-ttu-id="34233-p103">如果 SQL 语句包含查询的参数，您必须在执行操作之前设置这些参数。除非您重置了参数，否则每次执行查询时，都将应用相同的参数值。</span><span class="sxs-lookup"><span data-stu-id="34233-p103">If the SQL statement includes parameters for the query, you must set these before execution. Until you reset the parameters, the same parameter values are applied each time you execute the query.</span></span>

<span data-ttu-id="34233-116">在 Microsoft Access 工作区中，在对 Microsoft Access 数据库引擎连接的 ODBC 数据源执行 SQL 传递操作时，最好使用 **QueryDef** 对象。</span><span class="sxs-lookup"><span data-stu-id="34233-116">In a Microsoft Access workspace, using a **QueryDef** object is the preferred way to perform SQL pass-through operations on Microsoft Access database engine-connected ODBC data sources.</span></span> <span data-ttu-id="34233-117">通过将**QueryDef**对象的**[Connect](querydef-connect-property-dao.md)** 属性设置为 ODBC 数据源，您可以使用非 – Microsoft – Access – 数据库 SQL 查询中的传递给外部服务器。</span><span class="sxs-lookup"><span data-stu-id="34233-117">By setting the **QueryDef** object's **[Connect](querydef-connect-property-dao.md)** property to an ODBC data source, you can use non–Microsoft–Access–database SQL in the query to be passed to the external server.</span></span> <span data-ttu-id="34233-118">例如，对于 Microsoft SQL Server 或 Sybase SQL Server 数据库，可以使用 TRANSACT SQL 语句，Microsoft Access 数据库引擎不对其进行处理。</span><span class="sxs-lookup"><span data-stu-id="34233-118">For example, you can use TRANSACT SQL statements (with Microsoft SQL Server or Sybase SQL Server databases), which the Microsoft Access database engine would otherwise not process.</span></span>

> [!NOTE]
> <span data-ttu-id="34233-119">如果属性设置为非整数值时，连接字符串和系统参数指定非美国十进制字符，例如逗号分隔 (例如， `strSQL = "PRICE > " & lngPrice, and lngPrice = 125,50`)，当您尝试在 Microsoft 执行**QueryDef**对象时，将导致错误Access 数据库引擎数据库。</span><span class="sxs-lookup"><span data-stu-id="34233-119">If you set the property to a string concatenated with a non-integer value, and the system parameters specify a non-U.S. decimal character such as a comma (for example, `strSQL = "PRICE > " & lngPrice, and lngPrice = 125,50`), an error will result when you try to execute the **QueryDef** object in a Microsoft Access database engine database.</span></span> <span data-ttu-id="34233-120">这是因为在连接过程中，需要使用系统的默认小数字符将数字转换为字符串，并且 Microsoft Access SQL 只接受美国格式的小数字符。</span><span class="sxs-lookup"><span data-stu-id="34233-120">This is because during concatenation, the number will be converted to a string using your system's default decimal character, and Microsoft Access SQL only accepts U.S. decimal characters.</span></span>

## <a name="example"></a><span data-ttu-id="34233-121">示例</span><span class="sxs-lookup"><span data-stu-id="34233-121">Example</span></span>

<span data-ttu-id="34233-p106">以下示例通过设置并更改临时 **QueryDef** 的 **SQL** 属性并比较结果来演示 **SQL** 属性。若要使该过程运行，需要使用 SQLOutput 函数。</span><span class="sxs-lookup"><span data-stu-id="34233-p106">This example demonstrates the **SQL** property by setting and changing the **SQL** property of a temporary **QueryDef** and comparing the results. The SQLOutput function is required for this procedure to run.</span></span>

```vb
    Sub SQLX() 
     
       Dim dbsNorthwind As Database 
       Dim qdfTemp As QueryDef 
       Dim rstEmployees As Recordset 
     
       Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
       Set qdfTemp = dbsNorthwind.CreateQueryDef("") 
     
       ' Open Recordset using temporary QueryDef object and  
       ' print report. 
       SQLOutput "SELECT * FROM Employees " & _ 
          "WHERE Country = 'USA' " & _ 
          "ORDER BY LastName", qdfTemp 
     
       ' Open Recordset using temporary QueryDef object and  
       ' print report. 
       SQLOutput "SELECT * FROM Employees " & _ 
          "WHERE Country = 'UK' " & _ 
          "ORDER BY LastName", qdfTemp 
     
       dbsNorthwind.Close 
     
    End Sub 
     
    Function SQLOutput(strSQL As String, qdfTemp As QueryDef) 
     
       Dim rstEmployees As Recordset 
     
       ' Set SQL property of temporary QueryDef object and open  
       ' a Recordset. 
       qdfTemp.SQL = strSQL 
       Set rstEmployees = qdfTemp.OpenRecordset 
     
       Debug.Print strSQL 
     
       With rstEmployees 
          ' Enumerate Recordset. 
          Do While Not .EOF 
             Debug.Print "  " & !FirstName & " " & _ 
                !LastName & ", " & !Country 
             .MoveNext 
          Loop 
          .Close 
       End With 
     
    End Function 
```

<br/>

<span data-ttu-id="34233-p107">以下示例使用 **CopyQueryDef** 方法从现有的 **Recordset** 创建 **QueryDef** 的副本，然后通过向 **SQL** 属性添加子句修改副本。创建永久的 **QueryDef** 时，可以向 **SQL** 属性添加空格、分号或换行符；只有在删除这些额外的字符之后，才可以将任何新子句附加到 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="34233-p107">This example uses the **CopyQueryDef** method to create a copy of a **QueryDef** from an existing **Recordset** and modifies the copy by adding a clause to the **SQL** property. When you create a permanent **QueryDef**, spaces, semicolons, or linefeeds may be added to the **SQL** property; these extra characters must be stripped before any new clauses can be attached to the SQL statement.</span></span>

```vb
    Function CopyQueryNew(rstTemp As Recordset, _ 
       strAdd As String) As QueryDef 
     
       Dim strSQL As String 
       Dim strRightSQL As String 
     
       Set CopyQueryNew = rstTemp.CopyQueryDef 
       With CopyQueryNew 
          ' Strip extra characters. 
          strSQL = .SQL 
          strRightSQL = Right(strSQL, 1) 
          Do While strRightSQL = " " Or strRightSQL = ";" Or _ 
                strRightSQL = Chr(10) Or strRightSQL = vbCr 
             strSQL = Left(strSQL, Len(strSQL) - 1) 
             strRightSQL = Right(strSQL, 1) 
          Loop 
          .SQL = strSQL & strAdd 
       End With 
     
    End Function 
```

<br/>

<span data-ttu-id="34233-126">以下示例演示 CopyQueryNew() 可能的用法。</span><span class="sxs-lookup"><span data-stu-id="34233-126">This example shows a possible use of CopyQueryNew().</span></span> 
     
```vb
    Sub CopyQueryDefX() 
     
       Dim dbsNorthwind As Database 
       Dim qdfEmployees As QueryDef 
       Dim rstEmployees As Recordset 
       Dim intCommand As Integer 
       Dim strOrderBy As String 
       Dim qdfCopy As QueryDef 
       Dim rstCopy As Recordset 
     
       Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
       Set qdfEmployees = dbsNorthwind.CreateQueryDef( _ 
          "NewQueryDef", "SELECT FirstName, LastName, " & _ 
          "BirthDate FROM Employees") 
       Set rstEmployees = qdfEmployees.OpenRecordset( _ 
          dbOpenForwardOnly) 
     
       Do While True 
          intCommand = Val(InputBox( _ 
             "Choose field on which to order a new " & _ 
             "Recordset:" & vbCr & "1 - FirstName" & vbCr & _ 
             "2 - LastName" & vbCr & "3 - BirthDate" & vbCr & _ 
             "[Cancel - exit]")) 
          Select Case intCommand 
             Case 1 
                strOrderBy = " ORDER BY FirstName" 
             Case 2 
                strOrderBy = " ORDER BY LastName" 
             Case 3 
                strOrderBy = " ORDER BY BirthDate" 
             Case Else 
                Exit Do 
          End Select 
          Set qdfCopy = CopyQueryNew(rstEmployees, strOrderBy) 
          Set rstCopy = qdfCopy.OpenRecordset(dbOpenSnapshot, _ 
             dbForwardOnly) 
          With rstCopy 
             Do While Not .EOF 
                Debug.Print !LastName & ", " & !FirstName & _ 
                   " - " & !BirthDate 
                .MoveNext 
             Loop 
             .Close 
          End With 
          Exit Do 
       Loop 
     
       rstEmployees.Close 
       ' Delete new QueryDef because this is a demonstration. 
       dbsNorthwind.QueryDefs.Delete qdfEmployees.Name 
       dbsNorthwind.Close 
     
    End Sub 
```

<br/>

<span data-ttu-id="34233-p108">以下示例使用 **CreateQueryDef** 和 **OpenRecordset** 方法以及 **SQL** 属性，查询 Microsoft SQL Server 示例数据库 Pubs 中的书名表，并返回最畅销书籍的书名和书名标识符。然后查询作者表，并指示用户根据每个作者的版税份额向其发送红利支票（总红利为 ￥1,000，每个作者应收到该金额的一定份额）。</span><span class="sxs-lookup"><span data-stu-id="34233-p108">This example uses the **CreateQueryDef** and **OpenRecordset** methods and the **SQL** property to query the table of titles in the Microsoft SQL Server sample database Pubs and return the title and title identifier of the best-selling book. The example then queries the table of authors and instructs the user to send a bonus check to each author based on his or her royalty share (the total bonus is $1,000 and each author should receive a percentage of that amount).</span></span>

```vb
    Sub ClientServerX2() 
     
       Dim dbsCurrent As Database 
       Dim qdfBestSellers As QueryDef 
       Dim qdfBonusEarners As QueryDef 
       Dim rstTopSeller As Recordset 
       Dim rstBonusRecipients As Recordset 
       Dim strAuthorList As String 
     
       ' Open a database from which QueryDef objects can be  
       ' created. 
       Set dbsCurrent = OpenDatabase("DB1.mdb") 
     
       ' Create a temporary QueryDef object to retrieve 
       ' data from a Microsoft SQL Server database. 
       Set qdfBestSellers = dbsCurrent.CreateQueryDef("") 
       With qdfBestSellers 
          ' Note: The DSN referenced below must be configured to  
          '       use Microsoft Windows NT Authentication Mode to  
          '       authorize user access to the Microsoft SQL Server. 
          .Connect = "ODBC;DATABASE=pubs;DSN=Publishers" 
          .SQL = "SELECT title, title_id FROM titles " & _ 
             "ORDER BY ytd_sales DESC" 
          Set rstTopSeller = .OpenRecordset() 
          rstTopSeller.MoveFirst 
       End With 
     
       ' Create a temporary QueryDef to retrieve data from 
       ' a Microsoft SQL Server database based on the results from 
       ' the first query. 
       Set qdfBonusEarners = dbsCurrent.CreateQueryDef("") 
       With qdfBonusEarners 
          ' Note: The DSN referenced below must be configured to  
          '       use Microsoft Windows NT Authentication Mode to  
          '       authorize user access to the Microsoft SQL Server. 
          .Connect = "ODBC;DATABASE=pubs;DSN=Publishers" 
          .SQL = "SELECT * FROM titleauthor " & _ 
             "WHERE title_id = '" & _ 
             rstTopSeller!title_id & "'" 
          Set rstBonusRecipients = .OpenRecordset() 
       End With 
     
       ' Build the output string. 
       With rstBonusRecipients 
          Do While Not .EOF 
             strAuthorList = strAuthorList & "  " & _ 
                !au_id & ":  $" & (10 * !royaltyper) & vbCr 
             .MoveNext 
          Loop 
       End With 
     
       ' Display results. 
       MsgBox "Please send a check to the following " & _ 
          "authors in the amounts shown:" & vbCr & _ 
          strAuthorList & "for outstanding sales of " & _ 
          rstTopSeller!Title & "." 
     
       rstTopSeller.Close 
       dbsCurrent.Close 
     
    End Sub 
```

<br/>

<span data-ttu-id="34233-129">下面的示例演示如何创建参数查询。</span><span class="sxs-lookup"><span data-stu-id="34233-129">The following example shows how to create a parameter query.</span></span> <span data-ttu-id="34233-130">两个参数，名为 Param1 和 Param2 创建名为**myQuery**的查询。</span><span class="sxs-lookup"><span data-stu-id="34233-130">A query named **myQuery** is created with two parameters, named Param1 and Param2.</span></span> <span data-ttu-id="34233-131">若要执行此操作，查询的 SQL 属性设置为定义的参数的结构化查询语言 (SQL) 语句。</span><span class="sxs-lookup"><span data-stu-id="34233-131">To do this, the SQL property of the query is set to a Structured Query Language (SQL) statement that defines the parameters.</span></span>

<span data-ttu-id="34233-132">**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="34233-132">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

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

<span data-ttu-id="34233-133">下面的示例演示如何替换已保存的查询中的结构化查询语言 (SQL) 语句。</span><span class="sxs-lookup"><span data-stu-id="34233-133">The following example shows how to replace the Structured Query Language (SQL) statement in a saved query.</span></span>

```vb
    Dim qdf as QueryDef
    Dim db as Database
    Set db = CurrentDB
    Set qdf = db.QueryDefs("YourQueryName")
    qdf.SQL = ReplaceWhereClause(qdf.SQL, strYourNewWhereClause)
    set qdf = Nothing
    set db = Nothing
    
    Public Function ReplaceWhereClause(strSQL As Variant, strNewWHERE As Variant)
    On Error GoTo Error_Handler
    
    ‘This subroutine accepts a valid SQL string and Where clause, and
    ‘returns the same SQL statement with the original Where clause (if any)
    ‘replaced by the passed in Where clause.
    ‘
    ‘INPUT:
    ‘ strSQL valid SQL string to change
    ‘OUTPUT:
    ‘ strNewWHERE New WHERE clause to insert into SQL statement
    ‘
    Dim strSELECT As String, strWhere As String
    Dim strOrderBy As String, strGROUPBY As String, strHAVING As String
    
    Call ParseSQL(strSQL, strSELECT, strWhere, strOrderBy, _
    strGROUPBY, strHAVING)
    
    ReplaceWhereClause = strSELECT &""& strNewWHERE &""_
    & strGROUPBY &""& strHAVING &""& strOrderBy
    
    Exit_Procedure:
      Exit Function
    
    Error_Handler:
      MsgBox (Err.Number & ": " & Err.Description)
      Resume Exit_Procedure
    
    End Function
```
