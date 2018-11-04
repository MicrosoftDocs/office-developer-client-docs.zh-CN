---
title: Database.CreateQueryDef 方法 (DAO)
TOCTitle: CreateQueryDef Method
ms:assetid: 75ee7cac-dcd0-b4c5-b55b-9cbaaae2cbf0
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195966(v=office.15)
ms:contentKeyID: 48545686
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 1c4aaf826785a7c8033077ee76aed4d232e3a2a0
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25950242"
---
# <a name="databasecreatequerydef-method-dao"></a><span data-ttu-id="f0f2c-102">Database.CreateQueryDef 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="f0f2c-102">Database.CreateQueryDef method (DAO)</span></span>

<span data-ttu-id="f0f2c-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="f0f2c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="f0f2c-104">创建新的 **[QueryDef](querydef-object-dao.md)** 对象。</span><span class="sxs-lookup"><span data-stu-id="f0f2c-104">Creates a new **[QueryDef](querydef-object-dao.md)** object.</span></span>

## <a name="syntax"></a><span data-ttu-id="f0f2c-105">语法</span><span class="sxs-lookup"><span data-stu-id="f0f2c-105">Syntax</span></span>

<span data-ttu-id="f0f2c-106">*表达式*。CreateQueryDef （***名称***、 ***SQLText***）</span><span class="sxs-lookup"><span data-stu-id="f0f2c-106">*expression* .CreateQueryDef(***Name***, ***SQLText***)</span></span>

<span data-ttu-id="f0f2c-107">*表达式*一个代表**Database**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="f0f2c-107">*expression* A variable that represents a **Database** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="f0f2c-108">参数</span><span class="sxs-lookup"><span data-stu-id="f0f2c-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f0f2c-109">名称</span><span class="sxs-lookup"><span data-stu-id="f0f2c-109">Name</span></span></p></th>
<th><p><span data-ttu-id="f0f2c-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="f0f2c-110">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="f0f2c-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="f0f2c-111">Data Type</span></span></p></th>
<th><p><span data-ttu-id="f0f2c-112">说明</span><span class="sxs-lookup"><span data-stu-id="f0f2c-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f0f2c-113"><em>Name</em></span><span class="sxs-lookup"><span data-stu-id="f0f2c-113"><em>Name</em></span></span></p></td>
<td><p><span data-ttu-id="f0f2c-114">可选</span><span class="sxs-lookup"><span data-stu-id="f0f2c-114">Optional</span></span></p></td>
<td><p><span data-ttu-id="f0f2c-115"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="f0f2c-115"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="f0f2c-116">对新的 <strong>QueryDef</strong> 进行唯一命名的 <strong>Variant</strong>（<strong>String</strong> 子类型）。</span><span class="sxs-lookup"><span data-stu-id="f0f2c-116">A <strong>Variant</strong> (<strong>String</strong> subtype) that uniquely names the new <strong>QueryDef</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0f2c-117"><em>SQLText</em></span><span class="sxs-lookup"><span data-stu-id="f0f2c-117"><em>SQLText</em></span></span></p></td>
<td><p><span data-ttu-id="f0f2c-118">可选</span><span class="sxs-lookup"><span data-stu-id="f0f2c-118">Optional</span></span></p></td>
<td><p><span data-ttu-id="f0f2c-119"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="f0f2c-119"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="f0f2c-p101">一个 <strong>Variant</strong>（<strong>String</strong> 子类型）类型的值，它是一个定义 <strong>QueryDef</strong> 的 SQL 语句。如果省略此参数，则可以通过在将 <strong>QueryDef</strong> 追加到集合之前或之后设置它的 <strong><a href="querydef-sql-property-dao.md">SQL</a></strong> 属性对其进行定义。</span><span class="sxs-lookup"><span data-stu-id="f0f2c-p101">A <strong>Variant</strong> (<strong>String</strong> subtype) that is an SQL statement defining the <strong>QueryDef</strong>. If you omit this argument, you can define the <strong>QueryDef</strong> by setting its <strong><a href="querydef-sql-property-dao.md">SQL</a></strong> property before or after you append it to a collection.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="return-value"></a><span data-ttu-id="f0f2c-122">返回值</span><span class="sxs-lookup"><span data-stu-id="f0f2c-122">Return value</span></span>

