---
title: TableDef Object (DAO)
TOCTitle: TableDef Object
ms:assetid: 715146b6-c62a-abff-28ee-e6bbe3c08adf
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195790(v=office.15)
ms:contentKeyID: 48545582
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ef0a7c167321a45249fb022e0987a5f8d6364ea0
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465562"
---
# <a name="tabledef-object-dao"></a><span data-ttu-id="b8b6d-102">TableDef Object (DAO)</span><span class="sxs-lookup"><span data-stu-id="b8b6d-102">TableDef Object (DAO)</span></span>

<span data-ttu-id="b8b6d-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="b8b6d-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="b8b6d-104">**TableDef** 对象代表基表或链接表的已存储定义（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="b8b6d-104">A **TableDef** object represents the stored definition of a base table or a linked table (Microsoft Access workspaces only).</span></span>

## <a name="remarks"></a><span data-ttu-id="b8b6d-105">注解</span><span class="sxs-lookup"><span data-stu-id="b8b6d-105">Remarks</span></span>

<span data-ttu-id="b8b6d-p101">通过使用 **TableDef** 对象及其方法和属性来操作表定义。例如，您可以进行下列操作：</span><span class="sxs-lookup"><span data-stu-id="b8b6d-p101">You manipulate a table definition using a **TableDef** object and its methods and properties. For example, you can:</span></span>

- <span data-ttu-id="b8b6d-108">检查数据库中的任何本地表、链接表或外部表的字段和索引结构。</span><span class="sxs-lookup"><span data-stu-id="b8b6d-108">Examine the field and index structure of any local, linked, or external table in a database.</span></span>

- <span data-ttu-id="b8b6d-109">使用 **Connect** 和 **SourceTableName** 属性设置或返回有关链接表的信息，并使用 **RefreshLink** 方法更新与链接表的连接。</span><span class="sxs-lookup"><span data-stu-id="b8b6d-109">Use the **Connect** and **SourceTableName** properties to set or return information about linked tables, and use the **RefreshLink** method to update connections to linked tables.</span></span>

- <span data-ttu-id="b8b6d-110">使用 **ValidationRule** 和 **ValidationText** 属性设置或返回验证条件。</span><span class="sxs-lookup"><span data-stu-id="b8b6d-110">Use the **ValidationRule** and **ValidationText** properties to set or return validation conditions.</span></span>

- <span data-ttu-id="b8b6d-111">使用**OpenRecordset**方法创建表 –、 动态集类型、 动态 –、 快照类型或仅向前类型**Recordset**对象，根据表定义。</span><span class="sxs-lookup"><span data-stu-id="b8b6d-111">Use the **OpenRecordset** method to create a table–, dynaset–, dynamic–, snapshot–, or forward–only–type **Recordset** object, based on the table definition.</span></span>

<span data-ttu-id="b8b6d-112">对于基表， **RecordCount** 属性包含指定数据库表中的记录数。</span><span class="sxs-lookup"><span data-stu-id="b8b6d-112">For base tables, the **RecordCount** property contains the number of records in the specified database table.</span></span> <span data-ttu-id="b8b6d-113">对于链接表， **RecordCount**属性设置始终为-1。</span><span class="sxs-lookup"><span data-stu-id="b8b6d-113">For linked tables, the **RecordCount** property setting is always –1.</span></span>

<span data-ttu-id="b8b6d-114">若要创建新的 **TableDef** 对象，请使用 **[CreateTableDef](database-createtabledef-method-dao.md)** 方法。</span><span class="sxs-lookup"><span data-stu-id="b8b6d-114">To create a new **TableDef** object, use the **[CreateTableDef](database-createtabledef-method-dao.md)** method.</span></span>

### <a name="to-add-a-field-to-a-table"></a><span data-ttu-id="b8b6d-115">向表中添加字段</span><span class="sxs-lookup"><span data-stu-id="b8b6d-115">To add a field to a table</span></span>

