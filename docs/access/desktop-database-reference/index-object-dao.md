---
title: Index 对象-数据访问对象 (DAO)
TOCTitle: Index object
ms:assetid: 92c32cad-ec8a-1243-1d18-83f50b269ecb
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197655(v=office.15)
ms:contentKeyID: 48546380
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: ca0a975017b5c5396d23817716689b37433d8f97
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291766"
---
# <a name="index-object-dao"></a><span data-ttu-id="0710c-102">Index 对象 (DAO)</span><span class="sxs-lookup"><span data-stu-id="0710c-102">Index object (DAO)</span></span>

<span data-ttu-id="0710c-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="0710c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="0710c-p101">**Index** 对象指定从数据库表访问的记录的顺序，以及是否可接受重复的记录，以便提供高效的数据访问。对于外部数据库， **Index** 对象描述为外部表建立的索引（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="0710c-p101">**Index** objects specify the order of records accessed from database tables and whether or not duplicate records are accepted, providing efficient access to data. For external databases, **Index** objects describe the indexes established for external tables (Microsoft Access workspaces only).</span></span>

## <a name="remarks"></a><span data-ttu-id="0710c-106">注解</span><span class="sxs-lookup"><span data-stu-id="0710c-106">Remarks</span></span>

<span data-ttu-id="0710c-p102">Microsoft Access 数据库引擎在联接表和创建 **[Recordset](recordset-object-dao.md)** 对象时将会使用索引。索引确定表类型的 **Recordset** 对象返回记录时遵循的顺序，但是，索引不能确定 Microsoft Access 数据库引擎在基表中存储记录时遵循的顺序，也不能确定其他任何类型的 **Recordset** 对象返回记录时遵循的顺序。</span><span class="sxs-lookup"><span data-stu-id="0710c-p102">The Microsoft Access database engine uses indexes when it joins tables and creates **[Recordset](recordset-object-dao.md)** objects. Indexes determine the order in which table-type **Recordset** objects return records, but they don't determine the order in which the Microsoft Access database engine stores records in the base table or the order in which any other type of **Recordset** object returns records.</span></span>

<span data-ttu-id="0710c-109">使用 **Index** 对象，您可以进行下列操作：</span><span class="sxs-lookup"><span data-stu-id="0710c-109">With an **Index** object, you can:</span></span>

- <span data-ttu-id="0710c-110">使用 **Required** 属性确定索引中的 **[Field](field-object-dao.md)** 对象是否需要非 Null 值，然后使用 **IgnoreNulls** 属性确定空值是否具有索引项。</span><span class="sxs-lookup"><span data-stu-id="0710c-110">Use the **Required** property to determine whether the **[Field](field-object-dao.md)** objects in the index require values that are not Null, and then use the **IgnoreNulls** property to determine whether the null values have index entries.</span></span>

- <span data-ttu-id="0710c-111">使用 **Primary** 和 **Unique** 属性确定 **Index** 对象的排序和唯一性。</span><span class="sxs-lookup"><span data-stu-id="0710c-111">Use the **Primary** and **Unique** properties to determine the ordering and uniqueness of the **Index** object.</span></span>

<span data-ttu-id="0710c-p103">Microsoft Access 数据库引擎可自动维护所有的基表索引。只要在基表中添加、更改或删除了记录，它就会更新索引。创建数据库后，请定期使用 **[CompactDatabase](dbengine-compactdatabase-method-dao.md)** 方法将索引统计保持为最新状态。</span><span class="sxs-lookup"><span data-stu-id="0710c-p103">The Microsoft Access database engine maintains all base table indexes automatically. It updates indexes whenever you add, change, or delete records from the base table. Once you create the database, use the **[CompactDatabase](dbengine-compactdatabase-method-dao.md)** method periodically to bring index statistics up-to-date.</span></span>

<span data-ttu-id="0710c-115">在访问表类型 **Recordset** 对象时，可以使用该对象的 **Index** 属性指定记录的顺序。</span><span class="sxs-lookup"><span data-stu-id="0710c-115">When accessing a table-type **Recordset** object, you specify the order of records using the object's **Index** property.</span></span> <span data-ttu-id="0710c-116">将该属性设置为 **Indexes** 集合中的现有 **Index** 对象的 **Name** 属性设置。</span><span class="sxs-lookup"><span data-stu-id="0710c-116">Set this property to the **Name** property setting of an existing **Index** object in the **Indexes** collection.</span></span> <span data-ttu-id="0710c-117">此集合包含在要填充的**Recordset**对象的基础上的**[TableDef](tabledef-object-dao.md)** 对象中。</span><span class="sxs-lookup"><span data-stu-id="0710c-117">This collection is contained by the **[TableDef](tabledef-object-dao.md)** object underlying the **Recordset** object that you're populating.</span></span>

