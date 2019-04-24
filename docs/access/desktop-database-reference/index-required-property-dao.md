---
title: Index。 Required 属性 (DAO)
TOCTitle: Required Property
ms:assetid: ec8fafc4-8155-c48e-b3c8-2d9be425175a
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836310(v=office.15)
ms:contentKeyID: 48548518
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052963
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: a2660a4cb422d91cf46b98a8d3870d2ab2db73fc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291697"
---
# <a name="indexrequired-property-dao"></a>Index。 Required 属性 (DAO)

**适用于**：Access 2013、Office 2013

设置或返回一个值，该值指示 **[Field](field-object-dao.md)** 对象是否需要一个非 Null 值。

## <a name="syntax"></a>语法

*表达式*。必填

*表达式*一个代表**Index**对象的变量。

## <a name="remarks"></a>注解

> [!NOTE]
> [!注释] 在您可以为 **Index** 对象或 **Field** 对象设置该属性时，请为 **Field** 对象设置该属性。这是因为需要先检查 **Field** 对象属性设置的有效性，然后检查 **Index** 对象属性设置的有效性。

**Required** 属性的可用性取决于包含 [Fields](fields-collection-dao.md) 集合的对象，如下表所示。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>如果 Fields 集合属于</p></th>
<th><p>则 Required</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Index</strong> 对象</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="even">
<td><p><strong>QueryDef</strong> 对象</p></td>
<td><p>只读</p></td>
</tr>
<tr class="odd">
<td><p><strong>Recordset</strong> 对象</p></td>
<td><p>只读</p></td>
</tr>
<tr class="even">
<td><p><strong>Relation</strong> 对象</p></td>
<td><p>不受支持</p></td>
</tr>
<tr class="odd">
<td><p><strong>TableDef</strong> 对象</p></td>
<td><p>读/写</p></td>
</tr>
</tbody>
</table>

