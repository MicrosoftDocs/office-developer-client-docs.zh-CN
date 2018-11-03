---
title: 域成员 (DAO)
TOCTitle: Field Members
ms:assetid: 4b6a587f-1fd0-37fb-db7d-75b587a8dc60
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193511(v=office.15)
ms:contentKeyID: 48544689
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 549559756a2929e6b2daad01c4a0542a973a8bca
ms.sourcegitcommit: 38d0db57580cc5f4a0231c27b1643f8db5431ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25937118"
---
# <a name="field-members-dao"></a>域成员 (DAO)


**适用于**： Access 2013、 Office 2013

Field 对象代表具有普通数据类型和普通属性集的数据列。

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
<td><p><strong><a href="field-appendchunk-method-dao.md">AppendChunk</a></strong></p></td>
<td><p>将字符串表达式中的数据追加到 <strong><a href="field-object-dao.md">Recordset</a></strong> 中的"备注"或"长二进制"型 <strong><a href="recordset-object-dao.md">Field</a></strong> 对象。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="field-createproperty-method-dao.md">CreateProperty</a></strong></p></td>
<td><p>创建一个新的用户定义的 <strong><a href="property-object-dao.md">Property</a></strong> 对象（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="field-getchunk-method-dao.md">GetChunk</a></strong></p></td>
<td><p>返回 <strong><strong>Recordset</strong></strong> 对象的 <strong><a href="field-object-dao.md">Fields</a></strong> 集合中的 <a href="fields-collection-dao.md">Memo</a> 或 <strong>Long Binary</strong> <strong><a href="recordset-object-dao.md">Field</a></strong> 对象的全部或一部分内容。</p></td>
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
<td><p><strong><a href="field-allowzerolength-property-dao.md">AllowZeroLength</a></strong></p></td>
<td><p>设置或返回一个值，指示是否为零长度字符串 (&quot;&quot;) 是<strong><a href="field-object-dao.md">Field</a></strong>对象的<strong><a href="field-value-property-dao.md">Value</a></strong>属性的有效设置与文本或备注数据类型 （仅限 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="field-attributes-property-dao.md">Attributes</a></strong></p></td>
<td><p>设置或返回 <strong><a href="field-object-dao.md">Field</a></strong> 对象的一个或多个特征。 <strong>Long</strong> 类型，可读写。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="field-collatingorder-property-dao.md">CollatingOrder</a></strong></p></td>
<td><p>返回一个值，该值指定用于字符串比较或排序的文本中排序次序的序列（仅适用于 Microsoft Access 工作区）。只读 <strong>Long</strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="field-dataupdatable-property-dao.md">DataUpdatable</a></strong></p></td>
<td><p>返回一个值，该值指示是否可更新 <strong><a href="field-object-dao.md">Field</a></strong> 对象所代表的字段中的数据。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="field-defaultvalue-property-dao.md">DefaultValue</a></strong></p></td>
<td><p>设置或返回 <strong><a href="field-object-dao.md">Field</a></strong> 对象的默认值。对于尚未追加到 <a href="fields-collection-dao.md"><strong>Fields</strong></a> 集合的 <strong>Field</strong> 对象，该属性是可读写的（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="field-fieldsize-property-dao.md">字段大小</a></strong></p></td>
<td><p>返回 <strong><a href="field-object-dao.md">Recordset</a></strong> 对象的 <strong><a href="fields-collection-dao.md">Fields</a></strong> 集合中"备注"或"长二进制"类型 <strong><a href="recordset-object-dao.md">Field</a></strong> 对象的数据库（而不是内存）中使用的字节数。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="field-foreignname-property-dao.md">ForeignName</a></strong></p></td>
<td><p>设置或返回一个值，该值指定某个外表中的 <strong><a href="field-object-dao.md">Field</a></strong> 对象的名称，而该外表对应于某个关系的主表中的字段（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="field-name-property-dao.md">Name</a></strong></p></td>
<td><p>返回或设置指定对象的名称。对于尚未追加到集合中的对象，该属性为可读/写 <strong>String</strong> 类型；对于已追加到集合中的对象，该属性为只读 <strong>String</strong> 类型。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="field-ordinalposition-property-dao.md">OrdinalPosition</a></strong></p></td>
<td><p>设置或返回 <strong><a href="field-object-dao.md">Field</a></strong> 对象在 <strong><a href="fields-collection-dao.md">Fields</a></strong> 集合中的相对位置。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="field-originalvalue-property-dao.md">OriginalValue</a></strong></p></td>
<td><p><strong><a href="workspacetypeenum-enumeration-dao.md">WorkspaceTypeEnum</a></strong>值之一。</p>
<td><p><strong>注意</strong>： Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。 如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</p>
<p>返回数据库中的 <strong>Field</strong> 的值，该值在上一次批更新开始时已经存在（仅适用于 ODBCDirect 工作区）。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="field-properties-property-dao.md">属性</a></strong></p></td>
<td><p>返回指定对象的 <strong><a href="properties-collection-dao.md">Properties</a></strong> 集合。只读。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="field-required-property-dao.md">必填</a></strong></p></td>
<td><p>设置或返回一个值，该值指示 <strong><a href="field-object-dao.md">Field</a></strong> 对象是否需要一个非 Null 值。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="field-fieldsize-property-dao.md">大小</a></strong></p></td>
<td><p>返回 <strong><a href="field-object-dao.md">Recordset</a></strong> 对象的 <strong><a href="fields-collection-dao.md">Fields</a></strong> 集合中"备注"或"长二进制"类型 <strong><a href="recordset-object-dao.md">Field</a></strong> 对象的数据库（而不是内存）中使用的字节数。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="field-sourcefield-property-dao.md">SourceField</a></strong></p></td>
<td><p>返回一个值，该值指示作为 <strong>Field</strong> 对象的原始数据源的字段的名称。只读 <strong>String</strong>。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="field-sourcetable-property-dao.md">SourceTable</a></strong></p></td>
<td><p>返回一个值，该值指示作为 <strong>Field</strong> 对象的原始数据源的表的名称。只读 <strong>String</strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="field-type-property-dao.md">类型</a></strong></p></td>
<td><p>设置或返回一个值，该值指示对象的操作类型或数据类型。可读写 <strong>Integer</strong>。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="field-validateonset-property-dao.md">ValidateOnSet</a></strong></p></td>
<td><p>设置或返回一个值，该值指定当设置 <strong><a href="field-object-dao.md">Field</a></strong> 对象的 <strong><a href="field-value-property-dao.md">Value</a></strong> 属性时是否立即验证该对象的值（仅适用于 Microsoft Access 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="field-validationrule-property-dao.md">ValidationRule</a></strong></p></td>
<td><p>设置或返回一个值，当字段中的数据发生更改或被添加到表中时，该值将会验证该数据（仅适用于 Microsoft Access 工作区）。可读写 <strong>String</strong>。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="field-validationtext-property-dao.md">ValidationText</a></strong></p></td>
<td><p>设置或返回一个值，该值指定当 <strong>Field</strong> 对象的值不符合 <strong>ValidationRule</strong> 属性设置所指定的验证规则时应用程序显示的消息文本（仅适用于 Microsoft Access 工作区）。可读写 <strong>String</strong>。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="field-value-property-dao.md">值</a></strong></p></td>
<td><p>设置或返回对象的值。可读/写 <strong>Variant</strong> 类型。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="field-visiblevalue-property-dao.md">VisibleValue</a></strong></p></td>
<td><p><strong><a href="workspacetypeenum-enumeration-dao.md">WorkspaceTypeEnum</a></strong>值之一。</p>
<td><p><strong>注意</strong>： Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。 如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</p>
<p>返回数据库中现有的一个值，批更新冲突确定该值比 <strong>OriginalValue</strong> 属性新（仅适用于 ODBCDirect 工作区）。</p></td>
</tr>
</tbody>
</table>

