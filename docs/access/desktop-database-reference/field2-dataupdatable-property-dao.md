---
title: DataUpdatable 属性 (DAO)
TOCTitle: DataUpdatable Property
ms:assetid: e6619c4e-26b1-777b-f0de-78fed3dbc890
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835966(v=office.15)
ms:contentKeyID: 48548377
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 88a57ff2daeaaaab202daad55f01eebc6bdf86dd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292837"
---
# <a name="field2dataupdatable-property-dao"></a><span data-ttu-id="c0e6c-102">DataUpdatable 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="c0e6c-102">Field2.DataUpdatable property (DAO)</span></span>


<span data-ttu-id="c0e6c-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="c0e6c-103">**Applies to**: Access 2013, Office 2013</span></span>


<span data-ttu-id="c0e6c-104">返回一个值，该值指示是否可更新 **Field2** 对象所代表的字段中的数据。</span><span class="sxs-lookup"><span data-stu-id="c0e6c-104">Returns a value that indicates whether the data in the field represented by a **Field2** object is updatable.</span></span>

## <a name="syntax"></a><span data-ttu-id="c0e6c-105">语法</span><span class="sxs-lookup"><span data-stu-id="c0e6c-105">Syntax</span></span>

<span data-ttu-id="c0e6c-106">*表达式*。DataUpdatable</span><span class="sxs-lookup"><span data-stu-id="c0e6c-106">*expression* .DataUpdatable</span></span>

<span data-ttu-id="c0e6c-107">*表达式*一个代表**Field2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="c0e6c-107">*expression* A variable that represents a **Field2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="c0e6c-108">注解</span><span class="sxs-lookup"><span data-stu-id="c0e6c-108">Remarks</span></span>

<span data-ttu-id="c0e6c-109">使用此属性可确定是否可以更改**Field2**对象的**[Value](field-value-property-dao.md)** 属性设置。</span><span class="sxs-lookup"><span data-stu-id="c0e6c-109">Use this property to determine whether you can change the **[Value](field-value-property-dao.md)** property setting of a **Field2** object.</span></span> <span data-ttu-id="c0e6c-110">对于 **[Attributes](field-attributes-property-dao.md)** 属性为 **dbAutoIncrField** 的 **Field2** 对象，该属性始终为 **False**。</span><span class="sxs-lookup"><span data-stu-id="c0e6c-110">This property is always **False** on a **Field2** object whose **[Attributes](field-attributes-property-dao.md)** property is **dbAutoIncrField**.</span></span>

<span data-ttu-id="c0e6c-111">您可以对附加到**[QueryDef](querydef-object-dao.md)**、 **[Recordset](recordset-object-dao.md)** 和**[Relation](relation-object-dao.md)** 对象的**[fields](fields-collection-dao.md)** 集合中的**Field2**对象使用**DataUpdatable**属性, 但不能在的**fields**集合**[中使用Index](index-object-dao.md)** 或**[TableDef](tabledef-object-dao.md)** 对象。</span><span class="sxs-lookup"><span data-stu-id="c0e6c-111">You can use the **DataUpdatable** property on **Field2** objects that are appended to the **[Fields](fields-collection-dao.md)** collection of **[QueryDef](querydef-object-dao.md)**, **[Recordset](recordset-object-dao.md)**, and **[Relation](relation-object-dao.md)** objects, but not the **Fields** collection of **[Index](index-object-dao.md)** or **[TableDef](tabledef-object-dao.md)** objects.</span></span>

## <a name="example"></a><span data-ttu-id="c0e6c-112">示例</span><span class="sxs-lookup"><span data-stu-id="c0e6c-112">Example</span></span>

<span data-ttu-id="c0e6c-p102">以下示例演示使用了六个不同的 **Recordsets** 中的第一个字段的 **DataUpdatable** 属性。若要使该过程运行，需要使用 DataOutput 函数。</span><span class="sxs-lookup"><span data-stu-id="c0e6c-p102">This example demonstrates the **DataUpdatable** property using the first field from six different **Recordsets**. The DataOutput function is required for this procedure to run.</span></span>

```vb 
Sub DataUpdatableX() 
 
 Dim dbsNorthwind As Database 
 Dim rstNorthwind As Recordset 
 
 Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
 
 With dbsNorthwind 
 ' Open and print report about a table-type Recordset. 
 Set rstNorthwind = .OpenRecordset("Employees") 
 DataOutput rstNorthwind 
 
 ' Open and print report about a dynaset-type Recordset. 
 Set rstNorthwind = .OpenRecordset("Employees", _ 
 dbOpenDynaset) 
 DataOutput rstNorthwind 
 
 ' Open and print report about a snapshot-type Recordset. 
 Set rstNorthwind = .OpenRecordset("Employees", _ 
 dbOpenSnapshot) 
 DataOutput rstNorthwind 
 
 ' Open and print report about a forward-only-type Recordset. 
 Set rstNorthwind = .OpenRecordset("Employees", _ 
 dbOpenForwardOnly) 
 DataOutput rstNorthwind 
 
 ' Open and print report about a Recordset based on 
 ' a select query. 
 Set rstNorthwind = _ 
 .OpenRecordset("Current Product List") 
 DataOutput rstNorthwind 
 
 ' Open and print report about a Recordset based on a 
 ' select query that calculates totals. 
 Set rstNorthwind = .OpenRecordset("Order Subtotals") 
 DataOutput rstNorthwind 
 
 .Close 
 End With 
 
End Sub 
 
Function DataOutput(rstTemp As Recordset) 
 
 With rstTemp 
 Debug.Print "Recordset: " & .Name & ", "; 
 Select Case .Type 
 Case dbOpenTable 
 Debug.Print "dbOpenTable" 
 Case dbOpenDynaset 
 Debug.Print "dbOpenDynaset" 
 Case dbOpenSnapshot 
 Debug.Print "dbOpenSnapshot" 
 Case dbOpenForwardOnly 
 Debug.Print "dbOpenForwardOnly" 
 End Select 
 Debug.Print " Field: " & .Fields(0).Name & ", " & _ 
 "DataUpdatable = " & .Fields(0).DataUpdatable 
 Debug.Print 
 .Close 
 End With 
 
End Function 
 
```

