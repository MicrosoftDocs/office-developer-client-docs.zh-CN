---
title: 参数成员 (DAO)
TOCTitle: Parameter Members
ms:assetid: 38e19de8-5318-6077-13b1-10653069aaeb
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192517(v=office.15)
ms:contentKeyID: 48544228
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 25eae70d88307331c44983c4e7cbbcce3fe9d309
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288110"
---
# <a name="parameter-members-dao"></a>参数成员 (DAO)

**适用于**：Access 2013、Office 2013

Parameter 对象代表提供给查询的值。 此参数与从参数查询创建的 QueryDef 对象关联。

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
<td><p><strong><a href="parameter-direction-property-dao.md">Direction</a></strong></p></td>
<td><p><strong>注意</strong>: Microsoft Access 2013 中不支持 ODBCDirect 工作区。 如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</p>
<p>设置或返回一个值，该值指示 <strong><a href="parameter-object-dao.md">Parameter</a></strong> 对象代表的是输入参数、输出参数、此两者还是过程的返回值（仅适用于 ODBCDirect 工作区）。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="parameter-name-property-dao.md">Name</a></strong></p></td>
<td><p>返回指定对象的名称。 只读的 <strong>字符串</strong> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="parameter-properties-property-dao.md">属性</a></strong></p></td>
<td><p>返回指定对象的 <strong><a href="properties-collection-dao.md">Properties</a></strong> 集合。 只读。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="parameter-type-property-dao.md">Type</a></strong></p></td>
<td><p>设置或返回一个值，该值指示对象的操作类型或数据类型。 可读/写 <strong>Integer</strong> 类型。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="parameter-value-property-dao.md">值</a></strong></p></td>
<td><p>设置或返回对象的值。 <strong>Variant</strong> 类型，可读写。</p></td>
</tr>
</tbody>
</table>

