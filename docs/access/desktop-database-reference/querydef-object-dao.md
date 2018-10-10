---
title: QueryDef Object (DAO)
TOCTitle: QueryDef Object
ms:assetid: 0b3d901c-345d-42a2-f5f1-fb09cc562e27
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845129(v=office.15)
ms:contentKeyID: 48543169
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: bad2f4795dad8e308af85d3cca4ca0f71d88d9c2
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466459"
---
# <a name="querydef-object-dao"></a><span data-ttu-id="c62d8-102">QueryDef Object (DAO)</span><span class="sxs-lookup"><span data-stu-id="c62d8-102">QueryDef Object (DAO)</span></span>

<span data-ttu-id="c62d8-103">**适用于：** Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="c62d8-103">**Applies to:** Access 2013 | Office 2013</span></span> 

<span data-ttu-id="c62d8-104">**QueryDef** 对象是 Microsoft Access 数据库引擎数据库中某个查询的存储定义。</span><span class="sxs-lookup"><span data-stu-id="c62d8-104">A **QueryDef** object is a stored definition of a query in a Microsoft Access database engine database.</span></span>

## <a name="remarks"></a><span data-ttu-id="c62d8-105">注解</span><span class="sxs-lookup"><span data-stu-id="c62d8-105">Remarks</span></span>

<span data-ttu-id="c62d8-p101">可以使用 **QueryDef** 对象定义查询。例如，您可以进行下列操作：</span><span class="sxs-lookup"><span data-stu-id="c62d8-p101">You can use the **QueryDef** object to define a query. For example, you can:</span></span>

- <span data-ttu-id="c62d8-108">使用 **SQL** 属性设置或返回查询定义。</span><span class="sxs-lookup"><span data-stu-id="c62d8-108">Use the **SQL** property to set or return the query definition.</span></span>

- <span data-ttu-id="c62d8-109">使用 **QueryDef** 对象的 **Parameters** 集合设置或返回查询参数。</span><span class="sxs-lookup"><span data-stu-id="c62d8-109">Use the **QueryDef** object's **Parameters** collection to set or return query parameters.</span></span>

- <span data-ttu-id="c62d8-110">使用 **Type** 属性返回一个值，该值指示查询是从现有表中选择记录、制作一个新表、将记录从一个表插入到另一个表、删除记录还是更新记录。</span><span class="sxs-lookup"><span data-stu-id="c62d8-110">Use the **Type** property to return a value indicating whether the query selects records from an existing table, makes a new table, inserts records from one table into another table, deletes records, or updates records.</span></span>

- <span data-ttu-id="c62d8-111">使用 **MaxRecords** 属性限制从查询返回的记录数。</span><span class="sxs-lookup"><span data-stu-id="c62d8-111">Use the **MaxRecords** property to limit the number of records returned from a query.</span></span>

- <span data-ttu-id="c62d8-p102">使用 **ODBCTimeout** 属性指示查询返回记录之前需要等待的时间长短。 **ODBCTimeout** 属性可应用到访问开放式数据库连接 (ODBC) 数据的任何查询。</span><span class="sxs-lookup"><span data-stu-id="c62d8-p102">Use the **ODBCTimeout** property to indicate how long to wait before the query returns records. The **ODBCTimeout** property applies to any query that accesses ODBC data.</span></span>

- <span data-ttu-id="c62d8-p103">使用 **ReturnsRecords** 属性指示查询返回记录。 **ReturnsRecords** 属性仅对 SQL 传递查询有效。</span><span class="sxs-lookup"><span data-stu-id="c62d8-p103">Use the **ReturnsRecords** property to indicate that the query returns records. The **ReturnsRecords** property is only valid on SQL pass-through queries.</span></span>

- <span data-ttu-id="c62d8-116">使用 **Connect** 属性生成一个访问 ODC 数据库的 SQL 传递查询。</span><span class="sxs-lookup"><span data-stu-id="c62d8-116">Use the **Connect** property to make an SQL pass-through query to an ODC database.</span></span>

