---
title: Field2.OrdinalPosition 属性 (DAO)
TOCTitle: OrdinalPosition Property
ms:assetid: 55d89611-ad07-990d-fc33-f81d59472430
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194179(v=office.15)
ms:contentKeyID: 48544937
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052899
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 600fe2855ba10e1ab36413f6395d3455bb7bd00b
ms.sourcegitcommit: 38d0db57580cc5f4a0231c27b1643f8db5431ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25937055"
---
# <a name="field2ordinalposition-property-dao"></a><span data-ttu-id="d065b-102">Field2.OrdinalPosition 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="d065b-102">Field2.OrdinalPosition property (DAO)</span></span>


<span data-ttu-id="d065b-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="d065b-103">**Applies to**: Access 2013, Office 2013</span></span>


<span data-ttu-id="d065b-p101">设置或返回 **Field2** 对象在 **[Fields](fields-collection-dao.md)** 集合中的相对位置。</span><span class="sxs-lookup"><span data-stu-id="d065b-p101">Sets or returns the relative position of a **Field2** object within a **[Fields](fields-collection-dao.md)** collection. .</span></span>

## <a name="syntax"></a><span data-ttu-id="d065b-106">语法</span><span class="sxs-lookup"><span data-stu-id="d065b-106">Syntax</span></span>

<span data-ttu-id="d065b-107">*表达式*。OrdinalPosition</span><span class="sxs-lookup"><span data-stu-id="d065b-107">*expression* .OrdinalPosition</span></span>

<span data-ttu-id="d065b-108">*表达式*一个代表**Field2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="d065b-108">*expression* A variable that represents a **Field2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="d065b-109">注解</span><span class="sxs-lookup"><span data-stu-id="d065b-109">Remarks</span></span>

<span data-ttu-id="d065b-110">对于尚未追加到 **Fields** 集合中的对象，该属性是可读写的。</span><span class="sxs-lookup"><span data-stu-id="d065b-110">For an object not yet appended to the **Fields** collection, this property is read/write.</span></span>

<span data-ttu-id="d065b-111">默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="d065b-111">The default is 0.</span></span>

<span data-ttu-id="d065b-112">**OrdinalPosition** 属性的可用性取决于包含 **Fields** 集合的对象，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="d065b-112">The availability of the **OrdinalPosition** property depends on the object that contains the **Fields** collection, as shown in the following table.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="d065b-113">如果 Fields 集合属于</span><span class="sxs-lookup"><span data-stu-id="d065b-113">If the Fields collection belongs to a</span></span></p></th>
<th><p><span data-ttu-id="d065b-114">
则 OrdinalPosition</span><span class="sxs-lookup"><span data-stu-id="d065b-114">Then OrdinalPosition is</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d065b-115"><strong>Index</strong>对象</span><span class="sxs-lookup"><span data-stu-id="d065b-115"><strong>Index</strong> object</span></span></p></td>
<td><p><span data-ttu-id="d065b-116">不支持</span><span class="sxs-lookup"><span data-stu-id="d065b-116">Not supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d065b-117"><strong>QueryDef</strong>对象</span><span class="sxs-lookup"><span data-stu-id="d065b-117"><strong>QueryDef</strong> object</span></span></p></td>
<td><p><span data-ttu-id="d065b-118">只读</span><span class="sxs-lookup"><span data-stu-id="d065b-118">Read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d065b-119"><strong>Recordset</strong>对象</span><span class="sxs-lookup"><span data-stu-id="d065b-119"><strong>Recordset</strong> object</span></span></p></td>
<td><p><span data-ttu-id="d065b-120">只读</span><span class="sxs-lookup"><span data-stu-id="d065b-120">Read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d065b-121"><strong>Relation</strong>对象</span><span class="sxs-lookup"><span data-stu-id="d065b-121"><strong>Relation</strong> object</span></span></p></td>
<td><p><span data-ttu-id="d065b-122">不支持</span><span class="sxs-lookup"><span data-stu-id="d065b-122">Not supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d065b-123"><strong>TableDef</strong>对象</span><span class="sxs-lookup"><span data-stu-id="d065b-123"><strong>TableDef</strong> object</span></span></p></td>
<td><p><span data-ttu-id="d065b-124">读/写</span><span class="sxs-lookup"><span data-stu-id="d065b-124">Read/write</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d065b-p102">一般而言，追加到集合中的对象的排序位置取决于追加对象时遵循的顺序。第一个追加的对象位于第一个位置 (0)，第二个追加的对象位于第二个位置 (1)，以此类推。最后一个追加的对象位于排序位置 count - 1 的位置，其中 count 是集合中的对象数，该数目由 **[Count](containers-count-property-dao.md)** 属性设置指定。</span><span class="sxs-lookup"><span data-stu-id="d065b-p102">Generally, the ordinal position of an object that you append to a collection depends on the order in which you append the object. The first appended object is in the first position (0), the second appended object is in the second position (1), and so on. The last appended object is in ordinal position count – 1, where count is the number of objects in the collection as specified by the **[Count](containers-count-property-dao.md)** property setting.</span></span>

