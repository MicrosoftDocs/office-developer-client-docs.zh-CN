---
title: 关系成员 (DAO)
TOCTitle: Relation Members
ms:assetid: 9ee36e7d-3825-1de8-65fb-64bbcada847c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff198338(v=office.15)
ms:contentKeyID: 48546670
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 8d4b1b1a3a06d0605793667f8c9258ea5b6336f5
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25923726"
---
# <a name="relation-members-dao"></a>关系成员 (DAO)


**适用于**： Access 2013、 Office 2013

Relation 对象表示表或查询中的字段之间的关系（仅适用于 Microsoft Access 数据库引擎数据库）。

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
<td><p><strong><a href="relation-createfield-method-dao.md">CreateField</a></strong></p></td>
<td><p>创建一个新的 <strong><a href="field-object-dao.md">Field</a></strong> 对象（仅适用于 Microsoft Access 工作区）。</p></td>
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
<td><p><strong><a href="relation-attributes-property-dao.md">Attributes</a></strong></p></td>
<td><p>设置或返回一个值，该值指示 <strong>Relation</strong> 对象的一个或多个特征。可读写 <strong>Long</strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="relation-fields-property-dao.md">字段</a></strong></p></td>
<td><p>返回一个 <strong>Fields</strong> 集合，该集合表示指定对象的所有存储 <strong>Field</strong> 对象。只读。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="relation-foreigntable-property-dao.md">ForeignTable</a></strong></p></td>
<td><p>设置或返回某个关系中的外表的名称（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="relation-name-property-dao.md">Name</a></strong></p></td>
<td><p>返回或设置指定对象的名称。对于尚未追加到集合中的对象，该属性为可读/写 <strong>String</strong> 类型；对于已追加到集合中的对象，该属性为只读 <strong>String</strong> 类型。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="relation-partialreplica-property-dao.md">PartialReplica</a></strong></p></td>
<td><p>设置或返回 <strong>Relation</strong> 对象的值，用于指示从完全副本填充部分副本时是否应当考虑关系。（仅适用于 Microsoft Access 数据库引擎数据库）。可读写 <strong>Boolean</strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="relation-properties-property-dao.md">属性</a></strong></p></td>
<td><p>返回指定对象的 <strong><a href="properties-collection-dao.md">Properties</a></strong> 集合。只读。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="relation-table-property-dao.md">表</a></strong></p></td>
<td><p>指示 <strong><a href="relation-object-dao.md">Relation</a></strong> 对象的主表的名称。该属性应当等同于 <strong><a href="connection-name-property-dao.md">TableDef</a></strong> 或 <strong><a href="tabledef-object-dao.md">QueryDef</a></strong> 对象的 <strong><a href="querydef-object-dao.md">Name</a></strong> 属性设置（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
</tbody>
</table>