<span data-ttu-id="c62d8-p104">还可以创建临时 **QueryDef** 对象。与永久 **QueryDef** 对象不同，临时 **QueryDef** 对象不会被保存到磁盘，也不会被追加到 **QueryDefs** 集合。对于在运行时必须反复运行，但不需要在磁盘中保存的查询，使用临时 **QueryDef** 对象十分有用，对于在运行时需要创建其 SQL 字符串/语句的查询尤其如此。</span><span class="sxs-lookup"><span data-stu-id="c62d8-p104">You can also create temporary **QueryDef** objects. Unlike permanent **QueryDef** objects, temporary **QueryDef** objects are not saved to disk or appended to the **QueryDefs** collection. Temporary **QueryDef** objects are useful for queries that you must run repeatedly during run time but do not not need to save to disk, particularly if you create their SQL statements during run time.</span></span>

<span data-ttu-id="c62d8-p105">可以将 Microsoft Access 工作区中的永久 **QueryDef** 对象视为编译的 SQL 语句。如果从永久 **QueryDef** 对象执行查询，则查询的运行速度比通过 **OpenRecordset** 方法运行等效 SQL 语句的速度更快。这是因为 Microsoft Access 数据库引擎在执行查询之前，不需要对其进行编译。</span><span class="sxs-lookup"><span data-stu-id="c62d8-p105">You can think of a permanent **QueryDef** object in a Microsoft Access workspace as a compiled SQL statement. If you execute a query from a permanent **QueryDef** object, the query will run faster than if you run the equivalent SQL statement from the **OpenRecordset** method. This is because the Microsoft Access database engine doesn't need to compile the query before executing it.</span></span>

<span data-ttu-id="c62d8-p106">使用通过 Microsoft Access 数据库引擎访问的外部数据库引擎的本地 SQL 方言的首选方法是使用 **QueryDef** 对象。例如，可以创建一个 Microsoft SQL Server 查询，并将其存储在 **QueryDef** 对象中。如果需要使用非 Microsoft Access 数据库引擎 SQL 查询，必须提供一个指向外部数据源的 **Connect** 属性字符串。具有有效 **Connect** 属性的查询将绕过 Microsoft Access 数据库引擎，并将查询直接传递给外部数据库服务器，以进行处理。</span><span class="sxs-lookup"><span data-stu-id="c62d8-p106">The preferred way to use the native SQL dialect of an external database engine accessed through the Microsoft Access database engine is through **QueryDef** objects. For example, you can create a Microsoft SQL Server query and store it in a **QueryDef** object. When you need to use a non-Microsoft Access database engine SQL query, you must provide a **Connect** property string that points to the external data source. Queries with valid **Connect** properties bypass the Microsoft Access database engine and pass the query directly to the external database server for processing.</span></span>

<span data-ttu-id="c62d8-127">若要创建新的 **QueryDef** 对象，请使用 **CreateQueryDef** 方法。</span><span class="sxs-lookup"><span data-stu-id="c62d8-127">To create a new **QueryDef** object, use the **CreateQueryDef** method.</span></span> <span data-ttu-id="c62d8-128">在 Microsoft Access 工作区中，如果您提供名称参数的字符串或明确将新的**QueryDef**对象的**Name**属性设置为非 – 零长度字符串，您将创建自动将永久**QueryDef**追加到**QueryDefs**集合并保存到磁盘。</span><span class="sxs-lookup"><span data-stu-id="c62d8-128">In a Microsoft Access workspace, if you supply a string for the name argument or if you explicitly set the **Name** property of the new **QueryDef** object to a non–zero-length string, you will create a permanent **QueryDef** that will automatically be appended to the **QueryDefs** collection and saved to disk.</span></span> <span data-ttu-id="c62d8-129">提供一个零长度字符串作为名称参数或明确将**名称**属性设置为零长度字符串将导致临时**QueryDef**对象。</span><span class="sxs-lookup"><span data-stu-id="c62d8-129">Supplying a zero-length string as the name argument or explicitly setting the **Name** property to a zero-length string will result in a temporary **QueryDef** object.</span></span>

<span data-ttu-id="c62d8-130">若要按照序号或 **Name** 属性设置来引用集合中的 **QueryDef** 对象，可以使用下列任何一种语法形式：</span><span class="sxs-lookup"><span data-stu-id="c62d8-130">To refer to a **QueryDef** object in a collection by its ordinal number or by its **Name** property setting, use any of the following syntax forms:</span></span>

<span data-ttu-id="c62d8-131">QueryDefs(0)</span><span class="sxs-lookup"><span data-stu-id="c62d8-131">QueryDefs(0)</span></span>

<span data-ttu-id="c62d8-132">QueryDefs("name")</span><span class="sxs-lookup"><span data-stu-id="c62d8-132">QueryDefs("name")</span></span>

