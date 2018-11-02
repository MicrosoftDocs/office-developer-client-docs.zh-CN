---
title: Relation 对象 (DAO)
TOCTitle: Relation Object
ms:assetid: 46d6dfaf-a97d-3abd-0b4b-396a41eb3be7
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193195(v=office.15)
ms:contentKeyID: 48544578
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: cfabb36e539aaff1f6e12d431d2cfcfe79ff5d04
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25928085"
---
# <a name="relation-object-dao"></a><span data-ttu-id="f0371-102">Relation 对象 (DAO)</span><span class="sxs-lookup"><span data-stu-id="f0371-102">Relation object (DAO)</span></span>


<span data-ttu-id="f0371-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="f0371-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="f0371-104">**Relation** 对象表示表或查询中的字段之间的关系（仅适用于 Microsoft Access 数据库引擎数据库）。</span><span class="sxs-lookup"><span data-stu-id="f0371-104">A **Relation** object represents a relationship between fields in tables or queries (Microsoft Access database engine databases only).</span></span>

## <a name="remarks"></a><span data-ttu-id="f0371-105">注解</span><span class="sxs-lookup"><span data-stu-id="f0371-105">Remarks</span></span>

<span data-ttu-id="f0371-106">可以使用 **Relation** 对象创建新关系并检查数据库中的现有关系。</span><span class="sxs-lookup"><span data-stu-id="f0371-106">You can use the **Relation** object to create new relationships and examine existing relationships in your database.</span></span>

<span data-ttu-id="f0371-107">使用 **Relation** 对象及其属性，您可以进行下列操作：</span><span class="sxs-lookup"><span data-stu-id="f0371-107">Using a **Relation** object and its properties, you can:</span></span>

  - <span data-ttu-id="f0371-108">指定基表中的字段之间的实施关系（但不是与查询或链接表有关的关系）。</span><span class="sxs-lookup"><span data-stu-id="f0371-108">Specify an enforced relationship between fields in base tables (but not a relationship that involves a query or a linked table).</span></span>

  - <span data-ttu-id="f0371-109">在任何类型的表或查询（本地或链接）之间建立未实施的关系。</span><span class="sxs-lookup"><span data-stu-id="f0371-109">Establish unenforced relationships between any type of table or query— native or linked.</span></span>

  - <span data-ttu-id="f0371-110">使用 **Name** 属性引用被引用的主表和引用的外表中的字段之间的关系。</span><span class="sxs-lookup"><span data-stu-id="f0371-110">Use the **Name** property to refer to the relationship between the fields in the referenced primary table and the referencing foreign table.</span></span>

  - <span data-ttu-id="f0371-111">使用 **Attributes** 属性确定表中字段之间的关系是一对一还是一对多，以及如何实施参照完整性。</span><span class="sxs-lookup"><span data-stu-id="f0371-111">Use the **Attributes** property to determine whether the relationship between fields in the table is one-to-one or one-to-many and how to enforce referential integrity.</span></span>

  - <span data-ttu-id="f0371-112">使用 **Attributes** 属性确定 Microsoft Access 数据库引擎是否可以对主表和外表执行级联更新和级联删除操作。</span><span class="sxs-lookup"><span data-stu-id="f0371-112">Use the **Attributes** property to determine whether the Microsoft Access database engine can perform cascading update and cascading delete operations on primary and foreign tables.</span></span>

  - <span data-ttu-id="f0371-113">使用 **Attributes** 属性确定表中字段之间的关系是左联接还是右联接。</span><span class="sxs-lookup"><span data-stu-id="f0371-113">Use the **Attributes** property to determine whether the relationship between fields in the table is left join or right join.</span></span>

  - <span data-ttu-id="f0371-114">使用 **Relation** 对象的 **Fields** 集合中所有 **Field** 对象的 **Name** 属性设置或返回被引用表主键中的字段的名称，或者使用 **Field** 对象的 **ForeignName** 属性设置或返回引用表外键中的字段的名称。</span><span class="sxs-lookup"><span data-stu-id="f0371-114">Use the **Name** property of all **Field** objects in the **Fields** collection of a **Relation** object to set or return the names of the fields in the primary key of the referenced table, or the **ForeignName** property settings of the **Field** objects to set or return the names of the fields in the foreign key of the referencing table.</span></span>

