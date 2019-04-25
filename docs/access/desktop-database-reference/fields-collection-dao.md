---
title: Fields 集合 (DAO)
TOCTitle: Fields Collection
ms:assetid: 4be3ba07-20c1-d958-c1b8-7dd8b4731f60
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193530(v=office.15)
ms:contentKeyID: 48544702
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: d87d1535afeaf0740627a7af3852b1929a0e6d50
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292529"
---
# <a name="fields-collection-dao"></a><span data-ttu-id="1c4b4-102">Fields 集合 (DAO)</span><span class="sxs-lookup"><span data-stu-id="1c4b4-102">Fields collection (DAO)</span></span>


<span data-ttu-id="1c4b4-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="1c4b4-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="1c4b4-104">**Fields** 集合包含 **Index**、**QueryDef**、**Recordset**、**Relation** 或 **TableDef** 对象的所有存储 **Field** 对象。</span><span class="sxs-lookup"><span data-stu-id="1c4b4-104">A **Fields** collection contains all stored **Field** objects of an **Index**, **QueryDef**, **Recordset**, **Relation**, or **TableDef** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="1c4b4-105">说明</span><span class="sxs-lookup"><span data-stu-id="1c4b4-105">Remarks</span></span>

<span data-ttu-id="1c4b4-p101">**Index**、 **QueryDef**、 **Relation** 和 **TableDef** 对象的 **Fields** 集合包含这些对象代表的字段的规范。 **Recordset** 对象的 **Fields** 集合代表数据行中或记录中的 **Field** 对象。可使用 **Recordset** 对象中的 **Field** 对象读取和设置 **Recordset** 对象的当前记录中的字段的值。</span><span class="sxs-lookup"><span data-stu-id="1c4b4-p101">The **Fields** collections of the **Index**, **QueryDef**, **Relation**, and **TableDef** objects contain the specifications for the fields those objects represent. The **Fields** collection of a **Recordset** object represents the **Field** objects in a row of data, or in a record. You use the **Field** objects in a **Recordset** object to read and to set values for the fields in the current record of the **Recordset** object.</span></span>

<span data-ttu-id="1c4b4-109">若要按照序号或 **Name** 属性设置来引用集合中的 **Field** 对象，可以使用下列任何一种语法形式：</span><span class="sxs-lookup"><span data-stu-id="1c4b4-109">To refer to a **Field** object in a collection by its ordinal number or by its **Name** property setting, use any of the following syntax forms:</span></span>

<span data-ttu-id="1c4b4-110">**Fields**(0)</span><span class="sxs-lookup"><span data-stu-id="1c4b4-110">**Fields**(0)</span></span>

<span data-ttu-id="1c4b4-111">**Fields**("name")</span><span class="sxs-lookup"><span data-stu-id="1c4b4-111">**Fields**("name")</span></span>

<span data-ttu-id="1c4b4-112">**Fields**\!\[name\]</span><span class="sxs-lookup"><span data-stu-id="1c4b4-112">**Fields**\!\[name\]</span></span>

<span data-ttu-id="1c4b4-p102">还可以使用相同的语法形式，引用创建并追加到 **Fields** 集合中的 **Field** 对象的 **Value** 属性。字段引用的上下文将确定引用的是 **Field** 对象还是 **Field** 对象的 **Value** 属性。</span><span class="sxs-lookup"><span data-stu-id="1c4b4-p102">With the same syntax forms, you can also refer to the **Value** property of a **Field** object that you create and append to a **Fields** collection. The context of the field reference will determine whether you are referring to the **Field** object or the **Value** property of the **Field** object.</span></span>

## <a name="example"></a><span data-ttu-id="1c4b4-115">示例</span><span class="sxs-lookup"><span data-stu-id="1c4b4-115">Example</span></span>

<span data-ttu-id="1c4b4-p103">以下示例演示根据 **Field** 驻留的位置（例如 **TableDef** 的 **Fields** 集合、 **QueryDef** 的 **Fields** 集合，等等），有哪些属性对 **Field** 对象有效。若要使该过程运行，需要使用 FieldOutput 过程。</span><span class="sxs-lookup"><span data-stu-id="1c4b4-p103">This example shows what properties are valid for a **Field** object depending on where the **Field** resides (for example, the **Fields** collection of a **TableDef**, the **Fields** collection of a **QueryDef**, and so forth). The FieldOutput procedure is required for this procedure to run.</span></span>

