---
title: Recordset 对象 (DAO)
TOCTitle: Recordset Object
ms:assetid: 9774232c-e6da-175b-fc7f-ed2ab7908fa0
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197799(v=office.15)
ms:contentKeyID: 48546469
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: a4ce9b3480cfa2a8eb074065016131e2c82752c3
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25921126"
---
# <a name="recordset-object-dao"></a><span data-ttu-id="9a4aa-102">Recordset 对象 (DAO)</span><span class="sxs-lookup"><span data-stu-id="9a4aa-102">Recordset object (DAO)</span></span>

<span data-ttu-id="9a4aa-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="9a4aa-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="9a4aa-104">**Recordset** 对象代表基表中的记录或通过运行查询得到的记录。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-104">A **Recordset** object represents the records in a base table or the records that result from running a query.</span></span>

## <a name="remarks"></a><span data-ttu-id="9a4aa-105">注解</span><span class="sxs-lookup"><span data-stu-id="9a4aa-105">Remarks</span></span>

<span data-ttu-id="9a4aa-p101">使用 **Recordset** 对象在记录级别处理数据库中的数据。使用 DAO 对象时，几乎可以完全使用 **Recordset** 对象处理数据。所有 **Recordset** 对象都是使用记录（行）和字段（列）构建的。共有五种类型的 **Recordset** 对象：</span><span class="sxs-lookup"><span data-stu-id="9a4aa-p101">You use **Recordset** objects to manipulate data in a database at the record level. When you use DAO objects, you manipulate data almost entirely using **Recordset** objects. All **Recordset** objects are constructed using records (rows) and fields (columns). There are five types of **Recordset** objects:</span></span>

- <span data-ttu-id="9a4aa-110">表类型 Recordset - 基表在代码中的表示形式，可用于在单个数据库表中添加、更改或删除记录（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-110">Table-type Recordset— representation in code of a base table that you can use to add, change, or delete records from a single database table (Microsoft Access workspaces only).</span></span>

- <span data-ttu-id="9a4aa-p102">动态集类型 Recordset - 其中可以包含可更新记录的查询结果。动态集类型 **Recordset** 对象是一个动态的记录集，可用于在一个或多个基础数据库表中添加、更改或删除记录。动态集类型 **Recordset** 对象可以包含数据库中的一个或多个表中的字段。此类型对应于 ODBC 键集游标。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-p102">Dynaset-type Recordset— the result of a query that can have updatable records. A dynaset-type **Recordset** object is a dynamic set of records that you can use to add, change, or delete records from an underlying database table or tables. A dynaset-type **Recordset** object can contain fields from one or more tables in a database. This type corresponds to an ODBC keyset cursor.</span></span>

- <span data-ttu-id="9a4aa-p103">快照类型 Recordset - 一组记录的静态副本，可用于查找数据或生成报表。快照类型 **Recordset** 对象可以包含数据库中的一个或多个表中的字段，但不能进行更新。此类型对应于 ODBC 静态游标。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-p103">Snapshot-type Recordset— a static copy of a set of records that you can use to find data or generate reports. A snapshot-type **Recordset** object can contain fields from one or more tables in a database but can't be updated. This type corresponds to an ODBC static cursor.</span></span>

- <span data-ttu-id="9a4aa-p104">仅向前类型 Recordset - 除不提供游标外，其他均与快照类型相同。只能在记录中向前滚动。如果只需遍历结果集一次，这种类型可提高性能。此类型对应于 ODBC 仅向前游标。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-p104">Forward-only-type Recordset— identical to a snapshot except that no cursor is provided. You can only scroll forward through records. This improves performance in situations where you only need to make a single pass through a result set. This type corresponds to an ODBC forward-only cursor.</span></span>

- <span data-ttu-id="9a4aa-p105">动态类型 Recordset - 一个或多个基表中的查询结果集，可以在该基表中添加、更改或删除行返回查询产生的记录。此外，其他用户在基表中添加、删除或编辑的记录也出现在 **Recordset** 中。此类型对应于 ODBC 动态游标（仅适用于 ODBCDirect 工作区）。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-p105">Dynamic-type Recordset— a query result set from one or more base tables in which you can add, change, or delete records from a row-returning query. Further, records other users add, delete, or edit in the base tables also appear in your **Recordset**. This type corresponds to an ODBC dynamic cursor (ODBCDirect workspaces only).</span></span>

