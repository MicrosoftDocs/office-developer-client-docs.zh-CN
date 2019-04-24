---
title: FieldEnum (Access desktop database reference)
TOCTitle: FieldEnum
ms:assetid: fbd415c0-d6b4-278f-318b-98432c013634
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250289(v=office.15)
ms:contentKeyID: 48548876
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e42dcfe63194364986e5b235c59b011231307a7c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292592"
---
# <a name="fieldenum"></a>FieldEnum

**适用于**：Access 2013、Office 2013

指定在 [Record](record-object-ado.md) 对象的 [Fields](fields-collection-ado.md) 集合中引用的特殊字段。

## <a name="remarks"></a>注解

这些常量提供指向访问与 **Record** 关联的特殊字段的“快捷方式”。从 **Fields** 集合中检索 [Field](field-object-ado.md) 对象，然后使用 **Field** 对象的 [Value](value-property-ado.md) 属性获取其内容。

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>常量</p></th>
<th><p>值</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>adDefaultStream</strong></p></td>
<td><p>-1</p></td>
<td><p>引用包含与 <strong>Record</strong> 关联的默认 <a href="stream-object-ado.md">Stream</a> 对象的字段。</p></td>
</tr>
<tr class="even">
<td><p><strong>用 adrecordurl</strong></p></td>
<td><p>-2</p></td>
<td><p>引用包含当前 <strong>Record</strong> 的绝对 URL 字符串的字段。</p></td>
</tr>
</tbody>
</table>

