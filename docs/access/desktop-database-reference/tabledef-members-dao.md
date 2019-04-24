---
title: TableDef 成员 (DAO)
TOCTitle: TableDef Members
ms:assetid: bc55315e-bafe-d89e-ad31-fd4c9bb6486e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822714(v=office.15)
ms:contentKeyID: 48547408
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: ff9f6841b50b70f8846c829f0ee7b911c84c0e04
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32314901"
---
# <a name="tabledef-members-dao"></a>TableDef 成员 (DAO)


**适用于**：Access 2013、Office 2013

TableDef 对象代表基表或链接表的已存储定义（仅适用于 Microsoft Access 工作区）。

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
<td><p><strong><a href="tabledef-createfield-method-dao.md">CreateField</a></strong></p></td>
<td><p>创建一个新的 <strong><a href="field-object-dao.md">Field</a></strong> 对象（仅适用于 Microsoft Access 工作区）。 .</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="tabledef-createindex-method-dao.md">CreateIndex</a></strong></p></td>
<td><p>创建新的<strong><a href="index-object-dao.md">Index</a></strong>对象 (仅适用于 Microsoft Access 工作区)。 .</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="tabledef-createproperty-method-dao.md">CreateProperty</a></strong></p></td>
<td><p>创建一个新的用户定义的 <strong><a href="property-object-dao.md">Property</a></strong> 对象（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="tabledef-openrecordset-method-dao.md">OpenRecordset</a></strong></p></td>
<td><p>创建一个新的 <strong><a href="recordset-object-dao.md">Recordset</a></strong> 对象，并将其追加到 <strong>Recordsets</strong> 集合。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="tabledef-refreshlink-method-dao.md">RefreshLink</a></strong></p></td>
<td><p>更新链接表的连接信息（仅适用于 Microsoft Access 工作区）。</p></td>
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
<td><p><strong><a href="tabledef-attributes-property-dao.md">Attributes</a></strong></p></td>
<td><p>设置或返回一个值，该值指示 <strong>TableDef</strong> 对象的一个或多个特征。 <strong>Long</strong> 类型，可读写。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="tabledef-conflicttable-property-dao.md">ConflictTable</a></strong></p></td>
<td><p>返回冲突表（其中包含同步两个副本的过程中发生冲突的数据库记录）的名称（仅适用于 Microsoft Access 工作区）。只读 <strong>String</strong>。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="tabledef-connect-property-dao.md">Connect</a></strong></p></td>
<td><p>设置或返回一个值，该值提供有关链接表的信息。 可读/写 <strong>String</strong> 类型。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="tabledef-datecreated-property-dao.md">DateCreated</a></strong></p></td>
<td><p>返回对象的创建日期和时间（仅适用于 Microsoft Access 工作区）。 只读 <strong>变量</strong> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="tabledef-fields-property-dao.md">Fields</a></strong></p></td>
<td><p>返回一个 <strong>Fields</strong> 集合，该集合表示指定对象的所有存储 <strong>Field</strong> 对象。 只读。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="tabledef-indexes-property-dao.md">Indexes</a></strong></p></td>
<td><p>返回一个 <strong>Indexes</strong> 集合，该集合包含指定表的所有已存储 <strong>Index</strong> 对象。 只读。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="tabledef-lastupdated-property-dao.md">LastUpdated</a></strong></p></td>
<td><p>返回对象的最近更改日期和时间。 只读 <strong>Variant</strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="tabledef-name-property-dao.md">Name</a></strong></p></td>
<td><p>返回或设置指定对象的名称。 读/写， <strong>字符串</strong> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="tabledef-properties-property-dao.md">属性</a></strong></p></td>
<td><p>返回指定对象的 <strong><a href="properties-collection-dao.md">Properties</a></strong> 集合。 只读。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="tabledef-recordcount-property-dao.md">RecordCount</a></strong></p></td>
<td><p>返回 <strong><a href="tabledef-object-dao.md">TableDef</a></strong> 对象中的总记录数。 <strong>Long</strong> 类型，只读。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="tabledef-replicafilter-property-dao.md">ReplicaFilter</a></strong></p></td>
<td><p>设置或返回部分副本中的 <strong><a href="tabledef-object-dao.md">TableDef</a></strong> 对象中的一个值，用于指示哪部分记录从完全副本复制到该表中（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="tabledef-sourcetablename-property-dao.md">SourceTableName</a></strong></p></td>
<td><p>设置或返回一个值，该值指定链接表或基表的名称（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="tabledef-updatable-property-dao.md">Updatable</a></strong></p></td>
<td><p>返回一个值，该值指示是否可以更改 DAO 对象。 只读 <strong>Boolean</strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="tabledef-validationrule-property-dao.md">ValidationRule</a></strong></p></td>
<td><p>设置或返回一个值，当字段中的数据更改或添加到表中时，该值对这些数据进行验证（仅适用于 Microsoft Access 工作区）。可读写 <strong>String</strong>。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="tabledef-validationtext-property-dao.md">ValidationText</a></strong></p></td>
<td><p>设置或返回一个值，该值指定当 <strong>Field</strong> 对象的值不符合 <strong>ValidationRule</strong> 属性设置所指定的验证规则时应用程序显示的消息文本（仅适用于 Microsoft Access 工作区）。可读写 <strong>String</strong>。</p></td>
</tr>
</tbody>
</table>

