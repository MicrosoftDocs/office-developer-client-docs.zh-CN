---
title: Field2.SourceTable 属性 (DAO)
TOCTitle: SourceTable Property
ms:assetid: 24d2fdda-d924-d95e-8458-063dd1d36d5d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff191839(v=office.15)
ms:contentKeyID: 48543768
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: a3ecf8b6655bb9f1dd2b25d264708112834e8a90
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28717942"
---
# <a name="field2sourcetable-property-dao"></a>Field2.SourceTable 属性 (DAO)


**适用于**： Access 2013、 Office 2013

返回一个值，该值指示作为 **Field2** 对象的原始数据源的表的名称。只读 **String**。

## <a name="syntax"></a>语法

*表达式*。SourceTable

*表达式*一个代表**Field2**对象的变量。

## <a name="remarks"></a>注解

对于 **Field2** 对象， **SourceField** 和 **SourceTable** 属性的用法取决于包含 **Field2** 对象所追加到的 **Fields** 集合的对象，如下表所示。

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
<td><p>不支持</p></td>
</tr>
<tr class="odd">
<td><p><strong>TableDef</strong></p></td>
<td><p>只读</p></td>
</tr>
</tbody>
</table>


这些属性指示了与 **Field2** 对象关联的原始字段和表名称。例如，可以使用这些属性确定查询字段（其名称与基础表中的字段名不相关）的原始数据源。


> [!NOTE]
> [!注释] 如果将 **SourceTable** 属性用于表类型 **Recordset** 对象的 **Fields** 集合中的 **Field2** 对象，则该属性不会返回有意义的表名。


