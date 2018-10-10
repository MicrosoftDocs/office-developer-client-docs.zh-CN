---
title: Field2.Size Property (DAO)
TOCTitle: Size Property
ms:assetid: e252759a-cea9-25cb-667d-80b422fbf97e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835700(v=office.15)
ms:contentKeyID: 48548282
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ffca40d22d77a604e4c0b794a8070fb444d44a32
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468033"
---
# <a name="field2size-property-dao"></a>Field2.Size Property (DAO)


**适用于**： Access 2013 |Office 2013


设置或返回一个值，该值指示 **Field2** 对象的最大大小（以字节计）。

## <a name="syntax"></a>语法

*表达式*。大小

*表达式*一个代表**Field2**对象的变量。

## <a name="remarks"></a>注解

对于尚未追加到 **[Fields](fields-collection-dao.md)** 集合中的对象，该属性是可读写的。

对于包含字符数据的字段（"备注"类型字段除外）， **Size** 属性指示字段可以保存的最大字符数。对于数字字段， **Size** 属性指示需要多少字节的存储区。

**Size** 属性的用法取决于包含 **Field2** 对象所追加到的 **Fields** 集合的对象，如下表所示。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>对象追加到</p></th>
<th><p>用法</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Index</strong></p></td>
<td><p>不支持</p></td>
</tr>
<tr class="even">
<td><p><strong>QueryDef</strong></p></td>
<td><p>只读</p></td>
</tr>
<tr class="odd">
<td><p><strong>Recordset</strong></p></td>
<td><p>只读</p></td>
</tr>
<tr class="even">
<td><p><strong>Relation</strong></p></td>
<td><p>不支持</p></td>
</tr>
<tr class="odd">
<td><p><strong>TableDef</strong></p></td>
<td><p>只读</p></td>
</tr>
</tbody>
</table>


在创建一个数据类型不是"文本"的 **Field2** 对象时， **Type** 属性设置将自动确定 **Size** 属性设置；您不需要对其进行设置。但是，对于数据类型为"文本"的 **Field2** 对象，可以将 **Size** 设置为最大文本大小以下的任何整数（对于 Microsoft Access 数据库，最大文本大小为 255）。如果不设置大小，则字段将为数据库所允许的大小。

对于"长二进制"和"备注" **Field2** 对象， **Size** 始终设置为 0。使用 **Field2** 对象的 **FieldSize** 属性可以确定特定记录中的数据大小。"长二进制"或"备注"字段的最大大小只受系统资源或数据库允许的最大大小的限制。

## <a name="example"></a>示例

以下示例通过枚举 Employees 表中的 **Field2** 对象的名称和大小来演示 **Size** 属性。

```vb
    Sub SizeX() 
     
     Dim dbsNorthwind As Database 
     Dim tdfEmployees As TableDef 
     Dim fldNew As Field2 
     Dim fldLoop As Field2 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set tdfEmployees = dbsNorthwind.TableDefs!Employees 
     
     With tdfEmployees 
     
     ' Create and append a new Field object to the 
     ' Employees table. 
     Set fldNew = .CreateField("FaxPhone") 
     fldNew.Type = dbText 
     fldNew.Size = 20 
     .Fields.Append fldNew 
     
     Debug.Print "TableDef: " & .Name 
     Debug.Print " Field.Name - Field.Type - Field.Size" 
     
     ' Enumerate Fields collection; print field names, 
     ' types, and sizes. 
     For Each fldLoop In .Fields 
     Debug.Print " " & fldLoop.Name & " - " & _ 
     fldLoop.Type & " - " & fldLoop.Size 
     Next fldLoop 
     
     ' Delete new field because this is a demonstration. 
     .Fields.Delete fldNew.Name 
     
     End With 
     
     dbsNorthwind.Close 
     
    End Sub
```
