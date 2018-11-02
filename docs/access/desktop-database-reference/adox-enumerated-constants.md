---
title: ADOX 枚举常量
TOCTitle: ADOX enumerated constants
ms:assetid: 0ad716a0-8801-50cb-024a-85c308c65c78
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248840(v=office.15)
ms:contentKeyID: 48543163
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 5ee99f8795dce4587d795b2cea4ac70a74c5eaa7
ms.sourcegitcommit: 48bfe5ab15b11105f4f52937b886c92bdc26525a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25910808"
---
# <a name="adox-enumerated-constants"></a>ADOX 枚举常量

**适用于**： Access 2013、 Office 2013

为有助于进行调试，ADOX 枚举常量为每一个常量列出了一个值。但是，该值纯粹是参考性的，并且可能随不同的 ADOX 版本而变化。您的代码应依赖于枚举常量的名称，而不是实际值。

已定义下列枚举常量。

<br/>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>枚举</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="actionenum.md">ActionEnum</a></p></td>
<td><p>指定调用 <strong>SetPermissions</strong> 时要执行的操作的类型。</p></td>
</tr>
<tr class="even">
<td><p><a href="allownullsenum.md">AllowNullsEnum</a></p></td>
<td><p>指定是否对含有 null 值的记录进行索引。</p></td>
</tr>
<tr class="odd">
<td><p><a href="columnattributesenum.md">ColumnAttributesEnum</a></p></td>
<td><p>指定 <strong>Column</strong> 的特征。</p></td>
</tr>
<tr class="even">
<td><p><a href="datatypeenum.md">DataTypeEnum</a></p></td>
<td><p>用于指定 <strong>Field</strong>、<strong>Parameter</strong> 或 <strong>Property</strong> 的数据类型。</p></td>
</tr>
<tr class="odd">
<td><p><a href="inherittypeenum.md">InheritTypeEnum</a></p></td>
<td><p>指定对象将如何继承通过 <strong>SetPermissions</strong> 设置的权限。</p></td>
</tr>
<tr class="even">
<td><p><a href="keytypeenum.md">KeyTypeEnum</a></p></td>
<td><p>指定 <strong>Key</strong> 的类型：主键、外键或唯一键。</p></td>
</tr>
<tr class="odd">
<td><p><a href="objecttypeenum.md">ObjectTypeEnum</a></p></td>
<td><p>指定设置权限和所有权所针对的数据库对象的类型。</p></td>
</tr>
<tr class="even">
<td><p><a href="rightsenum.md">RightsEnum</a></p></td>
<td><p>指定组或用户对某个对象的权限。</p></td>
</tr>
<tr class="odd">
<td><p><a href="ruleenum.md">RuleEnum</a></p></td>
<td><p>指定删除 <strong>Key</strong> 时应遵循的规则。</p></td>
</tr>
<tr class="even">
<td><p><a href="sortorderenum.md">SortOrderEnum</a></p></td>
<td><p>指定索引列的排序顺序。</p></td>
</tr>
</tbody>
</table>

