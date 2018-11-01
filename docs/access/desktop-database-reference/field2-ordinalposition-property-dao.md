---
title: Field2.OrdinalPosition Property (DAO)
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
ms.openlocfilehash: 451f2d1045b900460a24533ca49579bd9252f456
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25881508"
---
# <a name="field2ordinalposition-property-dao"></a>Field2.OrdinalPosition Property (DAO)


**适用于**： Access 2013、 Office 2013


设置或返回 **Field2** 对象在 **[Fields](fields-collection-dao.md)** 集合中的相对位置。

## <a name="syntax"></a>语法

*表达式*。OrdinalPosition

*表达式*一个代表**Field2**对象的变量。

## <a name="remarks"></a>注解

对于尚未追加到 **Fields** 集合中的对象，该属性是可读写的。

默认值为 0。

**OrdinalPosition** 属性的可用性取决于包含 **Fields** 集合的对象，如下表所示。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>如果 Fields 集合属于</p></th>
<th><p>
则 OrdinalPosition</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Index</strong>对象</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="even">
<td><p><strong>QueryDef</strong>对象</p></td>
<td><p>只读</p></td>
</tr>
<tr class="odd">
<td><p><strong>Recordset</strong>对象</p></td>
<td><p>只读</p></td>
</tr>
<tr class="even">
<td><p><strong>Relation</strong>对象</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="odd">
<td><p><strong>TableDef</strong>对象</p></td>
<td><p>读/写</p></td>
</tr>
</tbody>
</table>


一般而言，追加到集合中的对象的排序位置取决于追加对象时遵循的顺序。第一个追加的对象位于第一个位置 (0)，第二个追加的对象位于第二个位置 (1)，以此类推。最后一个追加的对象位于排序位置 count - 1 的位置，其中 count 是集合中的对象数，该数目由 **[Count](containers-count-property-dao.md)** 属性设置指定。

可以使用 **OrdinalPosition** 属性，为新的 **Field2** 对象指定一个与将这些对象追加到集合时的顺序不同的排序位置。 这样，当您在应用程序中使用表、查询和记录集时，可以为它们指定字段顺序。 例如，在选择返回字段的顺序\*查询由当前**OrdinalPosition**属性值。

可通过将 **OrdinalPosition** 属性设置为任何正整数，永久地重置在记录集中返回字段时遵循的顺序。

同一集合中的两个或更多个 **Field2** 对象可能具有相同的 **OrdinalPosition** 属性值，在这种情况下，将以字母顺序对这些对象排序。例如，如果将名称为"Age"的字段设置为 4，同时又将名称为"Weight"的另一个字段设置为 4，则 Weight 在 Age 之后返回。

可以指定一个大于字段数减 1 的数字。将以相对于最大数的顺序返回字段。例如，如果将某个字段的 **OrdinalPosition** 属性设置为 20（总共只有 5 个字段），同时将其他两个字段的 **OrdinalPosition** 属性分别设置为 10 和 30，则设置为 20 的那个字段将在设置为 10 和 30 的字段之间返回。


> [!NOTE]
> <P>[!注释] 即使未刷新 <A href="tabledef-object-dao.md"><STRONG>TableDef</STRONG></A> 的 <STRONG>Fields</STRONG> 集合，从 <A href="recordset-object-dao.md">TableDef</A> 打开的 <STRONG><STRONG>Recordset</STRONG></STRONG> 中的字段顺序将反映 <STRONG>TableDef</STRONG> 对象的 <STRONG>OrdinalPosition</STRONG> 数据。表类型 <STRONG>Recordset</STRONG> 与基础表具有相同的 <STRONG>OrdinalPosition</STRONG> 数据，但是其他任何类型的 <STRONG>Recordset</STRONG> 将具有新的 <STRONG>OrdinalPosition</STRONG> 数据（由 0 开始），并且该数据遵循 <STRONG>TableDef</STRONG> 的 <STRONG>OrdinalPosition</STRONG> 数据确定的顺序。</P>



## <a name="example"></a>示例

以下示例更改 Employees **TableDef** 中的 **OrdinalPosition** 属性值，以便控制所得到的 **Recordset** 中的 **Field2** 顺序。通过将所有 **Fields** 的 **OrdinalPosition** 设置为 1，所有得到的 **Recordset** 将以字母顺序对 **Fields** 排序。请注意， **Recordset** 中的 **OrdinalPosition** 值不匹配 **TableDef** 中的值，而只是反映 **TableDef** 更改的最终结果。

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