> [!NOTE]
> <span data-ttu-id="9a4aa-125">Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-125">ODBCDirect workspaces are not supported in Microsoft Access 2013.</span></span> <span data-ttu-id="9a4aa-126">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-126">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span>

<span data-ttu-id="9a4aa-127">您可以选择您想要创建使用**OpenRecordset**方法的 type 参数的**Recordset**对象的类型。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-127">You can choose the type of **Recordset** object you want to create using the type argument of the **OpenRecordset** method.</span></span>

<span data-ttu-id="9a4aa-128">在 Microsoft Access 工作区中，如果未指定类型，DAO 尝试创建**Recordset**的类型有可用的大多数功能开头表。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-128">In a Microsoft Access workspace, if you don't specify a type, DAO attempts to create the type of **Recordset** with the most functionality available, starting with table.</span></span> <span data-ttu-id="9a4aa-129">如果此类型不可用，DAO 将尝试动态集类型，其次为快照类型，最后为仅向前类型的 **Recordset** 对象。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-129">If this type isn't available, DAO attempts a dynaset, then a snapshot, and finally a forward-only type **Recordset** object.</span></span>

<span data-ttu-id="9a4aa-130">在适用于 ODBCDirect 工作区中，如果未指定类型，DAO 尝试使用的最快的查询响应，创建**Recordset**的类型开头仅向前型。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-130">In an ODBCDirect workspace, if you don't specify a type, DAO attempts to create the type of **Recordset** with the fastest query response, starting with forward-only.</span></span> <span data-ttu-id="9a4aa-131">如果此类型不可用，DAO 将尝试快照类型，其次为动态集类型，最后为动态类型的 **Recordset** 对象。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-131">If this type isn't available, DAO attempts a snapshot, then a dynaset, and finally a dynamic- type **Recordset** object.</span></span>

<span data-ttu-id="9a4aa-p109">使用 Microsoft Access 工作区中的非链接 [**TableDef**](tabledef-object-dao.md) 对象创建 **Recordset** 对象时，将创建表类型 **Recordset** 对象。使用链接表或连接到 Microsoft Access 数据库引擎的 ODBC 数据库中的表只能创建动态集类型或快照类型 **Recordset** 对象。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-p109">When creating a **Recordset** object using a non-linked **[TableDef](tabledef-object-dao.md)** object in a Microsoft Access workspace, table-type **Recordset** objects are created. Only dynaset-type or snapshot-type **Recordset** objects can be created with linked tables or tables in Microsoft Access database engine-connected ODBC databases.</span></span>

<span data-ttu-id="9a4aa-134">打开 **Recordset** 对象时，会自动在 **Recordsets** 集合中添加一个新的相应对象；关闭该对象时，会自动删除相应的对象。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-134">A new **Recordset** object is automatically added to the **Recordsets** collection when you open the object, and is automatically removed when you close it.</span></span>

> [!NOTE]
> <span data-ttu-id="9a4aa-p110">[!注释] 如果使用变量表示 **Recordset** 对象和包含 **Recordset** 的 **Database** 对象，请确保这些变量具有相同的范围或生命周期。例如，如果声明了表示 **Recordset** 对象的公共变量，请确保表示包含了 **Recordset** 的 **Database** 的变量也是公共的，或者是使用 **Static** 关键字在 **Sub** 或 **Function** 过程中声明的。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-p110">If you use variables to represent a **Recordset** object and the **Database** object that contains the **Recordset**, make sure the variables have the same scope, or lifetime. For example, if you declare a public variable that represents a **Recordset** object, make sure the variable that represents the **Database** containing the **Recordset** is also public, or is declared in a **Sub** or **Function** procedure using the **Static** keyword.</span></span>

<span data-ttu-id="9a4aa-p111">可根据需要创建任意数目的 **Recordset** 对象变量。不同的 **Recordset** 对象可以在不发生冲突的情况下访问相同的表、查询和字段。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-p111">You can create as many **Recordset** object variables as needed. Different **Recordset** objects can access the same tables, queries, and fields without conflicting.</span></span>

<span data-ttu-id="9a4aa-139">动态集类型、 快照和仅向前类型**Recordset**对象存储在本地内存中。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-139">Dynaset–, snapshot–, and forward–only–type **Recordset** objects are stored in local memory.</span></span> <span data-ttu-id="9a4aa-140">如果本地内存的空间不足以存储数据，Microsoft Access 数据库引擎会将额外的数据保存到 TEMP 磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-140">If there isn't enough space in local memory to store the data, the Microsoft Access database engine saves the additional data to TEMP disk space.</span></span> <span data-ttu-id="9a4aa-141">如果此空间已耗尽，将发生可捕获的错误。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-141">If this space is exhausted, a trappable error occurs.</span></span>