<span data-ttu-id="d065b-128">可以使用 **OrdinalPosition** 属性，为新的 **Field2** 对象指定一个与将这些对象追加到集合时的顺序不同的排序位置。</span><span class="sxs-lookup"><span data-stu-id="d065b-128">You can use the **OrdinalPosition** property to specify an ordinal position for new **Field2** objects that differs from the order in which you append those objects to a collection.</span></span> <span data-ttu-id="d065b-129">这样，当您在应用程序中使用表、查询和记录集时，可以为它们指定字段顺序。</span><span class="sxs-lookup"><span data-stu-id="d065b-129">This enables you to specify a field order for your tables, queries, and recordsets when you use them in an application.</span></span> <span data-ttu-id="d065b-130">例如，在选择返回字段的顺序\*查询由当前**OrdinalPosition**属性值。</span><span class="sxs-lookup"><span data-stu-id="d065b-130">For example, the order in which fields are returned in a SELECT \* query is determined by the current **OrdinalPosition** property values.</span></span>

<span data-ttu-id="d065b-131">可通过将 **OrdinalPosition** 属性设置为任何正整数，永久地重置在记录集中返回字段时遵循的顺序。</span><span class="sxs-lookup"><span data-stu-id="d065b-131">You can permanently reset the order in which fields are returned in recordsets by setting the **OrdinalPosition** property to any positive integer.</span></span>

<span data-ttu-id="d065b-p104">同一集合中的两个或更多个 **Field2** 对象可能具有相同的 **OrdinalPosition** 属性值，在这种情况下，将以字母顺序对这些对象排序。例如，如果将名称为"Age"的字段设置为 4，同时又将名称为"Weight"的另一个字段设置为 4，则 Weight 在 Age 之后返回。</span><span class="sxs-lookup"><span data-stu-id="d065b-p104">Two or more **Field2** objects in the same collection can have the same **OrdinalPosition** property value, in which case they will be ordered alphabetically. For example, if you have a field named Age set to 4 and you set a second field named Weight to 4, Weight is returned after Age.</span></span>

<span data-ttu-id="d065b-p105">可以指定一个大于字段数减 1 的数字。将以相对于最大数的顺序返回字段。例如，如果将某个字段的 **OrdinalPosition** 属性设置为 20（总共只有 5 个字段），同时将其他两个字段的 **OrdinalPosition** 属性分别设置为 10 和 30，则设置为 20 的那个字段将在设置为 10 和 30 的字段之间返回。</span><span class="sxs-lookup"><span data-stu-id="d065b-p105">You can specify a number that is greater than the number of fields minus 1. The field will be returned in an order relative to the largest number. For example, if you set a field's **OrdinalPosition** property to 20 (and there are only 5 fields) and you've set the **OrdinalPosition** property for two other fields to 10 and 30, respectively, the field set to 20 is returned between the fields set to 10 and 30.</span></span>