1.  <span data-ttu-id="b8b6d-116">确保基于表的任何 **[Recordset](recordset-object-dao.md)** 对象全都已关闭。</span><span class="sxs-lookup"><span data-stu-id="b8b6d-116">Make sure any **[Recordset](recordset-object-dao.md)** objects based on the table are all closed.</span></span>

2.  <span data-ttu-id="b8b6d-117">使用 **CreateField** 方法创建 **Field** 对象变量，然后设置其属性。</span><span class="sxs-lookup"><span data-stu-id="b8b6d-117">Use the **CreateField** method to create a **Field** object variable and set its properties.</span></span>

3.  <span data-ttu-id="b8b6d-118">使用 **Append** 方法将 **Field** 对象添加到 **TableDef** 对象的 **Fields** 集合。</span><span class="sxs-lookup"><span data-stu-id="b8b6d-118">Use the **Append** method to add the **Field** object to the **Fields** collection of the **TableDef** object.</span></span>

<span data-ttu-id="b8b6d-119">如果没有给 **TableDefs** 集合中的 **Field** 对象分配任何索引，则可以将其删除，但是会丢失字段的数据。</span><span class="sxs-lookup"><span data-stu-id="b8b6d-119">You can delete a **Field** object from a **TableDefs** collection if it doesn't have any indexes assigned to it, but you will lose the field's data.</span></span>

### <a name="to-create-a-table-that-is-ready-for-new-records-in-a-database"></a><span data-ttu-id="b8b6d-120">创建可随时用作数据库中新记录的表</span><span class="sxs-lookup"><span data-stu-id="b8b6d-120">To create a table that is ready for new records in a database</span></span>

1.  <span data-ttu-id="b8b6d-121">使用 **CreateTableDef** 方法创建 **TableDef** 对象。</span><span class="sxs-lookup"><span data-stu-id="b8b6d-121">Use the **CreateTableDef** method to create a **TableDef** object.</span></span>

2.  <span data-ttu-id="b8b6d-122">设置该对象的属性。</span><span class="sxs-lookup"><span data-stu-id="b8b6d-122">Set its properties.</span></span>

3.  <span data-ttu-id="b8b6d-123">对于表中的每个字段，使用 **CreateField** 方法创建 **Field** 对象变量，然后设置其属性。</span><span class="sxs-lookup"><span data-stu-id="b8b6d-123">For each field in the table, use the **CreateField** method to create a **Field** object variable and set its properties.</span></span>

4.  <span data-ttu-id="b8b6d-124">使用 **Append** 方法，将字段添加到 **TableDef** 对象的 **Fields** 集合。</span><span class="sxs-lookup"><span data-stu-id="b8b6d-124">Use the **Append** method to add the fields to the **Fields** collection of the **TableDef** object.</span></span>

5.  <span data-ttu-id="b8b6d-125">使用 **Append** 方法，将新的 **TableDef** 对象添加到 **Database** 对象的 **TableDefs** 集合。</span><span class="sxs-lookup"><span data-stu-id="b8b6d-125">Use the **Append** method to add the new **TableDef** object to the **TableDefs** collection of the **Database** object.</span></span>

<span data-ttu-id="b8b6d-126">链接表由 **TableDef** 对象的 **SourceTableName** 和 **Connect** 属性连接到数据库。</span><span class="sxs-lookup"><span data-stu-id="b8b6d-126">A linked table is connected to the database by the **SourceTableName** and **Connect** properties of the **TableDef** object.</span></span>

### <a name="to-link-a-table-to-a-database"></a><span data-ttu-id="b8b6d-127">将表链接到数据库</span><span class="sxs-lookup"><span data-stu-id="b8b6d-127">To link a table to a database</span></span>

1.  <span data-ttu-id="b8b6d-128">使用 **CreateTableDef** 方法创建 **TableDef** 对象。</span><span class="sxs-lookup"><span data-stu-id="b8b6d-128">Use the **CreateTableDef** method to create a **TableDef** object.</span></span>

