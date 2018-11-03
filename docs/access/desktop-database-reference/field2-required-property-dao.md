---
title: Field2.Required 属性 (DAO)
TOCTitle: Required Property
ms:assetid: 7d14dfd7-a50d-6044-469e-1511c74c148d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196390(v=office.15)
ms:contentKeyID: 48545848
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: cf5e459773cd0fa0976704834b1b73467fc75294
ms.sourcegitcommit: 38d0db57580cc5f4a0231c27b1643f8db5431ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25937405"
---
# <a name="field2required-property-dao"></a>Field2.Required 属性 (DAO)


**适用于**： Access 2013、 Office 2013


设置或返回一个值，该值指示 **Field2** 对象是否需要非 Null 值。

## <a name="syntax"></a>语法

*表达式*。必填

*表达式*一个代表**Field2**对象的变量。

## <a name="remarks"></a>注解

对于尚未追加到 **Fields** 集合中的 **Field2**，该属性是可读写的。

**Required** 属性的可用性取决于包含 **[Fields](fields-collection-dao.md)** 集合的对象，如下表所示。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>如果 Fields 集合属于</p></th>
<th><p>则 Required</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Index</strong> 对象</p></td>
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


可以将 **Required** 属性与 **AllowZeroLength**、 **ValidateOnSet** 或 **ValidationRule** 属性一起使用，以确定该 **Field2** 对象的 **Value** 属性设置的有效性。如果 **Required** 属性设置为 **False**，则该字段可以包含 **null** 值以及满足 **AllowZeroLength** 和 **ValidationRule** 属性设置所指定的条件的值。


> [!NOTE]
> [!注释] 在您可以为 **Index** 对象或 **Field2** 对象设置该属性时，请为 **Field2** 对象设置该属性。这是因为需要先检查 **Field2** 对象属性设置的有效性，然后检查 **Index** 对象属性设置的有效性。



## <a name="example"></a>示例

以下示例使用 **Required** 属性报告为了添加新记录，三个不同表中的哪些字段必须包含数据。若要使该过程运行，需要使用 RequiredOutput 过程。

```vb 
Sub RequiredX() 
 
 Dim dbsNorthwind As Database 
 Dim tdfloop As TableDef 
 
 Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
 
 With dbsNorthwind 
 ' Show which fields are required in the Fields 
 ' collections of three different TableDef objects. 
 RequiredOutput .TableDefs("Categories") 
 RequiredOutput .TableDefs("Customers") 
 RequiredOutput .TableDefs("Employees") 
 .Close 
 End With 
 
End Sub 
 
Sub RequiredOutput(tdfTemp As TableDef) 
 
 Dim fldLoop As Field2 
 
 ' Enumerate Fields collection of the specified TableDef 
 ' and show the Required property. 
 Debug.Print "Fields in " & tdfTemp.Name & ":" 
 For Each fldLoop In tdfTemp.Fields 
 Debug.Print , fldLoop.Name & ", Required = " & _ 
 fldLoop.Required 
 Next fldLoop 
 
End Sub 
 
```