<span data-ttu-id="c62d8-133">QueryDefs\! \[名称\]</span><span class="sxs-lookup"><span data-stu-id="c62d8-133">QueryDefs\!\[ name\]</span></span>

<span data-ttu-id="c62d8-134">只能按分配给临时 **QueryDef** 对象的对象变量来引用这些临时对象。</span><span class="sxs-lookup"><span data-stu-id="c62d8-134">You can refer to temporary **QueryDef** objects only by the object variables that you have assigned to them.</span></span>

<span data-ttu-id="c62d8-135">**链接提供** [UtterAccess](https://www.utteraccess.com)社区。</span><span class="sxs-lookup"><span data-stu-id="c62d8-135">**Link provided by** the [UtterAccess](https://www.utteraccess.com) community.</span></span> <span data-ttu-id="c62d8-136">UtterAccess 是主要的 Microsoft Access Wiki 和帮助论坛。</span><span class="sxs-lookup"><span data-stu-id="c62d8-136">UtterAccess is the premier Microsoft Access wiki and help forum.</span></span>

- [<span data-ttu-id="c62d8-137">查询： SQL 到 Word 文档</span><span class="sxs-lookup"><span data-stu-id="c62d8-137">Queries: Document SQL to Word</span></span>](https://www.utteraccess.com/wiki/index.php/queries:_document_sql_to_word)

## <a name="example"></a><span data-ttu-id="c62d8-138">示例</span><span class="sxs-lookup"><span data-stu-id="c62d8-138">Example</span></span>

<span data-ttu-id="c62d8-p109">以下示例创建一个新的 **QueryDef** 对象，并将其追加到 Northwind **Database** 对象的 **QueryDefs** 集合。然后，该示例枚举 **QueryDefs** 集合和新 **QueryDef** 的 **Properties** 集合。</span><span class="sxs-lookup"><span data-stu-id="c62d8-p109">This example creates a new **QueryDef** object and appends it to the **QueryDefs** collection of the Northwind **Database** object. It then enumerates the **QueryDefs** collection and the **Properties** collection of the new **QueryDef**.</span></span>

```vb
    Sub QueryDefX() 
     
       Dim dbsNorthwind As Database 
       Dim qdfNew As QueryDef 
       Dim qdfLoop As QueryDef 
       Dim prpLoop As Property 
     
       Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
       ' Create new QueryDef object. Because it has a  
       ' name, it is automatically appended to the  
       ' QueryDefs collection. 
       Set qdfNew = dbsNorthwind.CreateQueryDef("NewQueryDef", _ 
             "SELECT * FROM Categories") 
     
       With dbsNorthwind 
          Debug.Print .QueryDefs.Count & _ 
             " QueryDefs in " & .Name 
     
          ' Enumerate QueryDefs collection. 
          For Each qdfLoop In .QueryDefs 
             Debug.Print "  " & qdfLoop.Name 
          Next qdfLoop 
     
          With qdfNew 
             Debug.Print "Properties of " & .Name 
     
             ' Enumerate Properties collection of new  
             ' QueryDef object. 
             For Each prpLoop In .Properties 
                On Error Resume Next 
                Debug.Print "  " & prpLoop.Name & " - " & _ 
                   IIf(prpLoop = "", "[empty]", prpLoop) 
                On Error Goto 0 
             Next prpLoop 
          End With 
     
          ' Delete new QueryDef because this is a  
          ' demonstration. 
          .QueryDefs.Delete qdfNew.Name 
          .Close 
       End With 
     
    End Sub 
```

<br/>

<span data-ttu-id="c62d8-p110">以下示例使用 **CreateQueryDef** 方法创建并执行临时和永久的 **QueryDef**。若要使该过程运行，需要使用 GetrstTemp 函数。</span><span class="sxs-lookup"><span data-stu-id="c62d8-p110">This example uses the **CreateQueryDef** method to create and execute both a temporary and a permanent **QueryDef**. The GetrstTemp function is required for this procedure to run.</span></span>

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

<span data-ttu-id="c62d8-143">下面的示例演示如何替换已保存的查询中的结构化查询语言 (SQL) 语句。</span><span class="sxs-lookup"><span data-stu-id="c62d8-143">The following example shows how to replace the Structured Query Language (SQL) statement in a saved query.</span></span>

<span data-ttu-id="c62d8-144">**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="c62d8-144">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

```vb
    ‘To change the Where clause in a saved query  
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

