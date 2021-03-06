---
title: 属性成员 (DAO)
TOCTitle: Property Members
ms:assetid: 32658adb-f153-148d-a216-eb97b996579a
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192303(v=office.15)
ms:contentKeyID: 48544076
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: fe60c12a85eff0dd8f796f9affeef71979dac580
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32301209"
---
# <a name="property-members-dao"></a>属性成员 (DAO)


**适用于**：Access 2013、Office 2013

Property 对象代表 DAO 对象的内部特征或用户定义特征。

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
<td><p><strong><a href="property-inherited-property-dao.md">继承</a></strong></p></td>
<td><p>返回一个值，该值指示某个 <strong><a href="property-object-dao.md">Property</a></strong> 对象是否是从基础对象中继承的。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="property-name-property-dao.md">Name</a></strong></p></td>
<td><p>返回或设置指定对象的名称。对于尚未追加到集合中的对象，该属性为可读/写 <strong>String</strong> 类型；对于已追加到集合中的对象，该属性为只读 <strong>String</strong> 类型。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="property-properties-property-dao.md">属性</a></strong></p></td>
<td><p>返回指定对象的 <strong><a href="properties-collection-dao.md">Properties</a></strong> 集合。 只读。</p></td>
</tr>
<tr class="even">
<td><p><strong><a href="property-type-property-dao.md">Type</a></strong></p></td>
<td><p>设置或返回一个值，该值指示对象的操作类型或数据类型。 可读/写 <strong>Integer</strong> 类型。</p></td>
</tr>
<tr class="odd">
<td><p><strong><a href="property-value-property-dao.md">值</a></strong></p></td>
<td><p>设置或返回对象的值。 <strong>Variant</strong> 类型，可读写。</p></td>
</tr>
</tbody>
</table>

