---
title: SourceTable 属性 (DAO)
TOCTitle: SourceTable Property
ms:assetid: 9564ea1c-eafd-0b72-fd68-d88fcc3ea189
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197694(v=office.15)
ms:contentKeyID: 48546429
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052900
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: a557a4941f5b4aa511489c5d057871df5fa72c08
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292984"
---
# <a name="fieldsourcetable-property-dao"></a>SourceTable 属性 (DAO)


**适用于**：Access 2013、Office 2013

返回一个值，该值指示作为 **Field** 对象的原始数据源的表的名称。只读 **String**。

## <a name="syntax"></a>语法

*表达式*。SourceTable

*表达式*一个代表**Field**对象的变量。

## <a name="remarks"></a>注解

对于 **Field** 对象， **SourceField** 和 **SourceTable** 属性的用法取决于包含 **Field** 对象所追加到的 **Fields** 集合的对象，如下表所示。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>对象追加到</p></th>
<th><p>用法</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>索引</strong></p></td>
<td><p>不支持</p></td>
</tr>
<tr class="even">
<td><p><strong>QueryDef</strong></p></td>
<td><p>只读</p></td>
</tr>
<tr class="odd">
<td><p><strong>Recordset</strong></p></td>
<td><p>只读</p></td>
</tr>
<tr class="even">
<td><p><strong>Relation</strong></p></td>
<td><p>不受支持</p></td>
</tr>
<tr class="odd">
<td><p><strong>TableDef</strong></p></td>
<td><p>只读</p></td>
</tr>
</tbody>
</table>


这些属性指示了与 **Field** 对象关联的原始字段和表名称。例如，可以使用这些属性确定查询字段（其名称与基础表中的字段名不相关）的原始数据源。


> [!NOTE]
> [!注释] 如果将 **SourceTable** 属性用于表类型 **Recordset** 对象的 **Fields** 集合中的 **Field** 对象，则该属性不会返回有意义的表名。