<span data-ttu-id="f0371-p101">如果所做的更改违背了为数据库建立的关系，将发生可捕获的错误。如果请求级联更新或级联删除操作，Microsoft Access 数据库引擎还将修改主键 或外键表，以实施建立的关系。</span><span class="sxs-lookup"><span data-stu-id="f0371-p101">If you make changes that violate the relationships established for the database, a trappable error occurs. If you request cascading update or cascading delete operations, the Microsoft Access database engine also modifies the primary key or foreign key tables to enforce the relationships you establish.</span></span>

<span data-ttu-id="f0371-p102">例如，Northwind 数据库包含 Orders 表和 Customers 表之间的关系。Customers 表的 CustomerID 字段为主键，Orders 表的 CustomerID 字段为外键。Microsoft Access 数据库引擎为了接受 Orders 表中的新记录，将搜索 Customers 表，以获取 Orders 表 CustomerID 字段的匹配项。如果 Microsoft Access 数据库引擎未找到匹配项，则不会接受新记录，同时将发生可捕获的错误。</span><span class="sxs-lookup"><span data-stu-id="f0371-p102">For example, the Northwind database contains a relationship between an Orders table and a Customers table. The CustomerID field of the Customers table is the primary key, and the CustomerID field of the Orders table is the foreign key. For the Microsoft Access database engine to accept a new record in the Orders table, it searches the Customers table for a match on the CustomerID field of the Orders table. If the Microsoft Access database engine doesn't find a match, it doesn't accept the new record, and a trappable error occurs.</span></span>

<span data-ttu-id="f0371-p103">在实施参照完整性时，被引用表的键字段必须已经存在唯一的索引。Microsoft Access 数据库引擎将使用 **Foreign** 属性自动创建一个索引，经设置的索引在引用表中充当外键。</span><span class="sxs-lookup"><span data-stu-id="f0371-p103">When you enforce referential integrity, a unique index must already exist for the key field of the referenced table. The Microsoft Access database engine automatically creates an index with the **Foreign** property set to act as the foreign key in the referencing table.</span></span>

<span data-ttu-id="f0371-p104">若要创建新的 **Relation** 对象，请使用 **CreateRelation** 方法。若要按照序号或 **Name** 属性设置来引用集合中的 **Relation** 对象，可以使用下列任何一种语法形式：</span><span class="sxs-lookup"><span data-stu-id="f0371-p104">To create a new **Relation** object, use the **CreateRelation** method. To refer to a **Relation** object in a collection by its ordinal number or by its **Name** property setting, use any of the following syntax forms:</span></span>

<span data-ttu-id="f0371-125">**Relations**(0)</span><span class="sxs-lookup"><span data-stu-id="f0371-125">**Relations**(0)</span></span>

<span data-ttu-id="f0371-126">**关系**("name")</span><span class="sxs-lookup"><span data-stu-id="f0371-126">**Relations**("name")</span></span>

<span data-ttu-id="f0371-127">**关系**\!\[名称\]</span><span class="sxs-lookup"><span data-stu-id="f0371-127">**Relations**\!\[name\]</span></span>

## <a name="example"></a><span data-ttu-id="f0371-128">示例</span><span class="sxs-lookup"><span data-stu-id="f0371-128">Example</span></span>

<span data-ttu-id="f0371-p105">以下示例演示现有的 **Relation** 对象如何控制数据输入。此过程尝试添加一个具有有意弄错的 CategoryID 的记录，从而触发错误处理例程。</span><span class="sxs-lookup"><span data-stu-id="f0371-p105">This example shows how an existing **Relation** object can control data entry. The procedure attempts to add a record with a deliberately incorrect CategoryID; this triggers the error-handling routine.</span></span>

```vb 
    Sub RelationX() 
     
     Dim dbsNorthwind As Database 
     Dim rstProducts As Recordset 
     Dim prpLoop As Property 
     Dim fldLoop As Field 
     Dim errLoop As Error 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set rstProducts = dbsNorthwind.OpenRecordset("Products") 
     
     ' Print a report showing all the different parts of 
     ' the relation and where each part is stored. 
     With dbsNorthwind.Relations!CategoriesProducts 
     Debug.Print "Properties of " & .Name & " Relation" 
     Debug.Print " Table = " & .Table 
     Debug.Print " ForeignTable = " & .ForeignTable 
     Debug.Print "Fields of " & .Name & " Relation" 
     With .Fields!CategoryID 
     Debug.Print " " & .Name 
     Debug.Print " Name = " & .Name 
     Debug.Print " ForeignName = " & .ForeignName 
     End With 
     End With 
     
     ' Attempt to add a record that violates the relation. 
     With rstProducts 
     .AddNew 
     !ProductName = "Trygve's Lutefisk" 
     !CategoryID = 10 
     On Error GoTo Err_Relation 
     .Update 
     On Error GoTo 0 
     .Close 
     End With 
     
     dbsNorthwind.Close 
     
     Exit Sub 
     
    Err_Relation: 
     
     ' Notify user of any errors that result from 
     ' the invalid data. 
     If DBEngine.Errors.Count > 0 Then 
     For Each errLoop In DBEngine.Errors 
     MsgBox "Error number: " & errLoop.Number & _ 
     vbCr & errLoop.Description 
     Next errLoop 
     End If 
     
     Resume Next 
     
    End Sub 
```

