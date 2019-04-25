---
title: Field.Attributes 属性 (DAO)
TOCTitle: Attributes Property
ms:assetid: 8e6f6afb-1a89-7315-c129-cf7ff19e0ca9
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197380(v=office.15)
ms:contentKeyID: 48546287
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: 010c7a2aea777a93d1ced2d33d8743320dd05ada
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32293152"
---
# <a name="fieldattributes-property-dao"></a>Field.Attributes 属性 (DAO)


**适用于**：Access 2013、Office 2013


设置或返回 **[Field](field-object-dao.md)** 对象的一个或多个特征。 读/写 **Long**。

## <a name="syntax"></a>语法

*表达式* .Attributes

*表达式* 一个表示 **Field** 对象的变量。

## <a name="remarks"></a>说明

该值指定 **Field** 对象表示的字段的特性，并且可以是以下常量的组合。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>常量</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>dbAutoIncrField</strong></p></td>
<td><p>新记录的字段值将自动增加到无法更改的唯一 Long 类型整数（在 Microsoft Access 工作区中，只受 Microsoft Access 数据库引擎数据库表的支持）。</p></td>
</tr>
<tr class="even">
<td><p><strong>dbDescending</strong></p></td>
<td><p>字段按降序（Z 到 A 或 100 至 0）排序；此选项仅适用于 <strong>Index</strong> 对象的 <strong>Fields</strong> 集合中的 <strong>Field</strong> 对象。 如果省略此常量，字段将按升序（A 到 Z 或 0 到 100）排序。 这是 <strong>Index</strong> 和 <strong>TableDef</strong> 字段的默认值（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbFixedField</strong></p></td>
<td><p>字段大小为固定值（数值字段的默认设置）。</p></td>
</tr>
<tr class="even">
<td><p><strong>dbHyperlinkField</strong></p></td>
<td><p>字段包含超链接信息（仅限备注字段）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbSystemField</strong></p></td>
<td><p>字段将存储副本的复制信息；不能删除这种类型的字段（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong>dbUpdatableField</strong></p></td>
<td><p>可以更改字段值。</p></td>
</tr>
<tr class="odd">
<td><p><strong>dbVariableField</strong></p></td>
<td><p>字段大小是可变值（仅限文本字段）。</p></td>
</tr>
</tbody>
</table>


对于尚未追加到集合中的对象，该属性是可读写的。对于已追加的 **Field** 对象， **Attributes** 属性的可用性取决于包含 **Fields** 集合的对象。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>如果 Field 对象属于</p></th>
<th><p>则 Attributes</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Index</strong> 对象</p></td>
<td><p>读/写，直至 <strong>Index</strong> 对象追加到的 <strong>TableDef</strong> 对象追加到 <strong>Database</strong> 对象；然后该属性变为只读。</p></td>
</tr>
<tr class="even">
<td><p><strong>QueryDef</strong> 对象</p></td>
<td><p>只读</p></td>
</tr>
<tr class="odd">
<td><p><strong>Recordset</strong> 对象</p></td>
<td><p>只读</p></td>
</tr>
<tr class="even">
<td><p><strong>Relation</strong> 对象</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="odd">
<td><p><strong>TableDef</strong> 对象</p></td>
<td><p>读/写</p></td>
</tr>
</tbody>
</table>


设置多个属性时，可通过对相应的常量求和来组合这些属性。将忽略所有无效值，且不产生错误。

## <a name="example"></a>示例

以下示例显示 Northwind 数据库中 **Field**、 **Relation** 和 **TableDef** 对象的 **Attributes** 属性。

```vb 
Sub AttributesX() 
 
 Dim dbsNorthwind As Database 
 Dim fldLoop As Field 
 Dim relLoop As Relation 
 Dim tdfloop As TableDef 
 
 Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
 
 With dbsNorthwind 
 
 ' Display the attributes of a TableDef object's 
 ' fields. 
 Debug.Print "Attributes of fields in " & _ 
 .TableDefs(0).Name & " table:" 
 For Each fldLoop In .TableDefs(0).Fields 
 Debug.Print " " & fldLoop.Name & " = " & _ 
 fldLoop.Attributes 
 Next fldLoop 
 
 ' Display the attributes of the Northwind database's 
 ' relations. 
 Debug.Print "Attributes of relations in " & _ 
 .Name & ":" 
 For Each relLoop In .Relations 
 Debug.Print " " & relLoop.Name & " = " & _ 
 relLoop.Attributes 
 Next relLoop 
 
 ' Display the attributes of the Northwind database's 
 ' tables. 
 Debug.Print "Attributes of tables in " & .Name & ":" 
 For Each tdfloop In .TableDefs 
 Debug.Print " " & tdfloop.Name & " = " & _ 
 tdfloop.Attributes 
 Next tdfloop 
 
 .Close 
 End With 
 
End Sub 
 
```

