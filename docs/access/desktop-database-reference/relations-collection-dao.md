---
title: Relations 集合 (DAO)
TOCTitle: Relations Collection
ms:assetid: 8929b5cc-cf52-03f2-8cf5-7f45276d258e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197067(v=office.15)
ms:contentKeyID: 48546153
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: fc8fa9bb24035e344ddb8e15179d4edd128abf7d
ms.sourcegitcommit: 38d0db57580cc5f4a0231c27b1643f8db5431ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25936845"
---
# <a name="relations-collection-dao"></a><span data-ttu-id="2712b-102">Relations 集合 (DAO)</span><span class="sxs-lookup"><span data-stu-id="2712b-102">Relations collection (DAO)</span></span>


<span data-ttu-id="2712b-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="2712b-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="2712b-104">**Relations** 集合包含 **Database** 对象的存储的 **Relation** 对象（仅适用于 Microsoft Access 数据库引擎数据库）。</span><span class="sxs-lookup"><span data-stu-id="2712b-104">A **Relations** collection contains stored **Relation** objects of a **Database** object (Microsoft Access database engine databases only).</span></span>

## <a name="remarks"></a><span data-ttu-id="2712b-105">注解</span><span class="sxs-lookup"><span data-stu-id="2712b-105">Remarks</span></span>

<span data-ttu-id="2712b-p101">可以使用 **Relation** 对象创建新关系并检查数据库中的现有关系。若要向 **Relations** 集合添加 **Relation** 对象，请首先使用 **CreateRelation** 方法创建该对象，然后使用 **Append** 方法将其追加到 **Relations** 集合中。此操作会导致在您关闭 **Database** 对象时保存 **Relation** 对象。若要从集合中删除 **Relation** 对象，请使用 **Delete** 方法。</span><span class="sxs-lookup"><span data-stu-id="2712b-p101">You can use the **Relation** object to create new relationships and examine existing relationships in your database. To add a **Relation** object to the **Relations** collection, first create it with the **CreateRelation** method, and then append it to the **Relations** collection with the **Append** method. This will save the **Relation** object when you close the **Database** object. To remove a **Relation** object from the collection, use the **Delete** method.</span></span>

<span data-ttu-id="2712b-110">若要按照序号或 **Name** 属性设置来引用集合中的 **Relation** 对象，可以使用下列任何一种语法形式：</span><span class="sxs-lookup"><span data-stu-id="2712b-110">To refer to a **Relation** object in a collection by its ordinal number or by its **Name** property setting, use any of the following syntax forms:</span></span>

<span data-ttu-id="2712b-111">**Relations**(0)</span><span class="sxs-lookup"><span data-stu-id="2712b-111">**Relations**(0)</span></span>

<span data-ttu-id="2712b-112">**关系**("name")</span><span class="sxs-lookup"><span data-stu-id="2712b-112">**Relations**("name")</span></span>

<span data-ttu-id="2712b-113">**关系**\!\[名称\]</span><span class="sxs-lookup"><span data-stu-id="2712b-113">**Relations**\!\[name\]</span></span>

## <a name="example"></a><span data-ttu-id="2712b-114">示例</span><span class="sxs-lookup"><span data-stu-id="2712b-114">Example</span></span>

<span data-ttu-id="2712b-p102">以下示例演示现有的 **Relation** 对象如何控制数据输入。此过程尝试添加一个具有有意弄错的 CategoryID 的记录，从而触发错误处理例程。</span><span class="sxs-lookup"><span data-stu-id="2712b-p102">This example shows how an existing **Relation** object can control data entry. The procedure attempts to add a record with a deliberately incorrect CategoryID; this triggers the error-handling routine.</span></span>

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

<span data-ttu-id="2712b-117">以下示例使用 **CreateRelation** 方法在 Employees **TableDef** 和名为 Departments 的新的 **TableDef** 之间创建一个 **Relation**。</span><span class="sxs-lookup"><span data-stu-id="2712b-117">This example uses the **CreateRelation** method to create a **Relation** between the Employees **TableDef** and a new **TableDef** called Departments.</span></span> <span data-ttu-id="2712b-118">它还演示了如何创建新的**Relation**还将创建任何必要的**索引**中的外表 （DepartmentsEmployees Employees 表中的索引）。</span><span class="sxs-lookup"><span data-stu-id="2712b-118">It also demonstrates how creating a new **Relation** will also create any necessary **Indexes** in the foreign table (the DepartmentsEmployees Index in the Employees table).</span></span>

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