<span data-ttu-id="f0f2c-123">QueryDef</span><span class="sxs-lookup"><span data-stu-id="f0f2c-123">QueryDef</span></span>

## <a name="remarks"></a><span data-ttu-id="f0f2c-124">注解</span><span class="sxs-lookup"><span data-stu-id="f0f2c-124">Remarks</span></span>

<span data-ttu-id="f0f2c-125">在 Microsoft Access 工作区中，如果在创建 **QueryDef** 时为名称提供了除零长度字符串之外的信息，产生的 **QueryDef** 对象将自动追加到 **[QueryDefs](querydefs-collection-dao.md)** 集合。</span><span class="sxs-lookup"><span data-stu-id="f0f2c-125">In a Microsoft Access workspace, if you provide anything other than a zero-length string for the name when you create a **QueryDef**, the resulting **QueryDef** object is automatically appended to the **[QueryDefs](querydefs-collection-dao.md)** collection.</span></span>

<span data-ttu-id="f0f2c-126">如果按名称指定的对象已**QueryDefs**集合的成员，将发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="f0f2c-126">If the object specified by name is already a member of the **QueryDefs** collection, a run-time error occurs.</span></span> <span data-ttu-id="f0f2c-127">您可以通过执行**CreateQueryDef**方法时的名称参数使用一个零长度字符串创建临时**QueryDef** 。</span><span class="sxs-lookup"><span data-stu-id="f0f2c-127">You can create a temporary **QueryDef** by using a zero-length string for the name argument when you execute the **CreateQueryDef** method.</span></span> <span data-ttu-id="f0f2c-128">还可以通过将新建的 [QueryDef](querydef-name-property-dao.md) 的 \*\*\*\*Name\*\*\*\* 属性设置为零长度字符串 ("") 来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="f0f2c-128">You can also accomplish this by setting the **[Name](querydef-name-property-dao.md)** property of a newly created **QueryDef** to a zero-length string ("").</span></span> 

<span data-ttu-id="f0f2c-129">如果您希望反复使用动态 SQL 语句，且不必在 **QueryDefs** 集合中创建任何新的永久对象，则使用临时的 **QueryDef** 对象十分有帮助。</span><span class="sxs-lookup"><span data-stu-id="f0f2c-129">Temporary **QueryDef** objects are useful if you want to repeatedly use dynamic SQL statements without having to create any new permanent objects in the **QueryDefs** collection.</span></span> <span data-ttu-id="f0f2c-130">不能将临时的 **QueryDef** 追加到任何集合，因为零长度字符串对永久的 **QueryDef** 对象来说是无效名称。</span><span class="sxs-lookup"><span data-stu-id="f0f2c-130">You can't append a temporary **QueryDef** to any collection because a zero-length string isn't a valid name for a permanent **QueryDef** object.</span></span> <span data-ttu-id="f0f2c-131">始终可以设置新建 **QueryDef** 的 **Name** 和 **SQL** 属性，然后将 **QueryDef** 追加到 **QueryDefs** 集合。</span><span class="sxs-lookup"><span data-stu-id="f0f2c-131">You can always set the **Name** and **SQL** properties of the newly created **QueryDef** object and subsequently append the **QueryDef** to the **QueryDefs** collection.</span></span>

<span data-ttu-id="f0f2c-132">若要在 **QueryDef** 对象中运行 SQL 语句，请使用 **[Execute](querydef-execute-method-dao.md)** 或 **[OpenRecordset](database-openrecordset-method-dao.md)** 方法。</span><span class="sxs-lookup"><span data-stu-id="f0f2c-132">To run the SQL statement in a **QueryDef** object, use the **[Execute](querydef-execute-method-dao.md)** or **[OpenRecordset](database-openrecordset-method-dao.md)** method.</span></span>

<span data-ttu-id="f0f2c-133">使用 **QueryDef** 对象是对 ODBC 数据库执行 SQL 传递查询的首选方法。</span><span class="sxs-lookup"><span data-stu-id="f0f2c-133">Using a **QueryDef** object is the preferred way to perform SQL pass-through queries with ODBC databases.</span></span>