> [!NOTE]
> <span data-ttu-id="0710c-p105">[!注释] 不一定非要为表创建索引，但是对于大型的未创建索引的表，访问特定的记录或处理联接可能需要花费较长的时间。反过来，具有太多的索引也会减慢更新数据库的速度，原因是需要修正每个表索引。</span><span class="sxs-lookup"><span data-stu-id="0710c-p105">You don't have to create indexes for a table, but for large, unindexed tables, accessing a specific record or processing joins can take a long time. Conversely, having too many indexes can slow down updates to the database as each of the table indexes is amended.</span></span>

<span data-ttu-id="0710c-120">索引中每个**Field**对象的**[Attributes](field-attributes-property-dao.md)** 属性决定了返回的记录的顺序, 因此决定了对该索引使用哪些访问技术。</span><span class="sxs-lookup"><span data-stu-id="0710c-120">The **[Attributes](field-attributes-property-dao.md)** property of each **Field** object in the index determines the order of records returned and consequently determines which access techniques to use for that index.</span></span>

<span data-ttu-id="0710c-p106">**Index** 对象的 **Fields** 集合中的每个 **Field** 对象都是索引的组成部分。要定义一个新的 **Index** 对象，请先设置其属性，然后再将其追加到集合中，使该 **Index** 对象可用于后续应用。</span><span class="sxs-lookup"><span data-stu-id="0710c-p106">Each **Field** object in the **Fields** collection of an **Index** object is a component of the index. To define a new **Index** object, set its properties before you append it to a collection, making the **Index** object available for subsequent use.</span></span>

> [!NOTE]
> <span data-ttu-id="0710c-123">[!注释] 仅当现有 **Index** 对象所在的 **TableDef** 对象的 **[Updatable](connection-updatable-property-dao.md)** 属性为 **True** 时，才可以修改该对象的 **Name** 属性设置。</span><span class="sxs-lookup"><span data-stu-id="0710c-123">You can modify the **Name** property setting of an existing **Index** object only if the **[Updatable](connection-updatable-property-dao.md)** property setting of the containing **TableDef** object is **True**.</span></span>

<span data-ttu-id="0710c-p107">在设置表的主键时，Microsoft Access 数据库引擎会自动将它定义为主索引。主索引包括一个或多个字段，这些字段可以按预定义的顺序唯一地标识表中的所有记录。由于主索引字段必须是唯一的，因此 Microsoft Access 数据库引擎会将主 **Index** 对象的 **Unique** 属性自动设置为 **True**。如果主索引包括多个字段，则每个字段可以包含重复值，但是所有索引字段中的值组合必须是唯一的。主索引包括表的键，并且始终由作为主键的相同字段组成。</span><span class="sxs-lookup"><span data-stu-id="0710c-p107">When you set a primary key for a table, the Microsoft Access database engine automatically defines it as the primary index. A primary index consists of one or more fields that uniquely identify all records in a table in a predefined order. Because the primary index field must be unique, the Microsoft Access database engine automatically sets the **Unique** property of the primary **Index** object to **True**. If the primary index consists of more than one field, each field can contain duplicate values, but the combination of values from all the indexed fields must be unique. A primary index consists of a key for the table and is always made up of the same fields as the primary key.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0710c-p108">[!重要信息] 确保数据符合新索引的属性。如果索引需要唯一值，请确保现有数据记录中没有重复值。如果存在重复值，Microsoft Access 数据库引擎将无法创建索引；当您尝试对新索引使用 Append 方法时，会生成可捕获的错误。</span><span class="sxs-lookup"><span data-stu-id="0710c-p108">Make sure your data complies with the attributes of your new index. If your index requires unique values, make sure that there are no duplicates in existing data records. If duplicates exist, the Microsoft Access database engine can't create the index; a trappable error results when you attempt to use the Append method on the new index.</span></span>

