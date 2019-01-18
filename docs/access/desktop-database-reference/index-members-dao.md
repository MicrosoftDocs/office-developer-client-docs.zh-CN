---
title: 索引成员 (DAO)
TOCTitle: Index Members
ms:assetid: e261c5fa-ca7d-0d63-1c29-48e9231b39d1
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835712(v=office.15)
ms:contentKeyID: 48548290
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 895f29a5dd3e7ed267b96d6a46dc2c8710b4998e
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28709157"
---
# <a name="index-members-dao"></a>索引成员 (DAO)


**适用于**： Access 2013、 Office 2013

Index 对象指定从数据库表访问的记录的顺序，以及是否可接受重复的记录，以便提供高效的数据访问。对于外部数据库，Index 对象描述为外部表建立的索引（仅适用于 Microsoft Access 工作区）。

## <a name="methods"></a>方法

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>名称</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong><a href="index-createfield-method-dao.md">CreateField</a></strong></p></td>
<td><p>创建一个新的 <strong><a href="field-object-dao.md">Field</a></strong> 对象（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="index-createproperty-method-dao.md">CreateProperty</a></strong></p></td>
<td><p>创建一个新的用户定义的 <strong><a href="property-object-dao.md">Property</a></strong> 对象（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
</tbody>
</table>


## <a name="properties"></a>属性

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>名称</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong><a href="index-clustered-property-dao.md">Clustered</a></strong></p></td>
<td><p>设置或返回一个值，该值指示某个 <strong>Index</strong> 对象是否代表某个表的聚簇索引（仅适用于 Microsoft Access 工作区）。可读写 <strong>Boolean</strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="index-distinctcount-property-dao.md">DistinctCount</a></strong></p></td>
<td><p>返回一个值，该值指示 <strong><a href="index-object-dao.md">Index</a></strong> 对象中的、包含在关联表中的唯一值的数目（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="index-fields-property-dao.md">Fields</a></strong></p></td>
<td><p>返回一个 <strong>Fields</strong> 集合，该集合代表指定对象的所有存储的 <strong>Field</strong> 对象。可读/写。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="index-foreign-property-dao.md">Foreign</a></strong></p></td>
<td><p>返回一个值，该值指示某个 <strong><a href="index-object-dao.md">Index</a></strong> 对象是否代表某个表中的外键（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="index-ignorenulls-property-dao.md">IgnoreNulls</a></strong></p></td>
<td><p>设置或返回一个值，该值指示索引字段中包含 Null 值的记录是否具有索引项（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="index-name-property-dao.md">Name</a></strong></p></td>
<td><p>返回或设置指定对象的名称。对于尚未追加到集合中的对象，该属性为可读/写 <strong>String</strong> 类型；对于已追加到集合中的对象，该属性为只读 <strong>String</strong> 类型。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="index-primary-property-dao.md">Primary</a></strong></p></td>
<td><p>设置或返回一个值，该值指示 <strong><a href="index-object-dao.md">Index</a></strong> 对象是否代表了对一个表的主键索引（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="index-properties-property-dao.md">属性</a></strong></p></td>
<td><p>返回指定对象的 <strong><a href="properties-collection-dao.md">Properties</a></strong> 集合。只读。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="index-required-property-dao.md">Required</a></strong></p></td>
<td><p>设置或返回一个值，该值指示 <strong><a href="field-object-dao.md">Field</a></strong> 对象是否需要一个非 Null 值。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="index-unique-property-dao.md">Unique</a></strong></p></td>
<td><p>设置或返回一个值，该值指示 <strong><a href="index-object-dao.md">Index</a></strong> 对象是否代表一个表的唯一（键）索引（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
</tbody>
</table>