<span data-ttu-id="f0f2c-134">若要从 Microsoft Access 数据库引擎数据库中的 **QueryDefs** 集合中删除一个 **QueryDef** 对象，请对该集合使用 **[Delete](querydefs-delete-method-dao.md)** 方法。</span><span class="sxs-lookup"><span data-stu-id="f0f2c-134">To remove a **QueryDef** object from a **QueryDefs** collection in a Microsoft Access database engine database, use the **[Delete](querydefs-delete-method-dao.md)** method on the collection.</span></span>

## <a name="example"></a><span data-ttu-id="f0f2c-135">示例</span><span class="sxs-lookup"><span data-stu-id="f0f2c-135">Example</span></span>

<span data-ttu-id="f0f2c-p104">以下示例使用 **CreateQueryDef** 方法创建并执行临时和永久的 **QueryDef**。若要使该过程运行，需要使用 GetrstTemp 函数。</span><span class="sxs-lookup"><span data-stu-id="f0f2c-p104">This example uses the **CreateQueryDef** method to create and execute both a temporary and a permanent **QueryDef**. The GetrstTemp function is required for this procedure to run.</span></span>

```vb
    Sub CreateQueryDefX() 
     
       Dim dbsNorthwind As Database 
       Dim qdfTemp As QueryDef 
       Dim qdfNew As QueryDef 
     
       Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
       With dbsNorthwind 
          ' Create temporary QueryDef. 
          Set qdfTemp = .CreateQueryDef("", _ 
             "SELECT * FROM Employees") 
          ' Open Recordset and print report. 
          GetrstTemp qdfTemp 
          ' Create permanent QueryDef. 
          Set qdfNew = .CreateQueryDef("NewQueryDef", _ 
             "SELECT * FROM Categories") 
          ' Open Recordset and print report. 
          GetrstTemp qdfNew 
          ' Delete new QueryDef because this is a demonstration. 
          .QueryDefs.Delete qdfNew.Name 
          .Close 
       End With 
     
    End Sub 
     
    Function GetrstTemp(qdfTemp As QueryDef) 
     
       Dim rstTemp As Recordset 
     
       With qdfTemp 
          Debug.Print .Name 
          Debug.Print "  " & .SQL 
          ' Open Recordset from QueryDef. 
          Set rstTemp = .OpenRecordset(dbOpenSnapshot) 
     
          With rstTemp 
             ' Populate Recordset and print number of records. 
             .MoveLast 
             Debug.Print "  Number of records = " & _ 
                .RecordCount 
             Debug.Print 
             .Close 
          End With 
     
       End With 
     
    End Function 
```

<br/>

<span data-ttu-id="f0f2c-p105">以下示例使用 **CreateQueryDef** 和 **OpenRecordset** 方法以及 **SQL** 属性，查询 Microsoft SQL Server 示例数据库 Pubs 中的书名表，并返回最畅销书籍的书名和书名标识符。然后查询作者表，并指示用户根据每个作者的版税份额向其发送红利支票（总红利为 ￥1,000，每个作者应收到该金额的一定份额）。</span><span class="sxs-lookup"><span data-stu-id="f0f2c-p105">This example uses the **CreateQueryDef** and **OpenRecordset** methods and the **SQL** property to query the table of titles in the Microsoft SQL Server sample database Pubs and return the title and title identifier of the best-selling book. The example then queries the table of authors and instructs the user to send a bonus check to each author based on his or her royalty share (the total bonus is $1,000 and each author should receive a percentage of that amount).</span></span>

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

<span data-ttu-id="f0f2c-140">下面的示例演示如何创建参数查询。</span><span class="sxs-lookup"><span data-stu-id="f0f2c-140">The following example shows how to create a parameter query.</span></span> <span data-ttu-id="f0f2c-141">两个参数，名为 Param1 和 Param2 创建名为**myQuery**的查询。</span><span class="sxs-lookup"><span data-stu-id="f0f2c-141">A query named **myQuery** is created with two parameters, named Param1 and Param2.</span></span> <span data-ttu-id="f0f2c-142">若要执行此操作，查询的 SQL 属性设置为定义的参数的结构化查询语言 (SQL) 语句。</span><span class="sxs-lookup"><span data-stu-id="f0f2c-142">To do this, the SQL property of the query is set to a Structured Query Language (SQL) statement that defines the parameters.</span></span>

<span data-ttu-id="f0f2c-143">**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="f0f2c-143">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

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
