---
title: Recordset.Index Property (DAO)
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
ms.openlocfilehash: 01a19fd621d8124616872bebc54c6ac9482ffe08
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468462"
---
# <a name="recordsetindex-property-dao"></a><span data-ttu-id="d12e8-102">Recordset.Index Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="d12e8-102">Recordset.Index Property (DAO)</span></span>

<span data-ttu-id="d12e8-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="d12e8-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="d12e8-104">设置或返回一个值，该值指示表类型 **[Recordset](index-object-dao.md)** 对象中的当前 **[Index](recordset-object-dao.md)** 对象的名称（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="d12e8-104">Sets or returns a value that indicates the name of the current **[Index](index-object-dao.md)** object in a table-type **[Recordset](recordset-object-dao.md)** object (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="d12e8-105">语法</span><span class="sxs-lookup"><span data-stu-id="d12e8-105">Syntax</span></span>

<span data-ttu-id="d12e8-106">*表达式*。索引</span><span class="sxs-lookup"><span data-stu-id="d12e8-106">*expression* .Index</span></span>

<span data-ttu-id="d12e8-107">*表达式*一个表示**Recordset**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="d12e8-107">*expression* A variable that represents a **Recordset** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="d12e8-108">注解</span><span class="sxs-lookup"><span data-stu-id="d12e8-108">Remarks</span></span>

<span data-ttu-id="d12e8-p101">基表中的记录不按任何特定顺序存储。设置 **Index** 属性会更改从数据库返回的记录的顺序；它不影响存储记录的顺序。</span><span class="sxs-lookup"><span data-stu-id="d12e8-p101">Records in base tables aren't stored in any particular order. Setting the **Index** property changes the order of records returned from the database; it doesn't affect the order in which the records are stored.</span></span>

<span data-ttu-id="d12e8-p102">必须已经定义了指定的 **Index** 对象。如果将 **Index** 属性设置为不存在的 **Index** 对象，或者当您使用 [**Seek**](recordset-seek-method-dao.md) 方法时 **Index** 属性不存在，则会发生可捕获的错误。</span><span class="sxs-lookup"><span data-stu-id="d12e8-p102">The specified **Index** object must already be defined. If you set the **Index** property to an **Index** object that doesn't exist or if the **Index** property isn't set when you use the **[Seek](recordset-seek-method-dao.md)** method, a trappable error occurs.</span></span>

<span data-ttu-id="d12e8-113">检查 **TableDef** 对象的 **Indexes** 集合，以确定哪些 **Index** 对象可用于从该 **TableDef** 对象创建的表类型 **Recordset** 对象。</span><span class="sxs-lookup"><span data-stu-id="d12e8-113">Examine the **Indexes** collection of a **TableDef** object to determine what **Index** objects are available to table-type **Recordset** objects created from that **TableDef** object.</span></span>

<span data-ttu-id="d12e8-114">可以为表创建新的索引，方法是创建新的 **Index** 对象，设置其属性，将其追加到基础 **TableDef** 对象的 **Indexes** 集合中，然后重新打开 **Recordset** 对象。</span><span class="sxs-lookup"><span data-stu-id="d12e8-114">You can create a new index for the table by creating a new **Index** object, setting its properties, appending it to the **Indexes** collection of the underlying **TableDef** object, and then reopening the **Recordset** object.</span></span>

<span data-ttu-id="d12e8-115">从表类型 **Recordset** 对象返回的记录只能按为基础 **TableDef** 对象定义的索引进行排序。</span><span class="sxs-lookup"><span data-stu-id="d12e8-115">Records returned from a table-type **Recordset** object can be ordered only by the indexes defined for the underlying **TableDef** object.</span></span> <span data-ttu-id="d12e8-116">要排序一些其他顺序的记录，可以通过使用 ORDER BY 子句的 SQL 语句打开动态集类型、 快照类型或仅向前类型**Recordset**对象。</span><span class="sxs-lookup"><span data-stu-id="d12e8-116">To sort records in some other order, you can open a dynaset–, snapshot–, or forward–only–type **Recordset** object by using an SQL statement with an ORDER BY clause.</span></span>


> [!NOTE]
> - <span data-ttu-id="d12e8-p104">您不必为表创建索引。对于大型的未编制索引的表，访问特定记录或创建 **Recordset** 对象可能花费很长时间。另一方面，由于所有索引都是自动更新的，创建太多索引会降低更新、追加和删除操作的速度。</span><span class="sxs-lookup"><span data-stu-id="d12e8-p104">You don't have to create indexes for tables. With large, unindexed tables, accessing a specific record or creating a **Recordset** object can take a long time. On the other hand, creating too many indexes slows down update, append, and delete operations because all indexes are automatically updated.</span></span>
> - <span data-ttu-id="d12e8-120">从不含索引的表中读取的记录没有特定返回顺序。</span><span class="sxs-lookup"><span data-stu-id="d12e8-120">Records read from tables without indexes are returned in no particular sequence.</span></span>
> - <span data-ttu-id="d12e8-121">[Index](field-attributes-property-dao.md) 对象中每个 [**Field**](field-object-dao.md) 对象的 \*\*\*\*Attributes\*\*\*\* 属性决定了记录的顺序，因此决定了对该索引使用的访问技术。</span><span class="sxs-lookup"><span data-stu-id="d12e8-121">The **[Attributes](field-attributes-property-dao.md)** property of each **[Field](field-object-dao.md)** object in the **Index** object determines the order of records and consequently determines the access techniques to use for that index.</span></span>
> - <span data-ttu-id="d12e8-122">唯一索引有助于优化记录的查找。</span><span class="sxs-lookup"><span data-stu-id="d12e8-122">A unique index helps optimize finding records.</span></span>
> - <span data-ttu-id="d12e8-123">索引不会影响基表，如何只记录由访问表类型**Recordset**对象时选择特定的索引，或打开**Recordset**时的索引影响物理的顺序。</span><span class="sxs-lookup"><span data-stu-id="d12e8-123">Indexes don't affect the physical order of a base table, indexes affect only how the records are accessed by the table-type **Recordset** object when a particular index is chosen or when **Recordset** is opened.</span></span>


## <a name="example"></a><span data-ttu-id="d12e8-124">示例</span><span class="sxs-lookup"><span data-stu-id="d12e8-124">Example</span></span>

<span data-ttu-id="d12e8-125">以下示例使用 **Index** 属性来设置表类型 **Recordset** 的不同记录顺序。</span><span class="sxs-lookup"><span data-stu-id="d12e8-125">This example uses the **Index** property to set different record orders for a table-type **Recordset**.</span></span>

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

<span data-ttu-id="d12e8-126">以下示例通过允许用户根据 ID 编号搜索产品，来演示 **Seek** 方法。</span><span class="sxs-lookup"><span data-stu-id="d12e8-126">This example demonstrates the **Seek** method by allowing the user to search for a product based on an ID number.</span></span>

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

<span data-ttu-id="d12e8-127">下面的示例演示如何使用 Seek 方法来查找链接表中的记录。</span><span class="sxs-lookup"><span data-stu-id="d12e8-127">The following example shows how to use the Seek method to find a record in a linked table.</span></span>

<span data-ttu-id="d12e8-128">**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="d12e8-128">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

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