<span data-ttu-id="9a4aa-p113">**Recordset** 对象的默认集合为 **Fields** 集合， **[Field](field-object-dao.md)** 对象的默认属性为 **[Value](field-value-property-dao.md)** 属性。可使用这些默认值简化代码。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-p113">The default collection of a **Recordset** object is the **Fields** collection, and the default property of a **[Field](field-object-dao.md)** object is the **[Value](field-value-property-dao.md)** property. Use these defaults to simplify your code.</span></span>

<span data-ttu-id="9a4aa-p114">在创建 **Recordset** 对象时，如果存在任何记录的话，当前记录将定位到第一条记录。如果不存在任何记录， **RecordCount** 属性设置为 0，并且 **BOF** 和 **EOF** 属性设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-p114">When you create a **Recordset** object, the current record is positioned to the first record if there are any records. If there are no records, the **RecordCount** property setting is 0, and the **BOF** and **EOF** property settings are **True**.</span></span>

<span data-ttu-id="9a4aa-146">可以使用 **MoveNext**、 **MovePrevious**、 **MoveFirst** 和 **MoveLast** 方法重新定位当前记录。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-146">You can use the **MoveNext**, **MovePrevious**, **MoveFirst**, and **MoveLast** methods to reposition the current record.</span></span> <span data-ttu-id="9a4aa-147">仅向前类型**Recordset**对象才支持仅**MoveNext**方法。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-147">Forward–only–type **Recordset** objects support only the **MoveNext** method.</span></span> <span data-ttu-id="9a4aa-148">在使用 Move 方法访问每条记录（或"遍历" **Recordset**）时，可以使用 **BOF** 和 **EOF** 属性检查 **Recordset** 对象的开头或结尾。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-148">When using the Move methods to visit each record (or "walk" through the **Recordset**), you can use the **BOF** and **EOF** properties to check for the beginning or end of the **Recordset** object.</span></span>

<span data-ttu-id="9a4aa-p116">对于 Microsoft Access 工作区中的动态集类型和快照类型 **Recordset** 对象，还可以使用 Find 方法（例如 **FindFirst**）根据条件查找特定的记录。如果未找到记录， **NoMatch** 属性将设置为 **True**。对于表类型 **Recordset** 对象，可以使用 **Seek** 方法扫描记录。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-p116">With dynaset- and snapshot-type **Recordset** objects in a Microsoft Access workspace, you can also use the Find methods, such as **FindFirst**, to locate a specific record based on criteria. If the record isn't found, the **NoMatch** property is set to **True**. For table-type **Recordset** objects, you can scan records using the **Seek** method.</span></span>

<span data-ttu-id="9a4aa-152">**Type** 属性指示所创建的 **Recordset** 对象的类型， **Updatable** 属性指示是否可以更改对象的记录。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-152">The **Type** property indicates the type of **Recordset** object created, and the **Updatable** property indicates whether you can change the object's records.</span></span>

<span data-ttu-id="9a4aa-153">**TableDef** 对象中存储了有关基表结构的信息，例如每个 **Field** 对象及任何 **Index** 对象的名称和数据类型。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-153">Information about the structure of a base table, such as the names and data types of each **Field** object and any **Index** objects, is stored in a **TableDef** object.</span></span>

<span data-ttu-id="9a4aa-154">若要按照序号或 **Name** 属性设置来引用集合中的 **Recordset** 对象，可以使用下列任何一种语法形式：</span><span class="sxs-lookup"><span data-stu-id="9a4aa-154">To refer to a **Recordset** object in a collection by its ordinal number or by its **Name** property setting, use any of the following syntax forms:</span></span>

- <span data-ttu-id="9a4aa-155">**Recordsets**(0)</span><span class="sxs-lookup"><span data-stu-id="9a4aa-155">**Recordsets**(0)</span></span>

- <span data-ttu-id="9a4aa-156">**记录集**("name")</span><span class="sxs-lookup"><span data-stu-id="9a4aa-156">**Recordsets**("name")</span></span>

- <span data-ttu-id="9a4aa-157">**记录集**\!\[名称\]</span><span class="sxs-lookup"><span data-stu-id="9a4aa-157">**Recordsets**\!\[name\]</span></span>