```vb
    Sub FieldX() 
     
     Dim dbsNorthwind As Database 
     Dim rstEmployees As Recordset 
     Dim fldTableDef As Field 
     Dim fldQueryDef As Field 
     Dim fldRecordset As Field 
     Dim fldRelation As Field 
     Dim fldIndex As Field 
     Dim prpLoop As Property 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set rstEmployees = _ 
     dbsNorthwind.OpenRecordset("Employees") 
     
     ' Assign a Field object from different Fields 
     ' collections to object variables. 
     Set fldTableDef = _ 
     dbsNorthwind.TableDefs(0).Fields(0) 
     Set fldQueryDef =dbsNorthwind.QueryDefs(0).Fields(0) 
     Set fldRecordset = rstEmployees.Fields(0) 
     Set fldRelation =dbsNorthwind.Relations(0).Fields(0) 
     Set fldIndex = _ 
     dbsNorthwind.TableDefs(0).Indexes(0).Fields(0) 
     
     ' Print report. 
     FieldOutput "TableDef", fldTableDef 
     FieldOutput "QueryDef", fldQueryDef 
     FieldOutput "Recordset", fldRecordset 
     FieldOutput "Relation", fldRelation 
     FieldOutput "Index", fldIndex 
     
     rstEmployees.Close 
     dbsNorthwind.Close 
     
    End Sub 
     
    Sub FieldOutput(strTemp As String, fldTemp As Field) 
     ' Report function for FieldX. 
     
     Dim prpLoop As Property 
     
     Debug.Print "Valid Field properties in " & strTemp 
     
     ' Enumerate Properties collection of passed Field 
     ' object. 
     For Each prpLoop In fldTemp.Properties 
     ' Some properties are invalid in certain 
     ' contexts (the Value property in the Fields 
     ' collection of a TableDef for example). Any 
     ' attempt to use an invalid property will 
     ' trigger an error. 
     On Error Resume Next 
     Debug.Print " " & prpLoop.Name & " = " & _ 
     prpLoop.Value 
     On Error GoTo 0 
     Next prpLoop 
     
    End Sub 
```

<br/>

<span data-ttu-id="1c4b4-p104">以下示例使用 **CreateField** 方法为新的 **TableDef** 创建三个 **Fields**。然后显示这些 **Field** 对象的、由 **CreateField** 方法自动设置的属性。（不显示创建 **Field** 时值为空的属性。）</span><span class="sxs-lookup"><span data-stu-id="1c4b4-p104">This example uses the **CreateField** method to create three **Fields** for a new **TableDef**. It then displays the properties of those **Field** objects that are automatically set by the **CreateField** method. (Properties whose values are empty at the time of **Field** creation are not shown.)</span></span>

```vb
    Sub CreateFieldX() 
     
     Dim dbsNorthwind As Database 
     Dim tdfNew As TableDef 
     Dim fldLoop As Field 
     Dim prpLoop As Property 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
     Set tdfNew = dbsNorthwind.CreateTableDef("NewTableDef") 
     
     ' Create and append new Field objects for the new 
     ' TableDef object. 
     With tdfNew 
     ' The CreateField method will set a default Size 
     ' for a new Field object if one is not specified. 
     .Fields.Append .CreateField("TextField", dbText) 
     .Fields.Append .CreateField("IntegerField", dbInteger) 
     .Fields.Append .CreateField("DateField", dbDate) 
     End With 
     
     dbsNorthwind.TableDefs.Append tdfNew 
     
     Debug.Print "Properties of new Fields in " & tdfNew.Name 
     
     ' Enumerate Fields collection to show the properties of 
     ' the new Field objects. 
     For Each fldLoop In tdfNew.Fields 
     Debug.Print " " & fldLoop.Name 
     
     For Each prpLoop In fldLoop.Properties 
     ' Properties that are invalid in the context of 
     ' TableDefs will trigger an error if an attempt 
     ' is made to read their values. 
     On Error Resume Next 
     Debug.Print " " & prpLoop.Name & " - " & _ 
     IIf(prpLoop = "", "[empty]", prpLoop) 
     On Error GoTo 0 
     Next prpLoop 
     
     Next fldLoop 
     
     ' Delete new TableDef because this is a demonstration. 
     dbsNorthwind.TableDefs.Delete tdfNew.Name 
     dbsNorthwind.Close 
     
    End Sub
```