2.  <span data-ttu-id="b8b6d-129">设置该对象的 **Connect** 和 **SourceTableName** 属性（并且有选择地设置它的 **Attributes** 属性）。</span><span class="sxs-lookup"><span data-stu-id="b8b6d-129">Set its **Connect** and **SourceTableName** properties (and optionally, its **Attributes** property).</span></span>

3.  <span data-ttu-id="b8b6d-130">使用 **Append** 方法，将该对象添加到 **Database** 的 **TableDefs** 集合。</span><span class="sxs-lookup"><span data-stu-id="b8b6d-130">Use the **Append** method to add it to the **TableDefs** collection of a **Database**.</span></span>

<span data-ttu-id="b8b6d-131">若要按照序号或 **Name** 属性设置来引用集合中的 **TableDef** 对象，可以使用下列任何一种语法形式：</span><span class="sxs-lookup"><span data-stu-id="b8b6d-131">To refer to a **TableDef** object in a collection by its ordinal number or by its **Name** property setting, use any of the following syntax forms:</span></span>

<span data-ttu-id="b8b6d-132">**TableDefs**(0)</span><span class="sxs-lookup"><span data-stu-id="b8b6d-132">**TableDefs**(0)</span></span>

<span data-ttu-id="b8b6d-133">**TableDefs**("name")</span><span class="sxs-lookup"><span data-stu-id="b8b6d-133">**TableDefs**("name")</span></span>

<span data-ttu-id="b8b6d-134">**TableDefs**\!\[名称\]</span><span class="sxs-lookup"><span data-stu-id="b8b6d-134">**TableDefs**\!\[name\]</span></span>

## <a name="example"></a><span data-ttu-id="b8b6d-135">示例</span><span class="sxs-lookup"><span data-stu-id="b8b6d-135">Example</span></span>

<span data-ttu-id="b8b6d-p103">以下示例创建一个新的 **TableDef** 对象，并将其追加到 Northwind Database 对象的 **TableDefs** 集合。然后，该示例枚举 **TableDefs** 集合和新 **TableDef** 的 **Properties** 集合。</span><span class="sxs-lookup"><span data-stu-id="b8b6d-p103">This example creates a new **TableDef** object and appends it to the **TableDefs** collection of the Northwind Database object. It then enumerates the **TableDefs** collection and the **Properties** collection of the new **TableDef**.</span></span>

```vb
    Sub TableDefX() 
     
       Dim dbsNorthwind As Database 
       Dim tdfNew As TableDef 
       Dim tdfLoop As TableDef 
       Dim prpLoop As Property 
     
       Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
       ' Create new TableDef object, append Field objects  
       ' to its Fields collection, and append TableDef  
       ' object to the TableDefs collection of the  
       ' Database object. 
       Set tdfNew = dbsNorthwind.CreateTableDef("NewTableDef") 
       tdfNew.Fields.Append tdfNew.CreateField("Date", dbDate) 
       dbsNorthwind.TableDefs.Append tdfNew 
     
       With dbsNorthwind 
          Debug.Print .TableDefs.Count & _ 
             " TableDefs in " & .Name 
     
          ' Enumerate TableDefs collection. 
          For Each tdfLoop In .TableDefs 
             Debug.Print "  " & tdfLoop.Name 
          Next tdfLoop 
     
          With tdfNew 
             Debug.Print "Properties of " & .Name 
     
             ' Enumerate Properties collection of new 
             ' TableDef object, only printing properties 
             ' with non-empty values. 
             For Each prpLoop In .Properties 
                Debug.Print "  " & prpLoop.Name & " - " & _ 
                   IIf(prpLoop = "", "[empty]", prpLoop) 
             Next prpLoop 
     
          End With 
     
          ' Delete new TableDef since this is a  
          ' demonstration. 
          .TableDefs.Delete tdfNew.Name 
          .Close 
       End With 
     
    End Sub 
```

<br/>