<span data-ttu-id="0710c-p109">在创建实施参照完整性的关系时，Microsoft Access 数据库引擎将使用 **Foreign** 属性自动创建一个索引，该索引在引用表中设置为外键。建立了表关系后，Microsoft Access 数据库引擎将防止对数据库执行会违背该关系的添加或更改操作。如果将 [**Relation**](relation-object-dao.md) 对象的 **Attributes** 属性设置为允许级联更新和级联删除，Microsoft Access 数据库引擎将自动更新或删除相关表中的记录。</span><span class="sxs-lookup"><span data-stu-id="0710c-p109">When you create a relationship that enforces referential integrity, the Microsoft Access database engine automatically creates an index with the **Foreign** property, set as the foreign key in the referencing table. After you've established a table relationship, the Microsoft Access database engine prevents additions or changes to the database that violate that relationship. If you set the **Attributes** property of the **[Relation](relation-object-dao.md)** object to allow cascading updates and cascading deletes, the Microsoft Access database engine updates or deletes records in related tables automatically.</span></span>

1.  <span data-ttu-id="0710c-135">对 **TableDef** 对象使用 **CreateIndex** 方法。</span><span class="sxs-lookup"><span data-stu-id="0710c-135">Use the **CreateIndex** method on a **TableDef** object.</span></span>

2.  <span data-ttu-id="0710c-136">对 **Index** 对象使用 **CreateField** 方法，为要包含在 **Index** 对象中的每个字段（列）创建 **Field** 对象。</span><span class="sxs-lookup"><span data-stu-id="0710c-136">Use the **CreateField** method on the **Index** object to create a **Field** object for each field (column) to be included in the **Index** object.</span></span>

3.  <span data-ttu-id="0710c-137">根据需要设置 **Index** 属性。</span><span class="sxs-lookup"><span data-stu-id="0710c-137">Set **Index** properties as needed.</span></span>

4.  <span data-ttu-id="0710c-138">将 **Field** 对象追加到 **Fields** 集合。</span><span class="sxs-lookup"><span data-stu-id="0710c-138">Append the **Field** object to the **Fields** collection.</span></span>

5.  <span data-ttu-id="0710c-139">将 **Index** 对象追加到 **Indexes** 集合。</span><span class="sxs-lookup"><span data-stu-id="0710c-139">Append the **Index** object to the **Indexes** collection.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0710c-140">[!注释] 对于使用 Microsoft Access 数据库引擎（不支持聚簇索引）的数据库，将忽略 **Clustered** 属性。</span><span class="sxs-lookup"><span data-stu-id="0710c-140">The **Clustered** property is ignored for databases that use the Microsoft Access database engine, which doesn't support clustered indexes.</span></span>

## <a name="example"></a><span data-ttu-id="0710c-141">示例</span><span class="sxs-lookup"><span data-stu-id="0710c-141">Example</span></span>

<span data-ttu-id="0710c-p110">以下示例创建一个新的 **Index** 对象，并将该对象追加到 Employees **TableDef** 的 **Indexes** 集合，然后枚举 **TableDef** 的 **Indexes** 集合。最后，该示例枚举 **Recordset**，方法是首先使用主 **Index**，然后使用新的 **Index**。若要使该过程正常运行，需要使用 IndexOutput 过程。</span><span class="sxs-lookup"><span data-stu-id="0710c-p110">This example creates a new **Index** object, appends it to the **Indexes** collection of the Employees **TableDef**, and then enumerates the **Indexes** collection of the **TableDef**. Finally, it enumerates a **Recordset**, first using the primary **Index**, and then using the new **Index**. The IndexOutput procedure is required for this procedure to run.</span></span>

```vb
    Sub IndexObjectX() 
     
     Dim dbsNorthwind As Database 
     Dim tdfEmployees As TableDef 
     Dim idxNew As Index 
     Dim idxLoop As Index 
     Dim rstEmployees As Recordset 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set tdfEmployees = dbsNorthwind!Employees 
     
     With tdfEmployees 
     ' Create new index, create and append Field 
     ' objects to its Fields collection. 
     Set idxNew = .CreateIndex("NewIndex") 
     
     With idxNew 
     .Fields.Append .CreateField("Country") 
     .Fields.Append .CreateField("LastName") 
     .Fields.Append .CreateField("FirstName") 
     End With 
     
     ' Add new Index object to the Indexes collection 
     ' of the Employees table collection. 
     .Indexes.Append idxNew 
     .Indexes.Refresh 
     
     Debug.Print .Indexes.Count & " Indexes in " & _ 
     .Name & " TableDef" 
     
     ' Enumerate Indexes collection of Employees 
     ' table. 
     For Each idxLoop In .Indexes 
     Debug.Print " " & idxLoop.Name 
     Next idxLoop 
     
     Set rstEmployees = _ 
     dbsNorthwind.OpenRecordset("Employees") 
     
     ' Print report using old and new indexes. 
     IndexOutput rstEmployees, "PrimaryKey" 
     IndexOutput rstEmployees, idxNew.Name 
     rstEmployees.Close 
     
     ' Delete new Index because this is a 
     ' demonstration. 
     .Indexes.Delete idxNew.Name 
     End With 
     
     dbsNorthwind.Close 
     
    End Sub 
     
    Sub IndexOutput(rstTemp As Recordset, _ 
     strIndex As String) 
     ' Report function for FieldX. 
     
     With rstTemp 
     ' Set the index. 
     .Index = strIndex 
     .MoveFirst 
     Debug.Print "Recordset = " & .Name & _ 
     ", Index = " & .Index 
     Debug.Print " EmployeeID - Country - Name" 
     
     ' Enumerate the recordset using the specified 
     ' index. 
     Do While Not .EOF 
     Debug.Print " " & !EmployeeID & " - " & _ 
     !Country & " - " & !LastName & ", " & !FirstName 
     .MoveNext 
     Loop 
     
     End With 
     
    End Sub 
```

