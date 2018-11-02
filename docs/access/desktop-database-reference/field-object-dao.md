---
title: Field 对象的数据访问对象 (DAO)
TOCTitle: Field Object
ms:assetid: 47282ce2-9b49-ccf9-ad37-c4bb25cfd037
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193203(v=office.15)
ms:contentKeyID: 48544587
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 644089e9ff4dddf2aed9f767a667cc3d80b6e039
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25924566"
---
# <a name="field-object-dao"></a><span data-ttu-id="4ade4-102">Field 对象 (DAO)</span><span class="sxs-lookup"><span data-stu-id="4ade4-102">Field object (DAO)</span></span>

<span data-ttu-id="4ade4-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="4ade4-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="4ade4-104">**Field** 对象代表具有普通数据类型和普通属性集的数据列。</span><span class="sxs-lookup"><span data-stu-id="4ade4-104">A **Field** object represents a column of data with a common data type and a common set of properties.</span></span>

## <a name="remarks"></a><span data-ttu-id="4ade4-105">注解</span><span class="sxs-lookup"><span data-stu-id="4ade4-105">Remarks</span></span>

<span data-ttu-id="4ade4-p101">**Index**、 **QueryDef**、 **Relation** 和 **TableDef** 对象的 **Fields** 集合包含这些对象代表的字段的规范。 **Recordset** 对象的 **Fields** 集合代表数据行中或记录中的 **Field** 对象。可使用 **Recordset** 对象中的 **Field** 对象读取和设置 **Recordset** 对象的当前记录中的字段的值。</span><span class="sxs-lookup"><span data-stu-id="4ade4-p101">The **Fields** collections of **Index**, **QueryDef**, **Relation**, and **TableDef** objects contain the specifications for the fields those objects represent. The **Fields** collection of a **Recordset** object represents the **Field** objects in a row of data, or in a record. You use the **Field** objects in a **Recordset** object to read and set values for the fields in the current record of the **Recordset** object.</span></span>

<span data-ttu-id="4ade4-p102">在 Microsoft Access 工作区中，可以使用 **Field** 对象及其方法和属性操作字段。例如，您可以进行下列操作：</span><span class="sxs-lookup"><span data-stu-id="4ade4-p102">In a Microsoft Access workspacee, you manipulate a field using a **Field** object and its methods and properties. For example, you can:</span></span>

  - <span data-ttu-id="4ade4-111">使用 **OrdinalPosition** 属性设置或返回 **Fields** 集合中的 **Field** 对象的表示顺序。</span><span class="sxs-lookup"><span data-stu-id="4ade4-111">Use the **OrdinalPosition** property to set or return the presentation order of the **Field** object in a **Fields** collection.</span></span>

  - <span data-ttu-id="4ade4-112">使用 **Recordset** 对象中的某个字段的 **Value** 属性设置或返回存储的数据。</span><span class="sxs-lookup"><span data-stu-id="4ade4-112">Use the **Value** property of a field in a **Recordset** object to set or return stored data.</span></span>

  - <span data-ttu-id="4ade4-113">使用 **AppendChunk** 和 **GetChunk** 方法以及 **FieldSize** 属性获取或设置 **Recordset** 对象的"OLE 对象"或"备注"字段中的值。</span><span class="sxs-lookup"><span data-stu-id="4ade4-113">Use the **AppendChunk** and **GetChunk** methods and the **FieldSize** property to get or set a value in an OLE Object or Memo field of a **Recordset** object.</span></span>

  - <span data-ttu-id="4ade4-114">使用 **Type**、 **Size** 和 **Attributes** 属性确定可以存储在字段中的数据的类型。</span><span class="sxs-lookup"><span data-stu-id="4ade4-114">Use the **Type**, **Size**, and **Attributes** properties to determine the type of data that can be stored in the field.</span></span>

  - <span data-ttu-id="4ade4-115">使用 **SourceField** 和 **SourceTable** 属性确定数据的原始源。</span><span class="sxs-lookup"><span data-stu-id="4ade4-115">Use the **SourceField** and **SourceTable** properties to determine the original source of the data.</span></span>

  - <span data-ttu-id="4ade4-116">使用 **ForeignName** 属性设置或返回与 **Relation** 对象中的外部字段有关的信息。</span><span class="sxs-lookup"><span data-stu-id="4ade4-116">Use the **ForeignName** property to set or return information about a foreign field in a **Relation** object.</span></span>

  - <span data-ttu-id="4ade4-117">使用 **AllowZeroLength**、 **DefaultValue**、 **Required**、 **ValidateOnSet**、 **ValidationRule** 或 **ValidationText** 属性设置或返回验证条件。</span><span class="sxs-lookup"><span data-stu-id="4ade4-117">Use the **AllowZeroLength**, **DefaultValue**, **Required**, **ValidateOnSet**, **ValidationRule**, or **ValidationText** properties to set or return validation conditions.</span></span>

  - <span data-ttu-id="4ade4-118">使用 **TableDef** 对象上的某个字段的 **DefaultValue** 属性，设置添加新记录后该字段的默认值。</span><span class="sxs-lookup"><span data-stu-id="4ade4-118">Use the **DefaultValue** property of a field on a **TableDef** object to set the default value for this field when new records are added.</span></span>