<span data-ttu-id="b8b6d-138">以下示例在 Northwind 数据库中创建一个新的 **TableDef** 对象。</span><span class="sxs-lookup"><span data-stu-id="b8b6d-138">This example creates a new **TableDef** object in the Northwind database.</span></span>

```vb 
Sub CreateTableDefX() 
 
   Dim dbsNorthwind As Database 
   Dim tdfNew As TableDef 
   Dim prpLoop As Property 
 
   Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
 
   ' Create a new TableDef object. 
   Set tdfNew = dbsNorthwind.CreateTableDef("Contacts") 
 
   With tdfNew 
      ' Create fields and append them to the new TableDef  
      ' object. This must be done before appending the  
      ' TableDef object to the TableDefs collection of the  
      ' Northwind database. 
      .Fields.Append .CreateField("FirstName", dbText) 
      .Fields.Append .CreateField("LastName", dbText) 
      .Fields.Append .CreateField("Phone", dbText) 
      .Fields.Append .CreateField("Notes", dbMemo) 
 
      Debug.Print "Properties of new TableDef object " & _ 
         "before appending to collection:" 
 
      ' Enumerate Properties collection of new TableDef  
      ' object. 
      For Each prpLoop In .Properties 
         On Error Resume Next 
         If prpLoop <> "" Then Debug.Print "  " & _ 
           prpLoop.Name & " = " & prpLoop 
         On Error GoTo 0 
      Next prpLoop 
 
      ' Append the new TableDef object to the Northwind  
      ' database. 
      dbsNorthwind.TableDefs.Append tdfNew 
 
      Debug.Print "Properties of new TableDef object " & _ 
         "after appending to collection:" 
 
      ' Enumerate Properties collection of new TableDef  
      ' object. 
      For Each prpLoop In .Properties 
         On Error Resume Next 
         If prpLoop <> "" Then Debug.Print "  " & _ 
           prpLoop.Name & " = " & prpLoop 
         On Error GoTo 0 
      Next prpLoop 
 
   End With 
 
   ' Delete new TableDef object since this is a  
   ' demonstration. 
   dbsNorthwind.TableDefs.Delete "Contacts" 
 
   dbsNorthwind.Close 
```

<br/>

<span data-ttu-id="b8b6d-139">下面的示例演示如何创建计算的字段。</span><span class="sxs-lookup"><span data-stu-id="b8b6d-139">The following example shows how to create a calculated field.</span></span> <span data-ttu-id="b8b6d-140">CreateField 方法创建一个名为**FullName**字段。</span><span class="sxs-lookup"><span data-stu-id="b8b6d-140">The CreateField method creates a field named **FullName**.</span></span> <span data-ttu-id="b8b6d-141">然后表达式属性设置为计算字段的值的表达式。</span><span class="sxs-lookup"><span data-stu-id="b8b6d-141">The Expression property is then set to the expression that calculates the value of the field.</span></span>

<span data-ttu-id="b8b6d-142">**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="b8b6d-142">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

```vb
    Sub CreateCalculatedField()
        Dim dbs As DAO.Database
        Dim tdf As DAO.TableDef
        Dim fld As DAO.Field2
        
        ' get the database
        Set dbs = CurrentDb()
        
        ' create the table
        Set tdf = dbs.CreateTableDef("tblContactsCalcField")
        
        ' create the fields: first name, last name
        tdf.Fields.Append tdf.CreateField("FirstName", dbText, 20)
        tdf.Fields.Append tdf.CreateField("LastName", dbText, 20)
        
        ' create the calculated field: full name
        Set fld = tdf.CreateField("FullName", dbText, 50)
        fld.Expression = "[FirstName] & "" "" & [LastName]"
        tdf.Fields.Append fld
        
        ' append the table and cleanup
        dbs.TableDefs.Append tdf
        
    Cleanup:
        Set fld = Nothing
        Set tdf = Nothing
        Set dbs = Nothing
    End Sub
```