<br/>

<span data-ttu-id="0710c-p111">以下示例使用 **CreateIndex** 方法创建两个新的 **Index** 对象，然后将它们追加到 Employees **TableDef** 对象的 **Indexes** 集合。然后，该示例枚举 **TableDef** 对象的 **Indexes** 集合、新 **Index** 对象的 **Fields** 集合，以及新 **Index** 对象的 Properties 集合。若要使该过程正常运行，需要使用 CreateIndexOutput 函数。</span><span class="sxs-lookup"><span data-stu-id="0710c-p111">This example uses the **CreateIndex** method to create two new **Index** objects and then appends them to the **Indexes** collection of the Employees **TableDef** object. It then enumerates the **Indexes** collection of the **TableDef** object, the **Fields** collection of the new **Index** objects, and the Properties collection of the new **Index** objects. The CreateIndexOutput function is required for this procedure to run.</span></span>

```vb
    Sub CreateIndexX() 
     
     Dim dbsNorthwind As Database 
     Dim tdfEmployees As TableDef 
     Dim idxCountry As Index 
     Dim idxFirstName As Index 
     Dim idxLoop As Index 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set tdfEmployees = dbsNorthwind!Employees 
     
     With tdfEmployees 
     ' Create first Index object, create and append Field 
     ' objects to the Index object, and then append the 
     ' Index object to the Indexes collection of the 
     ' TableDef. 
     Set idxCountry = .CreateIndex("CountryIndex") 
     With idxCountry 
     .Fields.Append .CreateField("Country") 
     .Fields.Append .CreateField("LastName") 
     .Fields.Append .CreateField("FirstName") 
     End With 
     .Indexes.Append idxCountry 
     
     ' Create second Index object, create and append Field 
     ' objects to the Index object, and then append the 
     ' Index object to the Indexes collection of the 
     ' TableDef. 
     Set idxFirstName = .CreateIndex 
     With idxFirstName 
     .Name = "FirstNameIndex" 
     .Fields.Append .CreateField("FirstName") 
     .Fields.Append .CreateField("LastName") 
     End With 
     .Indexes.Append idxFirstName 
     
     ' Refresh collection so that you can access new Index 
     ' objects. 
     .Indexes.Refresh 
     
     Debug.Print .Indexes.Count & " Indexes in " & _ 
     .Name & " TableDef" 
     
     ' Enumerate Indexes collection. 
     For Each idxLoop In .Indexes 
     Debug.Print " " & idxLoop.Name 
     Next idxLoop 
     
     ' Print report. 
     CreateIndexOutput idxCountry 
     CreateIndexOutput idxFirstName 
     
     ' Delete new Index objects because this is a 
     ' demonstration. 
     .Indexes.Delete idxCountry.Name 
     .Indexes.Delete idxFirstName.Name 
     End With 
     
     dbsNorthwind.Close 
     
    End Sub 
     
    Function CreateIndexOutput(idxTemp As Index) 
     
     Dim fldLoop As Field 
     Dim prpLoop As Property 
     
     With idxTemp 
     ' Enumerate Fields collection of Index object. 
     Debug.Print "Fields in " & .Name 
     For Each fldLoop In .Fields 
     Debug.Print " " & fldLoop.Name 
     Next fldLoop 
     
     ' Enumerate Properties collection of Index object. 
     Debug.Print "Properties of " & .Name 
     For Each prpLoop In .Properties 
     Debug.Print " " & prpLoop.Name & " - " & _ 
     IIf(prpLoop = "", "[empty]", prpLoop) 
     Next prpLoop 
     End With 
     
    End Function
```
