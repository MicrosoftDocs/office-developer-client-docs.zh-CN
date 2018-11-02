---
title: Index.Required 属性 (DAO)
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
ms.openlocfilehash: 44fa827be7359c598ff610313be4c2acf30d5e50
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25920562"
---
# <a name="indexrequired-property-dao"></a>Index.Required 属性 (DAO)


**适用于**： Access 2013、 Office 2013

设置或返回一个值，该值指示 **[Field](field-object-dao.md)** 对象是否需要一个非 Null 值。

## <a name="syntax"></a>语法

*表达式*。必填

*表达式*一个代表**Index**对象的变量。

## <a name="remarks"></a>注解


> [!NOTE]
> <P>[!注释] 在您可以为 <STRONG>Index</STRONG> 对象或 <STRONG>Field</STRONG> 对象设置该属性时，请为 <STRONG>Field</STRONG> 对象设置该属性。这是因为需要先检查 <STRONG>Field</STRONG> 对象属性设置的有效性，然后检查 <STRONG>Index</STRONG> 对象属性设置的有效性。</P>



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
<td><p><strong>QueryDef</strong>对象</p></td>
<td><p>只读</p></td>
</tr>
<tr class="odd">
<td><p><strong>Recordset</strong>对象</p></td>
<td><p>只读</p></td>
</tr>
<tr class="even">
<td><p><strong>Relation</strong>对象</p></td>
<td><p>不支持</p></td>
</tr>
<tr class="odd">
<td><p><strong>TableDef</strong>对象</p></td>
<td><p>读/写</p></td>
</tr>
</tbody>
</table>