<br/>

<span data-ttu-id="f0371-p106">以下示例使用 **CreateRelation** 方法在 Employees **TableDef** 和名为 Departments 的新的 **TableDef** 之间创建一个 **Relation**。该示例还演示创建新的 **Relation** 将如何同时在外部表中创建任何需要的 **Indexes**（Employees 表中的 DepartmentsEmployees 索引）。</span><span class="sxs-lookup"><span data-stu-id="f0371-p106">This example uses the **CreateRelation** method to create a **Relation** between the Employees **TableDef** and a new **TableDef** called Departments. This example also demonstrates how creating a new **Relation** will also create any necessary **Indexes** in the foreign table (the DepartmentsEmployees Index in the Employees table).</span></span>

```vb
    Sub CreateRelationX() 
     
     Dim dbsNorthwind As Database 
     Dim tdfEmployees As TableDef 
     Dim tdfNew As TableDef 
     Dim idxNew As Index 
     Dim relNew As Relation 
     Dim idxLoop As Index 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
     With dbsNorthwind 
     ' Add new field to Employees table. 
     Set tdfEmployees = .TableDefs!Employees 
     tdfEmployees.Fields.Append _ 
     tdfEmployees.CreateField("DeptID", dbInteger, 2) 
     
     ' Create new Departments table. 
     Set tdfNew = .CreateTableDef("Departments") 
     
     With tdfNew 
     ' Create and append Field objects to Fields 
     ' collection of the new TableDef object. 
     .Fields.Append .CreateField("DeptID", dbInteger, 2) 
     .Fields.Append .CreateField("DeptName", dbText, 20) 
     
     ' Create Index object for Departments table. 
     Set idxNew = .CreateIndex("DeptIDIndex") 
     ' Create and append Field object to Fields 
     ' collection of the new Index object. 
     idxNew.Fields.Append idxNew.CreateField("DeptID") 
     ' The index in the primary table must be Unique in 
     ' order to be part of a Relation. 
     idxNew.Unique = True 
     .Indexes.Append idxNew 
     End With 
     
     .TableDefs.Append tdfNew 
     
     ' Create EmployeesDepartments Relation object, using 
     ' the names of the two tables in the relation. 
     Set relNew = .CreateRelation("EmployeesDepartments", _ 
     tdfNew.Name, tdfEmployees.Name, _ 
     dbRelationUpdateCascade) 
     
     ' Create Field object for the Fields collection of the 
     ' new Relation object. Set the Name and ForeignName 
     ' properties based on the fields to be used for the 
     ' relation. 
     relNew.Fields.Append relNew.CreateField("DeptID") 
     relNew.Fields!DeptID.ForeignName = "DeptID" 
     .Relations.Append relNew 
     
     ' Print report. 
     Debug.Print "Properties of " & relNew.Name & _ 
     " Relation" 
     Debug.Print " Table = " & relNew.Table 
     Debug.Print " ForeignTable = " & _ 
     relNew.ForeignTable 
     Debug.Print "Fields of " & relNew.Name & " Relation" 
     
     With relNew.Fields!DeptID 
     Debug.Print " " & .Name 
     Debug.Print " Name = " & .Name 
     Debug.Print " ForeignName = " & .ForeignName 
     End With 
     
     Debug.Print "Indexes in " & tdfEmployees.Name & _ 
     " TableDef" 
     For Each idxLoop In tdfEmployees.Indexes 
     Debug.Print " " & idxLoop.Name & _ 
     ", Foreign = " & idxLoop.Foreign 
     Next idxLoop 
     
     ' Delete new objects because this is a demonstration. 
     .Relations.Delete relNew.Name 
     .TableDefs.Delete tdfNew.Name 
     tdfEmployees.Fields.Delete "DeptID" 
     .Close 
     End With 
     
    End Sub
```
