---
title: 参数成员 (DAO)
TOCTitle: Parameter Members
ms:assetid: 38e19de8-5318-6077-13b1-10653069aaeb
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192517(v=office.15)
ms:contentKeyID: 48544228
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e62125ee61598d6be125f9edb01f2aa4531043b9
ms.sourcegitcommit: 45feafb3b55de0402dddf5548c0c1c43a0eabafd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "26026069"
---
# <a name="parameter-members-dao"></a>参数成员 (DAO)

**适用于**： Access 2013、 Office 2013

Parameter 对象代表提供给查询的值。此参数与从参数查询创建的 QueryDef 对象关联。

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
<td><p><strong><a href="parameter-direction-property-dao.md">方向</a></strong></p></td>
<td><p><strong>注意</strong>： Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。 如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</p>
<p>设置或返回一个值，该值指示 <strong><a href="parameter-object-dao.md">Parameter</a></strong> 对象代表的是输入参数、输出参数、此两者还是过程的返回值（仅适用于 ODBCDirect 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="parameter-name-property-dao.md">Name</a></strong></p></td>
<td><p>返回指定对象的名称。只读 <strong>String</strong>。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="parameter-properties-property-dao.md">属性</a></strong></p></td>
<td><p>返回指定对象的 <strong><a href="properties-collection-dao.md">Properties</a></strong> 集合。只读。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="parameter-type-property-dao.md">Type</a></strong></p></td>
<td><p>设置或返回一个值，该值指示对象的操作类型或数据类型。可读写 <strong>Integer</strong>。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="parameter-value-property-dao.md">Value</a></strong></p></td>
<td><p>设置或返回对象的值。可读/写 <strong>Variant</strong> 类型。</p></td>
</tr>
</tbody>
</table>