> [!NOTE]
> <span data-ttu-id="d065b-137">即使尚未刷新**[TableDef](tabledef-object-dao.md)** 对象的**Fields**集合，从**TableDef**打开**[Recordset](recordset-object-dao.md)** 中的字段顺序将反映**TableDef**对象的**OrdinalPosition**数据。</span><span class="sxs-lookup"><span data-stu-id="d065b-137">Even if the **Fields** collection of a **[TableDef](tabledef-object-dao.md)** object has not been refreshed, the field order in a **[Recordset](recordset-object-dao.md)** opened from the **TableDef** will reflect the **OrdinalPosition** data of the **TableDef** object.</span></span> <span data-ttu-id="d065b-138">表类型 **Recordset** 与基础表具有相同的 **OrdinalPosition** 数据，但是其他任何类型的 **Recordset** 将具有新的 **OrdinalPosition** 数据（由 0 开始），并且该数据遵循 **TableDef** 的 **OrdinalPosition** 数据确定的顺序。</span><span class="sxs-lookup"><span data-stu-id="d065b-138">A table-type **Recordset** will have the same **OrdinalPosition** data as the underlying table, but any other type of **Recordset** will have new **OrdinalPosition** data (starting with 0) that follow the order determined by the **OrdinalPosition** data of the **TableDef**.</span></span>



## <a name="example"></a><span data-ttu-id="d065b-139">示例</span><span class="sxs-lookup"><span data-stu-id="d065b-139">Example</span></span>

<span data-ttu-id="d065b-p107">以下示例更改 Employees **TableDef** 中的 **OrdinalPosition** 属性值，以便控制所得到的 **Recordset** 中的 **Field2** 顺序。通过将所有 **Fields** 的 **OrdinalPosition** 设置为 1，所有得到的 **Recordset** 将以字母顺序对 **Fields** 排序。请注意， **Recordset** 中的 **OrdinalPosition** 值不匹配 **TableDef** 中的值，而只是反映 **TableDef** 更改的最终结果。</span><span class="sxs-lookup"><span data-stu-id="d065b-p107">This example changes the **OrdinalPosition** property values in the Employees **TableDef** in order to control the **Field2** order in a resulting **Recordset**. By setting the **OrdinalPosition** of all the **Fields** to 1, any resulting **Recordset** will order the **Fields** alphabetically. Note that the **OrdinalPosition** values in the **Recordset** don't match the values in the **TableDef**, but simply reflect the end result of the **TableDef** changes.</span></span>

```vb
    Sub OrdinalPositionX() 
     
     Dim dbsNorthwind As Database 
     Dim tdfEmployees As TableDef 
     Dim aintPosition() As Integer 
     Dim astrFieldName() As String 
     Dim intTemp As Integer 
     Dim fldTemp As Field2 
     Dim rstEmployees As Recordset 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set tdfEmployees = dbsNorthwind.TableDefs("Employees") 
     
     With tdfEmployees 
     ' Display and store original OrdinalPosition data. 
     Debug.Print _ 
     "Original OrdinalPosition data in TableDef." 
     ReDim aintPosition(0 To .Fields.Count - 1) As Integer 
     ReDim astrFieldName(0 To .Fields.Count - 1) As String 
     For intTemp = 0 To .Fields.Count - 1 
     aintPosition(intTemp) = _ 
     .Fields(intTemp).OrdinalPosition 
     astrFieldName(intTemp) = .Fields(intTemp).Name 
     Debug.Print , aintPosition(intTemp), _ 
     astrFieldName(intTemp) 
     Next intTemp 
     
     ' Change OrdinalPosition data. 
     For Each fldTemp In .Fields 
     fldTemp.OrdinalPosition = 1 
     Next fldTemp 
     
     ' Open new Recordset object to show how the 
     ' OrdinalPosition data has affected the record order. 
     Debug.Print _ 
     "OrdinalPosition data from resulting Recordset." 
     Set rstEmployees = dbsNorthwind.OpenRecordset( _ 
     "SELECT * FROM Employees") 
     For Each fldTemp In rstEmployees.Fields 
     Debug.Print , fldTemp.OrdinalPosition, fldTemp.Name 
     Next fldTemp 
     rstEmployees.Close 
     
     ' Restore original OrdinalPosition data because this is 
     ' a demonstration. 
     For intTemp = 0 To .Fields.Count - 1 
     .Fields(astrFieldName(intTemp)).OrdinalPosition = _ 
     aintPosition(intTemp) 
     Next intTemp 
     
     End With 
     
     dbsNorthwind.Close 
     
    End Sub
```
