---
title: Indexes 集合 (DAO)
TOCTitle: Indexes Collection
ms:assetid: 26450e85-c79d-b12a-d760-dfc89c37f36c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff191889(v=office.15)
ms:contentKeyID: 48543802
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3e38df07831e21a92afdf8106b6d8eb3844396cc
ms.sourcegitcommit: 38d0db57580cc5f4a0231c27b1643f8db5431ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25936754"
---
# <a name="indexes-collection-dao"></a><span data-ttu-id="ccb65-102">Indexes 集合 (DAO)</span><span class="sxs-lookup"><span data-stu-id="ccb65-102">Indexes collection (DAO)</span></span>


<span data-ttu-id="ccb65-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="ccb65-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="ccb65-104">**Indexes** 对象包含 **TableDef** 对象的所有存储的 **Index** 对象（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="ccb65-104">An **Indexes** collection contains all the stored **Index** objects of a **TableDef** object (Microsoft Access workspaces only).</span></span>

## <a name="remarks"></a><span data-ttu-id="ccb65-105">注解</span><span class="sxs-lookup"><span data-stu-id="ccb65-105">Remarks</span></span>

<span data-ttu-id="ccb65-p101">访问表类型的 Recordset 对象时，使用对象的 **Index** 属性来指定记录的顺序。将该属性设置为 \*\*\*\*Recordset\*\*\*\* 对象的基础 [**TableDef**](tabledef-object-dao.md) 对象的 **Indexes** 集合中现有 [Index](recordset-object-dao.md) 对象的 **Name** 属性设置。</span><span class="sxs-lookup"><span data-stu-id="ccb65-p101">When you access a table-type Recordset object, use the object's **Index** property to specify the order of records. Set this property to the **Name** property setting of an existing **Index** object in the **Indexes** collection of the **[TableDef](tabledef-object-dao.md)** object underlying the **[Recordset](recordset-object-dao.md)** object.</span></span>


> [!NOTE]
> <P><span data-ttu-id="ccb65-108">[!注释] 仅当包含 <STRONG>Indexes</STRONG> 集合的 <STRONG>TableDef</STRONG> 对象的 <A href="connection-updatable-property-dao.md"><STRONG>Updatable</STRONG></A> 属性设置为 <STRONG>True</STRONG> 时，才能对该集合使用 <STRONG>Append</STRONG> 或 <STRONG>Delete</STRONG> 方法。</span><span class="sxs-lookup"><span data-stu-id="ccb65-108">You can use the <STRONG>Append</STRONG> or <STRONG>Delete</STRONG> method on an <STRONG>Indexes</STRONG> collection only if the <STRONG><A href="connection-updatable-property-dao.md">Updatable</A></STRONG> property setting of the containing <STRONG>TableDef</STRONG> object is <STRONG>True</STRONG>.</span></span></P>



<span data-ttu-id="ccb65-109">创建新的 **Index** 对象之后，应使用 **Append** 方法将该对象添加到 **TableDef** 对象的 **Indexes** 集合中。</span><span class="sxs-lookup"><span data-stu-id="ccb65-109">After you create a new **Index** object, you should use the **Append** method to add it to the **TableDef** object's **Indexes** collection.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="ccb65-p102">[!重要信息] 确保数据符合新索引的属性。如果索引需要唯一值，请确保现有数据记录中没有重复值。如果存在重复值，Microsoft Access 数据库引擎将无法创建索引；当您尝试对新索引使用 Append 方法时，会生成可捕获的错误。</span><span class="sxs-lookup"><span data-stu-id="ccb65-p102">Make sure your data complies with the attributes of your new index. If your index requires unique values, make sure that there are no duplicates in existing data records. If duplicates exist, the Microsoft Access database engine can't create the index; a trappable error results when you attempt to use the Append method on the new index.</span></span>



## <a name="example"></a><span data-ttu-id="ccb65-113">示例</span><span class="sxs-lookup"><span data-stu-id="ccb65-113">Example</span></span>

<span data-ttu-id="ccb65-p103">以下示例创建一个新的 **Index** 对象，并将该对象追加到 Employees **TableDef** 的 **Indexes** 集合，然后枚举 **TableDef** 的 **Indexes** 集合。最后，该示例枚举 **Recordset**，方法是首先使用主 **Index**，然后使用新的 **Index**。若要使该过程正常运行，需要使用 IndexOutput 过程。</span><span class="sxs-lookup"><span data-stu-id="ccb65-p103">This example creates a new **Index** object, appends it to the **Indexes** collection of the Employees **TableDef**, and then enumerates the **Indexes** collection of the **TableDef**. Finally, it enumerates a **Recordset**, first using the primary **Index**, and then using the new **Index**. The IndexOutput procedure is required for this procedure to run.</span></span>

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

<span data-ttu-id="ccb65-p104">以下示例使用 **CreateIndex** 方法创建两个新的 **Index** 对象，然后将它们追加到 Employees **TableDef** 对象的 **Indexes** 集合。然后，该示例枚举 **TableDef** 对象的 **Indexes** 集合、新 **Index** 对象的 **Fields** 集合，以及新 **Index** 对象的 Properties 集合。若要使该过程正常运行，需要使用 CreateIndexOutput 函数。</span><span class="sxs-lookup"><span data-stu-id="ccb65-p104">This example uses the **CreateIndex** method to create two new **Index** objects and then appends them to the **Indexes** collection of the Employees **TableDef** object. It then enumerates the **Indexes** collection of the **TableDef** object, the **Fields** collection of the new **Index** objects, and the Properties collection of the new **Index** objects. The CreateIndexOutput function is required for this procedure to run.</span></span>

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