<span data-ttu-id="4ade4-119">要在 **Index**、 **TableDef** 或 **Relation** 对象中创建新的 **Field** 对象，请使用 **CreateField** 方法。</span><span class="sxs-lookup"><span data-stu-id="4ade4-119">To create a new **Field** object in an **Index**, **TableDef**, or **Relation** object, use the **CreateField** method.</span></span>

<span data-ttu-id="4ade4-p103">在访问作为 **Recordset** 对象一部分的 **Field** 对象时，当前记录中的数据将在 **Field** 对象的 **Value** 属性中可见。要操作 **Recordset** 对象中的数据，通常不需要直接引用 **Fields** 集合；而是间接引用 **Recordset** 对象的 **Fields** 集合中的 **Field** 对象的 **Value** 属性。</span><span class="sxs-lookup"><span data-stu-id="4ade4-p103">When you access a **Field** object as part of a **Recordset** object, data from the current record is visible in the **Field** object's **Value** property. To manipulate data in the **Recordset** object, you don't usually reference the **Fields** collection directly; instead, you indirectly reference the **Value** property of the **Field** object in the **Fields** collection of the **Recordset** object.</span></span>

<span data-ttu-id="4ade4-122">若要按照序号或 **Name** 属性设置来引用集合中的 **Field** 对象，可以使用下列任何一种语法形式：</span><span class="sxs-lookup"><span data-stu-id="4ade4-122">To refer to a **Field** object in a collection by its ordinal number or by its **Name** property setting, use any of the following syntax forms:</span></span>

- <span data-ttu-id="4ade4-123">**Fields**(0)</span><span class="sxs-lookup"><span data-stu-id="4ade4-123">**Fields**(0)</span></span>

- <span data-ttu-id="4ade4-124">**字段**("name")</span><span class="sxs-lookup"><span data-stu-id="4ade4-124">**Fields**("name")</span></span>

- <span data-ttu-id="4ade4-125">**字段**\!\[名称\]</span><span class="sxs-lookup"><span data-stu-id="4ade4-125">**Fields**\!\[name\]</span></span>

<span data-ttu-id="4ade4-p104">还可以使用相同的语法形式，引用创建并追加到 **Fields** 集合中的 **Field** 对象的 **Value** 属性。字段引用的上下文将确定引用的是 **Field** 对象还是 **Field** 对象的 **Value** 属性。</span><span class="sxs-lookup"><span data-stu-id="4ade4-p104">With the same syntax forms, you can also refer to the **Value** property of a **Field** object that you create and append to a **Fields** collection. The context of the field reference will determine whether you are referring to the **Field** object or the **Value** property of the **Field** object.</span></span>

## <a name="example"></a><span data-ttu-id="4ade4-128">示例</span><span class="sxs-lookup"><span data-stu-id="4ade4-128">Example</span></span>

<span data-ttu-id="4ade4-p105">以下示例演示根据 **Field** 驻留的位置（例如 **TableDef** 的 **Fields** 集合、 **QueryDef** 的 **Fields** 集合，等等），有哪些属性对 **Field** 对象有效。若要使该过程运行，需要使用 FieldOutput 过程。</span><span class="sxs-lookup"><span data-stu-id="4ade4-p105">This example shows what properties are valid for a **Field** object depending on where the **Field** resides (for example, the **Fields** collection of a **TableDef**, the **Fields** collection of a **QueryDef**, and so forth). The FieldOutput procedure is required for this procedure to run.</span></span>

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

<span data-ttu-id="4ade4-p106">以下示例使用 **CreateField** 方法为新的 **TableDef** 创建三个 **Fields**。然后显示这些 **Field** 对象的、由 **CreateField** 方法自动设置的属性。（不显示创建 **Field** 时值为空的属性。）</span><span class="sxs-lookup"><span data-stu-id="4ade4-p106">This example uses the **CreateField** method to create three **Fields** for a new **TableDef**. It then displays the properties of those **Field** objects that are automatically set by the **CreateField** method. (Properties whose values are empty at the time of **Field** creation are not shown.)</span></span>

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