> [!NOTE]
> <span data-ttu-id="9a4aa-p117">[!注释] 可以多次打开同一个数据源或数据库中的 **Recordset** 对象，并在 **Recordsets** 集合中创建重复的名称。应该将 **Recordset** 对象分配给对象变量，并通过变量名来引用它们。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-p117">You can open a **Recordset** object from the same data source or database more than once, creating duplicate names in the **Recordsets** collection. You should assign **Recordset** objects to object variables and refer to them by variable name.</span></span>

## <a name="example"></a><span data-ttu-id="9a4aa-160">示例</span><span class="sxs-lookup"><span data-stu-id="9a4aa-160">Example</span></span>

<span data-ttu-id="9a4aa-161">以下示例通过打开四个不同类型的 **Recordsets**，枚举当前 **Database** 的 Recordsets 集合，以及枚举每个 **Recordset** 的 **Properties** 集合，演示 **Recordset** 对象和 **Recordsets** 集合。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-161">This example demonstrates **Recordset** objects and the **Recordsets** collection by opening four different types of **Recordsets**, enumerating the Recordsets collection of the current **Database**, and enumerating the **Properties** collection of each **Recordset**.</span></span>

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

<span data-ttu-id="9a4aa-p118">以下示例使用 **OpenRecordset** 方法打开五个不同的 **Recordset** 对象并显示其内容。若要使该过程正常运行，需要使用 OpenRecordsetOutput 过程。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-p118">This example uses the **OpenRecordset** method to open five different **Recordset** objects and display their contents. The OpenRecordsetOutput procedure is required for this procedure to run.</span></span>

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

<span data-ttu-id="9a4aa-164">以下示例打开一个动态类型 **Recordset** 对象，然后枚举其记录。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-164">This example opens a dynamic-type **Recordset** object and enumerates its records.</span></span>

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

<span data-ttu-id="9a4aa-165">以下示例打开一个动态集类型 **Recordset**，然后显示其字段的可更新程度。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-165">This example opens a dynaset-type **Recordset** and shows the extent to which its fields are updatable.</span></span>

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

<span data-ttu-id="9a4aa-166">以下示例打开一个仅向前类型 **Recordset**，演示其只读特征，然后使用 **MoveNext** 方法遍历 **Recordset**。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-166">This example opens a forward-only-type **Recordset**, demonstrates its read-only characteristics, and steps through the **Recordset** with the **MoveNext** method.</span></span>

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

<span data-ttu-id="9a4aa-167">以下示例打开一个快照类型 **Recordset**，演示其只读特征。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-167">This example opens a snapshot-type **Recordset** and demonstrates its read-only characteristics.</span></span>

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

<span data-ttu-id="9a4aa-168">以下示例打开一个表类型 **Recordset**，并设置其 **Index** 属性，然后枚举其记录。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-168">This example opens a table-type **Recordset**, sets its **Index** property, and enumerates its records.</span></span>

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

<span data-ttu-id="9a4aa-169">下面的示例演示如何使用 Seek 方法来查找链接表中的记录。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-169">The following example shows how to use the Seek method to find a record in a linked table.</span></span>

<span data-ttu-id="9a4aa-170">**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-170">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>


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

<span data-ttu-id="9a4aa-171">以下示例说明如何打开基于参数查询的 Recordset。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-171">The following example shows how to open a Recordset that is based on a parameter query.</span></span>

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

<span data-ttu-id="9a4aa-172">以下示例说明如何打开基于表或查询的 Recordset。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-172">The following example shows how to open a Recordset based on a table or a query.</span></span>

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

<span data-ttu-id="9a4aa-173">以下示例说明如何打开基于结构化查询语言 (SQL) 语句的 Recordset。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-173">The following example shows how to open a Recordset based on a Structured Query Language (SQL) statement.</span></span>

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

<span data-ttu-id="9a4aa-174">下面的示例演示如何使用 FindFirst 和 FindNext 方法在记录集中查找记录。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-174">The following example shows how to use the FindFirst and FindNext methods to find a record in a Recordset.</span></span>

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

<span data-ttu-id="9a4aa-175">下面的示例演示如何将查询的结果复制到新的 Microsoft Excel 工作簿中的工作表。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-175">The following example shows how to copy the results of a query to a worksheet in a new Microsoft Excel workbook.</span></span>

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

